# Gaps

The real invention is not the protocol substrate. It is the anti-collapse model:

```text
event ≠ post ≠ artifact ≠ receipt
```

Each gap below is a place where existing systems either collapse those four into each other, or leave the boundary unspecified and let substrate gravity decide. The gaps are not a TODO list. They are the surface on which the model would have to hold up if anyone ever built it.

---

## Gap 1 — Provenance without leakage

A public artifact must be able to say "this came from a specific room event under a specific policy" without the proof becoming a tracking vector or a way to reconstruct the original event.

Candidates: content hashes, redacted references, room-local IDs, signed export receipts, source proofs. Each has tradeoffs in linkability and revealing information.

**Hard problem:** prove enough to make boundary crossings accountable without making private speech reconstructible.

---

## Gap 2 — Consent semantics

Author consent is a vector, not a boolean. A message may quote another person; a joke may rely on context; a thread may be exportable as a summary but not as raw quotes.

Possible shapes:

```text
may_quote_verbatim
may_quote_with_redaction
may_summarize
may_archive_in_room
may_publish_publicly
may_federate
may_index
expires_after
requires_review
```

**Hard problem:** keep this usable. Nobody wants to configure a Geneva Convention dropdown every time they say "lol."

---

## Gap 3 — Local standing

Identity can be portable. Authority must remain local.

The standing model has to answer:

```text
Who may approve export?
Who may archive?
Who may bridge?
Who may invite?
Who may override?
Who may revoke?
```

Existing authorization systems (SpiceDB, Cedar, OPA) can answer "may principal P perform action A on resource R." They do not natively encode social consent, source-context sensitivity, author expectation, destination risk, or "don't turn this room into evidence."

**Hard problem:** avoid both admin feudalism and process sludge.

---

## Gap 4 — Federation trust between rooms

Federating posts is easier than federating habitat boundaries. Rooms need to express:

```text
Room A trusts Room B to mirror artifacts.
Room A does not allow Room C to bridge live events.
Room A accepts moderation labels from Server D.
Room A rejects search indexing by Service E.
```

**Hard problem:** trust is not just server-level. It is room-level, action-level and sometimes artifact-level.

---

## Gap 5 — Search containment

Search changes the social meaning of speech by changing its future audience. A room may want to be searchable internally without being searchable globally; an artifact may want to be searchable publicly without exposing the room that produced it.

Possible policy shapes:

```text
searchable_in_room
searchable_by_members
searchable_by_adjacent_rooms
searchable_publicly
searchable_after_archive_only
not_searchable
```

**Hard problem:** public objects are hard to un-index once federated. "Forget" becomes policy theater unless the system is honest about the limits.

---

## Gap 6 — Bridge contracts

Bridges are boundary wounds. A bridge to Matrix, Discord, IRC, ActivityPub or ATProto can silently destroy Rhizome's semantics if it exports too much or imports context-free objects.

Every bridge needs a contract:

```text
what object types cross?
what metadata crosses?
what policy survives?
what receipts are minted?
what cannot cross?
what happens on revocation?
```

**Hard problem:** bridge culture defaults to "messages go over there." Rhizome needs the opposite default and the language to enforce it.

---

## Gap 7 — Private receipts

If a room is private but export requires accountability, what does the receipt contain?

Too little and the receipt is decorative. Too much and the receipt leaks the room.

Receipts likely need scoped visibility — some public, some room-local, some moderator-only, some hashed commitments.

**Hard problem:** accountability without surveillance. Both directions of failure are real.

---

## Gap 8 — UX for semi-permeability

The UI must make boundary state obvious — this room is private, this message may not be quoted, this artifact is public, this bridge is active — without becoming a cockpit.

**Hard problem:** make thresholds visible without making users feel like they are filing export paperwork for a shitpost. This is the adoption killer.

---

## Gap 9 — Temporal governance

Policies change. Members leave. Rooms split. Bridges become hostile. Artifacts outlive their consent assumptions.

```text
revocation
expiration
grandfathering
artifact withdrawal
policy versioning
standing decay
bridge suspension
```

**Hard problem:** past public artifacts cannot always be clawed back. The system needs honest degradation, not fake delete buttons.

---

## Gap 10 — Abuse model

Bad actors will use boundary language too. They will:

- create rooms that look private but are extractive
- launder screenshots as "artifacts"
- use consent machinery to harass
- create bridge traps
- weaponize searchability
- demand "federation neutrality" when blocked

**Hard problem:** Rhizome cannot be only a cozy architecture. It needs adversarial assumptions from the start.

---

## Gap 11 — Receipt validity under disagreement

Receipts record boundary crossings. They do not automatically settle whether a crossing remains legitimate.

A receipt may be:

- valid when minted
- valid but disputed
- invalidated by policy error
- revoked by later authority
- superseded by room fork
- accepted by one federation peer but rejected by another
- still pointing at a public artifact whose source community no longer endorses it

**Hard problem:** avoid turning every receipt into a miniature court case while still making legitimacy disputes visible.

---

## How the gaps relate

The gaps are not independent. Several share an underlying tension:

- **Provenance / private receipts / search containment** all turn on "how much can be exposed about a crossing without exposing the room." They are versions of the same cryptographic and policy question at different timescales.
- **Consent semantics / temporal governance / receipt validity** all turn on "what happens when authority changes after a crossing was approved." Receipts make this surface rather than hide it.
- **Standing / federation trust / bridge contracts** all turn on "what scope does authority have, and across which boundaries does it transfer." None of these reduce to single-server identity systems.
- **UX / abuse model** are the two places where the technical model contacts reality. If the technical layer is right but the UX or adversarial models are wrong, the system fails in deployment regardless of how clean the receipts are.

---

## Condensed ledger

1. **Provenance without leakage** — proving where an artifact came from without exposing the room.
2. **Consent semantics** — quote / export / archive / summarize are different acts.
3. **Local standing** — portable identity cannot become universal authority.
4. **Room-to-room trust** — federation policy needs action-level granularity.
5. **Search containment** — discovery without global indexing of interiors.
6. **Bridge contracts** — every bridge is a possible leak.
7. **Private receipts** — accountability without surveillance.
8. **Usable UX** — visible thresholds without bureaucratic sludge.
9. **Temporal governance** — policy drift, revocation, expiration, artifact afterlife.
10. **Abuse model** — boundary language will be weaponized if naïve.
11. **Receipt validity under disagreement** — legitimacy disputes need a surface, not a court.
