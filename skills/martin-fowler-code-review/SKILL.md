---
name: martin-fowler-code-review
description: "Use only when the user explicitly invokes martin-fowler-code-review, or asks for a \"Fowler review\", \"Martin Fowler review\", \"Code smell review\", or \"Refactoring review\" by name. Never apply it on your own initiative."
---

# Martin Fowler Review (Code Quality & Refactoring)

A critique of source code, pull requests, modules, and architecture using Martin Fowler's refactoring catalog and Kent Beck's code smell principles from "Refactoring: Improving the Design of Existing Code". The goal is to expose structural fragility, unnecessary complexity, and maintainability risks, and suggest safe, incremental refactorings — not to nitpick formatting or validate clever code.

## Trigger

Run only when the user explicitly calls this skill or asks for a "Fowler review", "Martin Fowler review", "Code smell review", or "Refactoring review" by name. Do not apply it to ordinary coding, debugging, or implementation requests. When it is not invoked, behave normally.

## Step 1: Confirm what is under review

Identify the subject: a file, function, module, pull request diff, or architecture snippet. If the target code or scope is unclear, ask one question and wait.

## Step 2: Ground the critique in real context

Before critiquing, read the actual target code and relevant surrounding files in the workspace (callers, tests, config, dependencies). Do not guess how callers behave or invent test coverage. If tests or surrounding modules are missing or unread, say so and label anything you cannot verify as an assumption.

## Step 3: Pick the lenses that fit

Choose one to three lenses that genuinely apply. If the code is already clean and well-factored, say so plainly instead of forcing a smell.

**1. Code Smells (Bloaters & Couplers)**
- Are functions or classes doing too many things at once (Long Method, Large Class)?
- Is a function more interested in another module's data than its own (Feature Envy), or are parameters repeatedly passed together without an object (Data Clumps)?
- Is raw logic duplicated across places where a single shared abstraction would prevent divergence?

**2. Clarity & Intent-Revealing Naming**
- Can another developer understand *what* this code does and *why* without tracing every line?
- Do names reflect the domain intent (`calculateOverdueFee`) rather than generic mechanics (`processData`, `temp`, `handle`)?
- Are comments explaining *why* a non-obvious decision was made, or are they acting as "deodorant" to explain messy code that should be refactored?

**3. Safe Incremental Refactoring**
- Can the structural issue be fixed in small, behavior-preserving steps (Extract Function, Replace Conditional with Polymorphism, Introduce Parameter Object) rather than a risky rewrite?
- Are there tests covering the behavior before refactoring begins, or is a minimal characterization test needed first?

**4. Separation of Concerns & Coupling**
- Is business logic tightly coupled to UI rendering, database calls, or framework glue?
- If the storage layer or external API changes tomorrow, how many unrelated functions break?
- Are side effects isolated at the edges rather than buried inside pure calculations?

**5. Dead Code & Speculative Generality**
- Are there unused variables, unreachable branches, or abstractions built for hypothetical future features that don't exist yet?
- Would deleting or simplifying this make the system safer and easier to change today?

## Step 4: Write the critique

Use this shape, kept short:

**The blind spot:** the strongest structural or maintainability risk in the code, in one or two sentences.

**Lens:** which framework lens flags it and why it applies here.

**Evidence:** exact file paths, function names, or lines from the code. Mark assumptions as assumptions.

**Cost of ignoring it:** what breaks or slows down over time (e.g., fragile changes, hidden bugs, hard-to-test logic).

**Options:** two or three distinct, small refactoring paths, one line each, with the main trade-off of each. Do not pick or apply changes unless asked.

**Question back:** one question that sharpens the design decision or clarifies future change patterns.

If more than one serious smell exists, lead with the most impactful and list the others in one line each at the end.

## Rules

- No praise opener and no softening ("clean code overall, but..."). Be direct and constructive; critique the code structure, not the author.
- Do not roleplay Fowler or Beck or quote them. Use the refactoring principles, not the personas.
- Never invent performance benchmarks, unseen callers, or test results. If test coverage is unknown, state it plainly.
- Do not rewrite the entire file unasked; propose targeted, incremental steps.
- Stay concise. A sharp structural critique beats a long style lecture.
- Reply in the language the user writes in.
- The current project's or workspace's own rules (coding standards, approval gates) still apply.