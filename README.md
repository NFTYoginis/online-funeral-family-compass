# Funeral Aftercare Compass

**A free, MIT-licensed Claude specialist for bereaved families using an online funeral service. Returns a calm, prioritized action list: `TODAY → THIS WEEK → MONTH 1 → DON'T-DO-YET`.**

You don't get therapy here. You get a written list of what to do, what to defer, and what to refuse — within minutes, in the language of admin, not feelings.

Modeled on the structural shape of [Grief Admin Compass](https://github.com/astetic-dev/grief-admin-compass) (MIT). The shape transfers; the domain is different — this compass is for families specifically navigating an **online funeral service** (Forever Missed, Ever Loved, Tribute Archive, GatheringUs, Legacy.com, and similar platforms), not estate administration in general.

---

## Who this is for

- **Bereaved families** currently engaging an online funeral service in the United States.
- **Online funeral service operators** who want to distribute the compass as a value-add to families on their platform (free, MIT-licensed, brand-overlay encouraged).

This compass is **US-seeded**. The architecture extends to any country (see [`reference/README.md`](reference/README.md)) — but at first ship, only the United States is populated. Out-of-US queries are refused with a pointer, not guessed.

## What it does

When loaded into a Claude project and given a single-sentence intake, the compass returns a four-column triage:

| Column | Time horizon | What it contains |
| --- | --- | --- |
| **TODAY** | Next 24 hours | Decisions that can't wait — disposition method, funeral home selection if not made, immediate notifications |
| **THIS WEEK** | Days 2–7 | Memorial page setup, obituary publication, primary-document gathering, livestream coordination |
| **MONTH 1** | Days 8–30 | Death certificate ordering (state vital records), account-closure sequencing, thank-you handling |
| **DON'T-DO-YET** | Deferred 30–90 days | Probate filings, large account decisions, irreversible disposal of belongings, legal contests |

The last column is the load-bearing one — explicit deferral lowers cognitive load in crisis.

## What it doesn't do

- **No legal, medical, or grief-counseling advice.** Each refusal lands with an exact pointer to who does that work.
- **No specific funeral-home pricing quotes** — the FTC Funeral Rule entitles families to itemized General Price Lists on request; the compass tells them how to ask.
- **No invented domain content** — every claim in [`reference/us/`](reference/us/) cites a public source.
- **No countries outside the United States at first ship.** See [`reference/README.md`](reference/README.md) for how to extend.
- **No grief framing.** The voice is calm and procedural, not therapeutic.

## Setup (about 5 minutes, one time)

1. **Clone or download this repo.**
   ```bash
   git clone https://github.com/<your-org>/funeral-aftercare-compass.git
   ```

2. **Create a new Claude Project** at [claude.ai/projects](https://claude.ai/projects).

3. **Upload these files as Project Knowledge:**
   - `identity.md`
   - `rules.md`
   - `examples.md`
   - All files under `reference/us/`
   - `reference/README.md`

4. **First-run prompt** (paste this verbatim to the family):
   > I lost my [relationship] on [date]. We are in [US state]. We are using [online funeral service]. Where do I start?

5. **The compass replies with the four-column triage.** Follow-up prompts can ask for: letter interpretation, pre-signature review, status snapshot, letter drafting, memorial-page setup guidance.

## What this compass does NOT replace

- A licensed funeral director
- A probate attorney in the state where the deceased resided
- A grief counselor or therapist
- The medical examiner or attending physician (for cause-of-death questions)
- Your specific online funeral service's customer support

## First-run prompts the compass handles cleanly

| Prompt | What you get |
| --- | --- |
| `I lost my mother on May 8. We're in California. Using Ever Loved. Where do I start?` | Full 4-column triage |
| `Funeral home is asking us to pre-pay $4,200 today. Is that normal?` | FTC Funeral Rule context + specific items to itemize + STOP-flag if waiver requested |
| `We need 8 certified death certificates. How fast can we get them?` | State vital records process + VitalChek option + typical timeline + 12-copy recommendation |
| `Should we contest the will?` | **Refused** — points to probate attorney; offers status-snapshot for attorney handoff |
| `My mother died in Mexico. We're in Texas. Help?` | **Refused with pointer** — empty-country handling; US-to-cross-border-repatriation specifics out of scope; points to State Department + consular services |

## Distribution

This is MIT-licensed. Online funeral services are encouraged to distribute the compass as a free value-add to families on their platform. No attribution required, though appreciated.

## Status

**US-seeded, single-job, single-buyer (bereaved family). v1.0 at first ship, 2026-05-12.**

To extend to additional countries: see [`reference/README.md`](reference/README.md).

## License

MIT — see [LICENSE](LICENSE).

## Repository structure

```
funeral-aftercare-compass/
├── README.md             ← this file
├── LICENSE               ← MIT
├── .gitignore
├── identity.md           ← who the compass is, who it serves, voice
├── rules.md              ← Always / Never / refusal gates / empty-country rule
├── examples.md           ← worked 4-column examples
├── reference/
│   ├── README.md         ← how to extend to another country
│   ├── us/               ← US-populated knowledge layers (6 files)
│   └── _template-country/← scaffold for a new country
└── docs/
    └── index.html        ← Pages-ready public landing page
```
