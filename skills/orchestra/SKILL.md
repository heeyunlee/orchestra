---
name: orchestra
description: Routes /orchestra to an individual stage or takes a product request through Why, Research, Draw, Divide, and Conquer. Use for /orchestra menu shortcuts or a request that starts with Let's build.
---

# Orchestra

The `/orchestra-<stage>` commands invoke individual skills directly. After `/orchestra`,
recognize `build` or a request beginning “Let's build” as the full workflow. Otherwise use the
first word to select a stage. Pass the request, files, links, and agreed decisions to the selected
workflow or skill as input.

| Menu shortcut | Direct command | Purpose |
| --- | --- | --- |
| `/orchestra build` | — | Take a product request from Why through Conquer |
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

## Run the full workflow

1. Check for an existing brief, artifacts, and checkpoint. Resume from the first stage whose
   required output is still open. For a fresh request, start with Why. Use the existing project
   profile when available. Ground short requests in the product's audience and current goal
   before choosing a direction.
2. Run the installed stage skills in order. Pass the agreed problem and success checks from
   `orchestra-why` to `orchestra-research`, the drawing brief to `orchestra-draw`, the approved
   revision to `orchestra-divide`, and the implementation plan and acceptance checks to
   `orchestra-conquer`. Carry the agreed product goal and success checks through each handoff.
   Open the selected stage's instructions as you reach it. If a stage is
   missing, name it and keep the latest checkpoint so work can resume after it is installed or
   supplied.
3. At each handoff, record the agreed output and next step in the project's chosen location.
   Continue when the next stage has what it needs. Honor the project's design, merge, QA, and
   release gates and pause for any outstanding decision or approval. When deployment is requested
   and authorized, Conquer follows the project's release procedure and verifies the live revision.
   If release evidence is pending, report the latest verified environment and the next action.

## Example

`/orchestra draw Resume from design/rounds/usage-alert/STATE.md` loads `orchestra-draw` and passes it the
state file to resume. On a host without a slash command, select or attach this skill and send
the same request in chat.
