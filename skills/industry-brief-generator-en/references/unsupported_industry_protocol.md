# Unsupported or Low-Information Industry Protocol

Use this protocol when the requested industry does not exist in the available configs, the public information base is too weak, or a useful candidate pool cannot be generated safely.

## Missing Industry Config

If the user only gives an industry name and no config exists:

1. Do not run the candidate pool.
2. Create a draft industry config first.
3. Include likely source tiers, included topics, excluded topics, scoring, and poster terms.
4. Ask the user to confirm target market, focus topics, exclusions, and final use.

## Broad or Ambiguous Industry

If the industry is too broad, such as “manufacturing”, “technology”, or “consumer goods”, ask the user to narrow it.

Example:

```text
This industry is too broad for a reliable candidate pool. Please choose a narrower subindustry, such as chemicals, packaging materials, semiconductor equipment, machine tools, industrial automation, AI software, cloud computing, consumer electronics, pet products, beauty, baby care, or home goods.
```

## Insufficient Sources

If search cannot find enough high-quality sources:

1. Do not force 20 weak candidates.
2. State how many high-quality candidates were found.
3. Explain the gap.
4. Use 30-90 day background items only if clearly marked as background.
5. If fewer than 12 strong candidates remain, stop and ask for better sources or narrower scope.

Suggested response:

```text
Public information is currently too thin to generate a reliable candidate pool.

High-quality candidates found: {n}
Main gaps:
- too few authoritative industry sources
- low news frequency
- most results are corporate soft copy
- weak connection to the target market

Please provide:
- 2-5 preferred media or association sources
- key company names
- target countries or regions
- whether company announcements or trade show pages are allowed
```

## Low-Quality Items

Do not include:

- self-media summaries without original sources,
- corporate promotion with no industry impact,
- undated items,
- unclear regions,
- weak relevance to the requested focus,
- stock-only news, job posts, ads, directories, or booth-sales pages.

## Degraded Output

If the user explicitly asks for a first pass despite limited information, produce `10 observation leads` instead of a formal candidate pool.

Label each lead:

- A: authoritative industry media or official source
- B: company announcement, trade show, or association
- C: background report or market summary

State clearly that it is not a formal candidate pool and should not directly feed the final brief.

## Never Do

- Do not fabricate sources, dates, company actions, or links.
- Do not include weakly related items just to fill the list.
- Do not turn generic financial news into an industry trend.
- Do not generate final posters or formal briefs before the user confirms the final selection.
