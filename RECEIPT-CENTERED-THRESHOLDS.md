# Receipt-Centered Thresholds

The memo introduces threshold verbs as the operational vocabulary of the system. That framing is correct but second-order. The first-order claim is about receipts.

## The hierarchy

```text
1. Rooms produce events.
2. Public memory requires crossings.
3. Crossings require judgment.
4. Judgment must be recorded.
5. The receipt is the constitutional object.
6. Threshold verbs are the operational vocabulary.
7. Negative defaults prevent substrate gravity from eating the model.
```

Read top to bottom. Each line constrains the next.

A room produces events. That is what rooms do. Events are not public objects, posts, or artifacts — they are situated speech inside a context.

Public memory — the durable, circulable, citable kind — does not happen passively. It requires a crossing: an event becoming something else, in some other place, under some authority.

A crossing is not a technical operation. It is a judgment: should this happen, by whom, under what conditions, with what consequences for who else was in the room?

That judgment must be recorded. Not because logs are virtuous, but because invisible judgment is laundered judgment. If the system permits crossings without recording who authorized them and why, it has chosen to obscure governance, not to provide it.

The record of the judgment is the receipt. The receipt is the constitutional object — the thing communities will eventually argue over when legitimacy fractures, fork, drift, or compromise.

Threshold verbs (`quote_out`, `archive`, `bridge`, `mirror`, etc.) are the operational shape these crossings take. They matter. But they are the surface — the API of the system. The receipt is the substance.

Negative defaults exist because every substrate Rhizome touches will try to bypass this hierarchy. Matrix will want to replicate room state by default. ActivityPub will want to circulate objects by default. ATProto will want to expose records by default. Auth systems will want to flatten judgment to allow/deny. The hierarchy holds only if the daemon refuses these defaults at every adapter boundary.

---

## Why receipts come first

A receipt is not merely an audit log.

A receipt records a boundary crossing: who approved it, under which policy, from what source context, toward what destination, with what redactions or constraints. That makes it politically load-bearing in a way audit logs are not.

A community does not only remember what was said. It remembers how speech became public, who authorized the crossing, which policy was invoked, and whether the crossing remained legitimate after the fact.

Receipts make governance inspectable. That is the value. Without receipts, every quote, export, archive, or bridge can pretend to be natural circulation rather than a deliberate act under specific authority. With receipts, it cannot.

But receipts are not free. They are not just bookkeeping — they are objects of dispute. One room may accept a receipt as valid. Another may reject it. A forked community may treat prior receipts as evidence of illegitimate moderation. A source author may revoke consent. A destination may mirror an artifact whose originating room now considers the crossing void.

The receipt does not eliminate conflict. It gives the conflict a surface.

> The receipt is not evidence of governance. The receipt is where governance becomes legible.

---

## The admissibility / legitimacy split

The daemon answers one question:

> Is actor A authorized to perform crossing C on event E under policy P, given the standing graph and current context?

That is admissibility. A graph problem, in principle solvable.

The daemon does not answer:

> Is this a culturally sane crossing to make right now, given that the room is upset, the source author said this in a moment of weakness, the destination is hostile, and three other people are implicated?

That is legitimacy. It is not a graph problem and the system should not pretend it is.

Rhizome's design choice: do not automate legitimacy. Provide a chamber where legitimacy is made explicit.

> Rhizome does not decide whether a crossing is wise. It prevents a crossing from pretending it was merely technical.

Or, sharpened:

> The system cannot supply judgment. It can only refuse to launder judgment into plumbing.

This is the entire social-software failure model in one line. Every platform that conflated admissibility with legitimacy ended up either authoritarian (the system decides what is sane) or extractive (every check passes because nobody asked).

Rhizome is neither. It does the boring half — admissibility — well, and it makes the judgment half visible without claiming to perform it.

---

## What this reframes

If receipts are first, several things in the memo move:

- **Threshold verbs** become the API surface, not the model. The model is "crossing producing receipt." The verbs are how you ask for one.
- **Standing** is not just permission. It is the question of who is empowered to mint receipts that the room will later treat as legitimate.
- **Federation** is not about object propagation. It is about whether peer rooms accept each other's receipts.
- **Moderation** is not policy enforcement. It is the act of granting, revoking, or disputing receipts.
- **Privacy** is not encryption. It is constraint on what receipts can contain and who can read them.
- **Negative defaults** are not paranoia. They are the operational form of "do not mint receipts without authority."

Every load-bearing concept in Rhizome reduces to: *what receipt would this produce, who can read it, and under what conditions does it remain valid?*

---

## The keeper

> **Rhizome makes crossings legible. It does not make them innocent.**
