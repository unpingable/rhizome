# Rhizome: Notes Toward Federated Social Habitats

## 0. Thesis

Modern social software is good at two things: making speech public and making rooms vanish.

Feeds circulate. Chats breathe. Forums remember. Discord shelters. Mastodon federates. None of them quite solve the thing subcultures actually need: **a semi-permeable membrane between interior life and public consequence**.

Rhizome is a proposal for that missing layer.

Not a better feed.
Not decentralized Discord.
Not Mastodon with channels.
Not a forum with typing indicators, God help us.

Rhizome is a model for **federated social habitats**: rooms that can remember without leaking, publish without collapsing and federate without becoming extractive surfaces.

The core primitive is not the post, the feed or the room.

The core primitive is the **threshold**.

> A social system is defined less by what it lets people say than by what it lets people carry across boundaries.

That is the whole thing in miniature.

**Gap note:** The term "threshold" is doing a lot of work. It needs to become a concrete object model: who can enter, quote, export, mirror, archive, bridge, search, federate and forget.

---

## 1. The platform ate the room

The older internet was not better because it was morally superior or technically purer. It was better at one narrow thing: it allowed social interiors to exist without immediately converting them into global performance surfaces.

A forum had memory.
An IRC channel had presence.
A mailing list had continuity.
A weird personal site had context.
A webring had adjacency.

None of these were perfect. Most were ugly. Many were run by emotionally complicated men with shell accounts and opinions about indentation. But they had one virtue: they did not assume every utterance wanted to become content.

The feed changed the default.

A feed treats speech as an object.
A room treats speech as an event.
A platform treats both as inventory.

Once speech becomes inventory, every boundary becomes a distribution opportunity. Search, quote, rank, recommend, embed, screenshot, train, summarize, trend. The platform does not destroy the room by banning it. It destroys the room by making every doorway a camera.

This is the central failure: **context collapse as infrastructure**.

**Complication:** This is not just capitalism bad / platforms bad. Users also want circulation, discovery and public consequence. The hard part is preserving room-life without turning it into a bunker or a content mine.

---

## 2. The existing forms all fail differently

No current form is simply wrong. Each one preserves something real.

Forums remember, but often do not breathe.
Feeds circulate, but collapse context.
Group chats feel alive, but disappear into private fog.
Discord preserves refuge, but kills the archive.
Mastodon federates public identity, but mostly federates streets, not interiors.
Matrix federates rooms, but has a strong gravity toward replicated room history and state. Matrix rooms distribute events across servers and clients, with power levels defining what actions users can perform inside a room.
XMPP MUC has a mature room/channel model with invitations, kicks, bans, moderators, admins, membership and passwords.

That last part matters. The pieces are not missing because nobody ever invented rooms. The pieces are missing because the system boundary is wrong.

The question is not "can people chat?"

Obviously they can chat. We have achieved chatting. Civilization may never recover.

The question is:

> Can a room produce durable public artifacts without becoming a public feed?

That is the missing shape.

**Gap note:** The closest existing systems solve either "room," "archive," "identity" or "federation." They rarely preserve the distinction between ambient interior speech and deliberately exported public artifacts.

---

## 3. The missing primitive is the threshold

A room is not a feed with fewer people.

A feed assumes publication by default.
A room assumes situated presence by default.
An archive assumes durability by default.
A habitat needs all three, but not at the same time and not under the same rules.

Rhizome treats thresholds as first-class.

A threshold is where speech changes state:

* from interior to public
* from event to object
* from chatter to artifact
* from local context to federated circulation
* from temporary memory to durable record
* from room standing to outside consequence

The key verbs are:

```text
enter
invite
read
reply
quote
export
archive
mirror
bridge
search
forget
ban
federate
defederate
```

These verbs are not UI actions. They are admissibility transitions.

A person saying something in a room is one act.
Someone quoting that statement outside the room is another.
A room archiving that discussion as a guide is another.
A bridge publishing it to a public feed is another.
A search index making it discoverable forever is another.

Modern systems collapse these acts because collapse is convenient. Rhizome refuses the convenience.

> Memory should be made, not leaked.

**Complication:** The threshold model will feel "frictional" by design. That is both the point and the adoption problem. People like safety until the safety makes them click twice.

---

## 4. Memory should be elected

The archive problem is not solved by amnesia.

Pure ephemerality is a luxury ideology for people whose culture has already been indexed somewhere else. If nothing persists, a community loses institutional memory, onboarding, lore, recipes, arguments, decisions and the little sedimentary layers that make a place feel like a place.

But automatic permanence is not memory. It is exhaust.

A healthy habitat needs **durability by election**.

Some things should become durable:

* announcements
* guides
* FAQs
* curated discussions
* event notes
* music lists
* public statements
* moderation decisions
* canon disputes, regrettably
* useful artifacts from otherwise messy conversations

But ambient room chatter should not automatically become historical evidence.

A chat message is an event.
A post is a public object.
An artifact is an elected durable object.
A receipt records the boundary crossing.

Those four should not collapse into each other.

```text
event      = situated speech inside a room
post       = intentionally public social object
artifact   = durable object promoted from room context
receipt    = record of why/how a boundary was crossed
```

> Archive should be a verb, not exhaust.

**Gap note:** Existing systems rarely encode "artifact minted from event" as a separate social/legal/technical state. Forums lean toward artifact-by-default. Chat leans toward event-by-default. Rhizome needs both without laundering one into the other.

---

## 5. Federation as membrane, not firehose

Federation is usually discussed as if the problem were reach.

Who can follow whom?
Which instance sees which post?
Which relay carries which object?

That matters, but it is not enough.

For social habitats, federation should mean **negotiated membrane behavior**:

* what public objects are visible outside the room
* which rooms can bridge to which other rooms
* which artifacts can be mirrored
* which identities are recognized
* which moderation signals are honored
* which search indexes are permitted
* what happens when trust changes

ActivityPub is useful here because it defines decentralized social networking with client-to-server and server-to-server delivery of content and notifications. ATProto is also useful because Lexicon lets applications define their own schemas for records, RPC methods and event-stream messages, which makes app-specific social objects plausible.

But neither substrate should define the social physics by itself.

ActivityPub is content-forward. ATProto is record-forward. Matrix is room-state-forward. XMPP MUC is room-control-forward.

Rhizome's job is to sit above those substrates and say:

> This may cross.
> This may not.
> This may cross only as an artifact.
> This may cross only with redaction.
> This may be referenced but not quoted.
> This may be mirrored by room X but not indexed globally.

Federation is not the feed getting larger.

Federation is the membrane becoming legible.

**Complication:** Protocol culture tends to treat "can be represented" as "should be circulated." Rhizome has to be aggressively boring about refusal.

---

## 6. Identity travels; standing remains local

Portable identity is good. Universal reputation is poison.

A person should be able to carry an identity across habitats. They should not carry one global social credit score, one universal trust rating, or one giant context-free aura of "good user" / "bad user."

Identity can travel. Standing should remain local.

A user may be:

* trusted in one room
* unknown in another
* banned from a third
* allowed to read but not export
* allowed to post but not invite
* allowed to archive but not bridge
* allowed to moderate one artifact class but not another

This is where existing authorization machinery becomes useful but also dangerous. SpiceDB is built for relationship-based permission systems where schemas and relationships combine to compute access decisions. Cedar's authorization model asks whether a principal can take an action on a resource in a context, which maps cleanly onto threshold verbs.

That shape is useful.

But permissions are not legitimacy. A graph can tell you whether Alice has `can_export`. It cannot tell you whether exporting the thing is culturally sane, normatively legitimate or a good idea at 2:13 a.m. while everyone is mad.

So Rhizome needs two layers:

```text
standing layer:
  who has what local authority?

policy layer:
  under what contextual conditions may that authority be used?
```

And probably a third:

```text
receipt layer:
  what was decided, by whom, under which policy, with what consequence?
```

**Gap note:** Existing auth systems can answer "may principal perform action on resource?" They do not natively encode social consent, source-context sensitivity, author expectation, destination risk, bridge trust or "don't turn this room into evidence." That is Rhizome's job.

---

## 7. Receipts are constitutional objects

A receipt is not merely an audit log.

In Rhizome, a receipt records a boundary crossing: who approved it, under which policy, from what source context, toward what destination, with what redactions or constraints.

That makes receipts politically load-bearing.

A community does not only remember what was said. It remembers how speech became public, who authorized the crossing, which policy was invoked and whether the crossing remained legitimate after the fact.

This is where governance becomes inspectable.

That is useful because it makes quiet laundering harder. A quote, export, archive or bridge cannot pretend to be natural circulation. It has a recorded crossing.

But it is dangerous because receipts themselves become objects of dispute.

One room may accept a receipt as valid.
Another may reject it.
A forked community may treat prior receipts as evidence of illegitimate moderation.
A source author may revoke consent.
A destination room may mirror an artifact whose originating room now considers the crossing void.

The receipt does not eliminate conflict. It gives the conflict a surface.

That is better than invisible governance, but it is not cheaper.

> The receipt is not evidence of governance. The receipt is where governance becomes legible.

> Rhizome does not decide whether a crossing is wise. It prevents a crossing from pretending it was merely technical.

The system cannot supply judgment. It can only refuse to launder judgment into plumbing.

---

## 8. The component strategy

Rhizome should not implement chat. That way lies madness, Electron and someone asking when screen share ships.

Rhizome should not implement federation from scratch unless forced. That way lies standards meetings, which are just Discord drama with RFC numbers.

Rhizome should be a threshold/orchestration layer.

A plausible component map:

```text
Live room substrate:
  Matrix or XMPP MUC

Public edge / portable records:
  ATProto Lexicons

Public federation:
  ActivityPub adapter

Boundary inspiration:
  Bonfire Boundaries

Authorization substrate:
  SpiceDB, Cedar or OPA-like policy engine

Private group crypto:
  MLS / OpenMLS, later

Durable artifact surface:
  static archive, forum, Discourse-like surface or custom artifact view

Rhizome native core:
  threshold verbs
  boundary evaluation
  artifact minting
  export receipts
  local standing
  bridge policy
  search/forget rules
```

Bonfire is especially worth studying because its Boundaries model already defines who can do what with posts or activities using users/circles and permissions. Bonfire's own writing also emphasizes that boundaries go beyond simple "who can see this" controls and include verbs for meaningful interaction and collaboration.

That is close to the Rhizome primitive.

But Rhizome generalizes the boundary from posts to transitions:

```text
can_enter
can_invite
can_read
can_reply
can_quote_out
can_export
can_archive
can_bridge
can_search
can_mirror
can_forget
can_moderate
can_federate
```

The native invention is not "permissions." The native invention is **boundary-preserving social object separation**.

```text
room event ≠ public post ≠ durable artifact ≠ receipt
```

That is the anti-collapse layer.

**Complication:** Component reuse will constantly tempt the system toward the defaults of the reused component. Matrix will want room history. ActivityPub will want public objects. ATProto will want record visibility. Auth systems will want binary allow/deny. Rhizome has to treat every adapter as suspect.

---

## 9. Negative defaults

Rhizome's value is mostly in what it makes annoying.

Things Rhizome should make annoying:

* global search across room interiors
* automatic transcripts
* bridge-by-default
* quote-posting from semi-private rooms
* "public unless configured otherwise"
* universal reputation
* room discovery by engagement ranking
* exporting someone else's speech as a default action
* treating membership as authority
* treating identity as standing
* treating encryption as governance
* treating archive as exhaust
* treating federation as entitlement

This is the line:

> Rhizome should optimize for explicit crossings, not frictionless leakage.

A good habitat needs walls. Not absolute walls. Not permanent walls. Not paranoid bunker walls. **Walls that sometimes open.**

That is what "semi-permeable" means.

**Gap note:** The UX problem is brutal. "Make bad things hard" often feels like "make normal things irritating" until the user understands the threat model. Rhizome needs affordances that make threshold state obvious without turning every action into a consent-policy tax form.

---

## 10. Search is a boundary crossing

Search deserves its own section because search is where social interiors go to die politely.

Search feels neutral. It is not. Search changes the social meaning of speech by changing its future audience.

A room can be searchable internally without being searchable globally.
An artifact can be searchable publicly without exposing the room that produced it.
A public room profile can be discoverable without indexing every conversation inside it.
A room can expose tags, descriptions and adjacency without exposing its bloodstream.

Discovery should follow paths, not spotlights.

Good discovery:

* public room profiles
* explicit room-to-room bridges
* member-curated indexes
* opt-in directories
* webring-like adjacency
* artifact trails
* event announcements

Bad discovery:

* global full-text search over interiors
* trending rooms
* engagement-ranked communities
* "people like you joined…"
* algorithmic recommendation into sensitive rooms
* search results that surface semi-private context as public object

**Complication:** Discovery is where growth pressure will attack the system first. If Rhizome ever became real, someone would immediately ask for trending rooms. That person should be given a decorative title and no database access.

---

## 11. Moderation is architecture

Moderation is not a policy page. It is a topology.

For Rhizome, moderation exists at several layers:

```text
user layer:
  mutes, blocks, personal filters

room layer:
  local norms, roles, bans, topic boundaries

artifact layer:
  what may be published, redacted, corrected, withdrawn

bridge layer:
  which rooms/servers may exchange objects

federation layer:
  which external actors/instances are recognized

index layer:
  what may be searched or discovered
```

Local moderation governs behavior inside the habitat.

Federation moderation governs what crosses the membrane.

Artifact moderation governs what persists.

Bridge moderation governs adjacency.

Search moderation governs future recoverability.

These cannot be one switch.

A room should be able to say:

```text
Outsiders may view public artifacts.
Outsiders may not search room history.
Room B may mirror event announcements.
Room C may not bridge into us.
Members may quote public artifacts.
Members may not quote ambient chat.
Moderators may archive discussions after author review.
```

That sounds fussy because reality is fussy. The alternative is pretending "public/private" is enough, which is how we got half the current garbage fire.

**Gap note:** Existing moderation systems tend to attach to content, accounts or instances. Rhizome needs moderation over **transitions**.

---

## 12. Private does not mean governed

Encryption is useful. It is not a social model.

MLS is relevant because it provides asynchronous group keying with forward secrecy and post-compromise security. That matters for real private rooms, especially if Rhizome ever wants to avoid "trust the server because vibes."

But encryption only protects transport and storage boundaries. It does not answer:

* who may quote?
* who may summarize?
* who may archive?
* who may bridge?
* who may invite?
* who may export?
* what happens when someone leaves?
* what happens when an artifact was made under old consent?

Private rooms still need governance.

Otherwise Rhizome becomes encrypted Discord with more self-satisfaction, and nobody needs that.

**Complication:** Strong privacy and durable receipts can pull against each other. A system may need receipts about boundary crossings without preserving the source content itself. That gets tricky fast.

---

## 13. A small walkthrough

Imagine a room called **/breakcore-garden**, because of course it is.

It is a semi-private electronic music habitat. Members chat, share tracks, hold listening nights, argue about snares and occasionally produce something useful by accident.

Inside the room:

* live chat
* voice/listening parties
* draft playlists
* half-formed arguments
* jokes
* local moderation
* temporary polls
* internal search over recent room history

Public edge:

* room profile
* public event announcements
* curated monthly playlist
* room-authored guide to labels/scenes
* selected archived discussion artifacts
* bridge policy
* moderation/federation policy

One night, someone writes a great explanation of why a certain wave of tracks sounds "overcompressed but emotionally correct," which is both stupid and true. Another member wants to quote it publicly.

In a normal platform, this becomes a screenshot, a quote post, or theft with deniability.

In Rhizome, it becomes a threshold action:

```text
request:
  actor: member_123
  action: quote_out
  source: room_event_789
  destination: public_artifact_or_post
  context:
    includes_author_text: true
    includes_room_context: partial
    redaction_requested: false
```

The boundary service checks:

* is the actor allowed to request quote-out?
* did the source author allow quote-out by default?
* does this room require author approval?
* is the destination public, federated or room-adjacent?
* does the quote include other users' context?
* is the room currently in restricted mode?
* does the target server/room have bridge trust?
* should this become a public post, artifact, summary or denied request?

Possible outcomes:

```text
deny:
  reason: author approval required

permit_with_redaction:
  reason: room policy forbids names in exported quotes

permit_as_artifact:
  reason: quote approved, archived as room artifact

permit_as_public_post:
  reason: author and room policy allow public quote-out
```

If approved, Rhizome mints:

```text
artifact:
  public excerpt or summary

receipt:
  source room
  source event reference/hash
  approving authority
  applicable policy
  destination
  timestamp
  redaction status
```

The public world sees the artifact.

The room does not become globally searchable.

The interior does not become feed exhaust.

That is the product.

Not the chat. Not the feed. **The crossing.**

**Gap note:** This requires source event references that can prove provenance without necessarily exposing content. That is a real technical gap, especially if the room substrate, privacy model and public artifact layer are separate systems.

---

## 14. How this could be mounted on existing substrates

The least insane prototype would not build the whole stack.

It would build `rhizomed`, a threshold daemon.

```text
[Room substrate: Matrix or XMPP]
          |
          | export / quote / archive / bridge request
          v
[Rhizome threshold daemon]
          |
          | standing + policy + context evaluation
          v
[Artifact mint]
          |
          +--> ATProto record
          +--> ActivityPub object
          +--> static artifact page
          +--> forum topic
```

The daemon owns:

* threshold verbs
* standing evaluation
* policy evaluation
* artifact minting
* receipts
* adapter contracts
* negative defaults

The room substrate owns:

* chat
* membership presence
* basic room moderation
* maybe encryption

The public substrate owns:

* public records
* public federation
* identity handles
* artifact distribution

The archive surface owns:

* durable reading UX
* artifact browsing
* public documentation
* curated memory

The authorization substrate owns:

* relationship graph
* policy decision support

But none of those substrates get to define what a room *means*.

That is the whole defense.

**Complication:** The daemon becomes the load-bearing moral object. If it is weak, every adapter will leak its native assumptions back into the system.

---

## 15. Actual gaps

### Gap 1: Event-to-artifact provenance

Rhizome needs a way to say:

> This public artifact came from this room event under this policy.

But it may not be allowed to expose the original event.

This suggests content hashes, redacted references, room-local IDs, signed export receipts or source proofs. But if done badly, the proof becomes a tracking vector.

**Hard problem:** prove enough to make boundary crossings accountable without making private speech reconstructible.

---

### Gap 2: Consent semantics

Author consent is not enough.

A message may quote another person. A joke may rely on room context. A discussion may include multiple participants. A thread may be exportable only as a summary, not as raw quotes.

Rhizome needs consent shapes beyond yes/no:

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

### Gap 3: Local standing

Identity can be portable, but authority is local.

Rhizome needs a standing model that can answer:

```text
Who may approve export?
Who may archive?
Who may bridge?
Who may invite?
Who may override?
Who may revoke?
```

Existing authorization tools can help, but the social concepts must be native.

**Hard problem:** avoid both admin feudalism and process sludge.

---

### Gap 4: Federation trust between rooms

Federating posts is easier than federating habitat boundaries.

Rooms need to know things like:

```text
Room A trusts Room B to mirror artifacts.
Room A does not allow Room C to bridge live events.
Room A accepts moderation labels from Server D.
Room A rejects search indexing by Service E.
```

**Hard problem:** trust is not just server-level. It is room-level, action-level and sometimes artifact-level.

---

### Gap 5: Search and indexing control

Robots will want to index everything. Users will want search. Communities will want discoverability until discoverability becomes exposure.

Rhizome needs explicit index policy:

```text
searchable_in_room
searchable_by_members
searchable_by_adjacent_rooms
searchable_publicly
searchable_after_archive_only
not_searchable
```

**Hard problem:** public objects are hard to un-index once federated. "Forget" becomes policy theater unless the system is honest about limits.

---

### Gap 6: Bridge containment

Bridges are boundary wounds.

A bridge to Matrix, Discord, IRC, ActivityPub or ATProto can silently destroy Rhizome's semantics if it exports too much or imports context-free objects.

**Hard problem:** every bridge needs a contract. Not "messages go over there." More like:

```text
what object types cross?
what metadata crosses?
what policy survives?
what receipts are minted?
what cannot cross?
what happens on revocation?
```

---

### Gap 7: Private receipts

If a room is private, but export requires accountability, what does the receipt contain?

Too little and the receipt is decorative.
Too much and the receipt leaks the room.

**Hard problem:** receipts need scoped visibility. Some receipts may be public, some room-local, some moderator-only, some hashed commitments.

---

### Gap 8: UX for semi-permeability

This is the adoption killer.

The UI must make boundary state obvious:

* "this room is private"
* "this message may not be quoted"
* "this thread can be archived"
* "this artifact is public"
* "this bridge is active"
* "this room is searchable only internally"

But it cannot become a cockpit.

**Hard problem:** make thresholds visible without making users feel like they're filing export paperwork for a shitpost.

---

### Gap 9: Governance after drift

Policies change. Members leave. Rooms split. Bridges become hostile. Artifacts outlive consent assumptions.

Rhizome needs temporal policy:

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

### Gap 10: Abuse handling

Bad actors will use boundary language too.

They will create rooms that look private but are extractive.
They will launder screenshots as "artifacts."
They will use consent machinery to harass.
They will create bridge traps.
They will weaponize searchability.
They will demand "federation neutrality" when blocked.

**Hard problem:** Rhizome cannot be only a cozy architecture. It needs adversarial assumptions from the start.

---

### Gap 11: Receipt validity under disagreement

Receipts record boundary crossings, but they do not automatically settle whether a crossing remains legitimate.

A system shaped this way needs to distinguish:

- valid when minted
- valid but disputed
- invalidated by policy error
- revoked by later authority
- superseded by room fork
- accepted by one federation peer but rejected by another
- public artifact persists, but source community no longer endorses it

**Hard problem:** avoid turning every receipt into a miniature court case while still making legitimacy disputes visible.

---

## 16. What exists, what doesn't

Existing component parts are enough to explore this seriously.

ATProto can carry app-specific public records and social objects through Lexicon.
ActivityPub can carry public/federated social objects.
Matrix and XMPP can carry live rooms.
Bonfire gives the strongest existing boundary/circle/verb inspiration.
SpiceDB and Cedar can support authorization decisions.
MLS can support serious group privacy, if the system reaches that stage.

What does not seem to exist as a coherent OSS primitive is:

> A threshold layer that preserves the distinction between room events, public posts, durable artifacts and boundary receipts.

That is the gap.

Not "federated chat."
Not "decentralized identity."
Not "forums plus ActivityPub."
Not "Discord but open source."
Not "private messages with E2EE."
Not "custom schemas."

The missing object is the **admissible crossing**.

---

## 17. Economic note

Rhizome assumes economic pluralism.

A system built around semi-permeable habitats is structurally hostile to the dominant platform business model. It does not want maximum circulation, global search, engagement ranking or frictionless extraction.

That means it cannot honestly be funded by pretending to be a slower, more ethical growth platform.

Possible support models look more like dues, co-ops, patronage, commissions, institutional hosting, scene infrastructure, grants or member-funded archives.

In other words: closer to furry convention economics than venture-scale social media.

If the goal is VC growth, Rhizome is the wrong system.

---

## 18. Closing frame

Subcultures do not need perfect privacy or maximum reach. They need **habitable gradients**.

A place can be findable without being exposed.
A room can be alive without being ephemeral.
An archive can exist without being exhaust.
A public artifact can travel without dragging the whole room behind it.
An identity can move without flattening standing into a universal score.
A federation can connect habitats without turning every interior into a feed.

The modern platform assumes circulation is the default and containment is an exception.

Rhizome reverses that.

The room is not content waiting to happen.
The archive is not exhaust.
The feed is not the natural destiny of speech.
Federation is not entitlement to context.

A subculture is not a feed with recurring users.

It is a room with memory, exits and walls that sometimes open.

---

# Condensed gap ledger

The **real invention** is not the protocol substrate. It is the **anti-collapse model**:

```text
event ≠ post ≠ artifact ≠ receipt
```

The biggest open gaps:

1. **Provenance without leakage** — proving where an artifact came from without exposing the room.
2. **Consent semantics** — quote/export/archive/summarize are different acts.
3. **Local standing** — portable identity cannot become universal authority.
4. **Room-to-room trust** — federation policy needs action-level granularity.
5. **Search containment** — discovery without global indexing of interiors.
6. **Bridge contracts** — every bridge is a possible leak.
7. **Private receipts** — accountability without surveillance.
8. **Usable UX** — visible thresholds without bureaucratic sludge.
9. **Temporal governance** — policy drift, revocation, expiration, artifact afterlife.
10. **Abuse model** — boundary language will be weaponized if naïve.
11. **Receipt validity under disagreement** — legitimacy disputes need a surface, not a court.

The one-line keepers:

> **Rhizome is a threshold layer for social habitats. It lets rooms produce public memory without becoming public exhaust, and it records the crossings without turning the room itself into evidence.**

> **Rhizome makes crossings legible. It does not make them innocent.**
