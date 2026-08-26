# Changelog

Notable changes to this list. Typo fixes and small wording tweaks are not logged.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## 1.1.1 — 2026-08-26

### Fixed

- 33 record descriptions rewritten. Thirty opened with or contained "AI-powered", which carries
  no information in a dataset where every record is an AI tool, and three carried a marketing
  word rather than a fact. Each now says what the product does. No URL, category, label, or
  verification date changed.

## 1.1.0 — 2026-08-26

### Added

- `## The records` — all 748 records listed in the README, grouped into the 20 categories and
  sorted by name inside each, with a linked index of category counts above them. The section is
  generated from `data/ai-tools.json` rather than written by hand, so it cannot disagree with
  the data files. They remain the source and the thing to use; the listing is a way to read
  them without leaving the page.

### Changed

- `AdMob` — description shortened. It ran to 36 words, which is longer than any other record and
  longer than a single entry should be.

## 1.0.0 — 2026-08-26

Initial public-ready release.

### Added

- 748 verified tool records as `data/ai-tools.csv` and `data/ai-tools.json`, with a
  ten-field schema, plus `data/categories.csv` covering 20 categories.
- `data/schema.json` — JSON Schema (draft 2020-12) for the records, covering both closed
  vocabularies, the category list, and the date format. All 748 records validate against it.
- Every official URL resolved over HTTP before release, including the redirect target.
  182 candidate records were excluded for failing verification.
- Categories: Audio, music, and voice, Automation and agents, Business and finance, Chatbots and assistants, Coding and development, Customer support, Data and analytics, Design and creative, Developer infrastructure and models, Education and learning, Health and lifestyle, Image generation and editing, Marketing and advertising, Presentations and documents, Productivity and workflow, Research and knowledge, SEO and search, Sales and CRM, Video, and Writing and content.
- Contribution files: `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md` (Contributor Covenant 2.1),
  `SECURITY.md`.
- `LICENSE` — CC BY 4.0, canonical text.
- Issue forms for suggesting a record and reporting a broken link, plus a pull
  request template and issue template configuration.
- `.editorconfig`, `.gitattributes`, and `.gitignore`.

### Notes

- Every official URL was checked before release. Entries whose product had been
  discontinued, absorbed, or renamed were corrected or dropped rather than carried over.
- All outbound links are clean canonical URLs. No affiliate or referral parameters.
- Licensed under CC BY 4.0. Provisional. The dataset licence is an open owner decision and may become CC0 1.0.
