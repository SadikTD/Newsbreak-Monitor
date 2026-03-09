# 📰 Newsbreak Article Monitor

**Auto-fetch and track article performance across Newsbreak publisher pages.**

Built by **Sadik Hossain** — a single-file HTML tool designed to monitor articles published on Newsbreak by the Gamurs Network (We Got This Covered, Attack of the Fanboy, Curveball/Operation Sports). See which articles are getting the most engagement, filter by author, analyze author performance, and export data — all without logging into Newsbreak.

---

## ✨ Features

### 📰 Articles Tab
- **One-click auto-fetch** — Scans multiple Newsbreak publisher pages and extracts all article data automatically
- **Auto-pagination** — Fetches page 1, 2, 3... up to your configured limit
- **Smart enrichment** — Page 2+ articles are enriched in parallel (20 at a time) to pull full author names and metrics
- **Live timer** — Shows total elapsed time, ETA, speed (articles/sec), and progress during fetching
- **"My Articles" filter** — Pre-configured author names; one click to see only your articles with totals
- **Full filter suite** — Search by title/author, filter by publisher, author dropdown, date range picker
- **Sortable columns** — Click any column header to sort ascending/descending
- **Color-graded metrics** — Comments and reactions are color-coded from red (low) to green (high)
- **Emoji breakdown** — See the full reaction breakdown (👍 😡 ❤️ 😂 😮 😢) per article
- **CSV export** — Export filtered results with all data points

### 📊 Analytics Tab
- **Author Leaderboard** — Ranked table showing every author's total articles, comments, reactions, averages, and an engagement bar
- **Gold/Silver/Bronze badges** — Top 3 authors get medal-style rank indicators
- **Overview Cards** — Total articles, total comments, total reactions, and top author at a glance
- **Top 10 Articles by Comments** — See which articles generated the most discussion
- **Top 10 Articles by Reactions** — See which articles got the most emoji engagement
- **Publisher Breakdown** — Per-publisher stats including article count, averages, and contributing authors

### ⚙️ General
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
| Total Reactions | ✅ (sum of all emojis) | ✅ (enriched) |
| Emoji breakdown | ✅ | ✅ |
| Shares | ✅ | n/a* |
| Date | ✅ | ✅ |
| Newsbreak URL | ✅ | ✅ |

*\*Newsbreak does not expose vote counts or share counts on individual article pages. This is a confirmed platform limitation.*

## 🚀 Quick Start

2. **Open** the file in any modern browser — or host it on GitHub Pages
3. **Select** which publishers to scan (WGTC, AOTF, Curveball)
4. **Set** how many pages to fetch (default: 2)
5. **Click** "⚡ Fetch All Articles"
6. Switch to the **📊 Analytics** tab to see author performance breakdowns

## ⚙️ Configuration

Click the **⚙️ gear icon** in the header to access settings:

- **"My Articles" Author Names** — One name per line, case-insensitive partial match
- **Publisher URLs** — Change the Newsbreak publisher page URLs if needed
- **CORS Proxy** — Switch between Auto, AllOrigins, CorsProxy.io, or CodeTabs
- **Theme** — Light or Dark mode

## 🎨 Color Grading

Comments and reactions use a color scale for quick visual scanning:

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

**Auto-fetch fails** — Try switching CORS proxy in Settings. Free proxies can be temporarily down.

**Author shows "⏳ Loading..."** — The enrichment for that article failed. Re-fetch to retry.

**Votes/shares show "n/a"** — Expected for page 2+ articles. Newsbreak only provides this in page 1 data.

**Reactions count seems wrong** — Reactions = sum of ALL emoji types (👍+😡+❤️+😂+😮+😢), not just likes.

## 📄 License

Proprietary — All Rights Reserved. See LICENSE file for details. Unauthorized copying, modification, or distribution is strictly prohibited.

## 👤 Author

**Sadik Hossain** — Writer at WGTC / Gamurs Network

---

*Built with vanilla HTML, CSS, and JavaScript. No frameworks, no build steps, no server required.*
