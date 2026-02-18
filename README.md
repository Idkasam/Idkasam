# Kora — Deterministic Authorization for AI Agent Spending

I'm building [Kora](https://koraprotocol.com), the financial control plane for autonomous AI agents.

Every AI agent gets a cryptographic spending mandate — daily limits, vendor allowlists, category controls — enforced in a single database transaction. No ML. No probabilistic logic. If the math says no, the money doesn't move.

## Quickstart

```bash
pip install kora-sdk
```

```python
from kora import Kora

kora = Kora("kora_agent_sk_...", mandate="mandate_abc123")
result = kora.spend(vendor="openai", amount_cents=5000, currency="USD")
```

## Packages

| Package | Install | What it does |
|---|---|---|
| [kora-sdk](https://github.com/Idkasam/kora-sdk) | `pip install kora-sdk` | Python SDK — 5 lines to authorized spend |
| [@kora-protocol/sdk](https://www.npmjs.com/package/@kora-protocol/sdk) | `npm i @kora-protocol/sdk` | TypeScript SDK |
| [kora-mcp-server](https://github.com/Idkasam/kora-mcp-server) | `pip install kora-mcp-server` | MCP server for Claude Desktop |
| [n8n-nodes-kora](https://github.com/Idkasam/n8n-nodes-kora) | Community Nodes | n8n integration with two-output branching |

## How it works

```
Agent sends spend request
  → Ed25519 signature verification
  → 14-step deterministic pipeline
  → SERIALIZABLE PostgreSQL transaction
  → APPROVED + cryptographic seal  or  DENIED + actionable hint
```

## Links

- **Website:** [koraprotocol.com](https://koraprotocol.com)
- **Patent:** PCT/EP2025/053553
- **Live:** Production on Railway, <50ms p99

<!--
**Idkasam/Idkasam** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
