---
name: orchestra-init
description: Checks available skills and interviews a team about tools and project defaults. Use when initializing orchestra or updating the tracker, skills, plugins, connectors, MCP servers, or workflow settings.
---

# Initial Lines

Run on request. The result is a project-level Markdown profile that each Orchestra skill can use.

## Check the current setup

1. Find the project root and read its governing instructions and existing `DESIGN-WORKFLOW.md`.
   Reuse answers already established by the user or those files. If an existing workflow document
   covers the same settings, ask whether to use that document and record its path in the handoff.
2. Check the current host's skill list or discovery mechanism for skills available to this
   project, including user-level skills when shown. If the host exposes no list, inspect its
   documented project and user skill directories when accessible. Where the host provides a list
   of enabled plugins, connected services, or MCP servers, check those too. Use names and
   descriptions for discovery. A configured server or plugin does not establish that its tools
   are usable in this session. Treat an inaccessible inventory as unknown and ask the user what
   they have. Give a short summary of the relevant items found and any discovery gaps.

## Ask about the workflow

Ask one short question at a time about decisions that are still open. Skip confirmed choices and
let the user defer any field.

1. **Project tracking.** Ask what kind of tool the team uses to plan and track work and which
   one to use for this project. Accept issue trackers such as Linear or Jira, project boards
   such as Trello, GitHub Issues, a Markdown plan, another system, or no tracker. Ask for the
   relevant team, project, board, or repository, and the ticket conventions that matter.
   Ask whether the default is to draft plans or create tickets when authorized. Choosing a
   tracker and having a working connection are separate facts.
2. **Companion tools by stage.** Ask which skills, plugins, connectors, and MCP servers the
   user wants to use in Why, Research, Draw, Divide, and Conquer. Suggest relevant choices from
   discovery and the chosen tracker. Let the user add a tool that needs setup. Show one stage
   at a time, using a multi-select control if the host offers one. Otherwise show a Markdown
   checklist and accept replies such as “check Jira for Divide” or “uncheck Figma for Draw.”
   Let users choose no companion tools or defer the choice. Start new options unchecked until
   confirmed. When editing a stage, show its current selections. When a project rule requires
   a tool, identify that requirement in the choice.
3. **Product context.** Read the relevant product brief or project overview if available. Capture
   what the product does, who it serves, and the current user or company goal. Ask only for
   missing information that would change the design work, and let the user defer it. Link to the
   source when available. Ask before saving sensitive context in a shared project file.
4. **Design and delivery.** Ask where to find design guidelines, artifacts, and checkpoints.
   Ask who approves designs, what evidence they need, and what counts as ready to deliver.
   Ask about merge or release approval if the project instructions leave it open.

## Record stage selections

- Save each stage under its skill name in the profile. Use one checkbox per discussed tool,
  with its host-discoverable name, type, purpose, and availability. Use the qualified
  plugin skill name when the host exposes it. Note if a helper requires direct user
  invocation, and add a fallback when agreed. The same tool can be checked for one stage
  and unchecked for another.
- A checked tool is eligible for that stage, subject to availability, permissions, and project
  rules. Unchecked tools are skipped. A stage with a checklist uses only its checked optional
  companions unless the user approves an override for the current run.
- Use `None` if the user chooses no companion tools. Use `Unspecified` when they defer.
  For an existing profile without checklists, use the existing tool preferences as starting
  points and confirm selections before saving them. Preserve the choices for other stages when
  updating one stage.

## Save confirmed choices

1. Review the proposed settings with the user before saving. Use the
   [profile template](assets/DESIGN-WORKFLOW.md) and record deferred choices as `Unspecified`.
   Resolve any conflict with the project's governing instructions before saving the affected value.
2. Save confirmed settings in `DESIGN-WORKFLOW.md` at the project root or the agreed location.
   Preserve unrelated settings on update. When the host cannot write files, return ready-to-paste
   Markdown and its intended path.
3. Give the user the path and one example invocation. Setup records preferences. Ask for
   tracker identifiers or links and keep credentials in the host's supported connection settings.
   Installing tools, connecting accounts, and writing tickets require their own authorization.

## Examples

Enable Matt Pocock's documentation interview in Why and skip it in Research:

```markdown
### orchestra-why

- [x] mattpocock-skills:grill-with-docs (skill) — sharpen the problem and capture agreed terminology or decisions. Available. User invocation required.

### orchestra-research

- [ ] mattpocock-skills:grill-with-docs (skill) — skip the interview during research. Available.
```

With those settings, Why prompts the user to invoke the helper if the host requires it,
then uses the agreed findings. Research uses its own research steps.

The host lists a browser review skill and a Jira connector. For a team that drafts Jira
tickets in project `SHOP`, the user might choose:

```markdown
### orchestra-draw

- [x] Browser review (skill) — test the prototype. Available.
- [ ] Jira (connector) — read design tickets. Available.

### orchestra-divide

- [x] Jira (connector) — ground ticket drafts for SHOP. Available.
```

With those settings, Draw skips Jira and Divide can read it when permitted. If access is
unavailable, Divide can still return Jira-ready Markdown drafts. The user can edit the
profile or rerun init to change a selection.
