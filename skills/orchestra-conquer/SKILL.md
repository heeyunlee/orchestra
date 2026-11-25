---
name: orchestra-conquer
description: Executes a dependency-aware design delivery plan and tracks real verification through readiness. Use when implementation slices are ready to start or delivery needs to resume from a checkpoint.
---

# Run the implementation plan

## Input

Bring the approved revision, slice list, dependencies, ownership, QA checks, and the project's definition of readiness.

## Instructions

Read `DESIGN-WORKFLOW.md` from the project root or the profile the user points to, if available.
Apply the relevant settings within the project's governing instructions.
In the `orchestra-conquer` tool checklist, use checked optional companions when relevant,
available, and authorized. Skip unchecked and unlisted optional companions unless the user
approves an override for this run. Treat `None` as no optional companions. If the checklist
is absent or `Unspecified`, follow the project's existing tool preferences. If a checked
tool is unavailable, use its agreed fallback if the stage permits it, or report the gap.
Resolve helpers by the name recorded in the profile, using the qualified name when provided.
If a checked helper requires direct user invocation, ask the user to run it and continue from
its output when supplied. Apply the same fallback rule if the user chooses to skip it.
Use the configured tracker for ticket evidence when available and permitted by the tool choices.
With a Markdown plan, use the plan and the project's review and QA evidence. If tracker access is
missing or unchecked, record any required status check that is still owed.

1. Read current tracker, branch, review and QA evidence. Match it to the approved plan. Record which slices are complete, active, runnable, or blocked. On resume, check for existing owners and sessions before starting work.
2. Start slices with satisfied dependencies. Run independent slices concurrently when authorized and supported, with separate ownership. Use sequential work in a host without delegation or when slices share prerequisites.
3. Follow each slice through the project's review and verification gates. Record the tested revision, environment, and observed outcomes. Route failures back to the owner, fix within scope, and rerun the affected checks against the new revision.
4. Run the combined acceptance check after the required slices land in the designated environment. Mark a slice or the parent ready only when its required evidence is in place. Apply any explicit approval rules before merging or deploying.
5. When deployment is requested and authorized, use the project's release procedure. Verify the
   deployed revision in the target environment and run the project's post-deploy smoke check.
   Record the observed result.
6. Save a checkpoint when work cannot continue. Include active ownership, tested revisions, evidence, blockers, the unblock condition, and the next runnable slice. On resume, reconcile the checkpoint with current evidence.

## Output

Return the **approved revision**, **slice status**, **tested implementation revisions**, **verification evidence**, and **readiness or next action**. Record production status only if verified.

## Example

The warning UI has merged and its unit checks pass. The staging seed account lacks the usage data needed for the browser check. Record the merged revision and pending staging check. Continue any unblocked slice, then resume that check when the seed account is available.
