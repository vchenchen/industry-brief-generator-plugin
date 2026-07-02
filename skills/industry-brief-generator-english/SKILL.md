---
name: industry-brief-generator-english
description: English Edition of the Industry Brief Generator. A universal Codex Skill for industry news briefings: enter an industry, market, focus topics, and final use; generate candidate story topics first; choose 8; then automatically create the brief, poster, and channel-ready copy. Use when the user wants an English industry news briefing, digest, candidate pool, internal brief, newsletter copy, customer update, social post, or poster-style brief for any industry.
---

# Industry Brief Generator - English Edition

Codex Skill: a universal industry news briefing generator. Enter an industry, market, focus topics, and final use. Generate candidate story topics first. After the user chooses 8, automatically create the brief, poster, and channel-ready copy.

## Quick Start

If the user has not provided enough input, ask for:

```text
Industry:
Target market, such as North America, Europe, APAC, or global:
Focus topics, such as M&A, pricing, supply and demand, capacity expansion, policy, trade shows, or new products:
Excluded content, such as generic finance, social media posts, or corporate soft copy:
Final use, such as internal brief, newsletter, customer update, or social post:
Preferred output language:
```

If the user provides all fields, run the candidate-pool stage. If the user only gives an industry name, create or locate a config draft first and stop.

## Required Workflow

1. Determine `industry`, `market`, `focus_topics`, `excluded_topics`, `final_use`, `output_language`, `candidate_count`, `final_count`, and `drop_count = candidate_count - final_count`.
2. Load an industry YAML config if available. If missing, create a draft config first; do not run the candidate pool yet.
3. Browse or search current sources for news, policies, events, deals, pricing, product launches, and industry shifts. For current news, always verify dates and links.
4. Generate the candidate pool first. Do not produce the final brief, poster, or social copy yet.
5. Wait for a clear selection. Accept inclusion wording, such as `keep 1,2...`, with exactly `final_count` item numbers; or exclusion wording, such as `remove 3,4...`, with exactly `drop_count` item numbers. Normalize exclusion replies into the final keep-set before validating the count.
6. Generate final text and poster only after the selection is clear.
7. Render and visually inspect the poster. Fix layout issues before delivery.
8. Save useful run memory if the local project has an output or memory convention.

## Candidate Pool Contract

Use the user's preferred output language. If no language is specified, use the language of the user's request.

Include exactly `candidate_count` items unless the unsupported-industry protocol applies.

Each candidate must include:

- item number, topic label, and region
- title
- source and date
- one-sentence summary
- selection rationale
- best editorial or business angle
- source link

End with a clear selection gate, for example:

```text
Please reply with the {final_count} item numbers you want to keep, or say `remove` with the {drop_count} item numbers you want to drop. I will use the final {final_count} kept items to generate the poster, text brief, and channel-ready copy.
```

Adjust the final wording for internal briefs, newsletters, customer updates, or social posts.

## Final Brief Contract

After selection, produce:

- top brand area
- cover headline
- quick reads
- `final_count` news cards
- main theme
- priority expansion suggestions
- title options for the requested channel
- closing or interaction line
- source links in the text version

For poster cards, omit source links, source dates, “why it matters”, and long explanatory fields. Keep the poster skimmable.

## Unsupported Industries

Never fabricate a source, date, company action, or link.

Use `references/unsupported_industry_protocol.md` when:

- no config exists,
- the industry boundary is too broad,
- current public information is insufficient,
- high-quality sources cannot support enough candidates,
- results are mostly self-media, SEO pages, ads, job posts, stock-only content, or corporate soft copy.

If fewer than 12 high-quality candidates can be found, stop and ask the user for source sites, company names, a narrower subindustry, or permission to include older background sources.

## Poster QA

Always inspect the rendered image, not just the HTML or file size.

Check:

- image resolution,
- brand or logo visibility,
- no card overlap,
- no text overflow,
- no awkward line breaks,
- no splitting key terms,
- bottom area is not crowded.

The bottom area needs special care: do not squeeze the main theme, usage labels, selected-count labels, and footer brand into one tight zone. Shorten the mainline or split hierarchy before delivery.

## References

Load only what is needed:

- `references/industry_brief_template.md` for the full workflow.
- `references/config_schema.md` when creating or validating industry YAML configs.
- `references/candidate_pool_template.md` when drafting the candidate pool.
- `references/final_brief_template.md` when producing final outputs.
- `references/poster_qa_checklist.md` before delivering a poster.
- `references/unsupported_industry_protocol.md` for missing, broad, or low-information industries.

Sample configs live in `assets/configs/`.
