# Community and Publications
&nbsp;

### Coinkite Tap Protocol library (Open-sourced - 2022)
- Open sourced [cktap](https://github.com/bithyve/cktap-protocol-react-native), A React Native library/sdk to enable easy communication with [TAPSIGNER™](https://tapsigner.com/) and [SATSCARD™](https://satscard.com/) with React-Native, Python and Javascript
&nbsp;

### Speaker @Bitcoin4India
- Spoke about *Securing Bitcoin with multisig* with [Bitcoin4India](https://bitcoin4india.org/) addressing a self-motivated crowd of about ~500.
&nbsp;

### Hosting Meetups on Bitcoin
- Hosting monthly meetups with [Bitcoin4India](https://www.meetup.com/bitcoinforindia/) with coffee and Bitcoin security

&nbsp;

# Projects

### Aegis Wallet — Agentic Bitcoin Wallet (MIT Bitcoin Hackathon 2026)
- **Description**: Seedless, self-custodial Bitcoin wallet where Claude (or Gemini) is the AI financial agent. Passkey authentication replaces seed phrases entirely — the WebAuthn PRF extension derives a BIP-32 master key from the device's secure enclave, and recovery is just syncing the passkey to a new device. Two-layer custody: L1 is a standard Taproot (BIP-86) wallet with keys derived client-side, and all on-chain transactions are signed in the browser — the server has zero access to funding keys. L2 is a custodial Lightning spending layer where the agent operates under a scoped macaroon tied to a litd account, with budget ceilings enforced cryptographically by LND's RPC middleware. When the agent exceeds its budget, the backend pushes an SSE notification to the dashboard and the user pays directly with one tap — sub-second latency, no polling. A Go sidecar handles LND gRPC via `lndclient` for proper protobuf handling. The backend has no database and no auth server — all state lives in litd accounts.
- **Tech Stack**: Next.js 15, React, Tailwind CSS, motion/react, Node.js 22 + Express + SSE, Go gateway (`lndclient`), bitcoinjs-lib, bip39, tiny-secp256k1, @simplewebauthn/browser, LND v0.20-beta + litd v0.16-alpha, Docker Compose, Bitcoin mainnet
- **Year**: 2026
- **Link**: [Aegis Wallet](https://github.com/PraneethGunas/aegis-wallet)
&nbsp;

---

### ln-mcp — Lightning Wallet MCP Server for AI Agents
- **Description**: Open-source MCP (Model Context Protocol) server published to npm that gives any AI agent a Bitcoin Lightning wallet. One `npx -y ln-mcp` and Claude Desktop, Claude Code, Gemini CLI, or ChatGPT can pay Lightning invoices, consume L402-gated APIs, and discover paid services — all within a macaroon-enforced budget. 10 tools across payments, spending, and discovery (proxied from the 402 Index's ~19,000 paid endpoints across L402, x402, and MPP protocols). The `l402_fetch` tool handles the full 402 → decode → pay → cache → retry loop in one call, with per-domain token caching. Deliberately minimal: 2 runtime dependencies, 4 source files, LND REST over gRPC. Deliberately omits `get_balance` and `decode_invoice` — agents used them to pre-check and refuse payments, defeating the approval flow. Distinguishes budget-exceeded failures from routing failures with explicit `TELL_USER` / `SHOW_TO_USER` response fields, after Gemini once invented a fake "Human-in-the-loop security policy" to explain a transient relay failure. Published via GitHub Actions OIDC trusted publishing with signed provenance via sigstore — zero long-lived npm credentials.
- **Tech Stack**: Node.js 22, @modelcontextprotocol/sdk, zod, LND REST API, 402 Index API, SendPaymentV2 streaming, stdio + HTTP transports
- **Year**: 2026
- **Link**: [ln-mcp](https://github.com/PraneethGunas/ln-mcp) | [npm](https://www.npmjs.com/package/ln-mcp)
&nbsp;

---

### x402 — L402-Powered Feed Reader
- **Description**: Pay-per-article feed reader where real RSS articles are gated behind HTTP 402 Payment Required. Readers connect their own Lightning node from the browser via LNC (Lightning Node Connect), pay a few sats, and read instantly. Features custom credential store fixing an upstream lnc-web reconnect bug, L402 token persistence, two-node payment architecture (provider + user), and a Go backend that fetches live feeds from Bitcoin Optech and Lightning Engineering with zero external dependencies.
- **Tech Stack**: Next.js, MobX, Emotion, Go, LNC, Aperture (L402), lnd, litd (watch-only + remote signer), Neutrino, Docker
- **Year**: 2026
- **Link**: [x402](https://github.com/PraneethGunas/x402)
&nbsp;

---

### PolicyPulse — AI-Powered Policy Impact Analyzer (HooHacks 2026 @ UVA)
- **Description**: Multi-agent AI system that analyzes how government policies personally impact you, backed by real government data. 7-agent pipeline across 4 stages — classification, research, parallel sector analysis (Labor, Housing, Consumer, Business), and synthesis. Features autonomous Lightning Network micropayments via L402 protocol: when free public data isn't enough, agents pay fractional satoshis to access premium databases, visualized in real-time. Streaming UI with live agent activity feeds, payment animations, and animated Sankey diagrams.
- **Tech Stack**: Next.js 16, React 19, Tailwind CSS 4, D3.js, FastAPI, Python, LangGraph, Google ADK, LND/Aperture (x402), Docker Compose
- **Year**: 2026
- **Link**: [PolicyPulse](https://github.com/PraneethGunas/HooHacks)
&nbsp;

---

### Empirical Comparison of Bitcoin Covenant Vault Designs
- **Description**: Three-way empirical comparison framework for CTV (BIP-119), CCV (BIP-443), and OP_VAULT (BIP-345) vault implementations. 12 experiments measuring transaction costs, security properties, and attack surfaces on regtest with Alloy formal verification.
- **Tech Stack**: Python, Bitcoin Core (regtest), Alloy
- **Year**: 2026
- **Link**: [Research Site](https://research.praneethg.xyz) | [Framework](https://github.com/PraneethGunas/vault-comparison)
&nbsp;

---

### CAT-CSFS Bitcoin Vault
- **Description**: A Bitcoin vault built on OP_CAT (BIP 347) and OP_CHECKSIGFROMSTACK (BIP 348) to enforce covenant spending rules on regtest. Implements on-chain transaction introspection using Schnorr signature tricks.
- **Tech Stack**: Python, Schnorr Signatures, Taproot
- **Year**: 2026
- **Link**: [CAT-CSFS Vault](https://github.com/PraneethGunas/cat-csfs-vault)
&nbsp;

---

### Liquid Network Mnemonic Recovery Tool
- **Description**: BIP39 mnemonic recovery tool for the Liquid Network. Brute-forces the last 2 missing words using a local Elements node at ~2,600 addr/s with no API rate limits.
- **Tech Stack**: Python, Elements (Liquid Network)
- **Year**: 2026
- **Link**: [Liquid Recovery](https://github.com/PraneethGunas/liquid-recovery)
&nbsp;

---

### Bitcoin Multisig Key Recovery Tool
- **Description**: A Rust-based CLI tool for key recovery in m-of-n Bitcoin multisig schemes. Addresses the vulnerability where loss of a single public key prevents recovery even with all private keys. Enables recovery with only 'm' keys using OP_RETURN.
- **Tech Stack**: Rust, Bitcoin Core
- **Year**: 2025
- **Link**: [Multisig Recovery](https://github.com/PraneethGunas/bitcoin-multisig-wallet)
&nbsp;

---

### Command & Control over DNS Tunneling
- **Description**: This project demonstrates a DNS Tunneling-based HTTP Proxy, allowing a client behind a firewall to send HTTP requests over DNS queries. This is useful in environments where internet access is blocked but DNS queries are allowed.
- **Tech Stack**: Python (dnscat2, iodine), Rust, Wireshark
- **Year**: 2025
- **Link**: [DNS Tunneling Attack](https://github.com/PraneethGunas/DNS-Tunnel-HTTP-Proxy)
&nbsp;

---

### Bitcoin Docker Dev Environments
- **Description**: Docker Compose setups for spinning up Blockstream's Elements (Liquid Network) and Bitcoin Inquisition (Bitcoin Core fork with OP_CAT, OP_CTV, etc. activated on signet) for research and development.
- **Tech Stack**: Shell, Docker Compose, Dockerfile, Bitcoin Core
- **Year**: 2025
- **Link**: [Elements Docker](https://github.com/PraneethGunas/elements-regtest-docker) | [Inquisition Docker](https://github.com/PraneethGunas/bitcoin-inquisition-docker)
&nbsp;

---

### TLS 1.3 0-RTT replay-attack vulnerability check
- **Description**: A network vulnerability experiment that exploits reply attack on TLS 1.3's 0-RTT early data
- **Tech Stack**: Rust, Openssl, Wireshark, Scapy, Python
- **Year**: 2024
- **Link**: [TLS 0-RTT reply](https://github.com/PraneethGunas/tls-1.3-0-rtt-reply-experiment)
&nbsp;

---

### Pictionary
- **Description**: A live socket-based interactive pictionary game for Android and iOS
- **Tech Stack**: React-Native, Typescript, Socket.io, Realm (MongoDB)
- **Year**: 2020
- **Link**: [Pictionary App](https://github.com/PraneethGunas/Pictionary-App)
&nbsp;

---

### Bitify (Decentralised Spotify)
- **Description**: A decentralised music streaming platform built on Ethereum where artists publish directly and listeners pay per stream via smart contracts.
- **Tech Stack**: Solidity, Javascript, React, Firebase, Truffle suite (Ganache, web3)
- **Year**: 2020
- **Link**: [Bitify](https://github.com/PraneethGunas/Bitify/tree/master)
&nbsp;
