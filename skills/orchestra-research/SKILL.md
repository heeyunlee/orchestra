---
name: orchestra-research
description: Compares design approaches and produces an agreed drawing brief. Use when the product problem is known and the team needs research, alternatives, or a list of states to design.
---

# Decide what to draw

## Input

Bring a problem statement, affected users, success criteria, and constraints. A ticket, transcript, or research note can supply these fields.

## Instructions

Read `ORCHESTRA-SCORE.md` from the project root or the profile the user points to, if available.
Apply the relevant settings within the project's governing instructions.
In the `orchestra-research` tool checklist, use checked optional companions when relevant,
available, and authorized. Skip unchecked and unlisted optional companions unless the user
approves an override for this run. Treat `None` as no optional companions. If the checklist
is absent or `Unspecified`, follow the project's existing tool preferences. If a checked
tool is unavailable, use its agreed fallback if the stage permits it, or report the gap.
Resolve helpers by the name recorded in the profile, using the qualified name when provided.
If a checked helper requires direct user invocation, ask the user to run it and continue from
its output when supplied. Apply the same fallback rule if the user chooses to skip it.

1. Trace the existing experience. List the surfaces and meaningful states, including permission, empty, loading, failure, recovery, and small-screen states where applicable. Record what you could actually inspect.
2. Gather relevant project precedents, primary references, or examples supplied by the user. For each, record the source and what transfers to this problem. If browsing or app access is missing, use supplied material and label the gaps.
3. Compare plausible approaches against the same criteria. Include tradeoffs and describe what evidence could change the recommendation. Reuse shared patterns when they fit the intended behavior.
4. Agree on a direction with the owner. Ask decision-changing questions individually and record the answers.
5. Produce a drawing brief with the target behavior, exact states and viewport or device needs, design system, deliverable and approval owner. Define review gates and which checks need browser, device, or independent reviewer access.

## Output

Provide the **problem and criteria**, **current experience**, **options and evidence**, **direction and rationale**, **states and transitions**, **constraints and deliverable**, **review gates and approver**, and **open decisions**. Label the brief as agreed or provisional.

## Example

Compare an admin-only warning banner with an account-menu warning. A banner exposes usage while the admin is working. The menu saves space but takes an extra step to find. The team chooses a banner and agrees to draw near-limit and over-limit states, narrow layout, the settings action, and the member state without admin controls.
