---
name: adam-shostack-threat-modeling
description: "Use only when the user explicitly invokes adam-shostack-threat-modeling, or asks for a \"Shostack review\", \"Adam Shostack review\", \"Threat model\", \"Threat modeling review\", or \"STRIDE review\" by name. Never apply it on your own initiative."
---

# Adam Shostack Review (Threat Modeling & STRIDE)

A critique of system design, architecture, and data flow using Adam Shostack's threat modeling method and the STRIDE taxonomy from "Threat Modeling: Designing for Security". The goal is to find where trust breaks down, name the threats that actually apply, and rank them — not to produce a generic security checklist or a penetration test.

## Trigger

Run only when the user explicitly calls this skill or asks for a "Shostack review", "Adam Shostack review", "Threat model", "Threat modeling review", or "STRIDE review" by name. Do not apply it to ordinary coding, debugging, or implementation requests. When it is not invoked, behave normally.

## Step 1: Confirm what is under review

Identify the subject: a design, an architecture diagram, a service, a data flow, a feature, or an existing system. If the scope or the deployment context is unclear, ask one question and wait.

## Step 2: Ground the model in real context

Before modeling, read the actual code, config, and diagrams in the workspace: entry points, data stores, auth, external calls, deployment boundaries. Do not invent infrastructure or infer a threat model from the stack name. If a component is unread or unknown, say so and label it as an assumption.

## Step 3: Pick the lenses that fit

Choose the lenses that genuinely apply. If the system is small and the boundary is obvious, say so instead of inflating it.

**1. Decompose and find trust boundaries**
- What are the processes, data stores, and external entities?
- Where does data cross from less trusted to more trusted — browser to API, API to database, service to service, admin to tenant?
- Which boundaries actually authenticate, and which rely on network position alone?

**2. STRIDE sweep**
For each element and boundary, ask which of these truly applies:
- **Spoofing** — can an attacker claim another identity?
- **Tampering** — can data be changed in transit or at rest?
- **Repudiation** — can an action be denied because nothing recorded it?
- **Information disclosure** — what leaks through errors, logs, timing, or over-broad responses?
- **Denial of service** — what is cheap to exhaust?
- **Elevation of privilege** — can a lower role reach a higher one?

**3. Assets and attacker goals**
- What is worth stealing, changing, or breaking here?
- Who benefits, and what would they have to control to get it?
- Which threat is realistic for this system's exposure, and which is theoretical?

**4. Rank by likelihood and impact**
- Which threats are reachable today versus blocked by an existing control?
- Rank by what an attacker gains, not by how clever the attack is.

**5. Mitigations and residual risk**
- For each top threat: prevent, detect, or respond — and which of the three is missing.
- What risk remains after the mitigation, and who accepts it?

## Step 4: Write the review

Use this shape, kept short:

**The blind spot:** the trust boundary or threat most likely to be missed, in one or two sentences.

**Threat:** STRIDE category, the element it hits, and the path an attacker takes. Mark assumptions as assumptions.

**Evidence:** exact file paths, config keys, endpoints, or diagram elements. Do not invent infrastructure.

**Impact if exploited:** what the attacker gains, in concrete terms.

**Mitigations:** two or three options, one line each, with the trade-off of each. Do not implement unless asked.

**Residual risk:** what remains after the recommended mitigation.

**Question back:** one question that sharpens the boundary or the asset at stake.

## Rules

- Defensive review only. Do not write exploit payloads, attack scripts, or step-by-step intrusion instructions.
- Do not roleplay Shostack or quote him. Use the method, not the persona.
- Never claim a system is secure. State what was reviewed and what was not.
- Do not invent CVEs, breach history, or infrastructure details.
- Stay concise. A sharp threat model beats a long checklist.
- Reply in the language the user writes in.
- The current project's or workspace's own rules still apply.
