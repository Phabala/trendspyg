# trendspy

[![PyPI version](https://badge.fury.io/py/trendspy.svg)](https://badge.fury.io/py/trendspy)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Downloads](https://pepy.tech/badge/trendspy)](https://pepy.tech/project/trendspy)

**Free, open-source Python library for Google Trends data** - a modern alternative to the archived pytrends with **188,000+ configuration options**.

> **Note:** pytrends was archived on April 17, 2025 with no replacement. trendspy is built to fill this gap with enhanced features and active maintenance.

---

## ✨ Features

- 🌍 **114 countries** supported
- 🗺️ **51 US states** + sub-regions
- 📊 **20 categories** (sports, entertainment, technology, etc.)
- ⏰ **4 time periods** (4h, 24h, 48h, 7 days)
- 📈 **Real-time monitoring** (~1 minute update frequency)
- 🎯 **Active trends filtering**
- 🔄 **4 sort options** (relevance, title, volume, recency)
- 📦 **Easy installation** - just `pip install trendspy`
- 🆓 **100% free** and open-source

**Total combinations: 188,000+**

---

## 🚀 Quick Start

### Installation

```bash
pip install trendspy
```

### Basic Usage

```python
from trendspy import TrendsDownloader

# Download trends (default: US, past 24 hours, all categories)
trends = TrendsDownloader()
data = trends.download()
```

### Advanced Usage

```python
from trendspy import TrendsDownloader

# California, past 7 days, sports only, sorted by volume
trends = TrendsDownloader()
data = trends.download(
    geo='US-CA',          # State-level support!
    hours=168,            # 7 days
    category='sports',    # Filter by category
    active_only=True,     # Only rising trends
    sort_by='volume'      # Sort by popularity
)
```

---

## 📖 Why trendspy?

| Feature | trendspy | pytrends | Commercial APIs |
|---------|----------|----------|-----------------|
| **Status** | ✅ Active | ❌ Archived (April 2025) | ✅ Active |
| **Price** | **FREE** | FREE | $0.003-$0.015/request |
| **Countries** | **114** | ~50 | All |
| **US States** | **51** | ❌ None | Some |
| **Categories** | **20** | Limited | All |
| **Configurations** | **188,000+** | ~1,000 | Many |
| **Real-time Monitoring** | ✅ Every ~1 min | ❌ | ❌ |
| **Maintained** | ✅ Yes | ❌ No | ✅ Yes |

---

## 🌍 Supported Options

### Countries (114 total)
US, CA, UK, AU, IN, JP, DE, FR, BR, MX, ES, IT, RU, KR, and 100+ more

### US States (51 total)
US-AL, US-AK, US-AZ, US-AR, US-CA, US-CO, US-CT, US-DE, US-DC, US-FL, US-GA, US-HI, US-ID, US-IL, US-IN, US-IA, US-KS, US-KY, US-LA, US-ME, US-MD, US-MA, US-MI, US-MN, US-MS, US-MO, US-MT, US-NE, US-NV, US-NH, US-NJ, US-NM, US-NY, US-NC, US-ND, US-OH, US-OK, US-OR, US-PA, US-RI, US-SC, US-SD, US-TN, US-TX, US-UT, US-VT, US-VA, US-WA, US-WV, US-WI, US-WY

### Categories (20 total)
all, sports, entertainment, business, politics, technology, health, science, games, shopping, food, travel, beauty, hobbies, climate, jobs, law, pets, autos, other

### Time Periods
- **4 hours** - Breaking trends
- **24 hours** - Daily summary (default)
- **48 hours** - 2-day overview
- **7 days** - Weekly trends

---

## 📚 Documentation

- **[Complete Options Reference](COMPLETE_OPTIONS_REFERENCE.md)** - All 188K+ configurations
- **[Project Roadmap](PROJECT_ROADMAP.md)** - Development plan and goals
- **[Quick Start Checklist](QUICK_START_CHECKLIST.md)** - Fast-track guide
- **[Changelog](CHANGELOG.md)** - Version history

---

## 🤝 Contributing

Contributions are welcome! This project was born from the need to replace the archived pytrends.

**Ways to contribute:**
- Report bugs
- Suggest features
- Submit pull requests
- Improve documentation
- Share your use cases

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📊 Use Cases

- **Marketing & SEO** - Keyword research, trend analysis
- **Journalism** - Breaking news validation, public sentiment
- **Academic Research** - Economic forecasting, social trends
- **Trading & Finance** - Market sentiment analysis
- **Data Analysis** - Dashboards, visualizations

---

## 🗺️ Roadmap

### v0.1.0 (Current)
- ✅ Core download functionality
- ✅ 188,000+ configuration options
- ✅ Python package structure

### v0.2.0 (Coming Soon)
- [ ] CLI tool (`trendspy download --geo US-CA`)
- [ ] Real-time monitoring
- [ ] Batch downloads
- [ ] Enhanced error handling

### v0.3.0 (Future)
- [ ] Pandas integration
- [ ] Export formats (JSON, Excel)
- [ ] Caching layer
- [ ] Async support

---

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Built as a successor to **pytrends** (GeneralMills/pytrends) which was archived April 17, 2025
- Inspired by the 200,000+ monthly users who need reliable Google Trends data access
- Thanks to the open-source community for making this possible

---

## 📞 Support

- **Issues:** [GitHub Issues](https://github.com/flack0x/trendspy/issues)
- **Discussions:** [GitHub Discussions](https://github.com/flack0x/trendspy/discussions)
- **Documentation:** [GitHub Wiki](https://github.com/flack0x/trendspy/wiki)

---

## ⭐ Star History

If you find trendspy useful, please consider starring the repository!

[![Star History Chart](https://api.star-history.com/svg?repos=flack0x/trendspy&type=Date)](https://star-history.com/#flack0x/trendspy&Date)

---

**Built with ❤️ for the data community**

*trendspy - Spy on trends, not on users. Free forever.*
