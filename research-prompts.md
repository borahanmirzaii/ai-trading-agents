# Research Prompts — AI Trading Agents Hackathon

> Run these in parallel across different AIs. Each is tuned to that AI's strengths.
> Copy-paste directly. Each prompt includes competition context.

---

## Perplexity (real-time search — what exists NOW)

```
I'm in the "AI Trading Agents Hackathon" by lablab.ai x Kraken x Surge (ends April 12, 2026). $55K prize pool. 2,499 enrolled.

I'm building a COMBINED submission (Kraken CLI + ERC-8004) to target all 7 prize categories. My competitors include:
- Botify: 12 CrewAI agents, self-evolving, ERC-8004
- QuantTrader: XAI mentor, deterministic signals
- TradeX: workflow canvas dashboard

I need CURRENT information on:

1. Search GitHub for "kraken-cli" agent examples — any real trading agent repos using it?
2. Search for "erc-8004" implementations beyond the official repo (erc-8004/erc-8004-contracts). Who has deployed working agents?
3. Find the Phala Network TEE agent (erc-8004-tee-agent) — what can I learn from their approach?
4. Search for "PRISM API" or "prismapi.ai" integration examples
5. What's the best Python library for EIP-712 typed data signing?
6. Search for Aerodrome Finance agent/bot integrations on Base L2
7. What are the most successful LangGraph trading agent architectures?
8. Any lablab.ai hackathon winner post-mortems or "how we won" blog posts?

I need SPECIFIC code repos, not general advice.
```

---

## Gemini (deep technical architecture — get the hard parts right)

```
I'm building an autonomous AI trading agent for a $55K hackathon. I have 7 days. Combined submission using BOTH:

CHALLENGE 1 - Kraken CLI:
- Zero-dependency Rust binary with built-in MCP server
- 151 commands, paper trading mode, JSON output
- PnL leaderboard ranking (net PnL = realized + unrealized)

CHALLENGE 2 - ERC-8004:
- Identity Registry (ERC-721 agent identity)
- Reputation Registry (feedback signals)
- Validation Registry (validator results)
- Must use EIP-712 typed data signatures for TradeIntents
- Must connect to Hackathon Capital Vault + Risk Router

My stack: Python + LangGraph + Claude API + Kraken CLI + web3.py + Streamlit

I need you to design the EXACT implementation for these 5 hard parts:

1. **EIP-712 TradeIntent Schema**: Design the exact typed data structure for a TradeIntent (asset, direction, size, price, timestamp, risk_score, strategy_rationale). Show me the Python code using eth_abi and web3.py to sign this.

2. **LangGraph Agent Graph**: Design the state machine with these nodes: [market_data_fetch, signal_analysis, strategy_decision, risk_check, execute_trade, record_on_chain, update_reputation]. What's the state schema? What are the edges and conditions?

3. **Risk Guardian Module**: Design a risk engine that enforces: max 5% position per trade, max 3% daily drawdown, circuit breaker after 3 losses, 2% stop-loss per position. How to enforce these BOTH pre-execution (Python) AND on-chain (Solidity modifier)?

4. **Kraken CLI Integration in Python**: Best way to call kraken CLI from Python? subprocess with JSON parsing? Or use the MCP server programmatically? Show the execution flow for: get_ticker → place_order → check_order_status → calculate_pnl.

5. **Aerodrome Yield Module**: Minimal viable integration — how to query Aerodrome pools on Base, find best yield, and allocate idle capital? What contracts do I interact with?

Give me CODE, not theory. Python + Solidity where needed.
```

---

## ChatGPT (full project scaffold — get the skeleton running fast)

```
Create a complete Python project for an autonomous AI trading agent called "TrustAgent".

Requirements:
- Uses LangGraph for agent orchestration
- Uses Kraken CLI (called via subprocess, outputs JSON) for trade execution
- Uses PRISM API (prismapi.ai) for AI signals
- Uses Claude API (anthropic SDK) for strategy reasoning
- Uses web3.py for ERC-8004 on-chain interactions on Base Sepolia
- Uses Streamlit for a live dashboard
- Uses pandas-ta for technical indicators

Project structure:
```
trustagent/
├── pyproject.toml              # uv project config
├── .env.example
├── .gitignore
├── README.md
├── src/
│   ├── __init__.py
│   ├── agent/
│   │   ├── __init__.py
│   │   ├── graph.py            # LangGraph agent definition
│   │   ├── state.py            # Agent state schema
│   │   └── nodes.py            # Node functions (fetch, analyze, decide, execute, record)
│   ├── data/
│   │   ├── __init__.py
│   │   ├── kraken.py           # Kraken CLI wrapper
│   │   ├── prism.py            # PRISM API client
│   │   └── indicators.py       # Technical indicators
│   ├── strategy/
│   │   ├── __init__.py
│   │   ├── engine.py           # Multi-strategy selector
│   │   └── reasoning.py        # Claude API for trade rationale
│   ├── risk/
│   │   ├── __init__.py
│   │   └── guardian.py         # Risk checks, circuit breaker, position limits
│   ├── trust/
│   │   ├── __init__.py
│   │   ├── identity.py         # ERC-8004 identity management
│   │   ├── reputation.py       # Reputation registry interactions
│   │   ├── validation.py       # Validation artifacts
│   │   └── eip712.py           # EIP-712 TradeIntent signing
│   ├── yield_module/
│   │   ├── __init__.py
│   │   └── aerodrome.py        # Aerodrome LP yield optimization
│   └── dashboard/
│       ├── __init__.py
│       └── app.py              # Streamlit dashboard
├── contracts/
│   └── RiskGuardian.sol        # On-chain risk enforcement
├── scripts/
│   ├── deploy.py               # Deploy ERC-8004 contracts
│   └── run_agent.py            # Main entry point
└── tests/
    ├── test_kraken.py
    ├── test_risk.py
    └── test_trust.py
```

For each file, write skeleton code with:
- Correct imports
- Class/function signatures with type hints
- TODO comments for implementation details
- Working connection between modules

The agent loop should run every 60 seconds:
fetch_data → compute_indicators → get_prism_signals → claude_analyze → risk_check → execute_via_kraken → sign_eip712_intent → record_on_chain → update_dashboard

Make it runnable with: `uv run python scripts/run_agent.py`
```

---

## Claude.ai (strategy + originality + presentation)

```
I'm competing in a $55K AI trading agents hackathon (ends April 12, 2026). 2,499 enrolled but only ~15 teams will submit. I'm building a COMBINED Kraken CLI + ERC-8004 submission.

My competitors:
- Botify: 12 CrewAI agents, self-evolving (over-engineered risk)
- QuantTrader: XAI mentor with risk caps (no ERC-8004)
- OneDev: solo dev, basic integration
- Ice Cream: no-code platform (not an agent)

Judges include people from Apple, Khalifa University, RB Global, NEOM, NativelyAI.

I need help with the TOP 3 things that separate winners from losers:

### 1. ORIGINALITY (most important)
What angle would make a hackathon judge who's seen 200 trading bots say "THIS is different"? My current idea: an agent that explains every trade decision on-chain (XAI + ERC-8004 validation = verifiable reasoning). Is this strong enough? What's stronger?

### 2. BUSINESS VALUE NARRATIVE
"Who would pay for this?" I need a 2-sentence pitch that makes institutional investors or compliance teams say "I need this NOW." Current idea: "TrustAgent is the first autonomous trader that proves its reasoning on-chain — giving institutions the auditability they need to deploy AI capital at scale." Better ideas?

### 3. DEMO VIDEO SCRIPT
Write me a 3-minute demo video script. Structure:
- 0:00-0:30 — Hook (the problem)
- 0:30-1:00 — Solution overview
- 1:00-2:00 — Live demo (what to show on screen)
- 2:00-2:30 — On-chain proof (ERC-8004 in action)
- 2:30-3:00 — Business value + call to action

Make it compelling enough to win. Think TED talk energy, not boring tech demo.
```

---

## DeepSeek (contrarian thinking — avoid common traps)

```
I'm building an AI trading agent for a hackathon in 7 days. Before I start coding, I need you to be my contrarian advisor. Challenge every assumption.

My plan:
- Python + LangGraph + Claude API for strategy
- Kraken CLI for execution (paper trading)
- ERC-8004 for on-chain identity/trust
- PRISM API for signals
- Streamlit dashboard
- Target all 7 prize categories

CHALLENGE ME:

1. Is LangGraph overkill for a 7-day hackathon? Would a simple Python loop with state management be faster to build and debug? What's the minimum viable agent architecture?

2. Using Claude API for trade decisions — is this actually smart, or will LLM latency and hallucination kill my trading performance? Should I use rule-based signals with LLM only for reasoning/explanation?

3. ERC-8004 integration — the official contracts are on 40+ networks. Should I deploy my own or use the existing registries? What's the fastest path to a working identity + validation flow?

4. Paper trading PnL — judges rank by net PnL. What trading strategy maximizes PnL in a 7-day window with paper trading? (Since there's no real risk, should I be more aggressive?)

5. Targeting all 7 prize categories — is this spreading too thin? Should I go deep on 2-3 categories instead? Which categories have the least competition?

6. What will ACTUALLY break during the build? Where do hackathon trading bots typically fail? (API rate limits? On-chain gas? LLM response format inconsistency?)

7. My competitors include a 12-agent CrewAI system (Botify). Should I compete on complexity or on simplicity and reliability?

Be brutal. I'd rather know the traps now than discover them on day 5.
```

---

## Bonus: Perplexity Search #2 (social engagement research)

```
Search for:
1. Best "build in public" posts for hackathons that got high engagement on X/Twitter in 2025-2026
2. What posting times get maximum engagement for tech/crypto content?
3. Examples of hackathon participants who won the "social engagement" prize — what did their posts look like?
4. Best tools for scheduling posts across X, LinkedIn, and Instagram simultaneously
5. Should I post threads or single tweets? Video or text? What format gets more impressions?

I need to win a social engagement prize judged purely on quantitative metrics (impressions, likes, shares, reach). Give me a data-driven posting strategy.
```
