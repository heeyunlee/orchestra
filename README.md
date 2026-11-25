# product-builder-skills

Five independent [Agent Skills](https://agentskills.io/specification) for taking product design from a problem to verified delivery. Start at the stage whose input you already have.

## Quick start

From the project where you want to use the skills, run:

```sh
npx skills add heeyunlee/product-builder-skills
```

Choose `pbs` and the stages you want, then select your agent. To install just the drawing
workflow, including its entry point:

```sh
npx skills add heeyunlee/product-builder-skills --skill pbs --skill design-draw
```

Run `/pbs draw` with an approved brief, or run `/pbs` to see the available stages.
Use [manual installation](#manual-installation) if your agent is absent from the installer or you
prefer copying the files yourself. See the [Skills CLI documentation](https://github.com/vercel-labs/skills)
for its Node.js requirements and agent support.

## Skill catalog

| Command | Skill | Bring | Get |
| --- | --- | --- | --- |
| `/pbs why` | [design-why](skills/design-why/SKILL.md) | A proposed change or a user problem | An agreed problem, evidence, and success criteria |
| `/pbs research` | [design-research](skills/design-research/SKILL.md) | A problem and success criteria | Compared approaches and a drawing brief |
| `/pbs draw` | [design-draw](skills/design-draw/SKILL.md) | A drawing brief or a saved round | A reviewed, approved revision and handover |
| `/pbs divide` | [design-divide](skills/design-divide/SKILL.md) | An approved revision | Independently verifiable implementation slices and dependencies |
| `/pbs conquer` | [design-conquer](skills/design-conquer/SKILL.md) | A delivery plan with dependencies | Verified delivery evidence or a resumable checkpoint |

## Optional project setup

Choose [Initial Lines](skills/initial-lines/SKILL.md) along with `pbs` in the installer,
or install both directly:

```sh
npx skills add heeyunlee/product-builder-skills --skill pbs --skill initial-lines
```

Run `/pbs init` to set up the workflow.
It asks which tracker you use, where design work lives, who approves it, and how you verify
delivery. It saves confirmed choices in `DESIGN-WORKFLOW.md` at your project's root. If you
use an existing workflow document, give the next skill its path. Every design stage can use
the profile, and you can still supply the same settings directly.

Try `/pbs init We use Linear and want ticket drafts first.`

## Manual installation

Clone or download this repository. Install the [pbs entry point](skills/pbs/SKILL.md)
and whichever stages you want to run. Open the repository root in a terminal and copy each
selected skill folder into your host's project skill directory. Keep the whole folder so
its references and templates travel with it. Run `/pbs` by itself to choose a stage.

| Host | Project directory | Start |
| --- | --- | --- |
| [Codex](https://developers.openai.com/codex/skills) | `.agents/skills/` | Select `pbs` and enter a stage, such as `draw` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `.claude/skills/` | Type `/pbs draw` |
| [Cursor](https://cursor.com/docs/skills) | `.cursor/skills/` | Select `pbs` in agent chat and enter a stage |
| [VS Code](https://code.visualstudio.com/docs/agent-customization/agent-skills) | `.github/skills/` | Select `/pbs` from the chat command menu and enter a stage |
| Any chat or editor | A folder you can open or attach | Provide the entry point, selected skill, and its references, then ask for `/pbs draw` or another stage |

For example, to install only the drawing stage in Codex on macOS or Linux:

```sh
project=/path/to/your/project
mkdir -p "$project/.agents/skills"
test ! -e "$project/.agents/skills/pbs" &&
  cp -R skills/pbs "$project/.agents/skills/"
test ! -e "$project/.agents/skills/design-draw" &&
  cp -R skills/design-draw "$project/.agents/skills/"
```

On Windows, copy the folder in Explorer. If you already have a copy, compare changes before
replacing it. Some hosts discover several skill directories. Install one copy per skill
in an active project to avoid ambiguous discovery.

Try `/pbs draw Use this approved brief and save state in design/rounds/usage-alert/STATE.md.`

## Customize the workflow

For CLI-managed installations, use `npx skills list` to see what's installed,
`npx skills check` to check for updates, and `npx skills remove design-research` to remove one
stage. Review local edits before updating a modified skill.


- **Remove a stage:** remove its copied folder from your host's skill directory. Supply the next
  stage with the equivalent input from your own process. For example, use a research team's
  agreed brief with `design-draw`.
- **Replace a stage:** edit your local copy or install a custom skill. Keep the agreed input and
  output fields that downstream stages use. Give custom skills unique names when both copies
  will be installed.
- **Add a stage:** create a sibling folder whose `SKILL.md` declares a matching `name` and a
  `description`. Document its inputs, outputs, and when to invoke it. Run it with
  `/pbs <skill-name>`. See [the accessibility review example](examples/custom-stage.md).
- **Set project rules:** pass the project design language, approval owner, review gates, artifact
  format, and tracker as inputs or put them in your project's instructions. A drawing round
  records these choices in its own state file. Teams can keep these settings alongside the project.

## Hosts and models

The instructions are plain Markdown and contain no required model IDs, plugins, or shell
commands. Native discovery, file writes, browser testing, and independent review depend on the
host. Use attached or pasted text when a host cannot read files. Save returned artifacts
manually when it cannot write files. Choose a drawing model that can produce the required
artifact and use a visual model for image evidence when available. External reviewers or
user-supplied test evidence can fill capability gaps. Record checks still owed and pause at
any required gate that lacks evidence.

## Examples and contributions

- [Build a usage alert](examples/usage-alert.md) follows all five stages and shows how to resume a drawing round.
- [Add a custom accessibility review](examples/custom-stage.md) shows how to extend the workflow and invoke the new skill through `/pbs`.
- [Contribute a skill](CONTRIBUTING.md) covers the directory layout, examples, and checks.
