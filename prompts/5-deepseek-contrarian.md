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
