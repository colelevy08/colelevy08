<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=175539&height=200&section=header&text=Cole%20Levy&fontSize=60&fontColor=f7f1e3&fontAlignY=38&desc=Full-Stack%20%26%20AI%20Engineer%20%E2%80%94%20Saratoga%20Springs%2C%20NY&descAlignY=58&descSize=18&animation=fadeIn" width="100%" alt="Cole Levy" />
</div>

<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=22&duration=2800&pause=1200&color=0EA5E9&center=true&vCenter=true&width=760&lines=Shipping+products+and+trading+systems+that+run+real+businesses;Portmint+Pulse%3A+open+source%2C+front+and+center;Post+time%3A+anytime" alt="Typing SVG" />
</div>

<br/>

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-175539?style=for-the-badge&logo=linkedin&logoColor=f7f1e3)](https://linkedin.com/in/colelevy)
[![Portfolio](https://img.shields.io/badge/Portfolio-175539?style=for-the-badge&logo=vercel&logoColor=f7f1e3)](https://colelevy.dev)
[![Dev.to](https://img.shields.io/badge/Dev.to-175539?style=for-the-badge&logo=devdotto&logoColor=f7f1e3)](https://dev.to/colelevy)
[![Email](https://img.shields.io/badge/Email-c03428?style=for-the-badge&logo=gmail&logoColor=f7f1e3)](mailto:colelevy08@gmail.com)

</div>

---

<div align="center">

### 🏇 The Summer Meet — Saratoga Springs, NY

|  |  |  |  |
|:---:|:---:|:---:|:---:|
| **15+** | **3** | **2** | **Anytime** |
| Projects shipped | Client retainers | Live trading systems | Post time |

</div>

---

## 🏆 Feature races — the two I'd show first

### 🥇 Portmint Pulse — open source, running in one line

**The live-limit instrument for Claude Code.** Reads your *real* OAuth rate-limit windows — live, local, before you hit the wall — and puts them everywhere you work: a browser dashboard, a terminal status line, a desktop warning at 80/95/100%, and a usage archive that survives Claude Code's own ~30-day transcript cleanup.

[![CI](https://github.com/colelevy08/portmint-pulse/actions/workflows/ci.yml/badge.svg)](https://github.com/colelevy08/portmint-pulse/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-34e0b3.svg)](https://github.com/colelevy08/portmint-pulse/blob/main/LICENSE)
[![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-2bd3a6.svg)](https://www.python.org/downloads/)
[![Platforms](https://img.shields.io/badge/platforms-macOS%20%C2%B7%20Windows%20%C2%B7%20Linux-0ea5e9.svg)](https://github.com/colelevy08/portmint-pulse#install)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-5cf0c4.svg)](https://github.com/colelevy08/portmint-pulse/blob/main/CONTRIBUTING.md)

**Get it running right now:**

```bash
pipx install git+https://github.com/colelevy08/portmint-pulse.git && portmint-pulse
```

No `pipx`? `git clone` + `python3 app.py` works with **zero dependencies** on macOS/Linux. Don't want to install anything — **[try the live demo →](https://colelevy08.github.io/portmint-pulse/)** (runs in your browser, fabricated data, no signup).

<div align="center">
  <img src="https://raw.githubusercontent.com/colelevy08/portmint-pulse/main/assets/screenshot.png" width="760" alt="Portmint Pulse dashboard — live rate-limit bars, token and cost trends by model and project" />
</div>

- Pure Python **standard library** — no Node, no build step, no cloud dependency
- Reads **live OAuth rate-limit windows** (not inferred from logs) — a desktop toast fires before you get throttled mid-task
- **Zero telemetry**, localhost-only, read-only against `~/.claude` — one outbound call, the same one Claude Code itself makes
- Runs on macOS, Windows, and Linux/WSL

**→ [github.com/colelevy08/portmint-pulse](https://github.com/colelevy08/portmint-pulse)** — a ⭐ helps other Claude Code users find it.

---

### 🥈 FableKalshi — quant trading, real money

A multi-strategy async Python platform trading Kalshi 15-minute and hourly crypto-binary markets. Four strategies plus an ensemble run in parallel; every candidate shadow-trades until it clears a promotion threshold. Regime detection (volatility / trend / chop) drives dynamic position sizing, and every order is gated through fee- and slippage-aware EV math with fractional-Kelly sizing. Automatic kill switches halt entries on drawdown, loss streaks, stale data, or reject spikes.

`Python` `asyncio` `WebSockets` `SQLite`

Strategy code is private. The fee/EV/Kelly math it trades under is open source:

[![kalshi-edge](https://img.shields.io/badge/repo-kalshi--edge-175539?style=flat-square&logo=github&logoColor=f7f1e3)](https://github.com/colelevy08/kalshi-edge)
Fee-aware EV and fractional-Kelly sizing math for Kalshi binary contracts. Zero dependencies.

---

## 🐎 The field — everything else currently running

| Post | Project | What it is | Stack | Link |
|:---:|:---|:---|:---|:---|
| 3 | **Bocage Champagne Society** | Members app + admin CRM for a private champagne society — one codebase to iOS, Android, and web | React · Vite · Capacitor · Supabase | [live](https://bocage-champagne-society.vercel.app) |
| 4 | **Standard Fare** | Restaurant site for the Saratoga Springs spot I helped launch — reservations, ticketed events, menu CMS | React · Vercel · Supabase | [live](https://standardfaresaratoga.com) |
| 5 | **Bocage** | Saratoga's first champagne bar — reservations, wine list, event calendar | React · Vercel · Supabase | [live](https://bocagechampagnebar.com) |
| 6 | **Legacy Path Planners** | Lead-gen site + back-office CRM for a Florida long-term-care insurance practice | React · Vercel · Supabase | [live](https://www.legacypathplanners.com/) |
| 7 | **Saratoga Handicapper** | NYRA handicapping PWA — Kelly-fraction stake sizing, live odds, Claude-powered pace/trip analysis | React · Vite · FastAPI | [live](https://saratoga-handicapper.vercel.app) |
| 8 | **PolyBot** | Polymarket copy-trading bot — whale identification, edge-verified Kelly sizing over WebSocket | Python · asyncio | [repo](https://github.com/colelevy08/PolyBot) |
| 9 | **GrooveStack** | Social marketplace for vinyl collectors — catalog, peer-to-peer trades, condition verification, discovery feed | React · Node · Vercel | [repo](https://github.com/colelevy08/groovestack) · [live](https://groovestack.vercel.app) |

---

## 🧰 Toolkit

<div align="center">

![React](https://img.shields.io/badge/React-175539?style=for-the-badge&logo=react&logoColor=f7f1e3)
![TypeScript](https://img.shields.io/badge/TypeScript-175539?style=for-the-badge&logo=typescript&logoColor=f7f1e3)
![Python](https://img.shields.io/badge/Python-175539?style=for-the-badge&logo=python&logoColor=f7f1e3)
![FastAPI](https://img.shields.io/badge/FastAPI-175539?style=for-the-badge&logo=fastapi&logoColor=f7f1e3)
![Supabase](https://img.shields.io/badge/Supabase-175539?style=for-the-badge&logo=supabase&logoColor=f7f1e3)
![Vercel](https://img.shields.io/badge/Vercel-175539?style=for-the-badge&logo=vercel&logoColor=f7f1e3)

*Frontend* — React · TypeScript · Next.js · Vite · Tailwind v4 · Framer Motion · Capacitor
*Backend & data* — Python · FastAPI · Node.js · Supabase · Postgres · SQLite
*Quant* — asyncio · WebSockets · Kelly sizing · backtesting · regime detection · EV modeling
*Native / mobile* — Swift/SwiftUI · Capacitor (iOS/Android) · PWA

</div>

---

## 💬 About

Full-stack & AI engineer in Saratoga Springs, NY. I build the web layer for small businesses that need to look serious on day one — restaurants, insurance practices, members clubs — three of which are on retainer right now. Off the client clock: quant trading against prediction markets, a horse-racing analytics PWA for the Saratoga meet, and developer tooling like the one above.

Before this I studied Communication at SUNY Geneseo (with semesters at La Sorbonne and Sciences Po), then Flatiron School's software engineering program in 2023. Claude Code sits in my terminal all day — I write the spec and read every diff; it's how one developer keeps fifteen-plus projects and three client retainers moving at once.

**→ [The full portfolio, all 12 entries](https://colelevy.dev)**

---

## 📊 GitHub Stats

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com?user=colelevy08&theme=dark&hide_border=true&background=0b1d15&ring=0ea5e9&fire=0ea5e9&currStreakLabel=0ea5e9" height="165" alt="Cole's GitHub streak" />
</div>

<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=colelevy08&bg_color=0b1d15&color=0ea5e9&line=0ea5e9&point=ece5d3&area=true&area_color=0ea5e9&hide_border=true&days=30" width="100%" alt="Cole's last 30 days of GitHub activity" />
</div>

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=175539&height=100&section=footer" width="100%" alt="" />
</div>

<div align="center">

**Health · History · Horses** — Saratoga Springs' town motto, and about as good a stack for life as any.

<img src="https://komarev.com/ghpvc/?username=colelevy08&color=175539&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile views" />

</div>
