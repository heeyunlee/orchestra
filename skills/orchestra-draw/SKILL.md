---
name: orchestra-draw
description: Runs an attended design round from a brief through drawing, evidence-based review, approval, and handover. Use to start a new round, review a revision, or resume a saved STATE.md.
---

# Draw and review a design

## Input

Bring an agreed drawing brief or an existing `STATE.md`. A brief identifies the problem, success criteria, agreed states, design language, deliverable, required checks, and approver. Ask about missing choices that can change the drawing. Use the same writable project location throughout the round when possible.

## Instructions

Read `ORCHESTRA-SCORE.md` from the project root or the profile the user points to, if available.
Apply the relevant settings within the project's governing instructions.
In the `orchestra-draw` tool checklist, use checked optional companions when relevant,
available, and authorized. Skip unchecked and unlisted optional companions unless the user
approves an override for this run. Treat `None` as no optional companions. If the checklist
is absent or `Unspecified`, follow the project's existing tool preferences. If a checked
tool is unavailable, use its agreed fallback if the stage permits it, or report the gap.
Resolve helpers by the name recorded in the profile, using the qualified name when provided.
If a checked helper requires direct user invocation, ask the user to run it and continue from
its output when supplied. Apply the same fallback rule if the user chooses to skip it.

1. Read the [round protocol](references/round.md) and create or resume the [state record](assets/STATE.md). Verify the location, revision, owner, required tools, and pending step. Ask decision-changing questions one at a time and record the answers. Obtain the go-ahead before drawing.
2. Produce an inspectable, versioned revision. Use a fresh drawer with the strongest available model for the required artifact when the host and user authorize delegation. Otherwise draw in the current session when you can produce the artifact, or ask for an artifact from a capable tool or collaborator.
3. Audit each revision and run the [review lanes](references/review.md). Keep the reviewer assignments, opened states, evidence and findings with the revision. Carry open findings forward. Resolve questions that could change the design before the next pass.
4. After a clean pass, show the exact revision with its state coverage and any residual limitations. Capture the owner's explicit ruling. A redesign starts a new review cycle and needs new verification.
5. Hand over the approved revision, prototype location, states and transitions, shared components, decisions, known follow-up, and verification evidence. Use the project's approval and delivery rules for any publish or repository writes.

## Output

Return the approved revision and its handover, or a checkpoint with the current revision, unresolved gates, and next action. Review coverage and user approval each attach to an exact revision.

## Example

The browser reviewer finds that the usage warning's action disappears at 320 px on revision `r1`. Record the viewport and reproduction steps, fix the layout in `r2`, and retest that state plus adjacent widths. Show `r2` once the required lanes are clean. Record the owner's approval of `r2`.
