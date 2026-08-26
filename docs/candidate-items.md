# Candidate pool

What was considered for this list, what was verified, and what was left out.

Two things are deliberately absent, and neither is an oversight:

- **Internal scores and per-product rejection notes.** Editorial scoring stays out of a
  public repository. Exclusions below are given as neutral categories, not as judgements
  about named companies.
- **A per-candidate TiorAI URL map.** Capturing a TiorAI link for every candidate would
  produce exactly the backlink list this portfolio's own rules prohibit.

## Sources of candidates

| Source | Role |
|---|---|
| TiorAI's published AI tools catalogue | Read-only, used to shortlist candidates and to confirm product identity. No description or stored URL was carried through |
| Direct knowledge of the category | Used to fill gaps the catalogue does not cover well and to remove products that have since shut down or been absorbed |
| The vendor's own site | The authority for every fact that ships: current name, canonical URL, pricing tier, platform support |

Category assignment, pricing, and platform labels from the catalogue were treated as
*signals*, never as published values. The catalogue's own taxonomy is far too large and too
redundant to publish, so this repository defines its own.

## Pool

| Stage | Count |
|---|---:|
| Candidates considered | 2244 |
| Shortlisted after scope filtering | 1047 |
| **Published** | **748** |

## Why candidates were dropped

- **URL did not resolve.** 82 candidates. The largest single exclusion, and the reason a verified dataset is smaller than an unverified one.
- **Redirects to a different registrable domain.** 93 candidates. Usually a rename or an acquisition; occasionally a squatter. None can be resolved automatically, so none shipped.
- **Domain lapsed and now serves a resale page.** 4 candidates. These return `200` and would have passed a naive status check, which is exactly why the redirect target is inspected.
- **Flagged as a possible duplicate.** 2,550 candidates, by normalised name, canonical URL, or shared host. Uncertain matches were dropped rather than merged.
- **No category, no pricing, or too little description.** 431 candidates.
- **Could not be classified into the public taxonomy.** 69 candidates.
- **Category allocation.** Categories are capped so no single one dominates the file.

## Verification

Every published entry had its official URL resolved over HTTP before release, following
redirects to the canonical destination. 748 distinct external URLs were checked:
722 answered normally, 26 returned a bot-protection or rate-limit
response, and 0 were broken.

A `401`, `403`, `405`, `429`, or `999` was never treated as evidence that a site is dead. Each
was re-probed by a second route and reasoned about rather than acted on automatically. No
entry was removed on the basis of a single failed request.

Time-sensitive facts — pricing tier, whether a free plan still exists, product availability,
renames, acquisitions, shutdowns, platform support — were re-checked against the vendor at
build time regardless of what the catalogue record said.
