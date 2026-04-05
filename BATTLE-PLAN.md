# BATTLE PLAN — Final Synthesized Strategy

> Synthesized from Claude.ai, Perplexity, DeepSeek, and Perplexity Social research.
> Tensions resolved. This is the plan we execute.

---

## Key Tension Resolved

| DeepSeek says | Claude.ai says | **Our decision** |
|---------------|---------------|-------------------|
| Skip LangGraph, use simple loop | Use LangGraph for orchestration | **Simple loop + state dict. DeepSeek is right — LangGraph is 2 days of debugging we can't afford** |
| Skip ERC-8004, it's irrelevant | ERC-8004 is THE differentiator | **Keep ERC-8004 but MINIMAL — use existing registries, not deploy our own. It unlocks combined submission = more prizes** |
| LLM will kill PnL with latency | Use Claude for reasoning | **Hybrid: rule-based signals for execution speed, LLM only for reasoning/explanation logs. DeepSeek is right about latency** |
| Target 2-3 categories, not 7 | Target all 7 | **Target 4: Best Trustless Agent, Best Risk-Adjusted, Kraken PnL, Social Engagement. Drop Yield/Compliance/Validation as separate efforts** |
| Be aggressive with paper PnL | — | **Yes — 10-25x leverage, high-volatility pairs, wide stops. Paper trading = no real risk** |

---

## The Architecture (Napkin-Simple)

```
while True:
    data = kraken_cli_ticker()           # 50ms
    signals = prism_api_signals()         # 100ms
    indicators = compute_ta(data)         # 10ms

    decision = rule_based_decide(         # 1ms (FAST PATH)
        signals, indicators
    )

    if decision != "HOLD":
        risk_ok = risk_check(decision)    # 1ms
        if risk_ok:
            execute_kraken(decision)      # 200ms
            log_erc8004(decision)         # async, non-blocking
            reasoning = claude_explain(   # async, non-blocking
                decision, data, signals
            )

    sleep(30)
```

**Key insight from DeepSeek:** Rule-based execution (fast), LLM explanation (async, for judges). Never let the LLM block a trade.

---

## Narrative (from Claude.ai — this is gold)

**Don't call it:** "AI trading bot"
**Call it:** "Cryptographically Auditable Autonomous Capital"

**One-liner for README:**
> "TrustAgent is the compliance layer the industry doesn't know it's legally required to have yet."

**Business pitch (2 sentences):**
> "Every institutional AI trading deployment today carries a hidden liability: when regulators demand to know why the algorithm made a decision, there is no verifiable answer. TrustAgent eliminates that liability by writing cryptographically signed reasoning on-chain at the moment of every trade."

**Regulatory hooks to mention:**
- EU AI Act Article 13 (transparency requirements)
- MiFID II algorithmic trading obligations
- SEC Rule 17a-4

---

## Tech Stack (Final — Simplified)

```
Python 3.12+
├── httpx              — PRISM API + async HTTP
├── anthropic          — Claude API (explanation only, async)
├── pandas + pandas-ta — technical indicators
├── eth-account        — EIP-712 signing (web3.py dependency)
├── web3.py            — ERC-8004 on-chain (Base Sepolia)
├── streamlit          — dashboard
├── python-dotenv      — env vars
└── kraken-cli (system) — execution via subprocess
```

**Removed:** LangGraph, CrewAI, ccxt (Kraken CLI replaces this)

---

## ERC-8004 — Minimal Viable Integration (1 day, not 3)

From Perplexity research:
- **Use existing Identity Registry** on Base Sepolia (address: 0x8004A818...)
- **Don't deploy your own contracts**
- Use `eth-account` for EIP-712 signing (already in web3.py)
- Study `0xgasless/agent-sdk` for fastest integration pattern
- Study `Phala-Network/erc-8004-tee-agent` for registration flow

Minimal flow:
1. Mint Agent Identity (ERC-721) — 1 transaction
2. Set Agent Registration JSON (capabilities) — 1 transaction
3. Per trade: sign EIP-712 TradeIntent + emit validation event — async

---

## Trading Strategy (Aggressive Paper Trading)

From DeepSeek:
- **10-25x leverage** on every trade (paper = no real risk)
- Trade **BTC/USD and ETH/USD only** (highest liquidity + volatility)
- **Mean reversion + momentum hybrid:**
  - RSI < 30 → BUY (oversold bounce)
  - RSI > 70 → SELL (overbought reversal)
  - MACD crossover → confirm direction
  - Volume spike → increase position size
- **Wide stops (15-20%)** to avoid noise
- **Take profit at 8-12%**
- **Decision caching:** same market signature within 60s = cached decision

---

## 7-Day Execution Plan

| Day | Focus | Deliverable | Social Post |
|-----|-------|-------------|-------------|
| **Apr 5** | Core loop + Kraken CLI | Working data fetch + paper trade execution | "Starting the build" announcement |
| **Apr 6** | Signal engine + indicators | RSI/MACD/Volume signals generating decisions | Architecture diagram |
| **Apr 7** | Risk module + validation | Position limits, stop-loss, circuit breaker | "First autonomous trade" screenshot |
| **Apr 8** | ERC-8004 minimal integration | Agent identity minted, TradeIntents signed | "On-chain identity live" txhash |
| **Apr 9** | Claude reasoning + dashboard | Async trade explanations + Streamlit UI | Code snippet of interesting part |
| **Apr 10** | Testing + aggressive tuning | Leverage up, PnL optimization, bug fixes | Short demo clip |
| **Apr 11** | Demo video + submission | 3-min video, README, slides, SUBMIT | Submission announcement |

---

## Demo Video Script (from Claude.ai — use this)

- **0:00-0:30** — Hook: Flash Crash story, "why did the algorithm do that?"
- **0:30-1:00** — Solution: "First agent that writes reasoning to blockchain"
- **1:00-2:00** — Live demo: signal → decision → trade → on-chain proof
- **2:00-2:30** — Show txhash on block explorer, "reasoning rewind" feature
- **2:30-3:00** — Business value: EU AI Act, MiFID II, "$18B market by 2030"

**Key demo moment:** Show the ERC-8004 transaction appearing in real-time on block explorer. That 5-second moment > 60 seconds of slides.

---

## Social Engagement Plan (from Perplexity Social)

**Tool:** Buffer (free tier) — schedule across X + LinkedIn + Instagram

**Daily cadence:**
- X: 2-3 posts (Tue-Thu 9-11am + 12-5pm target audience timezone) + 20+ replies to @krakenfx @lablabai @Surgexyz_
- LinkedIn: 1 strong post (11am-3pm)
- Instagram: 1 Reel/Story (6-11pm)

**Every post must have:**
- Hook in first line
- One specific number/outcome
- Visual (screenshot, screen recording, diagram)
- Tags: @krakenfx @lablabai @Surgexyz_
- Hashtags: #AITradingAgents #lablabai #Kraken #ERC8004 #BuildInPublic

**Thread format for X (daily):**
> Tweet 1: Hook + outcome ("TrustAgent just executed its first autonomous trade with on-chain proof. Here's what happened 👇")
> Tweet 2-4: What we built, screenshot, technical detail
> Tweet 5: CTA ("Follow for daily updates" / link to repo)

---

## What Will Break (Pre-Mortemed)

| Failure | Prevention |
|---------|-----------|
| Kraken CLI rate limits | 30s minimum between calls, queue + backoff |
| Claude API format inconsistency | Strict JSON schema, retry on parse fail, fallback to rule-based |
| Claude API costs ($0.12/call) | LLM for explanation only (async), not decisions. Cache similar contexts |
| ERC-8004 gas on Base Sepolia | Use testnet, batch validations if needed |
| Bot crash loses state | JSON file persistence for portfolio + positions |
| LLM flip-flops on same data | Decision caching (60s TTL per market hash) |
| Connection drops during volatility | 3-tier fallback: Kraken CLI → PRISM → cached data |

---

## Files to Build (in order)

```
trustagent/
├── .env.example
├── .gitignore
├── README.md
├── pyproject.toml
├── src/
│   ├── main.py              # The loop (entry point)
│   ├── config.py             # Settings + env vars
│   ├── kraken.py             # Kraken CLI subprocess wrapper
│   ├── prism.py              # PRISM API client
│   ├── signals.py            # Technical indicators (RSI, MACD, volume)
│   ├── strategy.py           # Rule-based decision engine
│   ├── risk.py               # Position limits, circuit breaker, stop-loss
│   ├── trust.py              # ERC-8004 identity + EIP-712 signing
│   ├── reasoning.py          # Claude API async explanation
│   ├── state.py              # Portfolio state + JSON persistence
│   └── dashboard.py          # Streamlit app
└── contracts/
    └── (not needed — use existing registries)
```

**Flat structure, no nested packages.** Every file is self-contained. Maximum simplicity.
