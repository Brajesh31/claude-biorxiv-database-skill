# Claude bioRxiv Database Skill

A Python-based skill for searching and retrieving life sciences preprints from bioRxiv. It supports literature discovery, author tracking, date- and category-based searches, metadata retrieval, and PDF downloads.

## What It Covers

- **Keyword search:** Search titles and abstracts with configurable fields and date ranges.
- **Author search:** Find preprints associated with an author over a selected period.
- **Category filtering:** Narrow results using bioRxiv subject categories.
- **DOI lookup:** Retrieve metadata for a specific preprint.
- **PDF downloads:** Download preprint full text for review and analysis.
- **Structured output:** Save results as JSON for citation workflows, reporting, and downstream analysis.
- **Research workflows:** Support literature reviews, trend analysis, and author tracking.

## Installation

Clone the repository into your Claude skills directory:

```bash
git clone https://github.com/Brajesh31/claude-biorxiv-database-skill.git ~/.claude/skills/biorxiv-database
```

Install the Python dependency:

```bash
python -m pip install requests
```

## Using the Skill

Example request:

```text
Use the biorxiv-database skill to find recent preprints about CRISPR
gene editing from the last six months and save the metadata as JSON.
```

The repository's `scripts/biorxiv_search.py` supports keyword, author, date-range, DOI, category, and PDF-download workflows. Run the script with `--help` to inspect its available command-line options.

## Example Search

```bash
python scripts/biorxiv_search.py \
  --keywords "CRISPR" "gene editing" \
  --days-back 180 \
  --category genomics \
  --output results.json
```

## Repository Resources

- [SKILL.md](SKILL.md) contains the skill instructions and complete usage patterns.
- `references/api_reference.md` documents the bioRxiv API and response formats.
- `scripts/` contains the search utility.
- `tests/` contains the search test suite.

## Good Practices

Use focused date ranges and subject categories, cache results when practical, respect service rate limits, and track preprint versions. Check DOI and publication status before treating a preprint as peer-reviewed literature. Review downloaded papers and metadata before using them in formal research.
