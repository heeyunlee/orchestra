---
name: initial-lines
description: Interviews a team and saves project defaults for the design workflow. Use when asked to initialize product-builder-skills or update their tracker, design, review, or delivery settings.
---

# Initial Lines

Run on request. The result is a project-level Markdown file that any of the design skills can use independently.

1. Find the project root and read its governing instructions. Read `DESIGN-WORKFLOW.md` there if it exists. Reuse answers already established by the user or those files. If the project already has a workflow document, offer to use that document when it covers the same settings. Record the chosen path in the handoff so later stages can find it.
2. Ask one short question at a time about choices that are still open. Skip questions that the user already answered. Let the user defer any field.
   - **Work tracking:** “Where should implementation work be planned and tracked?” Accept Linear, Jira, another tracker, or Markdown. For a tracker, ask for the team, project or board, and ticket conventions that matter. Ask whether the default is to draft plans or create tickets when the user has authorized tracker writes.
   - **Design:** Ask where to find the design system and where the team keeps design artifacts and round checkpoints. Ask who approves designs and what evidence they need.
   - **Delivery:** Ask what counts as ready and where to verify it. Ask about merge or release approval if the project instructions leave it open.
3. Review the proposed settings with the user before saving. Use the [profile template](assets/DESIGN-WORKFLOW.md). Record deferred choices as `Unspecified`. If a value conflicts with governing project instructions, surface the conflict and resolve it before saving that value.
4. Save confirmed settings in `DESIGN-WORKFLOW.md` at the project root or in the agreed location. When updating a profile, preserve unrelated settings and apply only confirmed changes. If you cannot write files, return ready-to-paste Markdown and its intended path.
5. Give the user the path and one example invocation. This setup records preferences. Get the authorization required by the host and project before connecting accounts, writing tickets, or changing project tooling. Request tracker identifiers or links only. Keep credentials in the host's supported connection settings.

## Example

A team uses Jira project `SHOP`, drafts tickets for review, approves designs through the product lead, and considers a slice ready after staging QA. Save those choices. Later, `design-divide` reads the profile and produces Jira-ready drafts for `SHOP`. The user can authorize ticket creation separately. A team using Markdown can choose a local plan and use the same skills without a tracker connection.
