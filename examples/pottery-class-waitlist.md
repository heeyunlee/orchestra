# From one line to deployment

In a project with an existing class booking flow, install `orchestra` and the five stage
skills. Then send this in your agent:

> /orchestra Let's build and deploy a waitlist that gives the next person 15 minutes to claim a canceled pottery class seat.

If the host has no slash commands, select the `orchestra` skill and send the same sentence
without the command. This is a fictional example of the decisions and evidence each stage
might produce.

| Stage | What happens | What goes forward |
| --- | --- | --- |
| **Why** | The studio messages waitlisted guests by hand. Replies overlap and an available seat can go unclaimed. The agreed goal is to offer a seat in waitlist order and ensure only one person can book it. | An agreed problem and two checks. A canceled seat is offered to the next guest, and two claim attempts cannot book it twice. |
| **Research** | Compare notifying the whole waitlist with sending one offer at a time. The studio chooses one 15-minute offer at a time and agrees what happens when an offer expires. | A brief covering join, offer, claim, expiration, and the next offer. |
| **Draw** | Prototype the guest flow and staff view. A reviewer exercises the expired-link screen and checks that it explains what happens next. The studio owner approves the revised design. | The exact approved prototype revision, state coverage, and review evidence. |
| **Divide** | Plan the offer and claim rules first, then add notifications and guest screens. Put the combined checkout after both are available. | An ordered plan with a seeded class, two waitlisted guests, a time-controlled expiration check, and a duplicate-claim check. |
| **Conquer** | Implement and review the slices, then verify the combined flow in staging. After release approval, deploy to the agreed production scope and run the post-deploy smoke check. | The deployed revision, rollout scope, and observed smoke result. |

A possible staging checkpoint:

> Staging verified that the first guest received an offer, an expired link could no longer
> claim the seat, and the second guest could book exactly once. Release approval is next.

A possible completion message after the approved rollout:

> Deployed revision `r42` to the pilot studio. On the production test class, the canceled
> seat was offered to the next guest and could be claimed only once. The pilot is live.

If approval or evidence is still pending, Conquer reports the last verified checkpoint and
the next action. The same request can resume from that checkpoint.
