# Humans as AI Skills

> Masters are scarce. Their methods are not.

Each folder in this repo packages one expert human's frameworks as a self-contained AI agent skill: a structured, repeatable review process any agent can run. **Not persona chatbots.** No roleplay, no invented quotes. Every skill uses the human's *method*, applied to your actual context.

## The collection

| Skill | Domain | The human | Invoke by |
|-------|--------|-----------|-----------|
| [`clayton-christensen-strategy`](skills/clayton-christensen-strategy/SKILL.md) | Strategy & Disruption | Clayton Christensen | "Christensen review", "Clayton review" |
| [`david-kelley-design`](skills/david-kelley-design/SKILL.md) | Design & Innovation | David Kelley (IDEO / Stanford d.school) & Double Diamond | "Kelley review", "Design review" |
| [`marty-cagan-product`](skills/marty-cagan-product/SKILL.md) | Product Risks & Scope | Marty Cagan (Silicon Valley Product Group) | "Cagan review", "Product risk review" |
| [`jeff-sutherland-agile`](skills/jeff-sutherland-agile/SKILL.md) | Agile Delivery | Jeff Sutherland (Scrum) | "Sutherland review", "Agile review" |
| [`april-dunford-positioning`](skills/april-dunford-positioning/SKILL.md) | Product Positioning | April Dunford (*Obviously Awesome*) | "Dunford review", "Positioning review" |
| [`donald-miller-storybrand`](skills/donald-miller-storybrand/SKILL.md) | Messaging & Brand Story | Donald Miller (*Building a StoryBrand*) | "Miller review", "StoryBrand review", "Messaging review" |
| [`alex-hormozi-value-pricing`](skills/alex-hormozi-value-pricing/SKILL.md) | Value Pricing & Offers | Alex Hormozi (*$100M Offers*) | "Hormozi review", "Value pricing review" |
| [`neil-rackham-sales`](skills/neil-rackham-sales/SKILL.md) | Consultative Sales | Neil Rackham (*SPIN Selling*) | "Rackham review", "SPIN review" |
| [`andy-grove-operations`](skills/andy-grove-operations/SKILL.md) | Operations & Management | Andy Grove & Eli Goldratt | "Grove review", "Operations review" |
| [`barbara-minto-communication`](skills/barbara-minto-communication/SKILL.md) | Communication | Barbara Minto (*The Pyramid Principle*) | "Minto review", "Communication review" |
| [`peter-kraljic-procurement`](skills/peter-kraljic-procurement/SKILL.md) | Procurement | Peter Kraljic & Arjan van Weele | "Kraljic review", "Procurement review" |
| [`russell-ackoff-ops-research`](skills/russell-ackoff-ops-research/SKILL.md) | Operations Research & Systems | Russell Ackoff (with C. West Churchman) | "Ackoff review", "Ops research review", "OR review" |
| [`lincoln-murphy-customer-success`](skills/lincoln-murphy-customer-success/SKILL.md) | Customer Success | Lincoln Murphy | "Murphy review", "Customer Success review" |
| [`matthew-dixon-customer-effort`](skills/matthew-dixon-customer-effort/SKILL.md) | Customer Effort & Support | Matthew Dixon, Nick Toman & Rick DeLisi | "Dixon review", "Customer effort review" |
| [`martin-fowler-code-review`](skills/martin-fowler-code-review/SKILL.md) | Code Quality & Refactoring | Martin Fowler & Kent Beck | "Fowler review", "Code smell review", "Refactoring review" |
| [`richard-feynman-code-translation`](skills/richard-feynman-code-translation/SKILL.md) | Plain-English Code Walkthrough | Richard Feynman (The Feynman Technique) | "Feynman translation", "Plain English code", "Code walkthrough" |
| [`adam-shostack-threat-modeling`](skills/adam-shostack-threat-modeling/SKILL.md) | Threat Modeling & STRIDE | Adam Shostack (*Threat Modeling: Designing for Security*) | "Shostack review", "Threat model", "STRIDE review" |
| [`troy-hunt-web-security`](skills/troy-hunt-web-security/SKILL.md) | Web Security & Breach Practice | Troy Hunt (Have I Been Pwned) | "Hunt review", "Web security review", "Breach review" |
| [`board`](skills/board/SKILL.md) | Convening the board | The collection, together | "@board", "board review" |

**Example:** point an agent at a plan and say *"give me a Christensen review of this"*: it picks the 1-3 Christensen lenses that genuinely apply, grounds the critique in your real workspace context, and surfaces the strongest blind spot, what it costs to ignore, and two or three ways to redirect. It will not pick for you unless asked.

## Why "explicit invocation only"

Every skill runs **only when you call it by name**. Ordinary requests stay ordinary: no skill hijacks them. This is built into every file's trigger and description.

## Shared anatomy

All skills follow the same shape:

1. **Trigger**: explicit invocation only
2. **Confirm** the subject and the mode (review / design / learn / plan / coach / advise)
3. **Ground** the work in real context (workspace files, records, connected tools), and mark any unverified claim as an assumption
4. **Lenses**: the frameworks, as numbered test-questions; choose only those that genuinely apply
5. **Structured output**: the finding, the lens that flags it, the evidence, the cost of ignoring it, distinct options with trade-offs, one question back
6. **Rules**: no praise openers, no roleplay, no invented data, concise, reply in the user's language

## Package a human: contribution checklist

1. Pick one human with clearly written frameworks (one anchor author; co-authors allowed in parentheses)
2. Follow the shared anatomy above; name the skill `<firstname>-<lastname>-<specialization>`
3. The description **must** say: use only when explicitly invoked, never on your own initiative
4. Use the method, not the persona: no roleplay, no invented quotes or data
5. Open a PR with the human added to the table above

## Credits

The frameworks belong to their authors: Christensen (*The Innovator's Dilemma*, *Competing Against Luck*, *How Will You Measure Your Life?*), Kelley (*Creative Confidence* with Tom Kelley) and the Design Council's Double Diamond, Cagan (*Inspired*, *Empowered* with Silicon Valley Product Group), Sutherland (*Scrum: The Art of Doing Twice the Work in Half the Time*) and Ken Schwaber, Dunford (*Obviously Awesome*), Hormozi (*$100M Offers*), Rackham (*SPIN Selling*), Grove (*High Output Management*) and Goldratt (*The Goal*), Minto (*The Pyramid Principle*), Kraljic (*Purchasing Must Become Supply Management*) and van Weele (*Purchasing and Supply Chain Management*), Ackoff (*Introduction to Operations Research* with Churchman and Arnoff, *The Art of Problem Solving*, *Creating the Corporate Future*), and Miller (*Building a StoryBrand*), Murphy (*Customer Success* with Mehta & Steinman), Dixon, Toman & DeLisi (*The Effortless Experience*), Fowler (*Refactoring: Improving the Design of Existing Code* with Kent Beck), Shostack (*Threat Modeling: Designing for Security*), Hunt (Have I Been Pwned), and Feynman (The Feynman Technique). These are independent applications of published ideas, not affiliated with or endorsed by the authors or their estates.

## License

[MIT](LICENSE)
