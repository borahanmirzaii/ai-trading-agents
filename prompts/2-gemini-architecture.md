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
