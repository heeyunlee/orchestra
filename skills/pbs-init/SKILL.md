---
name: pbs-init
description: Checks available skills and interviews a team about tools and project defaults. Use when initializing product-builder-skills or updating the tracker, skills, plugins, connectors, MCP servers, or workflow settings.
---

# Initial Lines

Run on request. The result is a project-level Markdown profile that each PBS skill can use.

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

1. **Companion tools.** Ask which existing or additional skills, plugins, connectors, and MCP
   servers the user wants to use alongside PBS. Suggest relevant options from the inventory
   when they fit the project. If a capability is missing, describe what would help, such
   as a browser review skill or a connector for the chosen tracker. Ask which stage or task
   each chosen tool should support. For each choice, record its name, type, purpose, and whether it is available now, needs setup,
   or has unknown availability. Record chosen tools rather than the full inventory. Ask what
   to use when a tool is unavailable if that would affect the workflow.
2. **Project tracking.** Ask what kind of tool the team uses to plan and track work and which
   one to use for this project. Accept issue trackers such as Linear or Jira, project boards
   such as Trello, GitHub Issues, a Markdown plan, another system, or no tracker. Ask for the
   relevant team, project, board, or repository, and the ticket conventions that matter.
   Ask whether the default is to draft plans or create tickets when authorized. Choosing a
   tracker and having a working connection are separate facts.
3. **Design and delivery.** Ask where to find design guidelines, artifacts, and checkpoints.
   Ask who approves designs, what evidence they need, and what counts as ready to deliver.
   Ask about merge or release approval if the project instructions leave it open.

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

## Example

The host lists a browser review skill and a Jira connector. The team chooses the browser skill
for `/pbs-draw`, wants to add a design MCP server later, and tracks work in Jira project `SHOP`.
Record the browser skill as available, the design MCP server as needing setup, and Jira with
the confirmed access status and a draft-first preference. If Jira access is unavailable,
`/pbs-divide` can still return Jira-ready Markdown drafts for `SHOP`.
