# MedLit

MedLit is a Codex skill for biomedical literature search and PDF retrieval. It turns PICO questions into reproducible PubMed searches, records search details, deduplicates citations, and locates full text and supplements through PMC, publishers, or authorized institutional access.

## Use with Codex

Install the skill folder in your Codex environment, then select **MedLit** from `/skills` or invoke `$medlit`. Pass a PICO question, an existing PubMed query, or a list of PMIDs, DOIs, or titles. Institutional downloads require an authorized browser session.

## Upstream projects and acknowledgments

- [cookjohn/pm-skills](https://github.com/cookjohn/pm-skills) informed the PubMed search, citation metadata, and export workflow.
- [jyluo1994/paper-acquisition-anti-scrape](https://github.com/jyluo1994/paper-acquisition-anti-scrape) informed the open-access-first approach and the use of an authorized browser session for institutional PDF retrieval.

MedLit adapts these workflows into one Codex skill. PubMed discovery produces a deduplicated set of records, then PMID, DOI, or title links each record to its full-text retrieval and verification steps. This repository contains MedLit's skill instructions and interface assets.

Thank you to **cookjohn**, **jyluo1994**, and the contributors to both projects for sharing their work.

## Download fallbacks

If the default routes do not produce a verified PDF, MedLit can resolve an open-access copy, follow a Web of Science record to the publisher, or resume a browser download after you complete verification. See [the fallback workflow](references/download-fallbacks.md).

The bundled [fetch-paper](references/upstream/fetch-paper/SKILL.md) comes from [research-paper-lifecycle-skills](https://github.com/shaishavmaisuria/research-paper-lifecycle-skills/tree/cf30d6452cc6fd0570dd760eb65696f4a3485398/skills/fetch-paper) under [Apache 2.0](references/upstream/fetch-paper/LICENSE). The fallback workflow links to the pinned upstream WoS and Zotero skills.
