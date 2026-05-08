# Negative Defaults

Rhizome exists to resist substrate defaults.

A room event is not a public object.
A public object is not an archive.
An archive is not exhaust.
A permission check is not legitimacy.
A bridge is not neutral.
A receipt is not a log line.
A deleted object is not forgotten.
A federated object is not entitled to context.

These are not slogans. They are the load-bearing refusals the daemon has to enforce against every substrate it touches. Read this before reading anything else.

---

## What each substrate wants

Every adapter brings its native physics. Rhizome's job is to refuse the parts that would eat the model.

```text
Matrix wants:
  replicated room history, broad event distribution, federation as topology

ActivityPub wants:
  circulating objects, public addressability, follower-graph reach

ATProto wants:
  globally visible records, indexer-friendly schemas, account-level history

Auth systems want:
  binary allow/deny, single-decision contexts, principal/action/resource shape

Archives want:
  permanence, completeness, search

Search systems want:
  discoverable surface area, broad indexing, ranked exposure

Bridges want:
  convenience, lossy translation, "messages go over there"

Encryption layers want:
  to be mistaken for governance
```

Rhizome's daemon exists to say, in each case:

> No, not like that.

If the daemon ever stops saying that, the substrate's gravity wins and Rhizome becomes a slower, more sanctimonious version of the thing it was supposed to replace.

---

## What Rhizome makes annoying

Annoyance is the feature. Things the system should structurally resist:

- global search across room interiors
- automatic transcripts
- bridge-by-default
- quote-posting from semi-private rooms
- "public unless configured otherwise"
- universal reputation
- room discovery by engagement ranking
- exporting someone else's speech as a default action
- treating membership as authority
- treating identity as standing
- treating encryption as governance
- treating archive as exhaust
- treating federation as entitlement
- "AI summarize every room you're not in" hell-gizmo behavior
- trending rooms (the person who asks for these gets a decorative title and no database access)

Each item on this list represents a real adoption pressure. Each one will be requested by someone reasonable, often. The doctrine is to refuse them anyway, because the cumulative effect of accepting them is the platform model with extra steps.

---

## The line

> Rhizome should optimize for explicit crossings, not frictionless leakage.

A good habitat needs walls. Not absolute walls. Not permanent walls. Not paranoid bunker walls. Walls that sometimes open.

That is what "semi-permeable" means. The negative defaults are how the walls stay walls between openings.

---

## The contributor test

Before adding a feature, ask:

1. Does this introduce a new boundary crossing? If yes, what receipt does it mint?
2. Does this default to the substrate's native behavior in a way that erases a Rhizome distinction? If yes, redesign.
3. Does this make a crossing easier without making it more legible? If yes, it is the wrong direction.
4. Could this be requested by a growth-pressure stakeholder? If yes, the answer needs to be explicit, not accidental.

If you cannot answer all four, the feature is not ready.
