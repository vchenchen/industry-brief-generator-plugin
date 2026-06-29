# Industry Config Schema

Each industry can have a YAML config. Sample configs live in `assets/configs/{industry}.yaml`; projects may store their own configs anywhere convenient.

## Required Fields

```yaml
industry: office_supplies
industry_name: Office supplies
brand: OfficeBiz Daily
logo_preferred: assets/brand/officebiz-daily-square-logo.png
candidate_count: 20
final_count: 8
regions: []
sources: []
source_tiers:
  tier_1: []
  tier_2: []
  tier_3: []
include_topics: []
exclude_topics: []
writing_style: []
scoring:
  scale: 0-5
  weights:
    freshness: 1.0
    industry_impact: 1.0
    business_value: 1.0
    regional_relevance: 1.0
    novelty: 1.0
    actionability: 1.0
    source_quality: 1.0
  priority_rules: []
dedupe_keys: []
poster:
  size: 1080x1350
  scale: 2
  cover_title_max_chars: 56
  quick_read_max_chars: 36
  card_title_max_chars: 42
  output_pattern: outputs/{industry}/{brand_slug}-poster-{date}@2x.png
  avoid_line_break_terms: []
memory_rules:
  memory_path: outputs/{industry}/memory.md
  output_dir: outputs/{industry}
  remember: []
  avoid: []
```

## Source Tiers

- `tier_1`: industry media, associations, regulators, official trade shows, professional databases.
- `tier_2`: company announcements, PR Newswire, Business Wire, exchange filings, strong mainstream industry desks.
- `tier_3`: consulting summaries, market research excerpts, broad financial media; use only as background.

## Config Principles

- Keep `include_topics` specific to the industry.
- Use `exclude_topics` to block soft copy, social posts, generic finance, and weakly related content.
- Put key phrases in `avoid_line_break_terms` so poster text does not split important terms.
- Use `memory_rules.avoid` to prevent saving raw search noise or unsupported market-size claims.
