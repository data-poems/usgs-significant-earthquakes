---
license: cc0-1.0
task_categories:
  - feature-extraction
language:
  - en
tags:
  - earthquakes
  - usgs
  - seismology
  - geospatial
  - natural-disasters
  - north-america
  - earth-science
  - geology
pretty_name: USGS M4.5+ North American Earthquakes (2000-2025)
size_categories:
  - 1K<n<10K
dataset_info:
  features:
    - name: latitude
      dtype: float64
    - name: longitude
      dtype: float64
    - name: name
      dtype: string
    - name: description
      dtype: string
    - name: category
      dtype: string
    - name: date
      dtype: string
    - name: magnitude
      dtype: float64
  splits:
    - name: train
      num_examples: 3742
---

# USGS M4.5+ North American Earthquakes (2000-2025)

3,742 significant earthquakes (magnitude 4.5+) across North America.

## What's Inside

- 3,742 earthquakes over 25 years
- Magnitude 4.5+ only (felt regionally)
- North American coverage (20°N-70°N, 170°W-65°W)
- Complete coordinates for mapping
- Removes 92.5% of minor tremors

## Geographic Coverage

| Region | Latitude | Longitude |
|--------|----------|-----------|
| North | 70°N | - |
| South | 20°N | - |
| West | - | 170°W |
| East | - | 65°W |

Covers continental US, Canada, Mexico, Alaska, and Caribbean.

## Record Structure

```json
{
  "latitude": 34.0522,
  "longitude": -118.2437,
  "name": "10km SSE of Ridgecrest, CA",
  "description": "M7.1 earthquake",
  "category": "usgs_earthquakes",
  "date": "2019-07-06",
  "magnitude": 7.1
}
```

## Usage

```python
import json
import pandas as pd

with open('usgs_significant_earthquakes.json') as f:
    quakes = json.load(f)

df = pd.DataFrame(quakes)
print(f"Total earthquakes: {len(df):,}")

# Find major earthquakes (M6+)
major = df[df['magnitude'] >= 6.0]

# Group by year
df['year'] = pd.to_datetime(df['date']).dt.year
yearly = df.groupby('year').size()
```

## Source & License

Public Domain -- U.S. Government Work. Data from USGS Earthquake Hazards Program.

https://earthquake.usgs.gov/earthquakes/

## Distribution

- **Kaggle**: [lucassteuber/usgs-significant-earthquakes](https://www.kaggle.com/datasets/lucassteuber/usgs-significant-earthquakes)
- **HuggingFace**: [lukeslp/usgs-significant-earthquakes](https://huggingface.co/datasets/lukeslp/usgs-significant-earthquakes)
- **GitHub Gist**: [Demo Notebook](https://gist.github.com/lukeslp/98c82e896ad688a4fc0407a3b76e59f7)

## Author

Luke Steuber | luke@lukesteuber.com | @lukesteuber.com (Bluesky)

## Structured Data (JSON-LD)

```json
{
  "@context": "https://schema.org",
  "@type": "Dataset",
  "name": "USGS M4.5+ North American Earthquakes (2000-2025)",
  "description": "3,742 significant earthquakes (magnitude 4.5+) across North America from USGS Earthquake Hazards Program. Filters out 92.5% of minor tremors.",
  "url": "https://www.kaggle.com/datasets/lucassteuber/usgs-significant-earthquakes",
  "sameAs": "https://huggingface.co/datasets/lukeslp/usgs-significant-earthquakes",
  "license": "https://creativecommons.org/publicdomain/zero/1.0/",
  "creator": {
    "@type": "Person",
    "name": "Luke Steuber",
    "url": "https://lukesteuber.com"
  },
  "keywords": ["earthquakes", "USGS", "seismology", "natural disasters", "geospatial", "North America"],
  "temporalCoverage": "2000/2025",
  "spatialCoverage": {
    "@type": "Place",
    "name": "North America"
  },
  "distribution": [
    {
      "@type": "DataDownload",
      "encodingFormat": "application/json",
      "contentUrl": "https://www.kaggle.com/datasets/lucassteuber/usgs-significant-earthquakes"
    }
  ]
}
```
