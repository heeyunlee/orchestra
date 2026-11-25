# Add a custom accessibility review

Create `pbs-accessibility/SKILL.md` in your host's project skill directory. Paste the
example below and run `/pbs-accessibility` on a candidate revision when specialized
accessibility review is needed. The review can supply evidence to the drawing round.

```markdown
---
name: pbs-accessibility
description: Checks an inspectable design revision against its agreed accessibility criteria. Use when a design round needs focused keyboard or assistive technology evidence.
---

# Review accessibility

Bring the exact revision, criteria, and assigned states. For each state, exercise the agreed
keyboard path and collect assistive technology evidence where the host supports it. Record
revision, state, device or viewport, action, expected result, observed result, and evidence.
List checks that need another reviewer.

Return findings ordered by severity. Include a short reproduction path and the affected
criterion for each finding. Add evidence to the drawing round's review record when authorized.
```

To remove the custom stage, remove its skill folder. If your project requires its evidence,
provide the equivalent review record through your own process.
