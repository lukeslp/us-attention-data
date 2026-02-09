# US Attention Data

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Data Sources](https://img.shields.io/badge/Sources-Wikipedia%20%7C%20GDELT%20%7C%20Google%20Trends-green)](https://en.wikipedia.org/wiki/Special:Statistics)
[![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-HuggingFace-yellow)](https://huggingface.co/datasets/lukeslp/us-attention-data)

Weekly cross-platform attention metrics for tracking how much the world pays attention to the United States. Combines Wikipedia pageviews, GDELT global event mentions, and Google Trends search interest from 2020-2025.

I built this dataset for the [one-year](https://dr.eamer.dev/datavis/one-year/) visualization project, which maps US global sentiment over time. Part of the [Data Trove](https://dr.eamer.dev/datavis/data_trove/) collection.

---

## What's Inside

| File | Size | Description |
|------|------|-------------|
| `wikipedia_pageviews.json` | 2.5 MB | Daily pageview counts for US-related Wikipedia articles |
| `wikipedia_event_articles.json` | 214 KB | Event-linked article metadata |
| `wikipedia_trending.json` | 256 KB | Trending article detection |
| `trends_data.json` | 810 KB | Google Trends search interest over time |
| `weekly_trends.json` | 26 KB | Weekly trending topic aggregations |
| `gdelt_timeline.json` | 131 KB | GDELT event mention timelines |
| `gdelt_weekly_events.json` | 158 KB | GDELT weekly aggregated event counts and tone |
| `events_unified.json` | 89 KB | Unified event data across all sources |
| `weekly_attention_timeline.json` | 57 KB | Combined weekly attention metrics |
| `unified_data.json` | 27 KB | Merged dataset across all attention sources |
| `attention_metadata.json` | 2 KB | Collection metadata and schema |

**Total: ~4.2 MB**

---

## Quick Start

### Python

```python
import json

with open("wikipedia_pageviews.json") as f:
    pageviews = json.load(f)

# Weekly attention across all sources
with open("weekly_attention_timeline.json") as f:
    timeline = json.load(f)
```

### D3.js

```javascript
const pageviews = await d3.json("wikipedia_pageviews.json");
const gdelt = await d3.json("gdelt_weekly_events.json");
```

---

## Data Sources

| Source | What It Tracks | Coverage |
|--------|---------------|----------|
| [Wikipedia Pageviews API](https://wikimedia.org/api/rest_v1/) | Article view counts | 2020-2025, daily |
| [GDELT Project](https://www.gdeltproject.org/) | Global event mentions and media tone | 2020-2025, weekly |
| [Google Trends](https://trends.google.com/) | Search interest indices | 2020-2025, weekly |

---

## Use Cases

- Tracking how global attention to the US shifts over time
- Correlating media events with Wikipedia traffic and search interest
- Identifying seasonal attention patterns (elections, holidays, crises)
- Building composite attention indices from multiple independent signals

---

## Related

- [one-year visualization](https://dr.eamer.dev/datavis/one-year/) — the viz this data powers
- [Data Trove](https://dr.eamer.dev/datavis/data_trove/) — full dataset catalog
- [lukesteuber.com](https://lukesteuber.com) — portfolio

---

## License

MIT. See [LICENSE](LICENSE).

Data sourced from Wikipedia (CC BY-SA), GDELT (open), and Google Trends (fair use for research).

Collected and packaged by [Luke Steuber](https://lukesteuber.com).
