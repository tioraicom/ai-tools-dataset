# AI Tools Dataset

**English** · [العربية](README.ar.md)

> A clean, reusable dataset of AI tools, categories, pricing models, platforms, and public product metadata.

<!-- counts:start -->
![Records](https://img.shields.io/badge/records-748-informational)
<!-- counts:end -->
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen)
[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-lightgrey)](LICENSE)

748 AI tools as CSV and JSON, with the same ten fields on every record and every URL
resolved over HTTP before release. It is small enough to read, load, and check by hand, which
is the point: a 40,000-row scrape nobody has verified is worse than useless for research.

Records that failed verification did not ship. That removed 182 candidates, including four
whose domains had lapsed and now redirect to a domain-resale page, and it is the main reason
this dataset is smaller than the catalogue it was drawn from.

Maintained by [TiorAI](https://tiorai.com/), which catalogues AI tools for a living.

<!-- last-reviewed:start -->
**Last reviewed:** 2026-08-26
<!-- last-reviewed:end -->

## Contents

- [What's in the dataset](#whats-in-the-dataset)
- [Schema](#schema)
- [How records are verified](#how-records-are-verified)
- [Using the data](#using-the-data)
- [Known limitations](#known-limitations)
- [Suggest a correction](#suggest-a-correction)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)
- [License](#license)
- [About TiorAI](#about-tiorai)

## What's in the dataset

```text
data/
├── ai-tools.csv        748 records, 11 columns, UTF-8, RFC 4180
├── ai-tools.json       the same 748 records, typed
├── categories.csv      the 20 categories, with a description and a count
└── schema.json         JSON Schema for ai-tools.json, to validate against
```

The CSV and the JSON are semantically identical. The JSON types the fields properly —
`pricing_model` and `platform` are arrays, `open_source` and `api_available` are booleans,
`secondary_category` is a string or `null` — while the CSV flattens the arrays with `; ` so it
opens cleanly in a spreadsheet.

### Records per category

| Category | Records |
|---|---:|
| Education and learning | 66 |
| Automation and agents | 61 |
| Customer support | 59 |
| Research and knowledge | 55 |
| Business and finance | 55 |
| Health and lifestyle | 50 |
| SEO and search | 44 |
| Productivity and workflow | 41 |
| Marketing and advertising | 37 |
| Coding and development | 35 |
| Data and analytics | 35 |
| Audio, music, and voice | 34 |
| Sales and CRM | 30 |
| Presentations and documents | 28 |
| Design and creative | 28 |
| Image generation and editing | 27 |
| Writing and content | 18 |
| Video | 17 |
| Developer infrastructure and models | 15 |
| Chatbots and assistants | 13 |

The distribution reflects what survived verification, not what the field looks like. It is not
a sample of the AI market and should not be used as one. See
[Known limitations](#known-limitations).

## Schema

Ten fields, identical on every record.

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | The product name, spelled as the vendor spells it |
| `official_url` | string | Yes | The product's own site. HTTPS, canonical, no tracking or affiliate parameters |
| `primary_category` | string | Yes | One of the 20 categories in `categories.csv` |
| `secondary_category` | string or null | No | A second category where one clearly applies |
| `pricing_model` | array of string | Yes | One or two of `Free`, `Freemium`, `Paid`, `Open Source`, `Free Trial` |
| `platform` | array of string | No | Zero or more of `Web`, `Windows`, `macOS`, `Linux`, `iOS`, `Android`, `API`, `CLI`, `Browser Extension`, `VS Code`, `JetBrains`, `Discord` |
| `short_description` | string | Yes | One or two sentences, up to 240 characters, ending in a full stop |
| `open_source` | boolean | Yes | Whether the product is released under an open-source licence |
| `api_available` | boolean | Yes | Whether the product exposes a public API |
| `last_verified` | string | Yes | ISO `YYYY-MM-DD`, the date the record was last checked |

In the CSV, arrays are joined with `; ` and booleans are the strings `true` and `false`.
Empty is the CSV equivalent of JSON `null`.

### Vocabularies

`pricing_model` and `platform` are closed sets. A value outside them is a defect, not a
variation, and the release check fails on one.

`Open Source` means an OSI-approved licence. Source-available products with commercial
restrictions do not carry it, and `open_source` is `false` for them.

### What is deliberately not in the schema

No internal identifiers, no editorial scores, no view counts, no ranking data, no submission
records, no contact details, no draft content, no affiliate data, and no database or taxonomy
IDs. None of it would mean anything outside TiorAI's own systems, and most of it should not
leave them.

### Validating against the schema

[`data/schema.json`](data/schema.json) is a JSON Schema (draft 2020-12) covering every field,
both closed vocabularies, the category list, and the date format. All 748 published records
validate against it, and it rejects the mistakes worth catching: a pricing label outside the
vocabulary, a non-HTTPS URL, a missing required field.

```python
import json, jsonschema

records = json.load(open("data/ai-tools.json", encoding="utf-8"))
schema  = json.load(open("data/schema.json", encoding="utf-8"))
jsonschema.validate(records, schema)          # raises on the first problem
```

Use it to check your own additions before opening a pull request, and to catch a breaking
change before it reaches your pipeline.

### Versioning

The schema follows semantic versioning through [CHANGELOG.md](CHANGELOG.md). **A field added,
removed, renamed, or retyped is a major version bump**, so you can pin a major version and
trust the columns. `data/schema.json` is where that contract is written down, so a diff of
that file is a diff of the contract.

## How records are verified

Records come from TiorAI's public AI tools catalogue and are then checked independently. Every
one of the 748 published records passed all of the following.

**1. The URL was rewritten, not inherited.** Every stored catalogue URL carries TiorAI referral
tracking, and a small number carried third-party affiliate parameters. Every URL here was
re-derived: forced to HTTPS, fragment removed, 21 classes of tracking and affiliate parameter
stripped by name, meaningful paths preserved.

**2. The URL was resolved over HTTP.** Browser user agent, redirects followed to a depth of 8,
12-second connect and 30-second total timeout, at least 400ms between requests to the same
host. A `403`, `405`, `429`, or `999` was treated as bot protection rather than death, and
re-probed by a second route before any judgement.

**3. The redirect target was checked, not just the status code.** This caught the failure mode
that matters most in a tool dataset: a lapsed domain that still returns `200` because it now
serves a domain-resale page. Four records were removed for this. A further 93 were removed for
redirecting to a different registrable domain, which usually means a rename or an acquisition
that could not be resolved automatically.

**4. Duplicates were removed four ways.** Normalised name, canonical URL, full host, and
registrable domain. Anything the internal build flagged as an uncertain match was dropped
rather than merged.

**5. Every field was checked against the schema.** Vocabularies, types, URL shape, date
format, description length, and CSV-to-JSON parity, on every record.

### What verification does not tell you

That a URL resolves does not mean the product still works, that the pricing label is current,
or that the description is accurate today. `last_verified` records when the record was
checked, and the honest reading of it is "this was true on that date".

Pricing is the fastest-moving field here and will be the first thing to go stale.

## Using the data

```python
import json

with open("data/ai-tools.json", encoding="utf-8") as f:
    tools = json.load(f)

free = [t for t in tools if "Free" in t["pricing_model"] or "Freemium" in t["pricing_model"]]
with_api = [t for t in tools if t["api_available"]]
print(len(tools), len(free), len(with_api))
```

```python
import csv

with open("data/ai-tools.csv", encoding="utf-8", newline="") as f:
    rows = list(csv.DictReader(f))

# arrays are joined with "; " in the CSV
for r in rows[:3]:
    print(r["name"], r["pricing_model"].split("; "))
```

```bash
# 20 categories with counts, without loading anything
column -s, -t data/categories.csv
```

The CSV is UTF-8 with a header row, `\n` line endings, and RFC 4180 quoting. It opens
correctly in Excel, Numbers, LibreOffice, pandas, and DuckDB without preprocessing.

### Updating

There is no live connection to any TiorAI system, and reproducing an update does not require
access to one. The process is:

1. Extract public candidate records.
2. Normalise URLs and map categories, pricing, and platforms onto the published vocabularies.
3. Verify every URL over HTTP, including the redirect target.
4. Validate the schema, vocabularies, duplicates, and CSV-to-JSON parity.
5. Compare against the previous release and review what changed.
6. Publish, and record the change in the changelog.

Steps 3 and 4 are the ones that matter. Anything can generate a large table of tools; what
makes this one usable is that the rows were checked and the failures were removed.

## Known limitations

Stated plainly, because a dataset that hides these is harder to use, not easier.

- **This is not a sample of the AI market.** It is what survived verification from one
  catalogue. Category proportions reflect that filter, not the field.
- **Descriptions come from TiorAI's own catalogue.** They were normalised and length-capped
  for this release, and the formulaic opening clause was trimmed where it only restated the
  product name. They are first-party editorial text, not independently rewritten prose, and
  they are not vendor marketing copy.
- **Pricing labels are categorical and go stale.** No amounts are published, because amounts
  are wrong within weeks. The labels last longer, but not forever.
- **`open_source` is conservative.** It is `true` only where an OSI-approved licence was
  established. Some source-available products are correctly `false` and may look like errors.
- **English-language bias.** The catalogue this was drawn from is English-first.
- **Coverage is uneven.** Some categories are thin because verification removed more of them,
  not because fewer such tools exist.
- **No quality signal.** There is no score, rating, or ranking, and none is planned. Inclusion
  means the record was verified, not that the product is good.

## Suggest a correction

- [Suggest a record](../../issues/new?template=suggest-a-record.yml)
- [Report a broken link](../../issues/new?template=report-a-broken-link.yml)

The most valuable report here is a record that is wrong rather than missing: a product that
has shut down, a pricing label that has changed, an `open_source` value that does not match
the licence. Those are the errors a user of the data cannot see.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md). Corrections are worth more than additions in this
repository, and both go through the same schema checks before release.

Do not open a pull request that edits `data/` directly. Those files are generated by a
verification pipeline, and a hand-edit is overwritten at the next release without anyone
noticing. Open an issue with the correction instead.

## Disclaimer

Every product described is built and operated by a third party, not by TiorAI. Product data
changes constantly: tools shut down, get acquired, change name, and change pricing without
notice. Records were accurate as far as could be established on the date in `last_verified`
and carry no guarantee beyond it. Verify anything you intend to rely on.

Inclusion is not endorsement, and no ranking or quality judgement is expressed or implied.
Product names and trademarks belong to their respective owners and are used here for
identification only.

## License

[CC BY 4.0](LICENSE). You may copy, adapt, and redistribute this dataset, including
commercially, as long as you credit TiorAI and indicate what you changed.

The licence covers the compilation: the selection of records, the category taxonomy, the field
definitions, and the descriptions. It does not cover the TiorAI name and logo, and it does not
cover the listed products, their trademarks, or their own content.

It also does not cover the underlying facts. A product's name, its address, and whether it has
a free tier belong to nobody, and attribution is owed for the work of collecting, verifying,
and describing them rather than for the facts themselves.

## About TiorAI

[TiorAI](https://tiorai.com/) is an AI tools directory. This dataset is a verified subset of
its public catalogue, published in a form that is useful to someone who wants the data rather
than the website.

- [AI tools directory](https://tiorai.com/tools/)
