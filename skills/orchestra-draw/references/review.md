# Review an exact revision

Start with an audit of the design artifact against the brief. Open the artifact or obtain
evidence of each required check. If the project has an audit script or rubric, run it against
the candidate revision. Attach its output and flag any missing state or broken transition.

## Reviewer prompts

Pass each reviewer the brief, exact revision and how to open it, assigned states, design language,
relevant prior findings, and the review lane below. Ask them to report the states they opened and
how they checked them, followed by findings with severity, state, evidence, and proposed outcome.
Ask them to record each check they could not perform. Reviewers should review in separate contexts
when independence is required. They should leave the artifact unchanged.

- **Finish:** Inspect the artifact and source where available. Check typography, spacing,
  hierarchy, shared component use, copy, alignment, legibility, and consistency with the
  project design system. Compare each assigned state across the required sizes.
- **Design critique:** Trace the assigned states from the user's goal. Check whether the flow
  meets the brief, exposes the right decisions and feedback, supports recovery, and handles
  permissions and edge cases. Flag places where intended behavior is unclear or a documented
  choice needs the owner's ruling.
- **Browser or device evidence:** Reproduce the assigned interactions in the target environment.
  Record viewport or device, inputs, and outcomes. Check keyboard focus, overlap, clipping,
  contrast, navigation, deep-link or reload behavior, and layout at the agreed sizes where
  applicable. Report limitations of browser, device, visual or accessibility tooling.

## Decision and follow-through

Use the project's severity rubric when supplied. Otherwise use this rubric:

| Severity | Meaning |
| --- | --- |
| P0 | A required flow is broken, inaccessible, or unverifiable |
| P1 | The design violates the brief, design system, or an agreed quality bar |
| P2 | Follow-up improvement that leaves the agreed behavior and review bar intact |

Reconcile duplicate findings and conflicting evidence against the artifact. Keep direct links
to each reviewer result. Document coverage as a row per required state with the reviewer, revision,
device or viewport, action, result, and evidence. A clean pass requires the required audit and
coverage, satisfaction of the agreed independence requirement, and resolution of P0 and P1
findings. If visual or browser checks could not run, preserve the gap until a capable reviewer
supplies evidence. A single session can perform several lanes if the project accepts that
arrangement. Record that all lanes came from one session.
