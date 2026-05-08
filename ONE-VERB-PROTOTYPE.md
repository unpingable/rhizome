# One-Verb Prototype

If Rhizome is ever built, it should not be built as Rhizome. It should be built as a single boundary crossing between two existing systems, with a receipt in the middle.

Everything else is decorative until that primitive holds.

## Scope

One verb: `quote_out`.

One source: a single Matrix room.

One destination: a single static artifact site (e.g. a directory of HTML pages with stable URLs, generated from artifact records).

One actor type: any room member with a default-deny policy and explicit per-message author opt-in.

One receipt format: a signed JSON object linked from the artifact page.

That is the entire prototype. If it does not feel right at this scale, no amount of additional substrate will save it.

---

## In scope

- Subscribing to events in one Matrix room
- Capturing a `quote_out` request (a structured message or out-of-band UI)
- Evaluating policy: room default + author per-message override
- Approval act: either author auto-approves at message time, or a moderator approves at request time
- Minting an artifact: a static page with the quoted text and minimal context
- Minting a receipt: signed JSON with source room ID, source event commitment (hash), approving authority, applicable policy, destination URL, timestamp, redaction status
- Linking the receipt from the artifact page so anyone reading the artifact can inspect the crossing
- A way to revoke the artifact (mark withdrawn) and append a revocation receipt

## Explicitly out of scope

- Federation. No ActivityPub. No ATProto. No multi-server anything.
- Bridges. No cross-protocol relays.
- Standing graph. No SpiceDB / Cedar / OPA. Hand-rolled allow/deny is fine.
- MLS. The Matrix room can be E2EE if Matrix handles it, but Rhizome adds no crypto.
- Cross-room trust. There is one room.
- Consent semantics beyond yes/no with optional redaction. No "may_summarize / may_archive_in_room / expires_after" matrix yet.
- Temporal governance. No policy versioning, grandfathering, decay.
- Abuse model. The prototype assumes a non-adversarial pilot room.
- Identity portability. The actor is a Matrix user; that is enough.
- Search containment. The artifact site is statically generated; whatever Google does to it is whatever Google does to it. The prototype does not try to control public-side indexing.
- UX legibility for the room itself. The Matrix client shows what Matrix shows. Rhizome's UI is the receipt and the artifact page, not the room.

The point of declaring these out of scope is not that they don't matter. It is that putting any of them in scope means the prototype no longer answers its question.

---

## The data flow

```text
Matrix room
    |
    | room member sends message: "I'd like to quote-out msg 0xABC, public artifact"
    |
    v
rhizomed (the daemon)
    |
    | check: did the author of msg 0xABC opt in to quote_out?
    | check: does the room default permit this destination?
    | check: who is the approving authority? (author, moderator, both?)
    |
    | if approved:
    |   compute commitment to source event (hash + room id)
    |   render artifact page from quoted text
    |   sign receipt: {source, commitment, authority, policy, dest, ts, redactions}
    |   publish artifact + receipt link
    |
    | if denied:
    |   mint a denial receipt (room-local only)
    |   notify requester
    v
artifact site
    /artifacts/0xABC.html  -> the public artifact
    /artifacts/0xABC.json  -> the signed receipt
```

That is the whole architecture. Two endpoints, one signing key, one policy file per room.

---

## What this teaches

- **The shape of a receipt.** What goes in. What is hashable. What is redactable. What is signable. What it feels like to read one. This is the constitutional object — getting its anatomy wrong early means getting governance wrong later.
- **Provenance without leakage, in miniature.** A commitment to a source event without exposing the event itself. The crypto is simple at this scale; the design choices are not.
- **The legibility-of-crossing UX.** What does it feel like to request a crossing? To approve one? To read an artifact and click through to its receipt? Does it feel like a deliberate act or like filing paperwork?
- **The minimum policy surface.** What is the smallest policy expression that captures author consent + room default + redaction? Anything more elaborate is premature.
- **Where the substrate's gravity actually hits.** Matrix will want to do things. The prototype reveals which of those things matter and which are background noise.

## What this does not teach

- Federation semantics. (Phase 5.)
- Multi-room trust and bridge contracts. (Phases 4–5.)
- Adversarial behavior under consent machinery. (Requires a real pilot in a real subculture.)
- Identity portability and standing graph design. (Phase 4.)
- Search containment as a public-side concern. (Genuinely hard, deferred.)
- Whether the model survives its first community fork. (Years out, if ever.)

The prototype is honest about being narrow. Subsequent phases extend the same primitive — they do not redesign it.

---

## Suggested phasing (if any of this ever gets built)

```text
Phase 1  one verb (quote_out), one room, one static artifact site, signed receipts
Phase 2  receipts as queryable, linkable, disputable objects (revocation, dispute)
Phase 3  second verb (archive) — forces event-vs-artifact distinction to become real
Phase 4  standing layer + portable identity (still single-server)
Phase 5  federation: ATProto first (record-shaped), ActivityPub second
Phase 6  bridges (with explicit bridge contracts and receipt translation)
Phase 7  consent semantics expansion, temporal governance, abuse model
```

Each phase should be capable of running indefinitely. There is no commitment to ever advance. If Phase 1 produces a useful tool that some weird small room adopts and never grows beyond, that is not a failure. That is what the system is for.

---

## The single test

The prototype works if, when looking at a public artifact and its receipt, a stranger can tell:

1. That this artifact came from a specific room context.
2. That a specific authority approved its crossing under a specific policy.
3. That the room itself remains opaque to them.
4. That the crossing was a deliberate act, not a passive leak.

If any of those four are unclear, the primitive is wrong and the prototype has done its job by surfacing that.
