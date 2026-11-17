# MedLit

MedLit is a Codex skill for biomedical literature search and PDF retrieval. It turns PICO questions into reproducible PubMed searches, records search details, deduplicates citations, and locates full text and supplements through PMC, publishers, or authorized institutional access.

## Use with Codex

Install the skill folder in your Codex environment, then select **MedLit** from `/skills` or invoke `$medlit`. Pass a PICO question, an existing PubMed query, or a list of PMIDs, DOIs, or titles. Institutional downloads require an authorized browser session.

## Upstream projects and acknowledgments

- [cookjohn/pm-skills](https://github.com/cookjohn/pm-skills) informed the PubMed search, citation metadata, and export workflow.
- [jyluo1994/paper-acquisition-anti-scrape](https://github.com/jyluo1994/paper-acquisition-anti-scrape) informed the open-access-first approach and the use of an authorized browser session for institutional PDF retrieval.

MedLit adapts these workflows into one Codex skill. PubMed discovery produces a deduplicated set of records, then PMID, DOI, or title links each record to its full-text retrieval and verification steps. This repository contains MedLit's skill instructions and interface assets.

Thank you to **cookjohn**, **jyluo1994**, and the contributors to both projects for sharing their work.
