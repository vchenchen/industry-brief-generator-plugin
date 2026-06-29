---
name: industry-brief-generator-zh
description: Create reusable, candidate-first Chinese industry briefs for overseas markets. Use when the user wants an industry news briefing, daily/weekly industry digest, trend candidate pool, internal brief, Xiaohongshu/WeChat copy, or poster-style brief for any industry; especially when the user provides or should provide industry, target market, focus topics, excluded content, and final use. Also use when adapting the workflow to a new industry, creating an industry YAML config, or handling an unsupported/low-information industry without fabricating sources.
---

# Industry Brief Generator

Generate industry briefs in two stages: first a sourced candidate pool, then final brief assets only after the user selects the required number of items.

## Quick Start

If the user has not provided enough input, ask for:

```text
输入具体行业：
输入具体市场（如：欧美/亚太/全球）：
输入重点关注内容：如行业并购、价格、供需、扩产、政策、展会、新品
输入排除内容：如泛财经、自媒体、企业软文
输入最终用途：如小红书/公众号/内部简报/客户沟通
```

If the user provides all fields, run the candidate-pool stage. If the user only gives an industry name, create or locate a config draft first and stop.

## Required Workflow

1. Determine `industry`, `market`, `focus_topics`, `exclude_topics`, `final_use`, `candidate_count`, and `final_count`.
2. Load an industry YAML config if available. If missing, create a draft config first; do not run the candidate pool yet.
3. Browse/search current sources for news, policies, events, deals, pricing, product launches, and industry shifts. For current news, always verify dates and links.
4. Generate the candidate pool first. Do not produce final brief, poster, or social copy yet.
5. Wait for the user to select exactly `final_count` item numbers. Accept either inclusion wording, such as `保留1,2...`, or exclusion wording, such as `去掉3,4...`.
6. Generate final text and poster only after the selection is clear.
7. Render and visually inspect the poster. Fix layout issues before delivery.
8. Save useful run memory if the local project has an output/memory convention.

## Candidate Pool Contract

Output in Chinese. Use professional, concise, card-like writing. Include exactly `candidate_count` items unless the unsupported-industry protocol applies.

Each candidate must include:

- `【编号｜领域标签｜区域】标题`
- 来源/日期
- 一句话摘要
- 入选理由
- 适合角度
- 来源链接

End with:

```text
请回复{final_count}个编号，我将据此生成今日快报海报、文字版快报和小红书文案。
```

Adjust the final wording for `内部简报` or `客户沟通` when appropriate.

## Final Brief Contract

After selection, produce:

- Top brand area
- Cover headline
- Quick reads
- `final_count` news cards
- Main theme
- Priority expansion suggestions
- Title options for the requested channel
- Closing/interaction line
- Source links in the text version

For poster cards, omit source links, source dates, “why it matters”, and long explanatory fields. Keep the poster skimmable.

## Unsupported Industries

Never fabricate a source, date, company action, or link.

Use `references/unsupported_industry_protocol.md` when:

- no config exists,
- the industry boundary is too broad,
- current public information is insufficient,
- high-quality sources cannot support enough candidates,
- results are mostly self-media, SEO pages, ads, job posts, stock-only content, or company soft copy.

If fewer than 12 high-quality candidates can be found, stop and ask the user for source sites, company names, a narrower subindustry, or permission to include older/background sources.

## Poster QA

Always inspect the rendered image, not just the HTML or file size.

Check:

- image resolution,
- brand/logo visibility,
- no card overlap,
- no text overflow,
- no awkward Chinese line breaks,
- no splitting key terms,
- bottom area is not crowded.

The bottom area needs special care: do not squeeze “今日主线”, usage labels such as “内部简报”, selected-count labels such as “精选8条”, and footer brand into one tight zone. Shorten the mainline or split hierarchy before delivery.

## References

Load only what is needed:

- `references/industry_brief_template.md` for the full workflow.
- `references/config_schema.md` when creating or validating industry YAML configs.
- `references/candidate_pool_template.md` when drafting the candidate pool.
- `references/final_brief_template.md` when producing final outputs.
- `references/poster_qa_checklist.md` before delivering a poster.
- `references/unsupported_industry_protocol.md` for missing, broad, or low-information industries.

Sample configs live in `assets/configs/`.
