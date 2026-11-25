# Contributing

Keep each skill useful on its own. It should accept an agreed input from a person, a document,
or another workflow. Include a realistic example that shows the result or handoff.

Put each skill in `skills/<skill-name>/`. The folder name and `name` in `SKILL.md` must match.
Give the skill a description that explains when to use it. Store templates in `assets/` and
detailed guidance in `references/` within the skill, and link to them with relative paths. For
metadata limits, see the [Agent Skills specification](https://agentskills.io/specification).

For new first-party stages, use a `orchestra-<stage>` name and update the README catalog and
the optional `orchestra` menu. Users can invoke custom skills by their installed name or through
`/orchestra <skill-name>`.

Before opening a pull request, list the skills from your checkout and install the one you changed
in a disposable project. Replace the source path and agent as needed.

```sh
npx skills add /path/to/orchestra --list
npx skills add /path/to/orchestra --skill orchestra-draw --agent codex
```

Check that the installed references open. Try one documented invocation where the host permits
it, and describe the host, inputs, and observed result in the pull request. Include an example of
what happens when a needed capability is unavailable if your change alters that behavior.
