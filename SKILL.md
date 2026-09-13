---
name: iform-web3-forms
displayName: IFORM Decentralized Web3 Forms
description: Create, deploy, and manage decentralized Web3 forms and surveys on EVM smart contracts via Model Context Protocol (MCP).
version: 1.0.0
homepage: https://iform.fun
---

# IFORM Web3 Forms & Survey Protocol

The **IFORM Protocol** empowers autonomous AI agents to build, deploy, manage, and query decentralized forms and surveys directly on EVM blockchains (Robinhood Chain, Arbitrum One, Optimism, and Ethereum).

## Remote MCP Server
- **Endpoint**: `https://iform.fun/api/ai/mcp`
- **Transport**: `HTTP / SSE` (Server-Sent Events)
- **JSON-RPC Protocol Version**: `2024-11-05`
- **Smart Contract (FormFactory)**: `0xE7202208254876b1de6384eab0637fCA6657c859`

## Available Tools

### 1. `generate_form_transaction`
Constructs an EVM transaction ready for a wallet or agent to sign and broadcast.
- **Actions supported**:
  - `createForm`: Deploys a new form on-chain with a computed schema hash and exact 0.00005 ETH protocol fee (`0x2d79883d2000`).
  - `closeForm`: Stops new submissions for a form.
  - `activateForm`: Re-enables a closed form.
  - `archiveForm`: Archives a form.
  - `updateSchemaHash`: Updates the on-chain IPFS / Keccak256 questions schema hash.

### 2. `confirm_form`
Indexes the on-chain created form in the IFORM decentralized registry, generating its 6-character short slug (e.g., `https://iform.fun/e3qa69`) and instant web interface.

### 3. `query_forms`
Searches and filters active forms by `chainId`, `owner`, or `status`.

### 4. `get_form_responses`
Retrieves responses and submission metrics for any given `formId` or slug.

## Example Claude Desktop Configuration
```json
{
  "mcpServers": {
    "iform": {
      "url": "https://iform.fun/api/ai/mcp"
    }
  }
}
```
