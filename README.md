# 📰 Newsbreak Article Monitor

**Auto-fetch and track article performance across Newsbreak publisher pages.**

Built by **Sadik Hossain** — a single-file HTML tool designed to monitor articles published on Newsbreak by the Gamurs Network (We Got This Covered, Attack of the Fanboy, Curveball/Operation Sports). See which articles are getting the most engagement, filter by author, and export data — all without logging into Newsbreak.

![Newsbreak Monitor Screenshot](screenshot.png)

---

## ✨ Features

- **One-click auto-fetch** — Scans multiple Newsbreak publisher pages and extracts all article data automatically
- **Auto-pagination** — Fetches page 1, 2, 3... up to your configured limit
- **Smart enrichment** — Page 2+ articles are enriched in parallel (20 at a time) to pull full author names and metrics
- **Live timer** — Shows elapsed time, ETA, speed (articles/sec), and progress during fetching
- **"My Articles" filter** — Pre-configured author names; one click to see only your articles with totals
- **Full filter suite** — Search by title/author, filter by publisher, author dropdown, date range picker
- **Sortable columns** — Click any column header to sort ascending/descending
- **Color-graded metrics** — Comments and reactions are color-coded from red (low) to green (high)
- **Emoji breakdown** — See the full reaction breakdown (👍 😡 ❤️ 😂 😮 😢) per article
- **CSV export** — Export filtered results with all data points
- **Dark mode** — Toggle between light and dark themes
- **Settings panel** — Customize author names, publisher URLs, CORS proxy, and theme
- **Persistent settings** — All preferences saved in localStorage
- **Zero dependencies** — Single HTML file, no build tools, no server needed

## 📊 Data Points Extracted

| Field | Page 1 | Page 2+ |
|-------|--------|---------|
| Title | ✅ | ✅ |
| Author | ✅ | ✅ (enriched) |
| Votes (up/down) | ✅ | n/a* |
| Comments | ✅ | ✅ |
| Reactions/Likes | ✅ | ✅ (enriched) |
| Emoji breakdown | ✅ | ✅ |
| Shares | ✅ | n/a* |
| Date | ✅ | ✅ |
| Newsbreak URL | ✅ | ✅ |
| Category | ✅ | ✅ |

*\*Newsbreak does not expose vote counts or share counts on individual article pages. This is a platform limitation.*

## 🚀 Quick Start

1. **Open** the file in any modern browser 
2. **Select** which publishers to scan (WGTC, AOTF, Curveball)
3. **Set** how many pages to fetch (default: 2 = ~20 articles per publisher)
4. **Click** "⚡ Fetch All Articles"
5. Done! Browse, filter, sort, and export your data.

## ⚙️ Configuration

Click the **⚙️ gear icon** in the header to access settings:

- **"My Articles" Author Names** — Add one name per line. These are matched case-insensitively. Pre-configured with: Sadik Hossain, Towhid Rafid, Sayed
- **Publisher URLs** — Change the Newsbreak publisher page URLs if needed
- **CORS Proxy** — Switch between Auto (tries all), AllOrigins, CorsProxy.io, or CodeTabs
- **Theme** — Light or Dark mode

All settings persist across sessions via localStorage.

## 🏗️ How It Works

The tool operates in two phases:

### Phase 1: Listing Scan
Fetches each publisher's Newsbreak page (including pagination) via a CORS proxy. Extracts the `__NEXT_DATA__` JSON embedded in the HTML, which contains article titles, dates, comments, reactions, and (for page 1 only) full author names, vote counts, and share counts.

### Phase 2: Article Enrichment
For page 2+ articles (which lack author names in the listing data), the tool fetches each individual article's Newsbreak page in parallel (20 at a time) and extracts the author name, like count, and comment count from that page's `__NEXT_DATA__`.

## 🎨 Color Grading

Comments and reactions use a color scale to quickly identify high-performing articles:

| Range | Color | Meaning |
|-------|-------|---------|
| 0–10 | 🔴 Red | Very low |
| 10–50 | 🟠 Orange | Low |
| 50–100 | 🟣 Magenta | Decent |
| 100–200 | 🟣 Purple | Good |
| 200–500 | 🔵 Blue | Very good |
| 500–1K | 🟢 Green | Great |
| 1K+ | 🟢 Dark Green | Excellent |

## 🔧 Troubleshooting

**Auto-fetch fails or times out**
- Try switching the CORS proxy in Settings (⚙️). Some proxies work better in different regions.
- If all proxies fail, the free proxy services may be temporarily down. Try again in a few minutes.

**Author shows "⏳ Loading..." after fetch completes**
- The individual article page may have failed to load. Click "Fetch All Articles" again — already-loaded articles won't be duplicated, and it will retry the failed ones.

**Votes and shares show "n/a"**
- This is expected for page 2+ articles. Newsbreak only provides vote/share data in page 1 listing results. There is no workaround for this platform limitation.

## 📝 Pre-configured Publishers

| Publisher | Newsbreak Slug |
|-----------|---------------|
| We Got This Covered | `we-got-this-covered-313382434` |
| Attack of the Fanboy | `attack-of-the-fanboy-313403529` |
| Curveball | `curveball-313400612` |

You can add or change publishers in Settings.

## 📄 License

MIT License — free to use, modify, and distribute.

## 👤 Author

**Sadik Hossain** — Digital Editor & Content Creator at WGTC / Gamurs Network

---

*Built with vanilla HTML, CSS, and JavaScript. No frameworks, no build steps, no server required.*
