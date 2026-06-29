# 行业配置规范

每个行业一个 YAML 文件。Skill 自带示例配置在 `assets/configs/{industry}.yaml`；实际项目可放在任意约定目录，例如 `configs/{industry}.yaml`。

## 必填字段

```yaml
industry: office_supplies
industry_name_zh: 海外办公用品行业
brand: OfficeBiz Daily｜海外办公用品商业快报
logo_preferred: outputs/brand/officebiz-daily-square-logo.png
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
  cover_title_max_chars: 20
  quick_read_max_chars: 18
  card_title_max_chars: 18
  output_pattern: outputs/{industry}/{brand_slug}-poster-{date}@2x.png
  avoid_line_break_terms: []
memory_rules:
  memory_path: outputs/{industry}/memory.md
  output_dir: outputs/{industry}
  remember: []
  avoid: []
```

## 来源分级

- `tier_1`：行业权威媒体、协会、监管机构、官方展会、专业数据库。
- `tier_2`：企业公告、PR Newswire、Business Wire、交易所公告、头部媒体行业栏目。
- `tier_3`：咨询报告、市场研究摘要、泛财经媒体；只作补充。

## 配置原则

- 行业越垂直，`include_topics` 越要具体。
- `exclude_topics` 必须写清软文、自媒体、泛财经、弱相关内容。
- `avoid_line_break_terms` 必须包含行业核心中文术语。
- `memory_rules.avoid` 用来避免保存搜索噪音或未经证实的数据。
