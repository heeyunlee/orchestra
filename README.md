# Orchestra

**Conduct your product workflow from idea to delivery.**

Orchestra gives your AI agent a set of [Agent Skills](https://agentskills.io/specification)
to define the problem, research options, review a design, plan the build, and verify delivery.
Start at any stage and choose which skills, plugins, connectors, and MCP servers it uses.

## Quick start

From the project where you want to use the skills, run:

```sh
npx skills add heeyunlee/orchestra
```

Choose the skills you want, then select your agent. Install `orchestra` as well if you want the
optional command menu. To install just the drawing skill:

```sh
npx skills add heeyunlee/orchestra --skill orchestra-draw
```

Run `/orchestra-draw` with an approved brief. If you also installed `orchestra`, run `/orchestra` to see the
available stages.
Use [manual installation](#manual-installation) if your agent is absent from the installer or you
prefer copying the files yourself. See the [Skills CLI documentation](https://github.com/vercel-labs/skills)
for its Node.js requirements and agent support.

## Skill catalog

| Command | Bring | Get |
| --- | --- | --- |
| [`/orchestra-why`](skills/orchestra-why/SKILL.md) | A proposed change or a user problem | An agreed problem, evidence, and success criteria |
| [`/orchestra-research`](skills/orchestra-research/SKILL.md) | A problem and success criteria | Compared approaches and a drawing brief |
| [`/orchestra-draw`](skills/orchestra-draw/SKILL.md) | A drawing brief or a saved round | A reviewed, approved revision and handover |
| [`/orchestra-divide`](skills/orchestra-divide/SKILL.md) | An approved revision | Independently verifiable implementation slices and dependencies |
| [`/orchestra-conquer`](skills/orchestra-conquer/SKILL.md) | A delivery plan with dependencies | Verified delivery evidence or a resumable checkpoint |

## Optional project setup

Choose [`orchestra-init`](skills/orchestra-init/SKILL.md) in the installer or install it directly:

```sh
npx skills add heeyunlee/orchestra --skill orchestra-init
```

Run `/orchestra-init` to discover available tools and choose which skills, plugins,
connectors, and MCP servers to use in each stage. For example, check
`mattpocock-skills:grill-with-docs` for Why and leave it unchecked for Research.
The interview also captures your tracker, design, and delivery defaults.

Selections are saved in `DESIGN-WORKFLOW.md` at your project's root. Edit the
`[x]` and `[ ]` entries there or run init again to change them. Each stage reads
its own checklist. If you use an existing workflow document, give the next skill
its path.

Try `/orchestra-init We use Linear and want ticket drafts first.`

## Manual installation

Clone or download this repository. Copy each selected skill folder into your host's project
skill directory. Keep the whole folder so its references and templates travel with it.
Copy [`orchestra`](skills/orchestra/SKILL.md) too if you want the optional menu.

| Host | Project directory | Start |
| --- | --- | --- |
| [Codex](https://developers.openai.com/codex/skills) | `.agents/skills/` | Select `orchestra-draw` or another installed skill |
| [Claude Code](https://code.claude.com/docs/en/skills) | `.claude/skills/` | Type `/orchestra-draw` |
| [Cursor](https://cursor.com/docs/skills) | `.cursor/skills/` | Select `orchestra-draw` or another installed skill in agent chat |
| [VS Code](https://code.visualstudio.com/docs/agent-customization/agent-skills) | `.github/skills/` | Select `/orchestra-draw` or another installed skill from the chat command menu |
| Any chat or editor | A folder you can open or attach | Provide the selected skill and its references, then ask for `/orchestra-draw` or another stage |

For example, to install only the drawing stage in Codex on macOS or Linux:

```sh
project=/path/to/your/project
mkdir -p "$project/.agents/skills"
test ! -e "$project/.agents/skills/orchestra-draw" &&
  cp -R skills/orchestra-draw "$project/.agents/skills/"
```

On Windows, copy the folder in Explorer. If you already have a copy, compare changes before
replacing it. Some hosts discover several skill directories. Install one copy per skill
in an active project to avoid ambiguous discovery.

Try `/orchestra-draw Use this approved brief and save state in design/rounds/usage-alert/STATE.md.`

## Customize the workflow

For CLI-managed installations, use `npx skills list` to see what's installed,
`npx skills check` to check for updates, and `npx skills remove orchestra-research` to remove one
stage. Review local edits before updating a modified skill.


- **Remove a stage:** remove its copied folder from your host's skill directory. Supply the next
  stage with the equivalent input from your own process. For example, use a research team's
  agreed brief with `orchestra-draw`.
- **Replace a stage:** edit your local copy or install a custom skill. Keep the agreed input and
  output fields that downstream stages use. Give custom skills unique names when both copies
  will be installed.
- **Add a stage:** create a sibling folder whose `SKILL.md` declares a matching `name` and a
  `description`. Document its inputs, outputs, and when to invoke it. Invoke it by name or use
  `/orchestra <skill-name>` from the optional menu. See [the accessibility review example](examples/custom-stage.md).
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
- [Add a custom accessibility review](examples/custom-stage.md) shows how to extend the workflow and invoke the new skill.
- [Contribute a skill](CONTRIBUTING.md) covers the directory layout, examples, and checks.
