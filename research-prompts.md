# Research Prompts — AI Trading Agents Hackathon

Run these in parallel across different AIs to maximize coverage.

---

## Perplexity (real-time search & winning patterns)

```
I'm in the "AI Trading Agents Hackathon" by lablab.ai x Kraken x Surge (ends April 12, 2026). Prize pool $55K. I need to build an autonomous AI trading agent using Kraken CLI and ERC-8004 (agent identity standard).

Search for:
1. Winning projects from previous lablab.ai trading/DeFi hackathons — what made them win?
2. ERC-8004 implementations and starter templates on GitHub
3. Any open-source AI trading agent repos that use Kraken API
4. PRISM API (prismapi.ai) tutorials or integrations
5. Best strategies for the Kraken PnL leaderboard challenge
6. Aerodrome Finance integration examples for yield agents

Give me specific repos, code links, and what differentiated winners from losers.
```

---

## Gemini (deep technical architecture)

```
I'm building an autonomous AI trading agent for a hackathon. Tech stack: Kraken CLI, ERC-8004 (on-chain agent identity), PRISM API (AI signals), Python/LangGraph.

Help me design the optimal architecture:
1. What's the best LLM-based trading decision loop? (signal ingestion → analysis → risk check → execution → monitoring)
2. How should I implement ERC-8004 agent identity on Base L2? Walk me through the smart contract and registration flow.
3. What trading strategy has the best risk-adjusted returns for a 7-day demo period? (I need impressive PnL for the leaderboard)
4. How to implement EIP-712 typed data signing for TradeIntents?
5. Circuit breaker patterns for autonomous trading agents
6. How to generate compelling PnL metrics even with small capital

Be specific with code architecture, not generic advice.
```

---

## ChatGPT (code scaffold generation)

```
Build me a Python project scaffold for an AI trading agent with this exact stack:
- LangGraph for agent orchestration
- Kraken CLI for trade execution
- PRISM API (prismapi.ai) for AI signals and risk scores
- ERC-8004 smart contracts on Base L2 for agent identity
- Streamlit dashboard for live PnL visualization

The agent should:
1. Fetch market data + AI signals every 60 seconds
2. Use Claude API to analyze signals and decide buy/sell/hold
3. Execute trades via Kraken CLI
4. Log everything on-chain via ERC-8004 TradeIntents
5. Display real-time PnL on a dashboard

Give me the full project structure, requirements.txt, and skeleton code for each module.
```

---

## Claude.ai (strategy & originality)

```
I have 7 days left in a $55K trading hackathon. Judging criteria: Technology Application (deep Kraken CLI + ERC-8004 integration), Presentation, Business Value, Originality.

Most teams will build basic trading bots. Help me find an angle that's ORIGINAL:
1. What unique agent architectures would stand out? (multi-agent, self-improving, social sentiment, cross-chain arbitrage?)
2. How can I make ERC-8004 integration deeply meaningful rather than superficial?
3. What's a compelling business narrative — who would actually pay for this agent?
4. What demo moments create "wow factor" for judges?
5. How should I structure my 3-5 minute demo video for maximum impact?

Think like a hackathon judge who's seen 200 trading bots. What would make you pick a winner?
```

---

## DeepSeek (alternative architecture & optimization)

```
I'm building an autonomous AI crypto trading agent for a hackathon (8 days left). The agent must use Kraken CLI for execution and ERC-8004 for on-chain identity.

I want you to challenge conventional approaches:
1. What's wrong with typical LLM-based trading agents? What fails in practice?
2. Is a hybrid approach better — rule-based signals + LLM for risk assessment only?
3. How should I handle the cold-start problem with no historical backtest data for my specific strategy?
4. What's the minimal viable ERC-8004 integration that still impresses judges?
5. If I only have 5 days of actual build time, what should I cut vs keep?
6. What open-source trading frameworks (not LLM-based) could I wrap with an AI layer for speed?

Prioritize practical, buildable answers over theoretical perfection.
```
