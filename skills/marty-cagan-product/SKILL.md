---
name: "marty-cagan-product"
description: "Product scope and risk review of a roadmap, feature spec or MVP (value, usability, feasibility, viability risks). Use only when the user explicitly invokes marty-cagan-product, or asks for a \"Cagan review\", \"Marty Cagan review\", \"Product risk review\", or \"Product review\" by name. Never apply it on your own initiative."
---

# Marty Cagan Review (Product Risks & Scope)

A critique of product scope, feature backlogs, MVP definitions, and solution assumptions using Marty Cagan's Four Big Product Risks framework from "Inspired" and the Silicon Valley Product Group (SVPG). The goal is to separate high-risk assumptions from working software before committing engineering bandwidth, not to validate feature wishlists.

## Trigger

Run only when the user explicitly calls this skill or asks for a "Cagan review", "Marty Cagan review", "Product risk review", or "Product review" by name. Do not apply it to ordinary sprint planning or bug tracking. When it is not invoked, behave normally.

## Step 1: Confirm what is under review

Identify the subject: a product roadmap, feature specification, MVP scope document, user story, or prototype architecture. If it is unclear, ask one question and wait.

## Step 2: Ground the critique in real context

Before critiquing, check whatever sources of truth the current project or workspace defines (its PRD, user flows, tech stack limitations, compliance rules, and delivery constraints). Do not assume user behavior or engineering capacity. If evidence of real user demand or technical viability is missing, label anything you cannot verify as an assumption.

## Step 3: Pick the lenses that fit

Choose one to three lenses that genuinely apply. If none fits, say so plainly instead of forcing one.

**1. Value Risk (Will customers choose to use / buy it?)**
- Have we validated that real people care enough about this problem to switch away from their current habit or pay money?
- Is this feature solving a real, frequent pain point, or is it an edge-case request from one person that adds bloat for everyone else?
- What evidence exists that users won't just ignore this feature after launch?

**2. Usability Risk (Can users figure out how to use it?)**
- Can the customer reach their "aha" moment within 60 seconds without reading documentation or needing an onboarding call?
- Are we forcing users to learn complex mental models, multi-step configurations, or manual data entry before delivering any reward?
- Where is the cognitive load heaviest in this flow?

**3. Feasibility Risk (Can we build it with the skills and time we have?)**
- Are we choosing an architecture or tech stack that introduces fragile dependencies, server maintenance, or complex infrastructure for a simple job?
- Can this feature be built, tested, and maintained within our actual available weekly bandwidth (people, hours and competing priorities)?
- What is the hardest technical hurdle, and have we prototyped it early or left it to the end?

**4. Viability Risk (Does this solution work for the business?)**
- Does this feature comply with privacy, legal, data security, and financial constraints (e.g., data protection, industry regulation, payment or contract rules)?
- Does the operational cost of supporting this feature (customer support, API costs, maintenance) exceed the revenue it generates?
- Does this feature align with our long-term brand focus, or does it drag us into a different business model?

**5. Output vs. Outcome (The Feature Factory Trap)**
- Are we measuring success by how many lines of code or features we shipped (output), or by whether the user's problem was solved (outcome)?
- What is the single metric that tells us this product actually worked in the real world?

## Step 4: Write the critique

Use this shape, kept short:

**The blind spot:** the strongest product objection or unvalidated risk, in one or two sentences.

**Lens:** which framework flags it and why it applies here.

**Evidence:** the facts from the sources behind the critique. Mark assumptions as assumptions.

**Cost of ignoring it:** what happens if nothing changes (e.g., spending weeks building software that users abandon, massive tech debt, support nightmare).

**Options:** two or three distinct ways to de-risk the product or cut scope, one line each, with the main trade-off of each. Do not pick for the user unless asked.

**Question back:** one question that forces the user to confront the riskiest product assumption.

## Rules

- No praise opener and no softening ("great feature idea, but..."). Be direct and objective; critique the product assumption, not the builder.
- Do not roleplay Cagan or quote him. Use the SVPG risk framework, not the persona.
- Never invent user analytics or compliance facts. If validation data is absent, state that it is an untested assumption.
- Stay concise. A sharp product de-risking critique beats a bulky specification document.
- Reply in the language the user writes in.
- The current project's or workspace's own rules (approval gates, confidentiality, tone) still apply.