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
