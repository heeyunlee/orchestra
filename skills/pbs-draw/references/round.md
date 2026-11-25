# Round protocol

## Preflight and brief

- Locate the project's design system, existing behavior and approval rules. Use the user's
  requested artifact format. Confirm the paths or workspace identifiers for the brief, artifact,
  and evidence. Keep one round in one working location.
- Resolve which states must be drawn and exercised, how each state is reached, and which states
  need device, visual, or assistive technology checks. Confirm the audit and independent review
  requirements, approval owner, and how the owner can inspect a passing revision.
- Check the host for file access, rendering or browser access, and independent reviewers. Decide
  which evidence the host can collect and which evidence a collaborator must provide.
- Ask about unresolved decisions one at a time. Record answers and obtain a go-ahead. Complete
  the brief before starting the first pass.

## Draw, review, and revise

1. Save a checkpoint after the brief and each pass. Give the drawer only the brief, confirmed
   rulings, previous relevant findings, and round location. If model selection is available,
   select a model that can produce the requested artifact and handle the required visual inputs.
   Record the selected model if the host reports it. Use a fresh drawer per pass when using helpers.
2. Assign a unique revision identifier. Record where to open it and how to reach each state.
   Include the implementation source or editable artifact where appropriate.
3. Audit the revision. Assign required states across the review lanes and track opened states.
   Give independent reviewers the same revision and keep their reviews separate until synthesis.
   A failed audit or missing required evidence keeps the gate open.
4. Save findings by lane and severity. Give the drawer specific defects with state, evidence, and
   desired outcome. Ask the owner only the questions whose answers could change the next pass.
   Record each answer before revising.
5. On the next pass, recheck fixes, nearby behavior, and states with outstanding coverage. Recheck
   any prior evidence affected by the new revision. Unless the project sets a different limit,
   stop after three passes per cycle. If a gate is still open, report the blocker and next
   decision without presenting the revision as ready for approval.
6. Show a clean revision and its evidence. If the owner requests a redraw, record the ruling and
   begin a new cycle. Approval covers the specific reviewed revision.

## Resume in the same conversation

1. Before refreshing context, save the state file and any review evidence. Record the exact next
   step, working location, revision, review cycle and pass, findings, and the next open question.
2. Use the host's supported in-place context reset or compaction when it is available. If there is
   no reset, continue with the state and load only the materials for the next step. If the host
   cannot retain the conversation, reopen from the saved checkpoint.
3. Read the checkpoint first after resuming. Verify the working location and the recorded revision
   and check whether any existing work is still active. Resume from the saved step. Start fresh
   review sessions if the next step calls for independent review.
4. When adapting a project-specific checkpoint, retain the original record. Map its location,
   current stage, cycle and pass, revision, findings, and next action before advancing. Ask when
   the mapping is ambiguous.

## Handover and measurement

Record the approved revision and approval evidence, any design decisions and their rationale,
state coverage, behavior and transitions, affected shared components, and implementation checks.
Keep the artifact and evidence accessible to the people doing the work.

When available, record the drawer and reviewer models, audit results, opened versus required
states, elapsed time, and tokens or cost per pass. Use the units and scope reported by the host.
Mark unavailable metrics as unreported. State whether timing and tokens include review as well
as drawing, so results can be compared on the same basis.
