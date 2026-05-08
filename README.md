# Rhizome

> **This repository is a static design memo and failure model. It is not an implementation repository. No daemon, client, schema package, adapter or validator lives here.**

Rhizome names a threshold problem in federated social habitats: how rooms produce public memory without becoming public exhaust.

It is not a product proposal. It is a failure model for federated rooms.

> Rhizome is what Roomy-like systems will need once they stop asking how to make rooms exist and start asking how rooms should leak.

---

## Files

- [`RHIZOME-MEMO.md`](./RHIZOME-MEMO.md) — the long-form memo. Threshold model, federation as membrane, receipts as constitutional objects, the anti-collapse model (`event ≠ post ≠ artifact ≠ receipt`).
- [`RECEIPT-CENTERED-THRESHOLDS.md`](./RECEIPT-CENTERED-THRESHOLDS.md) — the seven-step hierarchy. The admissibility-vs-legitimacy split. Why receipts come before verbs.
- [`NEGATIVE-DEFAULTS.md`](./NEGATIVE-DEFAULTS.md) — doctrine page on what the system refuses. Substrate gravity, contributor test.
- [`ONE-VERB-PROTOTYPE.md`](./ONE-VERB-PROTOTYPE.md) — conceptual sketch of the smallest experiment that could test the model. Single verb (`quote_out`), one room, one artifact site, one receipt format. Not a spec; a thought experiment.
- [`PRIOR-ART.md`](./PRIOR-ART.md) — what already exists in the blast radius (Roomy, Bonfire, OpenMeet, NIP-29, etc.) and where the gap actually sits.
- [`GAPS.md`](./GAPS.md) — consolidated gap ledger.

---

## Repo rules

This is an evidence locker, not an incubator.

```text
Allowed:
- markdown
- diagrams
- cited prior art
- gap ledgers
- conceptual pseudo-objects
- essay drafts
- static examples

Forbidden:
- src/
- Cargo.toml
- package.json
- pyproject.toml
- JSON Schema
- CI
- tests
- "just a tiny validator"
```

The real tell will be whether `ONE-VERB-PROTOTYPE.md` becomes `examples/quote_out.json`. That is when the ankle monitor starts beeping.

---

## What this repo is for

Naming things early so they have a handle. Recording the failure model so the next time someone asks "should we just bridge that?" there is something to point at. Holding doctrine in a place where it can be cited, contested, forked, or ignored — but not silently lost.

It is not a roadmap. It is not a pitch. It is not a TODO list.

If any of those start showing up, treat it as a perimeter breach.
