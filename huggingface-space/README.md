---
title: IG Machine
emoji: 🚀
colorFrom: purple
colorTo: red
sdk: docker
app_port: 5678
pinned: true
license: mit
short_description: Self-improving Instagram content machine - GO VIRAL OR DIE TRYING
---

# 🚀 IG Machine - Self-Improving Instagram Content Machine

**GO VIRAL OR DIE TRYING** 💀🔥

A fully automated, self-learning Instagram content machine built on n8n. Researches your niche across 10+ platforms, creates carousels, posts to IG, tracks performance, and continuously improves.

## 🛠️ What It Does

- 🔬 **Deep Research** — Scrapes TikTok, Instagram, Reddit, YouTube, Pinterest, Twitter, LinkedIn, Google Trends
- 🎨 **Creates Carousels** — HTML/CSS → Playwright screenshots → IG posts
- 📊 **Tracks Performance** — Monitors every post, detects viral/flop
- 🔄 **Self-Improves** — A/B tests hooks, learns best posting times
- 💰 **Monetizes** — Alerts you when it's time to sell
- 📡 **Cross-Platform** — Syndicates to Pinterest, Twitter, LinkedIn, TikTok
- 💬 **Engages** — Auto-replies to DMs and comments
- ♻️ **Recycles** — Repurposes viral content into new formats

## ⚡ Quick Start

1. **Duplicate this Space** (click the menu → Duplicate)
2. **Set environment variables** (see below)
3. **Wait for deployment** (~5 minutes)
4. **Open n8n** at your Space URL
5. **Import workflows** from the [GitHub repo](https://github.com/Atum246/n8n-ig-machine)
6. **Start chatting** with your Telegram bot!

## 🔧 Environment Variables

Set these when duplicating the Space:

| Variable | Value | Description |
|----------|-------|-------------|
| `DB_POSTGRESDB_HOST` | Your Supabase host | Database host |
| `DB_POSTGRESDB_PORT` | `6543` | Database port |
| `DB_POSTGRESDB_USER` | Your Supabase user | Database user |
| `DB_POSTGRESDB_PASSWORD` | Your Supabase password | Database password |
| `N8N_ENCRYPTION_KEY` | Random string | Generate with `openssl rand -base64 32` |
| `WEBHOOK_URL` | `https://your-space-name.hf.space/` | Your Space URL |
| `N8N_EDITOR_BASE_URL` | `https://your-space-name.hf.space/` | Your Space URL |
| `GENERIC_TIMEZONE` | `Asia/Shanghai` | Your timezone |
| `TZ` | `Asia/Shanghai` | Your timezone |

## 📦 Free Tech Stack

- 🖥️ **Hosting**: HuggingFace Spaces (Free — 2 vCPU, 16GB RAM, 50GB disk)
- 🗄️ **Database**: Supabase (Free — 500MB PostgreSQL)
- 🤖 **AI**: Groq API (Free) + Google Gemini API (Free)
- 🖼️ **Images**: Telegraph (Free) + ImgBB (Free)
- 📱 **Chat**: Telegram Bot API (Free)
- 🌐 **Browser**: Playwright + Chromium (included)

**Total Cost: $0.00** 💸

## 🔗 Links

- [GitHub Repository](https://github.com/Atum246/n8n-ig-machine)
- [Setup Guide](https://github.com/Atum246/n8n-ig-machine/blob/main/README.md)

---

Built with ❤️ by Neo ⚡
