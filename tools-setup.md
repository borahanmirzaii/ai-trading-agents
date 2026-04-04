# Tools & MCP Setup — AI Trading Agents Hackathon

## MCP Servers to Install

### 1. Kraken CLI (trade directly from Claude Code)
```bash
# Install Kraken CLI
curl --proto '=https' --tlsv1.2 -LsSf https://github.com/krakenfx/kraken-cli/releases/latest/download/kraken-cli-installer.sh | sh

# Add as MCP server
claude mcp add-json kraken '{"type":"stdio","command":"kraken","args":["mcp","-s","all"]}'
```

### 2. CCXT (multi-exchange market data)
```bash
npx -y @smithery/cli install mcp-server-ccxt --client claude
```

### 3. Foundry (ERC-8004 smart contract dev)
```bash
# Install Foundry
curl -L https://foundry.paradigm.xyz | bash
foundryup

# Add as MCP server
claude mcp add-json foundry '{"type":"stdio","command":"npx","args":["@pranesh.asp/foundry-mcp-server"],"env":{"RPC_URL":"","PRIVATE_KEY":""}}'
```

### 4. Base MCP (on-chain operations on Base L2)
```bash
claude mcp add-json base-mcp '{"type":"stdio","command":"npx","args":["-y","base-mcp@latest"],"env":{"COINBASE_API_KEY_NAME":"YOUR_KEY","COINBASE_API_PRIVATE_KEY":"YOUR_PRIV_KEY"}}'
```

## Claude Code Plugins & Skills

```bash
# Skill collections
/plugin marketplace add alirezarezvani/claude-skills
/plugin marketplace add affaan-m/everything-claude-code
```

## Key GitHub Repos to Study

| Repo | Purpose |
|------|---------|
| https://github.com/krakenfx/kraken-cli | Official Kraken CLI with MCP support |
| https://github.com/sudeepb02/awesome-erc8004 | ERC-8004 starter templates |
| https://eips.ethereum.org/EIPS/eip-8004 | ERC-8004 spec |
| https://github.com/Nayshins/mcp-server-ccxt | CCXT MCP server |
| https://github.com/PraneshASP/foundry-mcp-server | Foundry MCP |
| https://github.com/base/base-mcp | Base MCP by Coinbase |
| https://github.com/circlefin | Circle repos (useful for nano-payments later) |

## Recommended Tech Stack

```
Python 3.12+
├── LangGraph          — agent orchestration (decision loops)
├── ccxt               — Kraken market data
├── anthropic          — Claude API for signal analysis
├── web3.py            — ERC-8004 on-chain interactions
├── pandas + ta-lib    — technical indicators
├── streamlit          — live PnL dashboard
├── httpx              — PRISM API calls
└── python-dotenv      — env management
```
