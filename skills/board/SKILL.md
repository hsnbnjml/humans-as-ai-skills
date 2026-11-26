---
name: "board"
description: "Convene a board of expert advisors on a business, product, operations, sales, or engineering decision. Use when the user invokes @board, asks what the board or a panel would say, or explicitly requests a multi-expert review."
---

# Advisory Board

One decision, several expert methods, one call. The board seats the humans whose
methods would actually change the answer, has each pressure-test the decision,
and resolves the disagreements into a recommendation.

## Authority to convene

Invoking `board` is the user explicitly requesting these reviews. When the board
seats a human, that human's "use only when explicitly invoked / never on your own
initiative" rule is satisfied. Load the seated skills and proceed.

## Step 1: What is being decided

State the decision in one sentence. If there is no decision (it's a question, a
lookup, or a task), say so and answer normally. Do not convene a board for work
that has no trade-off in it.

## Step 2: Build the panel

Select from the human skills advertised to you, using their IDs and descriptions.

The test: **would this human's method change the decision?** Not "could they
comment". If yes, they are in. If they would only agree with someone already
seated, they are out.

- No cap. Seat everyone who passes, however many that is.
- Never seat someone just to fill a panel.
- If only one human passes, say "this is a review, not a board" and run that one.
- Judge every advertised human, not only the likely ones. Record the reason for
  each rejection in three to six words. Step 3 prints it.

## Step 3: Propose, then wait

Output the whole roster, then stop. Every advertised human appears exactly once,
under IN or OUT, so a seat can be forced:

```
Convening 3 of 14

IN
  Hormozi:  pricing and offer structure
  Dunford:  positioning and willingness to pay
  Dixon:    churn and customer effort

OUT
  Cagan:    no scope or discovery risk here
  Minto:    the argument is already answer-first
  Ackoff:   no allocation or capacity decision
  Rackham:  no discovery call involved

Go? Name anyone to force in, or drop a seat.
```

The OUT reason is the test that human failed. List all of them; do not collapse the
rest into "and others". Do not deliberate until the user says go.

If the user names anyone, seat them even if they failed the test. A forced seat is
the user's call, not a relevance question. Adjust and re-propose once.

## Step 4: Deliberate

On go, load each seated skill with the `skill` tool, then give every seat equal
airtime, not equal length.

For each advisor:

1. **Position:** what their method says to do.
2. **Assumption:** the one assumption the position rests on.
3. **Falsifier:** what would make them wrong.

Second round only for advisors who disagree with something already said.
Advisors who agree stay quiet; agreement is not a contribution.

## Step 5: Handle conflict

Never average. Averaging expert advice produces mush.

For each real disagreement:

1. Name it plainly.
2. Name why: different metric, time horizon, or assumption.
3. Say which one wins under which condition.

If no condition resolves it, present the fork and let the user choose. A clean
fork beats a fake consensus.

## Step 6: The board's call

End with:

- **Call:** the recommended path, one or two sentences.
- **Strongest dissent:** the best argument against it, one sentence.
- **What would change it:** the fact or threshold that flips the call.

## Rules

- Attribute by method, not persona: "the value-pricing lens says...", not "I am
  Hormozi". Never invent quotes or positions.
- Every claim must come from a loaded skill. If a skill did not load, say so and
  continue with the rest.
- No padding. If the board agrees in one paragraph, stop there.
- If no advertised human fits, say so and answer without a board.

## Scaling

The panel comes from the advertised skill list, not a written roster. A newly
installed human is eligible on the next step with no edit to this file. Their
`description` is what makes them selectable, so keep descriptions about domain,
not just trigger phrases.