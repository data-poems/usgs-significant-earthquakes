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
---

# USGS M4.5+ North American Earthquakes (2000-2025)

3,742 significant earthquakes (magnitude 4.5+) across North America

USGS Earthquake Hazards Program data filtered to magnitude 4.5+ events in North America from 2000-2025. Removes minor tremors to highlight earthquakes of scientific and public interest.

## Dataset Structure

See `demo_notebook.ipynb` for data exploration examples.

## Usage

```python
from datasets import load_dataset

# Load the dataset
dataset = load_dataset("lukeslp/usgs-significant-earthquakes")

# Or load from local files
import json
with open('data.json') as f:
    data = json.load(f)
```

## Citation

```bibtex
@dataset{usgs_significant_earthquakes_2026,
  title = {USGS M4.5+ North American Earthquakes (2000-2025)},
  author = {Steuber, Luke},
  year = {2026},
  url = {https://huggingface.co/datasets/lukeslp/usgs-significant-earthquakes}
}
```


## Distribution

- **GitHub**: [lukeslp/usgs-significant-earthquakes](https://github.com/lukeslp/usgs-significant-earthquakes)
- **Kaggle**: [lucassteuber/usgs-significant-earthquakes](https://www.kaggle.com/datasets/lucassteuber/usgs-significant-earthquakes)

## Author

**Luke Steuber**
- Website: [lukesteuber.com](https://lukesteuber.com)
- Bluesky: [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com)
- Email: luke@lukesteuber.com

## License

CC0-1.0
