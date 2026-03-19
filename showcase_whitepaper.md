# Solanalyze Showcase Whitepaper  
**Public Showcase Edition (Non-Replicable)**

> This document is intentionally designed for public demonstration.  
> It explains product value, analytical methodology, and system capabilities **without exposing proprietary implementation details**.

---

## 1) Executive Summary

**Solanalyze** is a forensic intelligence platform for Solana wallet investigations.  
It helps analysts, traders, and risk teams identify hidden relationships between wallets by combining transfer analysis, path tracing, funder discovery, deep counterparty scanning, shared token detection, and behavior signals into one coherent investigation workflow.

The platform is built to answer a hard question quickly:

**"Are these wallets truly independent, or part of the same behavioral cluster?"**

Solanalyze reduces manual chain investigation overhead and provides a structured, visual, and repeatable framework for wallet-level risk assessment.

---

## 2) Problem Statement

Most users rely on fragmented tools and raw explorers when investigating wallets.  
That creates several issues:

- Critical links are missed in high-volume transaction histories
- Shared funders and intermediary wallets remain hidden
- Hidden connections through counterparty overlap go undetected
- Coordinated token trading patterns are invisible without cross-wallet analysis
- Investigations are slow and non-repeatable
- Risk signals are hard to consolidate into one decision

For teams operating in volatile environments (memecoins, fresh launches, coordinated wallet activity), delayed insight means missed opportunities and avoidable losses.

---

## 3) What Solanalyze Does

Solanalyze transforms raw wallet activity into structured intelligence through **11 analysis modules**:

### Core Modules
1. **Direct Link Detection**  
   Detects direct SOL and token transfer relationships between analyzed wallets. Records amounts, timestamps, and transaction signatures for evidence.

2. **Common Funder Discovery**  
   Identifies external wallets funding multiple target wallets. Reveals shared funding origins that indicate coordination.

3. **Intermediate Path Tracing**  
   Reveals bridge patterns (A -> X -> B) across one-hop and multi-hop paths. Tracks SOL flow through intermediary wallets.

4. **Funding Source Mapping**  
   Tracks historical incoming-fund origins for each wallet. Identifies known exchange wallets (Binance, Coinbase, Kraken, OKX, Bybit, KuCoin).

5. **DEX Interaction Profiling**  
   Extracts protocol-level behavior patterns across trading venues including Jupiter, Raydium, Orca, Phoenix, Meteora, and Pump.fun.

6. **Token Launch Detection**  
   Detects Pump.fun launches and Raydium pool creation by analyzed wallets. Identifies insider buying patterns and sniper timing.

7. **Deep Discovery (Deep Search)** NEW  
   The most powerful module. Scans significant counterparties of analyzed wallets to find hidden connections invisible to standard analysis. Classifies connections as mutual contacts, fund relays, shared recipients, shared funders, or chain connections. Includes confidence scoring with temporal proximity bonuses. Extends all other modules with newly discovered findings.

8. **Shared Token Activity** NEW  
   Detects when multiple analyzed wallets traded the same token. Calculates confidence scores based on temporal proximity and trading pattern correlation. Enriches with token metadata (name, symbol, image).

9. **Wallet Labels (Investigator Annotation)**  
   Assign custom names to wallet addresses for improved readability. Labels propagate across all result sections, the network graph, and JSON exports.

10. **Top Holder Map (Bubble Map)** NEW  
    Interactive bubble map for any Solana token. Enter a token mint address and instantly see the top holders visualized as bubbles (sized by % of supply held). Transfer links between holders reveal potential bundle activity. Select holders and load them directly into the Tracer for full forensic analysis. **FREE for all logged-in users** — no credits required.

11. **Interactive Network Graph**  
    Converts all findings into an interactive force-directed graph. Color-coded nodes and edges for different entity types. Supports drag, zoom, and hover tooltips.

---

## 4) High-Level Analysis Pipeline (Public-Safe)

Below is a simplified, non-sensitive representation of the analysis flow:

```
INPUT: wallet_addresses[] (up to 30)

Step 1 — Validate & Ingest
  validate addresses (base58, max 30)
  fetch transaction history per wallet
  normalize transfers (SOL + token)
  classify program interactions (DEX, token, system)

Step 2 — Core Analysis
  detect direct links between wallets
  trace intermediate paths (A -> X -> B)
  discover common funders
  map funding sources per wallet
  profile DEX interactions
  detect token launches + insider buys
  detect shared token activity across wallets

Step 3 — Deep Discovery (optional, paid plans)
  score significant counterparties
  filter blacklisted addresses (Jito tips, protocols, bots)
  scan top counterparties for hidden connections
  classify connection types (mutual_contact, fund_relay, shared_recipient, shared_funder, chain_connection)
  calculate confidence scores
  extend core modules with deep findings

Step 4 — Visualize & Export
  build interactive network graph
  add discovery nodes to graph
  generate structured JSON export
  present results with wallet labels
```

---

## 5) Deep Discovery — In Detail

Deep Discovery is Solanalyze's most advanced analysis capability. It goes beyond the wallets you enter and actively scans their counterparties to find connections that would be invisible to standard analysis.

### How It Works
1. **Counterparty Scoring:** For each analyzed wallet, the system identifies significant recipients — wallets that received meaningful SOL amounts (not just dust or fees).
2. **Blacklist Filtering:** Known non-user addresses are automatically excluded: Jito tip accounts, protocol fee wallets, system programs, and high-frequency bot addresses.
3. **Discovery Scanning:** The system fetches transaction history for the top-scored counterparties.
4. **Connection Detection:** It checks whether any discovery wallet also transacted with OTHER analyzed wallets, revealing hidden links.
5. **Confidence Scoring:** Each discovered connection receives a confidence score based on connection type, transaction volume, and temporal proximity.

### Connection Types
- **Mutual Contact:** Discovery wallet transacted with both Wallet A and Wallet B
- **Fund Relay:** Discovery wallet received from A and sent to B (money laundering pattern)
- **Shared Recipient:** Both A and B sent funds to the same discovery wallet
- **Shared Funder:** Discovery wallet funded both A and B
- **Chain Connection:** Multi-hop chain (A -> X -> Y -> B) through multiple discovery wallets

### Why It Matters
Without Deep Discovery, an investigator would only see connections between the wallets they explicitly entered. With Deep Discovery enabled, Solanalyze automatically finds the "missing links" — intermediary wallets that connect seemingly unrelated addresses.

---

## 6) Shared Token Activity — In Detail

Shared Token Activity detects when multiple analyzed wallets traded or held the same token, which is a strong indicator of coordination.

### How It Works
1. Scans all token transfer activity across analyzed wallets
2. Identifies tokens that appear in transactions of 2+ analyzed wallets
3. Calculates confidence based on temporal proximity (closer trades = higher score)
4. Enriches with token metadata (name, symbol, image) via API
5. Provides per-wallet activity breakdown (buys, sells, transaction count)

### Why It Matters
Coordinated wallet clusters often trade the same tokens — especially in pump-and-dump schemes. If Wallet A and Wallet B both bought $PHANTOM within seconds of each other, that's a strong signal they're controlled by the same entity.

---

## 7) Pricing and Access

Solanalyze uses transparent, on-chain SOL payments with automatic detection.

### Free Trial
- **7 days** free access after registration
- All core analysis modules included
- Bring Your Own Helius API Key (free at helius.dev)
- Deep Discovery locked during trial

### Monthly Flatrate — 0.5 SOL
- Unlimited queries
- All modules including Deep Discovery
- Helius API included (no key needed)

### Yearly Flatrate — 4.0 SOL (save 33%)
- Unlimited queries
- All modules including Deep Discovery
- Helius API included (no key needed)

### Pay-per-Use Credits
- 10 credits per standard query
- 30 extra credits per Deep Discovery scan (40 total including base query)
- Credits never expire
- Helius API included

| Amount | Credits | Standard Queries (10 each) | Deep Discovery Scans (40 each) |
|--------|---------|---------------------------|-------------------------------|
| 0.10 SOL | 500 | 50 | ~12 |
| 0.20 SOL | 1,250 | 125 | ~31 |
| 0.30 SOL | 2,250 | 225 | ~56 |
| 0.40 SOL | 3,500 | 350 | ~87 |

### Payment Details
- **Payment Wallet:** `ADwDdN9EJvRhwZk1kv8WcmAbh973QoaBhc4johxNYNiM`
- Payments detected automatically within ~60 seconds
- Overpayment stored as credit balance
- Send from your registered wallet address

### Referral Program
- Earn 10% commission on all payments from referred users
- Unique referral codes and share links
- Payouts processed by admin

---

## 8) Investigation Workflow

A typical Solanalyze investigation follows this pattern:

1. **Enter Wallets:** Paste up to 30 suspicious wallet addresses
2. **Label Wallets:** Optionally assign names (e.g., "Deployer", "Sniper Bot A")
3. **Enable Deep Discovery:** Toggle on for maximum depth (paid plans)
4. **Run Analysis:** Click "Trace Connections" and watch real-time progress
5. **Review Results:** Examine each module's findings:
   - Network graph for visual overview
   - Direct links for explicit transfers
   - Intermediate paths for hidden routing
   - Common funders for shared origins
   - Token launches for insider patterns
   - Shared tokens for coordinated trading
   - Deep Discovery for hidden connections
6. **Export Evidence:** Download full JSON report with all findings and transaction signatures
7. **Verify On-Chain:** Click any transaction signature to verify on Sol

