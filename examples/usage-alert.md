# Worked example

A workspace app needs to help admins find the available action when usage nears the plan limit.
This fictional round illustrates the handoff records. Test results below are example evidence.

| Stage | Example record |
| --- | --- |
| Understand | Two reported cases of admins opening the wrong settings page. The baseline rate is unknown. Success means a seeded admin can reach the usage settings from the warning without a hint. |
| Research | Compared a banner with an account-menu warning. The owner agreed to a banner with near-limit, over-limit, narrow-layout, and non-admin states. Include keyboard access to the settings action. |
| Draw | At 320 px on r1 the action was clipped. The owner confirmed it should wrap below the copy. A reviewer tested all four states on r2 and verified keyboard access. The owner approved r2. |
| Divide | A supplies the usage threshold. B implements the banner after A. C verifies the settings destination and member permissions after B. Acceptance uses one admin and one member in the same seeded workspace. |
| Deliver | A and B landed. C was blocked by the missing seed workspace, with the tested revisions and blocker saved. On resume the seeded workspace was available and C passed on the recorded staging revision. |

## Resume after the first drawing pass

```markdown
# Design round state

- Round and project: usage-alert
- Working location: design/rounds/usage-alert/
- Stage and next action: revise, then reopen the narrow state and retest adjacent widths
- Cycle and pass: cycle 1, pass 2
- Brief and go-ahead: approved brief.md
- Artifact and revision: prototype-r1.html, r1
- Approver and approval evidence: product owner, approval pending
- Required audit, reviewers, states and environments: finish, design, browser at 320 and 768 px
- Coverage and review evidence: pass-1.md
- Open findings and decisions: action clipped at 320 px, owner ruled that the action wraps below the copy
- Host capabilities and outstanding checks: browser available, rerun keyboard check on r2
```

A team that already has an agreed brief can start here with just the drawing skill. Teams that
handle delivery separately can stop after design approval and pass the handover to engineering.
