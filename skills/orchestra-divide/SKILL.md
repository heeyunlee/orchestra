---
name: orchestra-divide
description: Turns an approved design into implementation slices, dependencies, and QA checks. Use when engineering needs a delivery plan tied to the exact approved revision.
---

# Plan the engineering work

## Input

Bring an approved revision, its handover and coverage, and the relevant code or architecture. Confirm the approved revision before cutting work.

## Instructions

Read `ORCHESTRA-SCORE.md` from the project root or the profile the user points to, if available.
Apply the relevant settings within the project's governing instructions.
In the `orchestra-divide` tool checklist, use checked optional companions when relevant,
available, and authorized. Skip unchecked and unlisted optional companions unless the user
approves an override for this run. Treat `None` as no optional companions. If the checklist
is absent or `Unspecified`, follow the project's existing tool preferences. If a checked
tool is unavailable, use its agreed fallback if the stage permits it, or report the gap.
Resolve helpers by the name recorded in the profile, using the qualified name when provided.
If a checked helper requires direct user invocation, ask the user to run it and continue from
its output when supplied. Apply the same fallback rule if the user chooses to skip it.
Use the configured tracker and destination when permitted by the stage's tool choices. If the
tracker is unspecified, ask only when the choice affects the requested output. Use Markdown when
the profile selects it, tracker access is unavailable or unchecked, or the user wants a draft.
For tracker-shaped drafts, preserve the destination, terminology, and dependencies.

1. Locate affected entry points, shared components, data contracts, flags, and existing tests. Note where existing behavior or older data needs support. Use project architecture and delivery conventions.
2. Split the work into the smallest independently verifiable slices. Give each slice an outcome, scope, out-of-scope boundary, dependencies, and acceptance checks. Map every required state to an owner.
3. Identify technical dependencies and the design states that can be delivered together. Order the dependency chain, looking for cycles, and mark parallel work that touches separate ownership boundaries.
4. Define verification with test data, environment, devices or viewports, expected outcomes, and any deployment dependency. Include the end-to-end check that confirms the assembled feature.
5. Create or update tickets when the task calls for tracker writes, they are authorized, and
   the configured tracker is available. For drafts, return the plan as Markdown. Record the
   parent outcome and when it is ready to ship.

## Output

Provide the **approved revision**, **slices and owners**, **dependencies**, **acceptance and QA checks**, **combined verification**, and **delivery constraints**.

## Example

Slice A exposes the existing usage data and near-limit threshold. Slice B renders the approved warning and depends on A. Slice C checks role permissions and the settings destination and depends on B. The plan names the seed accounts and the near-limit, over-limit, and non-admin outcomes.
