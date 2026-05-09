# 🚀 IG MACHINE - Complete Setup Guide

## GO VIRAL OR DIE TRYING 💀🔥

This is a self-improving, ever-learning Instagram content machine built on n8n.

---

## 📁 Workflow Files

| # | File | What It Does |
|---|------|-------------|
| 01 | `01-master-control.json` | 🧠 Telegram chat interface & command router |
| 02 | `02-research-engine.json` | 🔬 Deep research across 10+ platforms |
| 03 | `03-content-creation.json` | 🎨 Carousel creation via HTML/CSS + Playwright |
| 04 | `04-analytics-monitor.json` | 📊 Performance tracking & viral detection |
| 05 | `05-trend-monitor.json` | 🔥 Trend jacking & viral opportunity alerts |
| 06 | `06-monetization.json` | 💰 Monetization strategy & product creation |
| 07 | `07-cross-platform.json` | 📡 Pinterest, Twitter, LinkedIn, TikTok syndication |
| 08 | `08-comment-mining.json` | 💬 Comment analysis & auto-engagement |
| 09 | `09-content-recycling.json` | ♻️ Repurpose viral content into new formats |
| 10 | `10-smart-scheduler.json` | ⏰ Optimal posting times & A/B hook testing |
| 11 | `11-dm-automation.json` | 🤖 DM auto-responder & engagement bot |

---

## 🛠️ Tech Stack (100% FREE)

```
🖥️ VPS:           Oracle Cloud Free Tier (4 ARM cores, 24GB RAM)
🧠 Workflow:       n8n (self-hosted)
🗄️ Database:       NocoDB (self-hosted, Airtable alternative)
🤖 AI Brain:       Groq API (free, fast) + Google Gemini API (free)
🖼️ Image Host:     Telegraph (Telegram's free hosting)
📱 Chat:           Telegram Bot API
🌐 Browser:        Playwright (n8n community node)
📊 Analytics:      NocoDB dashboards
🔔 Alerts:         Telegram notifications
📦 Storage:        Cloudflare R2 (10GB free)
```

**Total Cost: $0.00** 💸

---

## ⚡ Step-by-Step Setup

### Step 1: Get a Free VPS

1. Go to [Oracle Cloud](https://www.oracle.com/cloud/free/)
2. Create a free account (no credit card charged)
3. Launch an **ARM Ampere A1** instance:
   - 4 OCPUs, 24GB RAM
   - Ubuntu 22.04
   - Always Free tier
4. Note your server IP and SSH key

### Step 2: Install n8n

SSH into your VPS and run:

```bash
# Install Docker
sudo apt update
sudo apt install -y docker.io docker-compose

# Create n8n directory
mkdir -p ~/n8n && cd ~/n8n

# Create docker-compose.yml
cat > docker-compose.yml << 'EOF'
version: '3.8'
services:
  n8n:
    image: n8nio/n8n:latest
    restart: always
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=YOUR_SECURE_PASSWORD
      - GENERIC_TIMEZONE=Asia/Shanghai
      - TZ=Asia/Shanghai
      - EXECUTIONS_DATA_PRUNE=true
      - EXECUTIONS_DATA_MAX_AGE=168
      - N8N_RUNNERS_ENABLED=true
    volumes:
      - n8n_data:/home/node/.n8n
      - ./uploads:/uploads

  nocodb:
    image: nocodb/nocodb:latest
    restart: always
    ports:
      - "8080:8080"
    volumes:
      - nocodb_data:/usr/app/data

  redis:
    image: redis:alpine
    restart: always
    ports:
      - "6379:6379"

volumes:
  n8n_data:
  nocodb_data:
EOF

# Start everything
sudo docker-compose up -d
```

### Step 3: Install Community Nodes

In n8n (http://YOUR_VPS_IP:5678):

1. Go to **Settings** → **Community Nodes**
2. Install these:
   - `n8n-nodes-playwright` (browser automation)
   - `n8n-nodes-telegram` (if not built-in)

### Step 4: Create Telegram Bot

1. Message [@BotFather](https://t.me/BotFather) on Telegram
2. Send `/newbot`
3. Name your bot (e.g., "IG Machine Neo")
4. Set username (e.g., "ig_machine_neo_bot")
5. Copy the **Bot Token**
6. In n8n, add **Telegram credential** with this token

### Step 5: Get Free API Keys

#### Groq API (AI Brain - Fast)
1. Go to [console.groq.com](https://console.groq.com)
2. Create free account
3. Get API key
4. Free tier: 14,400 requests/day

#### Google Gemini API (AI Brain - Quality)
1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Create free account
3. Get API key
4. Free tier: Generous limits

#### ImgBB API (Image Hosting Backup)
1. Go to [api.imgbb.com](https://api.imgbb.com)
2. Create free account
3. Get API key
4. Free tier: Unlimited uploads

### Step 6: Import Workflows

1. Open n8n at http://YOUR_VPS_IP:5678
2. Go to **Workflows**
3. Click **Import from File**
4. Import each workflow file in order (01 through 11)
5. Update credentials in each workflow:
   - Telegram Bot Token
   - Groq API Key
   - Gemini API Key
   - ImgBB API Key

### Step 7: Set Up NocoDB

1. Open NocoDB at http://YOUR_VPS_IP:8080
2. Create a new base called "IG Machine"
3. Create these tables:

#### Table: `knowledge_base`
| Column | Type |
|--------|------|
| niche | Text |
| data | JSON |
| updated_at | DateTime |
| total_data_points | Number |

#### Table: `posts`
| Column | Type |
|--------|------|
| post_id | Text |
| created_at | DateTime |
| hook | Text |
| idea | Text |
| caption | LongText |
| hashtags | Text |
| image_urls | JSON |
| slide_count | Number |
| ab_test_id | Text |
| design_style | Text |
| status | Text |
| views | Number |
| likes | Number |
| comments | Number |
| saves | Number |
| shares | Number |

#### Table: `analytics`
| Column | Type |
|--------|------|
| post_id | Text |
| timestamp | DateTime |
| views | Number |
| likes | Number |
| comments | Number |
| saves | Number |
| engagement_rate | Number |

#### Table: `leads`
| Column | Type |
|--------|------|
| username | Text |
| comment | Text |
| source | Text |
| timestamp | DateTime |
| status | Text |

### Step 8: Activate Workflows

1. Open each workflow
2. Set credentials (Telegram, Groq, etc.)
3. Update `YOUR_BRAND` in HTML generator with your actual IG handle
4. Toggle each workflow to **Active**

### Step 9: Start Chatting!

Open Telegram and message your bot:

```
/start          - Welcome message
/niche fitness  - Set your niche
/brand dark minimal fitness brand - Set brand identity
/ig yourname yourpass - Set IG credentials
[Upload carousel samples as images]
/create         - Generate & post carousel
/status         - Check progress
/knowledge      - See what it learned
/analytics      - Post performance
/viral          - Check viral trends
/monetize       - Monetization strategy
/research       - Update knowledge base
/help           - See all commands
```

---

## 🔄 How The System Works

```
┌─────────────────────────────────────────────────────┐
│                    TELEGRAM CHAT                     │
│              (Your command center)                   │
└──────────────────────┬──────────────────────────────┘
                       │
          ┌────────────▼────────────┐
          │    MASTER CONTROL (01)   │
          │   Routes all commands    │
          └────────────┬────────────┘
                       │
    ┌──────────────────┼──────────────────┐
    │                  │                  │
    ▼                  ▼                  ▼
┌────────┐      ┌──────────┐      ┌──────────┐
│RESEARCH│      │ CONTENT  │      │ANALYTICS │
│ (02)   │      │  (03)    │      │   (04)   │
│        │      │          │      │          │
│TikTok  │      │HTML/CSS  │      │ Track    │
│IG      │      │Playwright│      │ Views    │
│Reddit  │─────▶│Screenshot│─────▶│ Likes    │
│YouTube │      │Upload    │      │ Saves    │
│Pinterest│     │Post to IG│      │ Viral?   │
│Twitter │      └──────────┘      └──────────┘
│LinkedIn│            │                 │
│Google  │            ▼                 ▼
│Trends  │      ┌──────────┐      ┌──────────┐
│Articles│      │  TREND   │      │ MONETIZE │
└────────┘      │ MONITOR  │      │   (06)   │
     │          │   (05)   │      │          │
     │          │          │      │ Products │
     │          │ Trend    │      │ Coaching │
     │          │ Jacking  │      │ Affiliate│
     ▼          └──────────┘      │ Community│
┌──────────┐           │          └──────────┘
│COMMENT   │           ▼               │
│ MINING   │     ┌──────────┐          ▼
│   (08)   │     │ CROSS    │    ┌──────────┐
│          │     │ PLATFORM │    │ DM AUTO  │
│ Pain     │     │   (07)   │    │   (11)   │
│ Points   │     │          │    │          │
│ Questions│     │ Pinterest│    │ Auto-DM  │
│ Leads    │     │ Twitter  │    │ Auto-like│
│ Emotions │     │ LinkedIn │    │ Follow   │
└──────────┘     │ TikTok   │    │ Unfollow │
     │           │ Reddit   │    └──────────┘
     ▼           └──────────┘
┌──────────┐          │
│ CONTENT  │          ▼
│RECYCLING │    ┌──────────┐
│   (09)   │    │  SMART   │
│          │    │SCHEDULER │
│ Reels    │    │   (10)   │
│ Stories  │    │          │
│ Threads  │    │ Best Time│
│ Memes    │    │ A/B Test │
│ Infograph│    │ Hooks    │
└──────────┘    └──────────┘
```

---

## 📱 Telegram Commands

| Command | What It Does |
|---------|-------------|
| `/start` | Welcome message |
| `/niche [name]` | Set your niche (e.g., `/niche fitness`) |
| `/brand [desc]` | Set brand identity |
| `/ig [user] [pass]` | Set Instagram credentials |
| Upload images | Send carousel samples |
| `create` | Generate & post a carousel |
| `/status` | Check progress & stats |
| `/knowledge` | See what it learned |
| `/analytics` | Post performance report |
| `/viral` / `trending` | Check viral opportunities |
| `/monetize` | Monetization strategy |
| `/research` | Force knowledge base update |
| `/recycle` | See recyclable content |
| `/help` | All commands |

**You can also chat normally!** Ask it anything about your niche.

---

## ⏰ Automated Schedules

| Task | Frequency | What It Does |
|------|-----------|-------------|
| Deep Research | Every 6 hours | Scours ALL platforms for niche data |
| Performance Monitor | Every 2 hours | Checks post metrics, detects viral/flop |
| Trend Monitor | Every 3 hours | Finds trending topics for trend jacking |
| Comment Mining | Every 1 hour | Analyzes comments for insights & leads |
| Content Recycling | Every 12 hours | Finds viral content to repurpose |
| Smart Scheduler | Every 1 hour | Optimizes posting times |
| DM Automation | Every 30 min | Responds to DMs automatically |
| Engagement Bot | Every 30 min | Auto-likes, comments, follows |
| Cross-Platform | Every 8 hours | Syndicates content to other platforms |

---

## 🧠 Knowledge Base Structure

The system builds a MASSIVE knowledge base over time:

```
📚 Knowledge Base
├── 🎣 Hooks
│   ├── Top hooks from competitors
│   ├── Viral hook patterns
│   └── A/B tested winners
├── 🏷️ Hashtags
│   ├── Top performing hashtags
│   ├── Trending hashtags
│   └── Hashtag sets by category
├── 📝 Captions
│   ├── Caption templates
│   ├── CTA patterns
│   └── Engagement drivers
├── 😤 Psychology
│   ├── Audience pain points
│   ├── Desires & dreams
│   ├── Questions asked
│   ├── Emotional triggers
│   └── Audience language
├── 🏆 Competitors
│   ├── Top accounts tracked
│   ├── Their strategies
│   └── Their weaknesses
├── 🎨 Design
│   ├── Color palettes
│   ├── Typography styles
│   ├── Carousel layouts
│   └── Design trends
├── ⏰ Timing
│   ├── Best posting times
│   ├── Best days
│   └── Algorithm insights
├── 💰 Monetization
│   ├── Product ideas
│   ├── Pricing strategies
│   └── Affiliate opportunities
└── 📊 Performance
    ├── Viral patterns
    ├── Flop patterns
    └── Growth trends
```

---

## 🛡️ Safety & Limits

The system respects platform limits to avoid bans:

- **Max 15 engagements/hour** (likes, comments)
- **Max 20 follows/day**
- **Auto-unfollow after 3 days**
- **Random delays between actions** (human-like)
- **Rate limiting on API calls**
- **No spam — quality over quantity**

---

## 🔧 Customization

### Change Brand Watermark
In workflow `03-content-creation.json`, find `HTML Generator` node:
```
const brandWatermark = '@YOUR_BRAND';
```
Replace with your actual IG handle.

### Add New Niches
Just message the bot:
```
/niche your new niche here
```
It will automatically research and adapt.

### Adjust Posting Frequency
In `10-smart-scheduler.json`, modify the schedule trigger interval.

### Add Custom DM Responses
In `11-dm-automation.json`, add new trigger keywords and responses.

---

## 🚨 Troubleshooting

### n8n not starting?
```bash
sudo docker-compose logs n8n
```

### Playwright not working?
```bash
# Install Playwright in n8n container
sudo docker exec -it n8n_n8n_1 npm install playwright
sudo docker exec -it n8n_n8n_1 npx playwright install chromium
```

### NocoDB not connecting?
Check if it's running:
```bash
sudo docker-compose ps
```

### Bot not responding?
1. Check Telegram credential in n8n
2. Check bot token with BotFather
3. Check n8n execution logs

---

## 📈 Expected Timeline

| Week | Expected Results |
|------|-----------------|
| Week 1 | Knowledge base building, first posts, finding what works |
| Week 2 | 50K-100K views per post, patterns identified |
| Week 3 | Millions of views, monetization alert triggered |
| Week 4+ | Consistent viral content, product launches, revenue |

---

## 🎯 The Philosophy

> **GO VIRAL OR DIE TRYING** 💀🔥

This machine doesn't stop. Doesn't lag. Doesn't complain. Doesn't fatigue.

It learns your niche like it's studying for a PhD.
It treats every post like a science experiment.
It adapts. It evolves. It dominates.

**Your job?** Set the niche. Upload your brand. Let it cook. 🔥

---

Built with ❤️ by Neo ⚡
