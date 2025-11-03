# Configurable Google Trends Downloader - Complete Guide

## Overview

The **configurable downloader** allows you to download Google Trends data with custom filters all from **one script**. No need to visit the website - just specify your parameters and get the data you need!

---

## Features

Configure every aspect of your Google Trends download:
- **Location**: 100+ countries (US, CA, UK, IN, JP, BR, etc.)
- **Time Period**: Past 4 hours, 24 hours, 48 hours, or 7 days
- **Category**: Sports, Entertainment, Politics, Technology, and 17+ more
- **Active Trends**: Filter to show only currently active trends
- **Sort By**: Relevance, Title, Search Volume, or Recency

---

## Quick Start

### Basic Usage (Defaults: US, Past 24 hours, All categories)

```bash
py simple_downloaders/download_trends_configurable.py
```

### With Custom Filters

```bash
# Canada, Past 4 hours, Sports only
py simple_downloaders/download_trends_configurable.py --geo CA --hours 4 --category sports

# UK, Past 7 days, Entertainment, sorted by volume
py simple_downloaders/download_trends_configurable.py --geo UK --hours 168 --category entertainment --sort volume

# India, Active trends only
py simple_downloaders/download_trends_configurable.py --geo IN --active-only

# Japan, All categories, sorted by recency
py simple_downloaders/download_trends_configurable.py --geo JP --sort recency
```

### Windows Batch File

For easier Windows usage, use the batch file:

```cmd
REM Default (US, 24h, all)
batch_scripts\download_custom.bat

REM Canada, 4h, sports
batch_scripts\download_custom.bat CA 4 sports

REM UK, 7 days (168h), entertainment
batch_scripts\download_custom.bat UK 168 entertainment
```

---

## All Parameters

### `--geo` (Location / Country Code)

**Description**: Select which country's trends to download
**Default**: `US`
**Format**: 2-letter country code

**Popular Options**:
```
US  - United States
CA  - Canada
UK  - United Kingdom
AU  - Australia
IN  - India
JP  - Japan
DE  - Germany
FR  - France
BR  - Brazil
MX  - Mexico
ES  - Spain
IT  - Italy
RU  - Russia
KR  - South Korea
CN  - China
```

**Examples**:
```bash
--geo US    # United States
--geo CA    # Canada
--geo JP    # Japan
```

---

### `--hours` (Time Period)

**Description**: How far back to look for trending topics
**Default**: `24` (past 24 hours)
**Options**: `4`, `24`, `48`, `168`

**Mapping**:
```
4    - Past 4 hours
24   - Past 24 hours (default)
48   - Past 48 hours
168  - Past 7 days (168 hours)
```

**Examples**:
```bash
--hours 4      # Last 4 hours (very recent trends)
--hours 24     # Last day
--hours 168    # Last week
```

---

### `--category` (Topic Category)

**Description**: Filter trends by topic category
**Default**: `all` (no filter)

**Available Categories**:
```
all             - All categories (default, no filter)
sports          - Sports (football, basketball, baseball, etc.)
entertainment   - Movies, TV shows, celebrities, music
business        - Business news, stocks, companies
politics        - Political news, elections, government
technology      - Tech news, gadgets, software, startups
health          - Medical news, fitness, wellness
science         - Scientific discoveries, research
games           - Video games, gaming news
shopping        - Products, deals, e-commerce
food            - Recipes, restaurants, cooking
travel          - Tourism, destinations, hotels
beauty          - Fashion, cosmetics, style
hobbies         - DIY, crafts, collectibles
climate         - Weather, climate news
jobs            - Employment, careers, hiring
law             - Legal news, court cases
pets            - Animals, pet care
other           - Miscellaneous topics
```

**Examples**:
```bash
--category sports          # Only sports trends
--category technology      # Only tech trends
--category entertainment   # Only entertainment trends
```

---

### `--active-only` (Active Trends Filter)

**Description**: Show only trends that are currently active (still rising)
**Default**: Off (shows all trends, active or ended)
**Format**: Flag (no value needed)

**Examples**:
```bash
--active-only    # Only show currently trending topics
```

---

### `--sort` (Sort Order)

**Description**: How to order the results
**Default**: `relevance` (Google's recommended order)

**Options**:
```
relevance  - By relevance (default, Google's algorithm)
title      - Alphabetically by title (A-Z)
volume     - By search volume (highest first)
recency    - By recency (newest first)
```

**Examples**:
```bash
--sort relevance   # Most relevant trends first
--sort volume      # Most searched trends first
--sort recency     # Newest trends first
--sort title       # Alphabetical order
```

---

### `--visible` (Show Browser)

**Description**: Run the browser in visible mode instead of headless
**Default**: Off (headless mode)
**Format**: Flag (no value needed)
**Use Case**: Debugging or watching the script work

**Example**:
```bash
--visible    # See the browser window during download
```

---

### `--output-dir` (Custom Output Directory)

**Description**: Specify where to save the downloaded file
**Default**: `downloads/` folder in project directory

**Example**:
```bash
--output-dir "C:\My Data\Trends"    # Save to custom folder
```

---

## Complete Examples

### Example 1: Hot Sports Trends (Past 4 hours)
```bash
py simple_downloaders/download_trends_configurable.py \
    --geo US \
    --hours 4 \
    --category sports \
    --sort volume
```
**Use Case**: See what sports topics are trending RIGHT NOW, ordered by popularity

---

### Example 2: Weekly Technology Trends (UK)
```bash
py simple_downloaders/download_trends_configurable.py \
    --geo UK \
    --hours 168 \
    --category technology \
    --sort recency
```
**Use Case**: Technology trends in UK over the past week, newest first

---

### Example 3: Active Entertainment Trends (Global)
```bash
py simple_downloaders/download_trends_configurable.py \
    --geo US \
    --category entertainment \
    --active-only \
    --sort volume
```
**Use Case**: Currently hot entertainment topics, by search volume

---

### Example 4: All Canadian Trends (Default Sort)
```bash
py simple_downloaders/download_trends_configurable.py --geo CA
```
**Use Case**: Simple download of all Canadian trends from past 24 hours

---

### Example 5: Multiple Countries Comparison

Download trends from multiple countries for comparison:

```bash
# United States
py simple_downloaders/download_trends_configurable.py --geo US --hours 24 --category sports

# Canada
py simple_downloaders/download_trends_configurable.py --geo CA --hours 24 --category sports

# UK
py simple_downloaders/download_trends_configurable.py --geo UK --hours 24 --category sports
```

---

## Output Files

Files are automatically named with your configuration:

**Format**: `trends_{GEO}_{HOURS}h_{CATEGORY}_{TIMESTAMP}.csv`

**Examples**:
```
trends_US_24h_all_20251103-120530.csv
trends_CA_4h_sports_20251103-120645.csv
trends_UK_168h_entertainment_20251103-120730.csv
trends_JP_24h_technology_20251103-120815.csv
```

This makes it easy to organize and identify your downloads!

---

## Tips & Best Practices

### 1. Start with Defaults
```bash
# Test first with default settings
py simple_downloaders/download_trends_configurable.py
```

### 2. Narrow Down for Specific Needs
```bash
# Too much data? Add filters!
--category sports --hours 4 --active-only
```

### 3. Compare Across Time Periods
```bash
# Past 4 hours
py simple_downloaders/download_trends_configurable.py --geo US --hours 4 --category politics

# Past 7 days
py simple_downloaders/download_trends_configurable.py --geo US --hours 168 --category politics
```

### 4. Track Active vs All Trends
```bash
# All trends (including ended ones)
py simple_downloaders/download_trends_configurable.py --geo US --category technology

# Only active (currently rising)
py simple_downloaders/download_trends_configurable.py --geo US --category technology --active-only
```

### 5. Use Batch Files for Repetitive Tasks
```cmd
REM Create a custom batch file for your specific needs
@echo off
py simple_downloaders/download_trends_configurable.py --geo US --hours 4 --category sports --sort volume
pause
```

---

## Common Use Cases

### Marketing & Advertising
```bash
# What's trending now in your target market?
--geo US --hours 4 --category shopping --sort volume --active-only
```

### News & Journalism
```bash
# Breaking news trends
--geo US --hours 4 --category politics --sort recency
```

### Content Creation
```bash
# Weekly entertainment topics for content ideas
--geo US --hours 168 --category entertainment --sort volume
```

### Research & Analytics
```bash
# Comprehensive data for analysis
--geo US --hours 168 --category all
```

### Competitive Intelligence
```bash
# Monitor specific industries
--geo US --category technology --sort volume
--geo US --category business --sort volume
```

---

## Troubleshooting

### Problem: "No such file or directory"
**Solution**: Make sure you're in the project root directory
```bash
cd "C:\Users\YourName\Desktop\Googletrends"
py simple_downloaders/download_trends_configurable.py
```

### Problem: "ChromeDriver not found"
**Solution**: Install ChromeDriver matching your Chrome version
- Check Chrome version: `chrome://version`
- Download from: https://chromedriver.chromium.org/downloads
- Add to PATH or place in project folder

### Problem: Small file size (< 1 KB)
**Solution**: Category might be empty for that geo/time combination
- Try a different category or time period
- Use `--visible` flag to see what's happening

### Problem: Sort option doesn't apply
**Solution**: This is a known issue with some configurations
- The data still downloads correctly
- Sort will default to "relevance"
- Sorting feature is best-effort due to Google's dynamic UI

---

## Comparison: Simple vs Configurable

### Simple Downloader
```bash
py simple_downloaders/download_trends_simple.py
```
- ✅ **Pros**: Fastest, simplest
- ❌ **Cons**: US only, 24h only, all categories only

### Configurable Downloader
```bash
py simple_downloaders/download_trends_configurable.py --geo CA --hours 4 --category sports
```
- ✅ **Pros**: Full control, any country, any time period, any category
- ❌ **Cons**: Slightly slower due to filter application

**Recommendation**: Use configurable for most tasks, simple only for quick US downloads

---

## Advanced: Automation & Scheduling

### Windows Task Scheduler Example

1. Create a batch file:
```cmd
@echo off
cd "C:\Path\To\Googletrends"
py simple_downloaders/download_trends_configurable.py --geo US --category technology --sort volume
```

2. Schedule it in Task Scheduler:
   - Run every hour
   - Run every morning at 9 AM
   - Run daily at midnight

### Python Script Example

```python
import subprocess

# Download multiple configurations
configs = [
    ['--geo', 'US', '--category', 'sports'],
    ['--geo', 'CA', '--category', 'sports'],
    ['--geo', 'UK', '--category', 'sports']
]

for config in configs:
    subprocess.run(['py', 'simple_downloaders/download_trends_configurable.py'] + config)
```

---

## FAQ

### Q: Can I download trends from multiple countries at once?
**A**: Run the script multiple times with different `--geo` values, or create a batch/Python script to automate it.

### Q: What's the difference between 4 hours and 24 hours?
**A**: 4 hours shows very recent "breaking" trends, while 24 hours shows broader daily trends. Use 4h for real-time monitoring, 24h for daily summaries.

### Q: Why are some categories empty?
**A**: Not all categories have trends for every country/time period. Try a broader category or longer time period.

### Q: Can I filter by specific keywords?
**A**: Not directly, but you can download all trends and filter the CSV file afterward using Python/Excel.

### Q: How often does Google update trends?
**A**: CSV data updates approximately every minute, so you can run this script frequently for near-real-time data.

---

## Need Help?

1. **Check the help menu**:
   ```bash
   py simple_downloaders/download_trends_configurable.py --help
   ```

2. **View this guide**: `CONFIGURABLE_DOWNLOADER_GUIDE.md`

3. **Check main README**: `README.md`

4. **Use visible mode to debug**:
   ```bash
   --visible
   ```

---

**Happy Trend Tracking!** 📊🌍
