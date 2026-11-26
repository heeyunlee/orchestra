# The same feed request in two products

> /orchestra Let's build a social feed.

Orchestra starts with Why and checks the product context in the project's `ORCHESTRA-SCORE.md`,
existing product docs, and what the user has said. The same request can lead to different
briefs, depending on who uses the product and what they need.

| Product context | What Why should investigate | Possible success check |
| --- | --- | --- |
| A photo-sharing app wants people to keep up with the creators they follow. | Can a person open the app and find recent posts from people they follow? Should the first version focus on followed accounts or also help users discover new creators? | A person following several accounts can quickly find a recent post from one of them. |
| A workspace SaaS product wants admins to catch up on team changes. | Is “social feed” about user posts and discussion, an activity timeline, or both? Confirm the intended outcome before drawing. | If the team chooses an activity timeline, an admin can find who changed a workspace setting and when, using only events their role can view. |

These are example project goals. A SaaS team may genuinely want a social feed. If the context
is unclear, ask a question that distinguishes the outcomes:

> Should this feed help customers share and discuss posts, or help workspace admins catch up on changes?

Once the user agrees on the outcome, carry it into the research brief, design review, and
implementation checks.
