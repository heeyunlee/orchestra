---
name: orchestra
description: Lists installed Orchestra and routes optional /orchestra menu shortcuts. Use when the user invokes /orchestra, selects orchestra, or asks orchestra to run a stage.
---

# Orchestra

The `/orchestra-<stage>` commands invoke individual skills directly. When the user invokes this
menu, use the first word after `/orchestra` to select a stage. Pass the rest of the request,
including files, links, and agreed decisions, to the selected skill as its input.

| Menu shortcut | Direct command | Purpose |
| --- | --- | --- |
| `/orchestra init` | `/orchestra-init` | Set up or update project workflow defaults |
| `/orchestra why` | `/orchestra-why` | Define the product problem and success criteria |
| `/orchestra research` | `/orchestra-research` | Compare approaches and agree on a drawing brief |
| `/orchestra draw` | `/orchestra-draw` | Draw, review, approve, or resume a design round |
| `/orchestra divide` | `/orchestra-divide` | Plan implementation slices and verification |
| `/orchestra conquer` | `/orchestra-conquer` | Execute a delivery plan and verify readiness |

An exact installed skill name is also a valid stage. This lets users invoke a custom skill
such as `/orchestra orchestra-accessibility`. Discover it through the host's available skills or its
documented skill directories. Treat the stage as a skill name and resolve it only from those
sources. Follow the selected skill's instructions and the project's governing rules.

If the requested skill is absent, give its name and explain that it needs to be installed or
supplied as Markdown. If the user invokes `/orchestra` without a stage, show the available stages
and ask which one they want. If a stage is unrecognized, show the supported commands and ask
which installed skill to use. Run just the selected skill unless the user asks for more.

## Example

`/orchestra draw Resume from design/rounds/usage-alert/STATE.md` loads `orchestra-draw` and passes it the
state file to resume. On a host without a slash command, select or attach this skill and send
the same request in chat.
