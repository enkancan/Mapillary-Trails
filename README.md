# Mapillary Human Route Analysis

A comprehensive toolkit for analyzing Mapillary user contributions, movement patterns, and mapping behaviors. This project enables researchers and analysts to collect, visualize, and present street-level imagery data with user-specific insights.

## Purpose

This toolkit is designed for user behavior analysis, enabling systematic tracking of what users upload and how their mapping patterns evolve over time. It supports **route analysis by visualizing and evaluating user trails and spatial coverage areas. Through interest mapping, it identifies user-specific points of interest and recurring movement behaviors**. It also facilitates structured data collection, allowing Mapillary data to be gathered consistently for research and analysis purposes. Finally, it produces presentation-ready outputs, including publication-quality maps and animations to present.
## Features

### Mapillary.ipynb - Data Collection & User Analytics
Comprehensive analysis notebook for understanding user contributions and behaviors:

- **Bulk Image Download**: Systematically collect all Mapillary images in your study area
  - Quad-tree division algorithm to bypass API's 1000-image limit of Mapillary
  - Automatic retry mechanism for robust data collection
  - Multi-format support (JPEG, WebP, PNG)
    
<img width="1589" height="798" alt="output" src="https://github.com/user-attachments/assets/665cb1a9-8613-40df-acf3-3d64d9a738b8" />

- **User Contribution Analysis**:
  - Track individual user upload patterns
  - Identify most active contributors in the region
  - Analyze contribution frequency and coverage
  - Multi-user route comparison with color coding
    
<img width="1589" height="799" alt="output3" src="https://github.com/user-attachments/assets/5689595f-9592-4f8f-8362-efedd93208c3" />

- **Temporal Analysis**:
  - Year-by-year coverage evolution
  - Identify data collection gaps and trends
  - Track user activity over time

- **Data Management**:
  - Automatic CSV export with full metadata (coordinates, timestamps, usernames)
  - User-specific folder organization

### GIF_Street.ipynb - Route Visualization & Animation
Generate engaging animations to present user movement patterns:

- **9:16 Portrait Format** (1080x1920):
  - Mobile-optimized vertical layout
  - Aesthetic map tiles (CartoDB Positron)
  - Ready for social media and presentations
 

![map_street_SMART](https://github.com/user-attachments/assets/da908389-43ab-48b3-a8e3-4fb93c7a3ee0)

- **Smart Route Analysis**:
  - Greedy Nearest Neighbor sorting for logical route progression
  - Meter-based distance calculation for accurate paths
  - Synchronized map + street view animation
  - User-specific route animations

## Requirements

```bash
pip install pandas geopandas imageio matplotlib shapely contextily pillow numpy osmnx requests tqdm
```

## Quick Start with Sample Data

Try the visualization tools immediately with included sample data:

```python
# In GIF_Street.ipynb, update the configuration:
csv_path = Path("sample_data/metadata.csv")
image_folder = Path("sample_data")
```

The `sample_data/` folder contains 8 sample images from the Karaköy area (Istanbul) with metadata, perfect for testing all visualization features.

## Usage

### 1. Data Collection & Analysis (Mapillary.ipynb)

**Step 1: Configure Data Collection**
- Set your Mapillary API token
- Define BBOX coordinates for your study area 
- Optionally define polygon for precise area filtering

**Step 2: The Pipeline**
Execute cells sequentially to:
1. Download all images in region with full metadata
2. Filter by polygon boundary (optional)
3. Generate OSM overlay maps for spatial context
4. Perform temporal analysis (year-by-year breakdown)
5. Analyze user contributions and identify active mappers
6. Create multi-user route comparison visualizations
7. Organize files by user for individual analysis

**Output:**
- `data/mapillary/metadata.csv` - Full dataset with all attributes
- `mapillary_osm_plot.pdf` - Static map with geographic context
- `mapillary_users_routes.pdf` - Multi-user comparison map
- User-organized folders for individual analysis

### 2. Route Visualization & Presentation (GIF_Street.ipynb)

**Step 1: Select Data Source**
- Use `sample_data/` for testing
- Or use your collected data from `data/mapillary/`

**Step 2: Configure Analysis**
- Select target user for route analysis
- Define polygon area of interest
- Set animation parameters (frames, duration)

**Step 3: Generate Animations**
Choose from three visualization modes:
1. **9:16 Portrait Mode**: Aesthetic vertical format for mobile and presentations
2. **Smart Route Mode**: OSM-based map with street view sync
3. **Linear Route Mode**: Fast animation along defined path

**Output:**
- High-quality GIF animations showing user movement patterns
- Presentation-ready visualizations for reports and papers


## Study Area: Karaköy, Istanbul

### Why Karaköy?

Karaköy, a historic waterfront neighborhood in Istanbul, Turkey, was selected as the example study area for several reasons:

- **Dense Mapping Activity**: High concentration of Mapillary contributions from multiple users
- **Compact Geography**: Well-defined boundaries ideal for demonstrating polygon-based filtering
- **Historic Significance**: Rich urban fabric with diverse street characteristics
- **Multi-User Coverage**: Multiple contributors provide opportunities for comparative analysis
- **Representative Urban Area**: Typical characteristics of a historic city neighborhood

### Sample Data

The included `sample_data/` folder contains 8 street-level images from Karaköy contributed by the user "mapfool". This dataset demonstrates:
- **Route reconstruction** from GPS coordinates
- **Temporal metadata** analysis (capture dates and times)
- **Geographic filtering** by custom polygon boundaries
- **Presentation-ready visualizations** for academic and public outreach

The Karaköy polygon boundaries are pre-configured in both notebooks, making it easy to replicate the analysis or adapt it to your own study area.

## License

MIT License



