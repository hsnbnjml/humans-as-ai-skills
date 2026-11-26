---
name: "troy-hunt-web-security"
description: "Defensive web security review of an app, API, auth flow or data handling (credentials, data exposure, breach readiness). Use only when the user explicitly invokes troy-hunt-web-security, or asks for a \"Hunt review\", \"Troy Hunt review\", \"Web security review\", \"Security review\", or \"Breach review\" by name. Never apply it on your own initiative."
---

# Troy Hunt Review (Web Security & Breach Practice)

A practical review of web applications, APIs, auth flows, and data handling using Troy Hunt's breach-driven approach: what is actually exposed, what happens if it leaks, and what to fix first. The goal is real exposure and blast radius, not theoretical risk or a compliance checkbox.

## Trigger

Run only when the user explicitly calls this skill or asks for a "Hunt review", "Troy Hunt review", "Web security review", "Security review", or "Breach review" by name. Do not apply it to ordinary coding, debugging, or implementation requests. When it is not invoked, behave normally.

## Step 1: Confirm what is under review

Identify the subject: a web app, an API, an auth flow, a data-handling path, or an incident. If the scope or the deployment context is unclear, ask one question and wait.

## Step 2: Ground the review in real context

Read the actual code and config: auth, sessions, headers, secrets, logging, dependency versions, data models. Do not invent deployment details or assume protections that are not visible. Label anything you cannot verify as an assumption.

## Step 3: Pick the lenses that fit

Choose the lenses that genuinely apply. If the surface is small and already well-handled, say so plainly.

**1. Credentials and sessions**
- How are passwords stored: algorithm, cost, salt? Anything reversible or unsalted?
- Is MFA available, and is it enforced where it matters?
- How long do sessions live, where are tokens stored, and can they be revoked?
- Do reset and invite flows leak whether an account exists?

**2. Data exposure**
- What personal data is collected, and is all of it necessary?
- What appears in logs, error messages, API responses, and analytics?
- Are backups, exports, and admin views protected to the same standard as the app?
- Is data encrypted in transit and at rest, and who holds the keys?

**3. Breach readiness**
- If the database leaked tomorrow, what would attackers get, and how fast would you know who was affected?
- Is there rate limiting, enumeration protection, and monitoring on auth and data endpoints?
- Is there a disclosure path and a plan for notifying affected users?

**4. Common web attack surface**
- Injection, XSS, CSRF, SSRF, IDOR, open redirects, permissive CORS, missing security headers.
- Dependency versions with known CVEs, and whether updates are routine.
- Anything reachable that was meant to stay internal.

**5. Third parties and supply chain**
- What data leaves for vendors, and what a vendor breach would expose.
- Which third-party scripts run with access to sessions or user data.

## Step 4: Write the review

Use this shape, kept short:

**The blind spot:** the exposure most likely to be missed, in one or two sentences.

**Exposure:** what is reachable or leakable, and by whom.

**Evidence:** exact file paths, config keys, endpoints, or headers. Mark assumptions as assumptions.

**Blast radius:** what an attacker gets, and how many users it touches.

**Fix now:** one or two items, one line each, with the trade-off of each.

**Fix later:** one or two items, one line each, with the trade-off of each.

**Question back:** one question that sharpens the exposure or the data at stake.

## Rules

- Defensive review only. Do not write exploit payloads, attack scripts, or step-by-step instructions for breaching a system.
- Do not roleplay Hunt or quote him. Use the method, not the persona.
- Never invent breach data, CVEs, or compliance status.
- Do not claim an application is secure. State what was reviewed and what was not.
- Do not implement fixes unless asked; propose them.
- Stay concise. A sharp exposure review beats a long checklist.
- Reply in the language the user writes in.
- The current project's or workspace's own rules still apply.