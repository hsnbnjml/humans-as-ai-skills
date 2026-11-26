---
name: "richard-feynman-code-translation"
description: "Plain-English walkthrough of code for non-technical readers (story, analogy, input and output). Use only when the user explicitly invokes richard-feynman-code-translation, or asks for a \"Feynman translation\", \"Plain English code\", or \"Code walkthrough\" by name. Never apply it on your own initiative."
---

# Richard Feynman Code Translation (Plain English Walkthrough)

A step-by-step, plain-English translation of code logic and architecture using Richard Feynman's technique: stripping away jargon, tech-speak, and complexity to explain what the code does behind the scenes using clear mental models and analogies.

## Trigger

Run only when the user explicitly calls this skill or asks for a "Feynman translation", "Plain English code", or "Code walkthrough" by name. Do not apply it to ordinary code explanations or debugging chats. When it is not invoked, behave normally.

## Step 1: Confirm what is under review

Identify the subject: a specific code file, function, algorithm, or system workflow. If it is unclear, ask one question and wait.

## Step 2: Ground the translation in real context

Before translating, inspect the exact code files or snippets provided in the workspace. Do not invent behavior or guess what hidden libraries do. If code is missing or unreadable, state what is missing and ask. Label any unverified assumptions about execution flow.

## Step 3: Pick the lenses that fit

Choose one to three lenses that genuinely apply. If none fits, say so plainly instead of forcing one.

**1. The Plain English Story (Paragraph-by-Paragraph)**
- What is this block of code doing as a real-world story? (e.g., *"First, it opens the filing cabinet, looks for folders matching today's date, and pulls out the receipts..."*)
- Translating syntax (`if/else`, loops, async/await, maps) into plain human intent.

**2. The Behind-the-Scenes Analogy**
- What physical or everyday situation mirrors this digital process? (e.g., comparing a queue/buffer to a bakery line, or state management to a whiteboard in a conference room).

**3. Input $\rightarrow$ Transformation $\rightarrow$ Output**
- What goes in (raw ingredients), what happens in the middle (the kitchen processing), and what comes out (the final dish served to the user)?

**4. The "Why" for Non-Technical Readers**
- Why does this code exist from a product or human standpoint? What frustration does it eliminate for the person using the app?

## Step 4: Write the translation

Use this shape, kept short and clear:

**The big picture:** one sentence explaining what this code accomplishes in plain human terms.

**Paragraph-by-paragraph walkthrough:** clear, jargon-free bullet points breaking down the logic flow line-by-line or block-by-block.

**The analogy:** a concise real-world parallel that locks in the mental model.

**Input & Output:** what enters the code and what leaves it.

**Question back:** one question that checks whether the non-technical translation captured the intent accurately.

## Rules

- No technical jargon without an immediate plain-English translation. Avoid lecturing or talking down to the reader.
- Do not roleplay Feynman or quote him. Use the Feynman technique (simplicity, analogies, first principles), not the persona.
- Never invent code behavior. Translate exactly what is written.
- Stay concise. A clear, intuitive explanation beats a technical textbook.
- Reply in the language the user writes in.
- The current project's or workspace's own rules (approval gates, confidentiality, tone) still apply.