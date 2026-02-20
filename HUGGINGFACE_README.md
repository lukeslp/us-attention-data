---
license: mit
task_categories:
- time-series-forecasting
- text-classification
language:
- en
tags:
- attention-metrics
- wikipedia
- google-trends
- gdelt
- pageviews
- search-interest
- media-coverage
- sentiment-analysis
- event-tracking
pretty_name: US Attention Data
size_categories:
- 1K<n<10K
---

# US Attention Data

Digital attention metrics tracking Wikipedia pageviews, Google Trends search interest, and GDELT global event coverage for United States-related topics throughout 2025.

## Dataset Description

This dataset aggregates attention signals from three authoritative sources to track how digital attention flows around US-related topics:

- **Wikipedia Pageviews** (Wikimedia REST API) - 2.5MB tracking 8 key articles across countries
- **Google Trends** (pytrends API) - 810KB covering 138 search terms in the US region
- **GDELT 2.1** (Doc API) - Event mentions across 44 countries

### Use Cases

- Media attention analysis
- Event impact measurement
- Search trend correlation
- Cross-platform attention patterns
- News cycle dynamics
- Public interest tracking

## Dataset Structure

### Data Files (10 total, 4.3 MB)

#### Wikipedia Pageviews
- `wikipedia_pageviews.json` - 2.5 MB - Country-level pageview analysis
- `wikipedia_trending.json` - 250 KB - Top 500 trending articles
- `wikipedia_event_articles.json` - 210 KB - Event-driven article tracking

#### Google Trends
- `trends_data.json` - 810 KB - 138 search terms, full year time series
- `weekly_trends.json` - 26 KB - Weekly aggregated snapshot

#### GDELT Event Coverage
- `gdelt_timeline.json` - 131 KB - 44 countries, event mentions
- `gdelt_weekly_events.json` - 158 KB - Weekly event aggregation

#### Unified Cross-Source
- `events_unified.json` - 88 KB - 177 events combined
- `unified_data.json` - 27 KB - High-level unified analysis
- `weekly_attention_timeline.json` - 56 KB - Weekly cross-platform metrics

### Metadata Files

Each data file has a companion `*_metadata.json` with:
- Source API details
- Field descriptions
- Update timestamps
- Record counts
- Usage notes

## Data Collection

### Wikipedia (Wikimedia REST API)
- **Endpoint**: `https://wikimedia.org/api/rest_v1`
- **Auth**: None required
- **Rate Limit**: 5000 req/hour per IP
- **License**: CC0 Public Domain

### Google Trends (pytrends)
- **Package**: `pytrends` Python library
- **Auth**: None required
- **Rate Limit**: Soft limits (use responsibly)
- **License**: Google Terms of Service

### GDELT (GDELT 2.1 Doc API)
- **Endpoint**: `https://api.gdeltproject.org/api/v2/doc/doc`
- **Query**: `("United States" OR "United States of America")`
- **Auth**: None required
- **License**: Free for research and commercial use

## Loading the Data

```python
import json
import pandas as pd

# Load Wikipedia pageviews
with open('data/wikipedia_pageviews.json') as f:
    wp_data = json.load(f)

# Load Google Trends
trends = pd.read_json('data/trends_data.json')

# Load GDELT events
with open('data/gdelt_timeline.json') as f:
    gdelt = json.load(f)
```

## Key Findings

- **Wikipedia** serves as primary information source with event-driven pageview spikes
- **Google Trends** shows search volatility averaging 3-5 day persistence
- **GDELT** reveals uneven global media coverage (Western bias)
- **Cross-source correlation** during major events (disasters, elections, conflicts)
- **Attention decay** follows exponential curve with 2-4 day half-life

## Visualizations

Three live dashboards built on this data:

1. **One-Year US Global Sentiment** - [dr.eamer.dev/datavis/one-year](https://dr.eamer.dev/datavis/one-year)
   - Uses: `gdelt_timeline.json`
   - Visualizes global media coverage patterns

2. **Trends 2025** - [dr.eamer.dev/datavis/trends-2025](https://dr.eamer.dev/datavis/trends-2025)
   - Uses: `trends_data.json`
   - Interactive Google Trends dashboard

3. **Wikipedia Attention Analytics** - [dr.eamer.dev/datavis/wiki-attention](https://dr.eamer.dev/datavis/wiki-attention)
   - Uses: `wikipedia_pageviews.json`
   - Pageview trend analysis

## Citation

```bibtex
@dataset{steuber2026attention,
  title={US Attention Data: Digital Attention Metrics from Wikipedia, Google Trends, and GDELT},
  author={Steuber, Luke},
  year={2026},
  publisher={HuggingFace},
  url={https://huggingface.co/datasets/lukeslp/us-attention-data}
}
```


## Distribution

- **GitHub**: [lukeslp/us-attention-data](https://github.com/lukeslp/us-attention-data)
- **Kaggle**: [lucassteuber/us-attention-data](https://www.kaggle.com/datasets/lucassteuber/us-attention-data)

## License

MIT License - See LICENSE file for details.

Data sources have their own licenses:
- Wikipedia data: CC0 Public Domain
- Google Trends: Subject to Google Terms of Service
- GDELT: Free for research and commercial use

## About

Created by Luke Steuber

- **Website**: [lukesteuber.com](https://lukesteuber.com)
- **Portfolio**: [dr.eamer.dev](https://dr.eamer.dev)
- **Bluesky**: [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com)
