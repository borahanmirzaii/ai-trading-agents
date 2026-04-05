# Winning Strategy — AI Trading Agents Hackathon

> **Deadline:** April 12, 2026 7:30 PM IST (6:00 PM UAE)
> **Days left:** 7
> **Enrolled:** 2,499 — but only ~10-20 teams will actually submit

---

## Competition Analysis

### What Already Exists (from other submissions)
| Project | Approach | Weakness We Can Exploit |
|---------|----------|------------------------|
| **Botify** | 12 CrewAI agents, self-evolving, ERC-8004 | Over-engineered, likely unstable in 2 weeks |
| **QuantTrader** | XAI trading mentor, deterministic signals | Single agent, no ERC-8004, no on-chain trust |
| **TradeX** | Workflow canvas, market data consolidation | Dashboard tool, not an autonomous agent |
| **Ice Cream** | No-code platform for trading agents | Platform play, not a trading agent itself |
| **OneDev** | Solo dev, ERC-8004 + Kraken CLI | Solo = limited scope |

### Key Insight
Most teams will either:
- Build a basic Kraken CLI bot (no ERC-8004) → only eligible for Kraken prizes ($3K)
- Build a basic ERC-8004 demo (no real trading) → weak on PnL
- Over-engineer and not finish

**Our edge: Combined submission + target ALL 7 prize categories simultaneously.**

---

## Prize Category Targeting

We can be eligible for **every single prize** with one well-architected project:

| Prize | Amount | How We Win It |
|-------|--------|---------------|
| 1st - Best Trustless Trading Agent | $10,000 | Combined Kraken + ERC-8004 with real trades + on-chain identity |
| 2nd - Best Risk-Adjusted Return | $5,000 | Sharpe ratio optimization, low drawdown, circuit breakers |
| 3rd - Best Validation & Trust Model | $2,500 | Deep ERC-8004: identity + reputation + validation artifacts per trade |
| Best Yield/Portfolio Agent | $2,500 | Add Aerodrome LP yield optimization module |
| Best Compliance & Risk Guardrails | $2,500 | On-chain circuit breakers, position limits, stop-loss on-chain |
| Kraken PnL 1st | $1,800 | Paper trading with optimized strategy |
| Kraken Social 1st | $1,200 | Daily posts on X + LinkedIn + Instagram |
| **TOTAL POSSIBLE** | **$25,500** | |

---

## The Winning Architecture

### Project Name: **TrustAgent** (or pick something memorable)

**One-liner:** An autonomous, trustless multi-strategy trading agent with on-chain identity, real-time risk guardrails, and verifiable execution — combining Kraken CLI execution with ERC-8004 trust infrastructure.

### System Design

```
┌─────────────────────────────────────────────────────────┐
│                    TrustAgent Core                       │
│                                                         │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐              │
│  │ Signal    │  │ Strategy │  │ Risk     │              │
│  │ Ingestion │→ │ Engine   │→ │ Guardian │              │
│  │ Module    │  │ (LLM)    │  │ Module   │              │
│  └──────────┘  └──────────┘  └──────────┘              │
│       ↑                           ↓                     │
│  ┌──────────┐            ┌──────────────┐               │
│  │ PRISM    │            │ Execution    │               │
│  │ API +    │            │ Layer        │               │
│  │ Kraken   │            │ (Kraken CLI) │               │
│  │ Data     │            └──────────────┘               │
│  └──────────┘                  ↓                        │
│                    ┌──────────────────┐                  │
│                    │ ERC-8004 Trust   │                  │
│                    │ Layer (Base L2)  │                  │
│                    │ • Identity       │                  │
│                    │ • Reputation     │                  │
│                    │ • Validation     │                  │
│                    └──────────────────┘                  │
│                           ↓                             │
│                    ┌──────────────┐                      │
│                    │ Dashboard    │                      │
│                    │ (Streamlit)  │                      │
│                    └──────────────┘                      │
└─────────────────────────────────────────────────────────┘
```

### Modules (each maps to a prize category)

#### 1. Signal Ingestion (Foundation)
- Kraken CLI: live ticker, OHLCV, order book depth
- PRISM API: AI signals, risk scores, asset resolution
- Technical indicators: RSI, MACD, Bollinger Bands via pandas-ta

#### 2. Strategy Engine (Originality)
- LangGraph agent with Claude API for reasoning
- Multi-strategy: momentum + mean-reversion + sentiment
- Strategy selection based on market regime detection
- **Key differentiator:** Agent explains WHY it trades (XAI) — every decision has a human-readable rationale logged on-chain

#### 3. Risk Guardian (→ Best Compliance & Risk Guardrails prize)
- Position size limits (max 5% per trade)
- Daily drawdown limit (max 3%)
- Circuit breaker: halt after 3 consecutive losses
- Stop-loss per position (2%)
- Max leverage cap
- All limits enforced BOTH off-chain (pre-execution) AND on-chain (Risk Router)

#### 4. Execution Layer (→ Kraken PnL prize)
- Kraken CLI for all order placement
- Paper trading mode for safe PnL demonstration
- Order status monitoring + auto-retry
- PnL tracking: realized + unrealized, logged per-trade

#### 5. ERC-8004 Trust Layer (→ Best Trustless Agent + Best Validation prizes)
- Deploy Agent Identity (ERC-721) on Base Sepolia
- Agent Registration JSON with capabilities, endpoints
- EIP-712 signed TradeIntents for every trade
- Validation artifacts: pre-trade risk check + post-trade PnL
- Reputation accumulation from objective outcomes
- On-chain events for every checkpoint

#### 6. Yield Module (→ Best Yield/Portfolio Agent prize)
- Aerodrome Finance integration for LP optimization
- Agent allocates idle capital to highest-yield pools
- Rebalances based on IL risk + yield comparison
- Even a simple version scores this prize (few competitors here)

#### 7. Dashboard (→ Presentation score)
- Streamlit: live PnL chart, trade log, risk metrics
- On-chain activity viewer (ERC-8004 events)
- Agent reasoning log (why each trade was made)
- Strategy performance comparison

---

## 7-Day Build Plan

### Day 1 (April 5) — Foundation
- [ ] Register at early.surge.xyz
- [ ] Create GitHub repo, project structure, .env setup
- [ ] Install Kraken CLI + configure MCP
- [ ] Get PRISM API key (code: LABLAB)
- [ ] Build data fetcher: Kraken CLI market data + PRISM signals
- [ ] First social post: "Day 1 — Starting my AI trading agent build"

### Day 2 (April 6) — Strategy Engine
- [ ] Implement LangGraph agent with Claude API
- [ ] Build signal analysis → decision pipeline
- [ ] Implement multi-strategy logic (momentum + mean-reversion)
- [ ] Test with historical data
- [ ] Social post: architecture diagram

### Day 3 (April 7) — Execution + Risk
- [ ] Connect strategy output → Kraken CLI execution
- [ ] Implement paper trading flow
- [ ] Build Risk Guardian module (all limits)
- [ ] Test end-to-end: signal → analyze → risk check → execute
- [ ] Social post: "First autonomous trade executed"

### Day 4 (April 8) — ERC-8004 Trust Layer
- [ ] Deploy Identity Registry on Base Sepolia
- [ ] Mint Agent Identity (ERC-721)
- [ ] Implement EIP-712 TradeIntent signing
- [ ] Connect to Validation Registry
- [ ] Emit on-chain events per trade
- [ ] Social post: "On-chain agent identity live"

### Day 5 (April 9) — Yield Module + Polish
- [ ] Implement Aerodrome yield module (even basic)
- [ ] Build Streamlit dashboard
- [ ] Full integration testing
- [ ] Bug fixes, error handling
- [ ] Social post: code snippet of the most interesting part

### Day 6 (April 10) — Demo + Presentation
- [ ] Record 3-5 min demo video showing:
  - Agent making autonomous trades
  - Risk guardrails activating
  - On-chain identity + validation artifacts
  - PnL dashboard
  - Agent explaining its reasoning
- [ ] Build slide deck (8 slides)
- [ ] Create cover image
- [ ] Social post: 30-sec demo clip

### Day 7 (April 11) — Submit Early
- [ ] Clean up code, write README
- [ ] Final PnL screenshot for Kraken leaderboard
- [ ] Submit on lablab.ai (don't wait for April 12)
- [ ] Submit read-only Kraken API key
- [ ] Final social media blast
- [ ] Self-score on judging criteria

---

## What Makes This WIN (vs. Competition)

| Factor | Our Approach | Why It Wins |
|--------|-------------|-------------|
| **Depth of integration** | Both Kraken CLI AND ERC-8004 deeply integrated | Eligible for ALL prizes, judges see serious effort |
| **Not just a bot** | Agent with identity, reputation, compliance | Trustless + accountable = real business value |
| **XAI reasoning** | Every trade has a logged rationale | Judges can understand WHY the agent trades |
| **Risk-first** | Circuit breakers, stop-loss, position limits | Shows maturity, maps to "Best Compliance" prize |
| **Yield module** | Aerodrome LP optimization | Few competitors for this special award |
| **Presentation** | Live dashboard + clear demo video | Judges don't need to run your code |
| **Social engagement** | 9 posts over 9 days, tagged correctly | Separate $2K prize pool |

---

## Judging Criteria Self-Check

| Criterion | Target Score | How |
|-----------|-------------|-----|
| **Application of Technology** | 9/10 | Deep Kraken CLI + ERC-8004 + PRISM integration, not superficial |
| **Presentation** | 9/10 | Pro demo video, live dashboard, clean slide deck |
| **Business Value** | 8/10 | "Trustless autonomous trading for institutional DeFi" narrative |
| **Originality** | 9/10 | XAI reasoning + on-chain compliance + multi-strategy + yield optimization in one agent |

---

## Social Engagement Calendar

Post on X, LinkedIn, and Instagram. Tag @krakenfx @lablabai @Surgexyz_ every time.

| Date | Post Theme | Content Idea |
|------|-----------|-------------|
| Apr 5 | Announcement | "Building an autonomous trading agent for the @lablabai hackathon" |
| Apr 6 | Architecture | Share the system diagram above |
| Apr 7 | Tech deep-dive | "How I'm using Kraken CLI MCP to let my AI agent trade autonomously" |
| Apr 8 | Progress | "First live signal → trade → on-chain validation pipeline working" |
| Apr 9 | ERC-8004 | "Why your AI agent needs an on-chain identity (ERC-8004)" |
| Apr 10 | Challenge | "Hardest problem I solved: [specific technical challenge]" |
| Apr 11 | Demo | Short video clip of the agent trading |
| Apr 12 | Submission | "We submitted! Here's what we built in 7 days" |

Use hashtags: `#AITradingAgents #lablabai #Kraken #ERC8004 #BuildInPublic #AIAgents #DeFi #Web3`

---

## Tech Stack (Final)

```
Python 3.12+
├── langgraph           — agent orchestration
├── anthropic           — Claude API for strategy reasoning
├── ccxt                — Kraken market data (backup to CLI)
├── httpx               — PRISM API calls
├── pandas + pandas-ta  — technical indicators
├── web3.py             — ERC-8004 on-chain interactions
├── eth-abi             — EIP-712 typed data encoding
├── streamlit           — live dashboard
├── python-dotenv       — env management
└── kraken-cli (system) — trade execution via MCP/subprocess
```

---

## Critical Reminders

1. **Register at early.surge.xyz FIRST** — no registration = no prize eligibility
2. **Read-only Kraken API key ONLY** — never withdrawal access
3. **Never commit API keys** — use .env
4. **Submit by April 11** — don't risk deadline issues
5. **Paper trading is fine** — you don't need real money for impressive PnL
6. **Combined submission** — explicitly state you're entering BOTH challenges
7. **Tag all 3 accounts** in every social post (Kraken, lablab, Surge)
