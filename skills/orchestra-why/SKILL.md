---
name: orchestra-why
description: Defines a product design problem and how to measure improvement. Use when a feature or redesign has been proposed and the affected users, evidence, or success criteria need agreement.
---

# Understand the problem

## Input

Bring the request or symptom, any observations, and access to the people or material that can answer open questions. Honor the project's working and privacy rules.

## Instructions

Read `DESIGN-WORKFLOW.md` from the project root or the profile the user points to, if available.
Apply the relevant settings within the project's governing instructions.
In the `orchestra-why` tool checklist, use checked optional companions when relevant,
available, and authorized. Skip unchecked and unlisted optional companions unless the user
approves an override for this run. Treat `None` as no optional companions. If the checklist
is absent or `Unspecified`, follow the project's existing tool preferences. If a checked
tool is unavailable, use its agreed fallback if the stage permits it, or report the gap.
Resolve helpers by the name recorded in the profile, using the qualified name when provided.
If a checked helper requires direct user invocation, ask the user to run it and continue from
its output when supplied. Apply the same fallback rule if the user chooses to skip it.

1. Inspect available product evidence. Separate what was observed, what someone reported, and what you infer. Record the affected user, task, and current behavior.
2. Write the problem as an observable user failure. Note the impact and whether its size or frequency is known. Put proposed solutions in a separate list of hypotheses.
3. Identify constraints and boundaries. Use a short question for each ambiguity that could change the problem or success criteria. Explain the decision each answer affects.
4. Define observable outcomes, a way to check them, and a baseline when available. Mark unknown baselines and name the evidence needed to establish them.
5. Ask the owner to confirm the problem and criteria. Save or return the agreed record. If agreement or evidence is still pending, identify the open item and who can resolve it.

## Output

Record the **problem**, **affected users and task**, **evidence and unknowns**, **success criteria and checks**, **constraints and exclusions**, and **agreement status**. This record can feed any research process.

## Example

A usage warning tells workspace admins they are near the limit, but support reports that some admins open the wrong settings page. The agreed problem is difficulty finding the available action. Check the revised flow by asking admins to find the current usage and reach the correct settings without a hint. Record the observed results and sample size before making a broader claim.
