---
name: design-conquer
description: Executes a dependency-aware design delivery plan and tracks real verification through readiness. Use when implementation slices are ready to start or delivery needs to resume from a checkpoint.
---

# Run the implementation plan

## Input

Bring the approved revision, slice list, dependencies, ownership, QA checks, and the project's definition of readiness.

## Instructions

1. Read current tracker, branch, review and QA evidence. Match it to the approved plan. Record which slices are complete, active, runnable, or blocked. On resume, check for existing owners and sessions before starting work.
2. Start slices with satisfied dependencies. Run independent slices concurrently when authorized and supported, with separate ownership. Use sequential work in a host without delegation or when slices share prerequisites.
3. Follow each slice through the project's review and verification gates. Record the tested revision, environment, and observed outcomes. Route failures back to the owner, fix within scope, and rerun the affected checks against the new revision.
4. Run the combined acceptance check after the required slices land in the designated environment. Mark a slice or the parent ready only when its required evidence is in place. Apply any explicit approval rules before merging or deploying.
5. Save a checkpoint when work cannot continue. Include active ownership, tested revisions, evidence, blockers, the unblock condition, and the next runnable slice. On resume, reconcile the checkpoint with current evidence.

## Output

Return the **approved revision**, **slice status**, **tested implementation revisions**, **verification evidence**, and **readiness or next action**. Record production status only if verified.

## Example

The warning UI has merged and its unit checks pass. The staging seed account lacks the usage data needed for the browser check. Record the merged revision and pending staging check. Continue any unblocked slice, then resume that check when the seed account is available.
