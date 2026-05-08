# Prior Art

The short version: no one obvious is building Rhizome. But Roomy is close enough on substrate that the memo has to name it by name, and Bonfire is close enough on conceptual vocabulary that ignoring it would be dishonest.

The pieces of the answer exist. The shape that combines them — *interior event → boundary decision → consent/standing/policy check → artifact mint → public object → receipt* — does not appear to exist as a coherent project.

---

## The closest substrate cousin: Roomy

[Roomy](https://blog.muni.town/roomy-deep-dive/) is an ATProto + Automerge group chat / community thing. Its own writeup describes it as "similar in scope to Discord," using ATProto for social discovery and Automerge for peer-to-peer / local-first sync. It already has public group spaces with channels and categories.

Architecturally it is doing the right kind of parasitism: chat data lives in the browser and on users' PDSes, syncs through Automerge snapshots, and uses lightweight coordinator/router services rather than a giant AppView ingesting the full firehose. That is aligned with "don't build another full platform if you can parasitize identity and storage."

The honest red flag: ATProto PDS data is essentially public today. Private messaging in Roomy requires encryption and key management, and their current default keyserver can technically decrypt user messages because it holds the secret keys. They acknowledge this and plan alternatives. Worth tracking, not panicking about.

**Why this matters for Rhizome:** Roomy occupies the lane "rooms-on-ATProto." That is exactly the lane Rhizome should not try to occupy. If Roomy succeeds, Rhizome has a substrate cousin. If Roomy fails, Rhizome's substrate question is open again, but the doctrine layer is unaffected either way.

> Roomy may be trying to solve *rooms on ATProto*.
> Rhizome is trying to name the threshold problem those rooms will eventually hit.

That is a much cleaner separation than competing for the same lane.

---

## The closest conceptual cousin: Bonfire

[Bonfire's Boundaries](https://docs.bonfirenetworks.org/boundaries.html) model is the strongest existing match for the threshold-verb intuition. Users can be granted roles like *read, interact, participate, contribute, moderator, caretaker* — and there are explicit negative roles that override positive permissions. That is genuinely closer to "boundary verbs" than the post-or-not-post defaults of most platforms.

Bonfire's own writing is even sharper on this: boundaries are framed as granular verbs for meaningful interaction and collaboration, not just "who can see this." That is the right shape.

**Where Bonfire stops:** it remains a federated social / community framework with granular permissions. It does not encode the *event-vs-post-vs-artifact-vs-receipt* distinction. It does not treat crossings as load-bearing constitutional acts that mint signed receipts. It has the membrane intuition without the controlled-export layer.

So: closest on vocabulary, not on the anti-collapse model.

---

## ATProto-adjacent pieces

The [ATmosphere catalog](https://www.courier.social/) lists several ATProto messaging and community projects worth knowing about:

- **Squawk** — instant real-time group chats on ATProto.
- **freeq** — IRC rebuilt with ATProto identity.
- **OpenMeet** — groups, events and organizing on ATProto. Overlaps with the "habitat emits public edges" part of Rhizome (events, groups) but does not address controlled export of interior speech.

These cluster around *rooms, events, chats, communities*. None of them appear to be working on *controlled transformation of interior events into public artifacts with receipts.*

---

## Off-axis cousin: Nostr NIP-29

[NIP-29](https://nips.nostr.com/29) defines relay-based groups on Nostr — membership, moderation and permission enforcement administered by relay/group admins. There are open-source NIP-29 group chat clients ([example](https://github.com/max21dev/groups)).

This is structurally interesting because it locates group authority at the *relay*, which is a different topology choice than Matrix's room state or ATProto's PDS-as-storage model. But it is still "groups with relay authority and moderation." Not artifact minting from room events. Not receipts.

Worth knowing about because it shows that the protocol-design space has not converged on a single answer for "where does group authority live." That is useful context for the standing-vs-policy-vs-receipt split.

---

## How the existing projects cluster

```text
Roomy        = ATProto group chat / local-first Discord-ish viability
Bonfire      = granular boundary/permission vocabulary
OpenMeet     = groups / events / organizing on ATProto
Squawk/freeq = messaging / chat experiments on ATProto
Nostr NIP-29 = group moderation via relay authority
```

The missing piece, still:

> **Public objects should know how they became public, without making the room itself public.**

That is the gap.

---

## What this means for Rhizome

The substrate question is being worked on. The vocabulary question has a partial answer. The federation question has multiple competing answers.

The threshold / receipt question — *how does an interior event become a public artifact in a way that records the crossing without exposing the room* — does not appear to have an active project.

The lane is therefore:

> Here is what any ATProto / Matrix / federated room system must preserve if it does not want to become feed exhaust or encrypted amnesia.

That is theory work. It does not require building chat, sync, clients, key management, mobile notifications, a moderation UI, a settings page, or the inevitable GIF-search issue.

It does require: documenting the failure model clearly enough that someone building rooms can tell, in advance, which design choices will eventually betray their users.

That is enough.
