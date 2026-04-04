Here is your full checklist and action plan. Since today is **April 4, 2026**, the hackathon started 5 days ago and you have **8 days left** until the April 12 deadline. The plan is adjusted to be realistic for the remaining time.

---

```markdown
# ✅ AI Trading Agents Hackathon — Action Plan & Checklist
> Hackathon: March 30 – April 12, 2026 | Today: April 4 | ⏳ 8 Days Remaining
> Location: Online | Prize Pool: $55,000 | Platform: lablab.ai

---

## 🚨 URGENT — Do These TODAY (April 4)

- [ ] **Register your project at https://early.surge.xyz** ← REQUIRED for prize eligibility
- [ ] Enroll on lablab.ai (if not done): https://lablab.ai/ai-hackathons/ai-trading-agents
- [ ] Join lablab.ai Discord: https://discord.gg/lablabai
- [ ] Create or join a team on lablab.ai → click "Create or join a team"
- [ ] Create your GitHub repository (name it something like `ai-trading-agent`)
- [ ] Sign up for PRISM API at https://prismapi.ai — use code **LABLAB** for $10 free credits
- [ ] Create a Kraken account at https://www.kraken.com (if you don't have one)
- [ ] Generate a **read-only** Kraken API key (for leaderboard — no withdrawal access)
- [ ] Set up your multi-signature wallet (required to receive prize funds)
- [ ] Post on X/Twitter/LinkedIn: "I just joined the AI Trading Agents Hackathon by
      @lablabai x @krakenfx x @Surgexyz_ — building an autonomous AI trading agent!
      #AITradingAgents #BuildInPublic #lablabai"

---

## 📋 PHASE 1 — Setup & Foundation (April 4–5)

### 🔧 Environment Setup
- [ ] Install Kraken CLI from https://github.com/krakenfx/kraken-cli
- [ ] Configure Kraken CLI with your read-only API key
- [ ] Test Kraken CLI — fetch market data for at least 1 asset
- [ ] Set up PRISM API key (`prism_sk_...`)
- [ ] Test PRISM API:
      `curl -H "X-API-Key: YOUR_KEY" https://api.prismapi.ai/resolve/BTC`
- [ ] Test PRISM endpoints:
  - [ ] `/resolve/{asset}` — asset identity
  - [ ] `/crypto/{symbol}/price` — real-time price
  - [ ] `/signals/{symbol}` — AI signals
  - [ ] `/risk/{symbol}` — volatility + risk metrics
- [ ] Set up Python or Rust project structure
- [ ] Set up virtual environment / dependencies
- [ ] Set up `.env` file for all API keys (never commit to GitHub)
- [ ] Add `.gitignore` with `.env` excluded
- [ ] Push initial commit with README.md to GitHub

### 🧠 Strategy Decision (April 4–5) — Pick ONE to focus on first
- [ ] **Option A:** Pure Kraken PnL trading agent (simpler, faster to build)
- [ ] **Option B:** ERC-8004 trustless agent (more complex, higher prize potential)
- [ ] **Option C (Recommended):** Combined — Kraken CLI execution + ERC-8004 identity layer
- [ ] Define your trading strategy type:
  - [ ] Trend following (moving averages, momentum)
  - [ ] Mean reversion (RSI, Bollinger Bands)
  - [ ] Sentiment-driven (news + social signals)
  - [ ] Yield / LP optimization (Aerodrome Finance)
  - [ ] Risk/compliance agent (circuit breakers, guardrails)
- [ ] Define your target assets (BTC, ETH, or other Kraken-listed pairs)
- [ ] Define your risk parameters:
  - [ ] Max position size per trade
  - [ ] Stop-loss % threshold
  - [ ] Max daily drawdown limit
  - [ ] Max leverage

---

## 📋 PHASE 2 — Core Build (April 5–9)

### 📊 Data Layer
- [ ] Build market data fetcher using Kraken CLI (OHLCV, order book, tickers)
- [ ] Build PRISM API integration for AI signals and risk scores
- [ ] (Optional) Add on-chain data feed (DEX volume, wallet flows)
- [ ] Store/cache data locally for backtesting
- [ ] Build a simple data normalization layer

### 🤖 AI / Signal Analysis Module
- [ ] Choose your LLM/AI approach:
  - [ ] OpenAI GPT-4o function calling
  - [ ] Claude API (Anthropic)
  - [ ] Open-source LLM (Mistral, LLaMA, etc.)
  - [ ] Rule-based signals only (no LLM)
- [ ] Implement signal analysis logic (technical indicators or LLM-based)
- [ ] Implement strategy decision engine (buy / sell / hold logic)
- [ ] Add risk check before every trade (position size, drawdown)
- [ ] Test signal output with historical or live data

### ⚙️ Execution Layer (Kraken Challenge)
- [ ] Connect AI signal output to Kraken CLI execution
- [ ] Implement order placement via Kraken CLI (market / limit orders)
- [ ] Implement order status monitoring
- [ ] Implement PnL tracking (realized + unrealized)
- [ ] Test with small amounts in live or paper trading mode
- [ ] Implement auto-retry / error handling for failed orders
- [ ] Implement circuit breaker (stop trading if drawdown exceeds threshold)

### 🔗 Trust Layer (ERC-8004 Challenge)
- [ ] Read ERC-8004 spec: https://eips.ethereum.org/EIPS/eip-8004
- [ ] Read the Ethereum Magicians discussion
- [ ] Read the Medium article (savvysid)
- [ ] Check Awesome ERC-8004 repo for starter templates
- [ ] Choose your deployment chain (Base L2 recommended, or testnet)
- [ ] Deploy Agent Identity (ERC-721) on chosen chain
- [ ] Create Agent Registration JSON (capabilities, metadata)
- [ ] Point identity to your Agent Registration JSON
- [ ] Implement EIP-712 typed data signing for TradeIntents
- [ ] Implement EIP-1271 for smart-contract wallet support
- [ ] Connect to Hackathon Capital Vault (claim sandbox capital)
- [ ] Connect to Risk Router contract for on-chain execution
- [ ] Emit on-chain events per trade/checkpoint
- [ ] Register scores with Validation Registry
- [ ] Test full flow: Identity → TradeIntent → Risk Router → Validation

### 🏗️ Aerodrome Finance (Optional Enhancement)
- [ ] Read Aerodrome docs: https://aerodrome.finance/docs
- [ ] Explore Aerodrome Launcher for token/pool creation
- [ ] Consider integrating LP optimization as a yield agent track
- [ ] If building yield agent, test on Base testnet first

---

## 📋 PHASE 3 — Social Engagement (Ongoing — April 4–12)

> This is a **scored category** worth up to $1,200 (1st place). Post consistently!

### Platforms to Post On
- [ ] X (Twitter): tag @krakenfx, @lablabai, @Surgexyz_
- [ ] LinkedIn: tag Kraken, lablab.ai, Surge
- [ ] Instagram: tag @krakenfx, @lablab.ai

### Hashtags to Use Every Post
`#AITradingAgents #lablabai #Kraken #ERC8004 #BuildInPublic #AIAgents #DeFi #Web3`

### Content Calendar
- [ ] **April 4:** Announcement post — "I just joined the hackathon, here's my plan..."
- [ ] **April 5:** Architecture post — share a diagram of your agent design
- [ ] **April 6:** Tech stack post — "Here's the tech I'm using: Kraken CLI, ERC-8004, PRISM API..."
- [ ] **April 7:** Progress post — "Day 4: First live signal generated by the agent 🎯"
- [ ] **April 8:** Code snippet post — share an interesting piece of your code
- [ ] **April 9:** Challenge post — "Here's the hardest problem I solved today..."
- [ ] **April 10:** Demo video (short, 30–60 seconds) — agent running live
- [ ] **April 11:** "Final push" post — almost at the finish line
- [ ] **April 12:** Submission announcement — "We submitted! Here's our project link"

---

## 📋 PHASE 4 — Polish & Submission (April 10–12)

### 🎬 Demo & Presentation
- [ ] Record a demo video (2–5 minutes recommended):
  - [ ] Explain the problem you're solving
  - [ ] Show the agent running live (or replay)
  - [ ] Explain your tech stack
  - [ ] Show PnL results / on-chain validation data
  - [ ] Explain business value and originality
- [ ] Create slide deck / pitch presentation:
  - [ ] Slide 1: Project title + one-liner
  - [ ] Slide 2: Problem statement
  - [ ] Slide 3: Your solution & architecture
  - [ ] Slide 4: Technology used (Kraken CLI, ERC-8004, PRISM, etc.)
  - [ ] Slide 5: Live results / PnL / leaderboard standing
  - [ ] Slide 6: Business value & use cases
  - [ ] Slide 7: Team + next steps
- [ ] Design a cover image for your project

### 📁 GitHub Repository
- [ ] Clean up code and add comments
- [ ] Write comprehensive README.md
- [ ] Add setup instructions (how to install, configure, run)
- [ ] Add architecture diagram image
- [ ] Add `.env.example` (with dummy values, no real keys)
- [ ] Make repository **public**
- [ ] Tag the final release (e.g., `v1.0.0-hackathon`)

### 📤 lablab.ai Submission Form
- [ ] Project Title
- [ ] Short Description (1–2 sentences)
- [ ] Long Description (full explanation)
- [ ] Technology & Category Tags
- [ ] Cover Image uploaded
- [ ] Video Presentation URL (YouTube or similar)
- [ ] Slide Presentation (PDF or link)
- [ ] Public GitHub Repository URL
- [ ] Demo Application URL (if hosted)
- [ ] Submit before **April 12, 2026 deadline**

### 🏆 Prize Eligibility Final Checks
- [ ] Project registered at https://early.surge.xyz ← double check!
- [ ] Read-only Kraken API key submitted for leaderboard verification
- [ ] Multi-sig wallet set up for receiving Surge prize tokens
- [ ] All team members listed on the lablab.ai team page
- [ ] Social media accounts linked on lablab.ai profile (for engagement tracking)

---

## 📋 JUDGING CRITERIA — Self-Assessment Checklist

Before submitting, score yourself honestly on each criterion:

| Criterion | What Judges Look For | Your Score (1–10) |
|-----------|---------------------|-------------------|
| **Application of Technology** | Are Kraken CLI and/or ERC-8004 deeply integrated, not just superficially? | /10 |
| **Presentation** | Is your demo video clear? Does the slide deck tell a compelling story? | /10 |
| **Business Value** | Could this agent be used in a real trading firm, hedge fund, or DeFi protocol? | /10 |
| **Originality** | Is your strategy, architecture, or approach genuinely unique or novel? | /10 |

---

## 📋 DAILY STANDUP TEMPLATE

Use this every day to stay on track:

```

Date: ___________
✅ What I completed yesterday
-

-

🔨 What I'm building today
-

-

🚧 Blockers / Problems
-

-

📣 Social post planned for today
-

⏳ Days remaining: ___

```

---

## ⏰ TIMELINE AT A GLANCE

```

April 4  ██ TODAY — Setup, register surge.xyz, Kraken API, PRISM API, first post
April 5  ██ Strategy finalized, environment ready, first data flowing
April 6  ██ AI signal module working, Kraken CLI executing test trades
April 7  ██ ERC-8004 agent identity deployed, Trust layer connecting
April 8  ██ Full agent pipeline running end-to-end
April 9  ██ Testing, bug fixing, optimizing PnL & risk controls
April 10 ██ Record demo video, build slide deck
April 11 ██ Final code cleanup, README complete, cover image done
April 12 ██ SUBMIT before deadline + final social media blast

```

---

## ⚠️ CRITICAL REMINDERS

1. ❗ **Register at early.surge.xyz NOW** — without this your team is NOT prize-eligible
2. ❗ **Read-only API key only** — never use a key with withdrawal permissions on Kraken
3. ❗ **Never commit API keys** to GitHub — use `.env` files
4. ❗ **PRISM free tier expires** — cancel before billing period if not continuing
5. ❗ **Multi-sig wallet required** — set this up before submission day
6. ❗ **Post publicly** every day — social engagement is a scored, prizeable category
7. ❗ **Submit early** — don't wait until April 12 evening, submit by April 11 to be safe

---

## 🔗 QUICK REFERENCE LINKS

| Action | Link |
|--------|------|
| Hackathon Page | https://lablab.ai/ai-hackathons/ai-trading-agents |
| Register Project | https://early.surge.xyz |
| Discord | https://discord.gg/lablabai |
| Kraken CLI | https://github.com/krakenfx/kraken-cli |
| EIP-8004 Spec | https://eips.ethereum.org/EIPS/eip-8004 |
| Awesome ERC-8004 | https://github.com/sudeepb02/awesome-erc8004 |
| PRISM API | https://prismapi.ai (code: LABLAB) |
| Aerodrome Docs | https://aerodrome.finance/docs |
| Submission Guide | https://lablab.ai/delivering-your-hackathon-solution |
| Submission Video | https://www.youtube.com/watch?v=VKgOh0rKjSM |
```

---

Save this as `ACTION_PLAN.md` in your repo alongside the `README.md`.

**The single most important thing right now:** Go register your project at **<https://early.surge.xyz>** — without that, you are not eligible for any prizes regardless of how good your project is. Do that first, right now, before anything else.

Want me to help you decide on your trading strategy, or help you write the first code modules?
