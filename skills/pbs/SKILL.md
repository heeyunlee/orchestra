---
name: pbs
description: Lists installed Product Builder Skills and routes optional /pbs menu shortcuts. Use when the user invokes /pbs, selects pbs, or asks pbs to run a stage.
---

# Product Builder Skills

The `/pbs-<stage>` commands invoke individual skills directly. When the user invokes this
menu, use the first word after `/pbs` to select a stage. Pass the rest of the request,
including files, links, and agreed decisions, to the selected skill as its input.

| Menu shortcut | Direct command | Purpose |
| --- | --- | --- |
| `/pbs init` | `/pbs-init` | Set up or update project workflow defaults |
| `/pbs why` | `/pbs-why` | Define the product problem and success criteria |
| `/pbs research` | `/pbs-research` | Compare approaches and agree on a drawing brief |
| `/pbs draw` | `/pbs-draw` | Draw, review, approve, or resume a design round |
| `/pbs divide` | `/pbs-divide` | Plan implementation slices and verification |
| `/pbs conquer` | `/pbs-conquer` | Execute a delivery plan and verify readiness |

An exact installed skill name is also a valid stage. This lets users invoke a custom skill
such as `/pbs design-accessibility`. Discover it through the host's available skills or its
documented skill directories. Treat the stage as a skill name and resolve it only from those
sources. Follow the selected skill's instructions and the project's governing rules.

If the requested skill is absent, give its name and explain that it needs to be installed or
supplied as Markdown. If the user invokes `/pbs` without a stage, show the available stages
and ask which one they want. If a stage is unrecognized, show the supported commands and ask
which installed skill to use. Run just the selected skill unless the user asks for more.

## Example

`/pbs draw Resume from design/rounds/usage-alert/STATE.md` loads `pbs-draw` and passes it the
state file to resume. On a host without a slash command, select or attach this skill and send
the same request in chat.
