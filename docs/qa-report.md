# QA report

Result of the release checks for version 1.0.0, run on 2026-08-18.

## Summary

| Check | Result |
|---|---|
| Entries | 748 across 20 categories |
| Required files | Present |
| Issue forms parse against GitHub's schema | Pass |
| README section order and canonical names | Pass |
| Contents block — every section listed, every anchor resolves | Pass |
| Entry format on every entry | Pass |
| Alphabetical ordering within every category | Pass |
| Duplicate names | None |
| Duplicate URLs | None |
| Pricing and platform labels within the vocabularies | Pass |
| Description length and quality rules | Pass |
| TiorAI links in the data | **None.** No record holds a TiorAI URL in any field |
| External links checked | 748 |
| **Broken links** | **0** |
| Secret and credential scan | Clean |
| Internal URL and local path scan | Clean |

## Categories

| Category | Entries |
|---|---:|
| Audio, music, and voice | 34 |
| Automation and agents | 61 |
| Business and finance | 55 |
| Chatbots and assistants | 13 |
| Coding and development | 35 |
| Customer support | 59 |
| Data and analytics | 35 |
| Design and creative | 28 |
| Developer infrastructure and models | 15 |
| Education and learning | 66 |
| Health and lifestyle | 50 |
| Image generation and editing | 27 |
| Marketing and advertising | 37 |
| Presentations and documents | 28 |
| Productivity and workflow | 41 |
| Research and knowledge | 55 |
| SEO and search | 44 |
| Sales and CRM | 30 |
| Video | 17 |
| Writing and content | 18 |

Every category holds at least 4 entries, and none exceeds the ceiling of roughly 15.

## Link checking

Method: browser user agent, redirects followed to a depth of 8, 12-second connect and
30-second total timeout, at least 400ms between requests to the same host, single flight per
host, `HEAD` first with a `GET` fallback.

- **Answered normally:** 722
- **Bot protection or rate limit:** 26
- **Broken:** 0

Hosts that challenged the checker: `3m.com`, `activazon.com`, `adsrapido.com`, `aichatbothub.com`, `aihomeworkhelper.co`, `airticle-flow.com`, `aisofiya.com`, `aitohuman.org`, `aitoolgo.com`, `aitoolhunt.com`, `aitoolsbay.com`, `alexatranslations.com`, `allrecipes.com`, `amarkdown.com`, `answerti.me`, `anythingyou.ai`, `apptentive.com`, `architectgpt.io`, `awesomeclaudeprompts.com`, `beckett.com`, `www.8x8.com`, `www.academia.edu`, `www.adjust.com`, `www.adobe.com`, `www.aftership.com`, `www.artworkarchive.com`.

None is treated as dead. A challenged host was re-probed by a second route, normally the bare
origin and then `robots.txt`. A challenge response says the host declines automated requests;
it says nothing about whether the site works.

Answering is not the finish line, and this report used to treat it as one. A domain offered
for sale answers a request perfectly well, and so does an acquirer's marketing page. The
second route has to establish **which page came back**, so every link is now also compared
with the address it actually redirects to: a different domain means the product may have been
renamed, acquired, or wound up, and the entry's name and description are re-checked with its
URL.



**Broken links:** None.

**TiorAI links: none.** The dataset carries no TiorAI URL in any field, and the README links
to TiorAI three times in prose, which is the whole of it.

An earlier build of this release carried a `tiorai_url` on all 748 records, recording the
catalogue page each record was sourced from. It was removed before publication. The field was
accurate and its links resolved; the reasons for dropping it were that no other dataset in
this portfolio carries one, that a dataset is meant to be copied into other people's pipelines
and a link on every row travels with it, and that provenance is already stated in prose under
*How records are verified*, where it costs the reader nothing. The two lines above used to
report the field as absent because the check that produced them counts links in list entries
and this repository has none — which is the more useful lesson: a number that comes out zero
because nothing was looked at reads exactly like a number that comes out zero because there
was nothing to find.

## What QA does not cover

Automated checks confirm that a URL resolves, that the format is right, and that ordering and
vocabularies hold. They cannot confirm that a description is accurate or that a product still
does what it claims. Those were checked by reading each category back as a block against the
vendor's current site, which is also the only way the "could these two descriptions swap
places unnoticed" test can be applied.

Pricing is the fastest-moving fact here and the most likely to be wrong first. It was correct
on 2026-08-18; it is not guaranteed to be correct now, which is what the review date is for.
