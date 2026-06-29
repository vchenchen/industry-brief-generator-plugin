# General Industry Brief Workflow

When using this workflow, reference these files as needed:

- `references/config_schema.md`
- `references/candidate_pool_template.md`
- `references/final_brief_template.md`
- `references/poster_qa_checklist.md`
- `references/unsupported_industry_protocol.md`

## User Inputs

Ask for:

```text
Industry:
Target market, such as North America, Europe, APAC, or global:
Focus topics, such as M&A, pricing, supply and demand, capacity expansion, policy, trade shows, or new products:
Excluded content, such as generic finance, social media posts, or corporate soft copy:
Final use, such as internal brief, newsletter, customer update, or social post:
Preferred output language:
```

If the user only gives an industry name, locate or draft the industry config first. Do not run the candidate pool yet.

## Input Variables

Determine:

- `industry`
- `date`
- `config_path`
- `candidate_count`
- `final_count`
- `region_scope`
- `output_dir`
- `final_use`
- `output_language`

User instructions override config defaults.

## Source Strategy

Search by source tiers. Avoid unbounded general web search.

Source rules:

- `tier_1`: industry media, databases, associations, regulators; prioritize for top candidates.
- `tier_2`: company announcements, PR Newswire, Business Wire, exchange filings; use to supplement events.
- `tier_3`: consulting summaries, market research excerpts, broad financial media; use only for background unless uniquely relevant.

Search order:

1. Latest 24-48 hours from `tier_1`.
2. Latest 24-48 hours from `tier_2`.
3. Last 7 days from high-quality `tier_1` and `tier_2`.
4. Last 30-90 days from `tier_3` only as background.

Every candidate must have a clickable source link.

## Inclusion and Exclusion

Include:

- direct relevance to `include_topics`,
- direct relevance to the target market,
- market impact through expansion, capital activity, supply chain, regulation, pricing, technology, or competitive dynamics.

Exclude:

- items matching `exclude_topics`,
- stock-only moves,
- generic macro news,
- generic consumer news,
- soft copy with no industry impact,
- items with unclear date, source, subject, or region.

## Deduplication

For the same event across multiple sources, keep one main candidate.

Prefer:

1. original announcements or regulatory filings,
2. authoritative industry media,
3. the most complete report,
4. the newest report.

## Scoring

Use config scoring weights for ranking. Do not show scores in the final output.

Default dimensions:

- freshness
- industry impact
- business value
- regional relevance
- novelty
- actionability
- source quality

## Selection Gate

Before the user selects exactly `final_count` items, do not generate:

- final brief,
- poster image,
- social copy,
- newsletter copy.

If the selected count is wrong, ask the user to complete or confirm the change.

## Poster QA

After rendering, check:

- image clarity,
- no overflow,
- no card overlap,
- no awkward line breaks,
- no split key terms,
- visible logo and brand,
- bottom information density is comfortable.

If the footer is crowded, shorten the mainline or split the footer hierarchy before delivery.

## Memory

When the project has a memory/output convention, record:

- run date,
- industry config,
- whether the candidate pool was generated,
- whether the final selection was made,
- major themes used or rejected,
- selected item numbers and source links.

Do not save raw search noise.
