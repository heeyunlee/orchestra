---
name: design-divide
description: Turns an approved design into implementation slices, dependencies, and QA checks. Use when engineering needs a delivery plan tied to the exact approved revision.
---

# Plan the engineering work

## Input

Bring an approved revision, its handover and coverage, and the relevant code or architecture. Confirm the approved revision before cutting work.

## Instructions

1. Locate affected entry points, shared components, data contracts, flags, and existing tests. Note where existing behavior or older data needs support. Use project architecture and delivery conventions.
2. Split the work into the smallest independently verifiable slices. Give each slice an outcome, scope, out-of-scope boundary, dependencies, and acceptance checks. Map every required state to an owner.
3. Identify technical dependencies and the design states that can be delivered together. Order the dependency chain, looking for cycles, and mark parallel work that touches separate ownership boundaries.
4. Define verification with test data, environment, devices or viewports, expected outcomes, and any deployment dependency. Include the end-to-end check that confirms the assembled feature.
5. Create or update tickets when authorized and a tracker is available. Otherwise return the same plan as Markdown. Record the parent outcome and when it is ready to ship.

## Output

Provide the **approved revision**, **slices and owners**, **dependencies**, **acceptance and QA checks**, **combined verification**, and **delivery constraints**.

## Example

Slice A exposes the existing usage data and near-limit threshold. Slice B renders the approved warning and depends on A. Slice C checks role permissions and the settings destination and depends on B. The plan names the seed accounts and the near-limit, over-limit, and non-admin outcomes.
