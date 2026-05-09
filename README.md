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
🤗 OPTION A — HuggingFace Spaces (Easiest):
   🖥️ Hosting:    HuggingFace Spaces Free (2 vCPU, 16GB RAM)
   🗄️ Database:    Supabase Free (500MB PostgreSQL)
   🤖 AI Brain:    Groq API (free) + Google Gemini API (free)
   🖼️ Image Host:  Telegraph (free) + ImgBB (free)
   📱 Chat:        Telegram Bot API (free)
   🌐 Browser:     Playwright + Chromium (included)

🖥️ OPTION B — Oracle Cloud VPS (More Power):
   🖥️ VPS:         Oracle Cloud Free Tier (4 ARM cores, 24GB RAM)
   🗄️ Database:     NocoDB self-hosted (unlimited)
   🤖 AI Brain:     Groq API (free) + Google Gemini API (free)
   🖼️ Image Host:   Telegraph (free) + ImgBB (free)
   📱 Chat:         Telegram Bot API (free)
   🌐 Browser:      Playwright (n8n community node)
   📊 Analytics:    NocoDB + Grafana self-hosted
```

**Total Cost: $0.00** 💸

---

## 🤗 Option A: Deploy on HuggingFace Spaces (EASIEST — Recommended!)

> **No VPS needed. No Docker knowledge needed. Just click and go.** 🚀

HuggingFace Spaces gives you **FREE hosting**: 2 vCPU, 16GB RAM, 50GB disk. Perfect for n8n!

### Step 1: Create Free Accounts

You need two free accounts:

#### A. Supabase (Free Database)
1. Go to [supabase.com/dashboard/sign-up](https://supabase.com/dashboard/sign-up)
2. Create a free account
3. Create a new project
4. **Save your database password** — you'll need it!
5. Click the **Connect** button (top left)
6. Select **SQLAlchemy** → **Transaction pooler**
7. Note down:
   - **Host** (e.g., `aws-0-us-east-1.pooler.supabase.com`)
   - **Port** (usually `6543`)
   - **User** (e.g., `postgres.xxxxx`)
   - **Database name** (usually `postgres`)

#### B. HuggingFace (Free Hosting)
1. Go to [huggingface.co/join](https://huggingface.co/join)
2. Create a free account
3. Remember your **profile name** (e.g., `dav`)

### Step 2: Duplicate the n8n Space

1. Go to [huggingface.co/spaces/tomowang/n8n](https://huggingface.co/spaces/tomowang/n8n)
2. Click the **menu dropdown** (top right corner)
3. Select **Duplicate this Space**
4. Fill in the environment variables (see table below)
5. Click **Duplicate Space**
6. Wait ~5 minutes for deployment

### Step 3: Set Environment Variables

When duplicating, fill in these variables:

| Variable | Where to Find It | Example |
|----------|-------------------|---------|
| `DB_POSTGRESDB_HOST` | Supabase → Connect → Transaction pooler host | `aws-0-us-east-1.pooler.supabase.com` |
| `DB_POSTGRESDB_PORT` | Supabase → Connect → Transaction pooler port | `6543` |
| `DB_POSTGRESDB_USER` | Supabase → Connect → Transaction pooler user | `postgres.abcxyz` |
| `DB_POSTGRESDB_PASSWORD` | The password you set when creating Supabase project | `your-db-password` |
| `N8N_ENCRYPTION_KEY` | Generate one (see below) | `aBcDeFgHiJkLmNoPqRsTuVwXyZ012345` |
| `WEBHOOK_URL` | Your HuggingFace Space URL | `https://dav-ig-machine.hf.space/` |
| `N8N_EDITOR_BASE_URL` | Same as WEBHOOK_URL | `https://dav-ig-machine.hf.space/` |
| `GENERIC_TIMEZONE` | Your timezone | `Asia/Shanghai` |
| `TZ` | Same as above | `Asia/Shanghai` |

**Generate encryption key:** Open terminal and run:
```bash
openssl rand -base64 32
```
Or use any random string of letters and numbers (32+ characters).

### Step 4: Get Your Space URL

After deployment completes:
1. Go to your Space (e.g., `https://huggingface.co/spaces/dav/ig-machine`)
2. Your n8n URL will be: `https://dav-ig-machine.hf.space`
3. Open this URL in your browser
4. You'll see the n8n login page!

### Step 5: Set Up n8n

1. Open your n8n URL
2. Create your admin account (first time only)
3. Go to **Settings** → **Community Nodes**
4. Install: `n8n-nodes-playwright`

### Step 6: Import Workflows

1. Go to [github.com/Atum246/n8n-ig-machine](https://github.com/Atum246/n8n-ig-machine)
2. Download all 11 workflow JSON files
3. In n8n, go to **Workflows** → **Import from File**
4. Import each workflow (01 through 11)

### Step 7: Set Up Credentials

In n8n, go to **Credentials** and add:

#### Telegram Bot
1. Message [@BotFather](https://t.me/BotFather) on Telegram
2. Send `/newbot`, name it, get the token
3. In n8n → Credentials → Add → Telegram API
4. Paste your bot token

#### Groq API (AI Brain)
1. Go to [console.groq.com](https://console.groq.com)
2. Create free account → Get API key
3. In n8n → Credentials → Add → HTTP Header Auth
4. Header Name: `Authorization`
5. Header Value: `Bearer YOUR_GROQ_API_KEY`

#### Gemini API (Backup AI)
1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Create free account → Get API key
3. In n8n → Credentials → Add → HTTP Header Auth
4. Header Name: `Authorization`
5. Header Value: `Bearer YOUR_GEMINI_API_KEY`

### Step 8: Update Brand Name

In workflow `03-content-creation.json`, find the `HTML Generator` node:
```javascript
const brandWatermark = '@YOUR_BRAND';
```
Replace `@YOUR_BRAND` with your actual Instagram handle.

### Step 9: Activate & Go!

1. Toggle each workflow to **Active**
2. Open Telegram → Message your bot
3. Send: `/help` to see all commands
4. Send: `/niche fitness` to start!

### ⚠️ Important HuggingFace Notes

#### Space Sleep
HuggingFace Spaces go to sleep after **48 hours of inactivity**. To prevent this:
- Use an uptime monitor (e.g., [UptimeRobot](https://uptimerobot.com/) — free)
- Set it to ping your Space URL every 30 minutes
- This keeps your Space alive 24/7

#### Community Nodes
If `n8n-nodes-playwright` doesn't install via the UI:
1. Go to your Space → **Files** tab
2. Edit the `Dockerfile`
3. Add before `USER node`:
```dockerfile
RUN cd /usr/local/lib/node_modules/n8n && \
    npm install n8n-nodes-playwright
```
4. Commit and the Space will rebuild

#### Persistent Storage
HuggingFace Spaces have **non-persistent storage**. This means:
- n8n workflows and credentials are stored in Supabase (persistent ✅)
- Uploaded files may be lost on restart
- Use external storage (Cloudflare R2, Google Drive) for images

#### Custom Dockerfile (Advanced)
For full control, use the Dockerfile in `huggingface-space/Dockerfile`:
1. Create a new HuggingFace Space (SDK: Docker)
2. Upload the `Dockerfile` and `README.md` from the `huggingface-space/` folder
3. Set environment variables in Space settings
4. The Space will build and run automatically

### 🎯 Quick Reference

```
🤗 HuggingFace Space URL: https://YOUR_USERNAME-ig-machine.hf.space
🗄️ Supabase Dashboard: https://supabase.com/dashboard
📱 Telegram Bot: @your_bot_name
📊 n8n Dashboard: https://YOUR_USERNAME-ig-machine.hf.space
```

---

## 🖥️ Option B: Deploy on Oracle Cloud VPS (More Power)

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
