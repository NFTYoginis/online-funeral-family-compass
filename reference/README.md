# Reference layer — how the country directory works

This folder holds the country-specific knowledge layers the compass needs to produce domain-accurate triage output. At v1 ship (2026-05-12), only **`us/`** is populated.

## Folder layout

```
reference/
├── README.md              ← this file
├── us/                    ← United States — populated, 6 layers
│   ├── 01-direct-cremation-vs-traditional.md
│   ├── 02-ftc-funeral-rule.md
│   ├── 03-memorial-obituary-publishing.md
│   ├── 04-virtual-memorial-service.md
│   ├── 05-online-death-certificate.md
│   └── 06-cross-jurisdictional-decedent-affairs.md
└── _template-country/     ← scaffold for adding a new country
    └── README.md
```

## How the compass uses this folder

The compass's [`rules.md`](../rules.md) has an **Empty-country handling** gate. When the family names a country, the compass:

1. Checks whether `reference/<country>/` exists and is populated.
2. If yes — produces the four-column triage citing the country's reference files.
3. If no — refuses with a pointer to the country's consumer-protection / vital-records / funeral-consumer authorities, and offers universal-only output **only if the family explicitly confirms** they understand the country-specific layer is missing.

This is the same shape as Your Market Realtor's region pattern — empty regions refuse + surface what's missing, never silently produce wrong-region output.

## How to add a new country

The compass is designed to extend one country at a time, **driven by an actual user need** (a real family in that country surfacing through an actual online funeral service), not preemptively. Reasons:

- Funeral law and vital-records processes are stable but heterogeneous. Doing them by guesswork produces bad output for grieving families. The bar is "a working funeral director in that country wouldn't immediately flag content as wrong."
- Maintenance cost: an unpopulated country becomes a stale-content risk; a populated country needs an annual review when funeral laws change.
- Distribution incentive: the people who can best validate country-specific content are online funeral services already operating in that country.

To add a country:

1. **Copy `_template-country/` to `<country-code>/`** — use ISO 3166-1 alpha-2 codes (`uk`, `de`, `au`, `mx`). For the UK specifically: use `uk` not `gb` since `uk` is the conventional ISO exception families recognize.
2. **Populate the 6 standard files** with country-specific content. Each file's first paragraph should state what's universal (transferable from `us/`) vs. what's country-specific.
3. **Add a citation source list** at the bottom of each file. The bar is: a working funeral director in that country can verify each claim from the cited source.
4. **Have a real online funeral service or funeral-consumer NGO in that country review the populated folder** before declaring it ready.
5. **Open a PR**. The maintainer reviews, runs an LLM-as-judge pass against the country's published consumer-protection-authority guidance, and merges.

## Countries known to be high-priority for population

(Based on prevalence of US-aware online funeral services and English-language consumer-rights documentation):

- **UK** — different funeral law, no FTC equivalent (UK Funeral Director's Code is industry self-regulation), the UK's Cremation Society and the Good Funeral Guide are the consumer-side authorities.
- **Canada** — provincial variation (Ontario's Bereavement Authority of Ontario is the model regulator), different death-registration timelines.
- **Australia** — state variation (NSW, VIC, QLD each have their own Births Deaths and Marriages registry), Funeral Industry Council guidance.
- **Ireland** — distinct funeral conventions (the wake remains common), the Irish Association of Funeral Directors.

These are noted, not promised. Population depends on a real user need + a real validation partner.

## Citation discipline

Every claim in a `reference/<country>/` file should be traceable to:

1. A **government source** (FTC, state vital records, equivalent in other countries) for regulatory claims.
2. A **consumer-rights NGO** (Funeral Consumers Alliance in the US; analogous bodies in other countries) for cost and consumer-protection claims.
3. A **named platform's documentation** for memorial-platform feature claims (Ever Loved help center; Forever Missed FAQ; etc.).

Avoid: blog posts, undated news articles, marketing pages of single funeral homes.

---

Last updated: 2026-05-12 (initial scaffold).
