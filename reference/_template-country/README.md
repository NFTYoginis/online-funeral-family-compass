# Country reference scaffold — fill in for [COUNTRY]

This folder is the template for adding a new country to the Funeral Aftercare Compass. To populate a country, **copy this folder** to `reference/<country-code>/` (use ISO 3166-1 alpha-2 codes — `uk`, `de`, `au`, `mx`, etc.) and fill in the six standard files.

The bar: a working funeral director in [COUNTRY] would not immediately flag the populated content as wrong.

## The six standard files to populate

Mirror the structure of `reference/us/`. Each file's first paragraph should state what's **universal** (transfers from US or from cross-country principles) vs. what's **country-specific**.

### `01-direct-cremation-vs-traditional.md`

- The three operational paths (direct cremation / cremation with service / traditional burial) AND any country-specific paths (e.g., natural burial in the UK, Hindu funeral rites in India, Muslim ghusl-and-shroud burial in Indonesia)
- Cost ranges in local currency, year noted
- Cremation waiting periods and authorization requirements by region (state / province / county)
- What's universal across the country vs. what varies by region

### `02-[country-consumer-protection-rule].md`

The country's equivalent of the US FTC Funeral Rule, if one exists. Examples:
- **UK:** Funeral Director's Code of Practice (industry self-regulation via NAFD / SAIF) + the Funeral Plans Authorisation Regime (FCA, since 2022 for pre-need plans)
- **Australia:** State-by-state Fair Trading regimes; no federal funeral-industry rule
- **Canada:** Provincial — Bereavement Authority of Ontario (BAO) is the strongest model
- **Germany:** Bestattungsgesetz (Burial Act) at the state (Land) level
- **France:** Code général des collectivités territoriales (Articles L. 2223-1 et seq.)

If the country has NO national funeral-consumer-rights rule, **say so explicitly**. The compass's refusal language for that country should be calibrated accordingly.

### `03-memorial-obituary-publishing.md`

- Named online memorial platforms operating in the country (some US platforms are global; some countries have local champions — e.g., MuchLoved in the UK)
- Traditional obituary publication channels (newspapers, regional press conventions)
- Privacy norms and conventions for memorial pages in the country's culture
- What's free vs. paid

### `04-virtual-memorial-service.md`

- Streaming platforms commonly used in the country
- Cultural/religious conventions around streaming services (some traditions discourage recording; some require specific decorum)
- Bandwidth and infrastructure realities (in countries with weaker internet, defaults shift toward hybrid or in-person)

### `05-death-certificate.md`

- The issuing authority (national civil registry vs. regional vs. municipal)
- The process to order certified copies — in person, by mail, online if available
- Typical number of certified copies needed (varies — some countries' institutions accept apostilled photocopies; the US-style "10 originals" doesn't translate everywhere)
- Typical processing times and costs
- Cross-border use: apostille / authentication requirements

### `06-cross-jurisdictional-decedent-affairs.md`

- Within-country cross-region scenarios (state-to-state, province-to-province, Land-zu-Land)
- Across-border scenarios with the country's diaspora (e.g., for the UK: family in the UK, deceased in Spain — Costa del Sol repatriation is common enough to warrant attention)
- The country's consulate process for citizens dying abroad

## How to validate before merging

A populated country folder should pass a three-step review:

1. **Source citation discipline:** every regulatory claim cites the government source (national funeral law, regional regulator, consumer-protection authority). No blog posts, no marketing pages.
2. **Working-funeral-director review:** at least one practicing funeral director or funeral-consumer-NGO representative in the country has reviewed the populated content.
3. **LLM-as-judge pass:** an LLM grader, given the country's published consumer-rights documentation and the populated folder, reports concordance or flags drift.

## Universal templates that transfer (start here)

These shape elements come from US but should work everywhere — adapt copy, keep structure:

- The four-column triage `TODAY → THIS WEEK → MONTH 1 → DON'T-DO-YET` (universal)
- The `STOP` capitalization convention for irreversible decisions (universal)
- The "ask for prices in writing before signing" principle (universal — though the legal basis varies)
- The "refusal lands with a pointer, never a wall" principle (universal)
- The status-snapshot job (`DONE / IN PROGRESS / WAITING ON / DON'T-DO-YET / NEXT 7 DAYS`) (universal)

## Universal anti-patterns that transfer

These warnings hold across countries — keep them, just localize the institution names:

- Don't sign waivers in the first week
- Don't pre-pay beyond what's needed to start services
- Don't dispose of personal effects before probate / estate equivalent is sorted
- Don't make irreversible decisions about real estate or large accounts in the first month
- Don't pay non-essential bills from the deceased's accounts after death

## When NOT to populate a country folder

- The country is **identified as high-priority** but there's no real user need yet → wait. Populating preemptively creates stale-content risk.
- The country has **fragmented or rapidly-changing funeral regulation** with no consolidated source → wait until a local validation partner is found.
- The contributor cannot pass a **conflict-of-interest check** (e.g., a single funeral home in the country wants to populate the file to drive customers to themselves) → decline. The Funeral Consumers Alliance model — a non-commercial consumer-rights NGO — is what to seek.

---

Last updated: 2026-05-12 (initial scaffold).
