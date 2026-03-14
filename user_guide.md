# Solanalyze User Guide

> Complete guide to using Solanalyze — the forensic intelligence platform for Solana wallet investigations.

---

## 1. What is Solanalyze?

Solanalyze is a web-based forensic tool that analyzes relationships between Solana wallets. Enter up to 10 wallet addresses and the platform will automatically detect:

- **Direct Links** — Direct SOL and token transfers between wallets
- **Common Funders** — External wallets that funded multiple target wallets
- **Intermediate Paths** — Hidden routing through intermediary wallets (A → X → B)
- **Funding Sources** — Where each wallet received its initial funding
- **DEX Activity** — Trading behavior across Jupiter, Raydium, Orca, Pump.fun, and more
- **Token Launches** — Pump.fun and Raydium token deployments by analyzed wallets, with insider buy detection
- **Deep Discovery (Deep Search)** — Scans counterparties to find hidden connections invisible to standard analysis *(NEW)*
- **Shared Token Activity** — Detects when wallets traded the same token with confidence scoring *(NEW)*
- **Wallet Labels** — Assign custom names to wallets for readability across all results *(NEW)*
- **Interactive Network Graph** — Visual force-directed graph of all findings

All findings include clickable transaction signatures for on-chain verification via Solscan.

---

## 2. Getting Started

### 2.1 Create an Account
1. Go to [solanalyze.com](https://solanalyze.com)
2. Click **"Start Free Trial"** or navigate to `/tracer`
3. Register with your email and password
4. Verify your email via the confirmation link
5. Your **7-day free trial** starts immediately

### 2.2 Set Up Your Wallet (for payments)
1. Go to **Account** page
2. Enter your Solana wallet address
3. This wallet will be used to match payments for plan upgrades

### 2.3 Helius API Key (Trial Users)
During the free trial, you need to provide your own Helius API key:
1. Go to [helius.dev](https://www.helius.dev/) and create a free account
2. Copy your API key
3. Enter it in the **Account** page or directly in the Tracer

Paid plan users (Monthly, Yearly, Credits) get Helius API access included — no key needed.

---

## 3. Using the Tracer

### 3.1 Enter Wallet Addresses
- Navigate to the **Tracer** page (`/tracer`)
- Paste up to **10 wallet addresses** in the text area
- Addresses can be separated by newlines, commas, or spaces
- The system validates base58 format automatically

### 3.2 Label Your Wallets (Optional)
After entering addresses, a label section appears below:
- Assign custom names to each wallet (e.g., "Deployer", "Sniper Bot A", "Suspect 1")
- Labels appear across ALL result sections, the network graph, and JSON exports
- Maximum 20 characters per label
- Labels are optional but highly recommended for readability

### 3.3 Enable Deep Discovery (Optional)
- Toggle the **Deep Discovery** switch to enable deep counterparty scanning
- Deep Discovery scans significant recipients of your analyzed wallets to find hidden connections
- **Available on:** Monthly, Yearly, and Pay-per-Use plans
- **Not available on:** Free trial
- **Credit cost:** 30 credits per scan (Pay-per-Use plans)

### 3.4 Run the Analysis
- Click **"Trace Connections"**
- Watch the real-time progress bar showing each analysis step
- Analysis typically takes 15-60 seconds depending on wallet activity and Deep Discovery

---

## 4. Understanding Results

After analysis completes, results are displayed in the following sections:

### 4.1 Summary
Overview statistics including:
- Wallets analyzed, total transactions, total transfers
- Direct links found, intermediate links found, common funders found
- DEX platforms detected, token launches found
- Discovered connections found (Deep Discovery)
- Shared token connections found
- Whether Deep Discovery was enabled

### 4.2 Interactive Network Graph
A visual force-directed graph showing:
- **Purple nodes:** Analyzed wallets
- **Orange nodes:** Intermediate/discovery wallets
- **Yellow nodes:** Exchange wallets
- **Colored edges:** Different connection types (direct, funding, intermediate, discovered)
- Drag nodes to rearrange, scroll to zoom, hover for details

### 4.3 Direct Links
Shows all direct SOL and token transfers between analyzed wallets:
- Total SOL transferred, transaction count, token transfer count
- First-seen and last-seen timestamps
- Individual transfer details (amount, source protocol, timestamp)
- Clickable transaction signatures for Solscan verification

### 4.4 Intermediate Links
Shows hidden routing paths through intermediary wallets:
- Full path visualization (A → X → B or A → X → Y → B)
- Path labels showing wallet names
- Hop count, total SOL flow, timestamps
- Evidence transaction signatures

### 4.5 Common Funders
Shows external wallets that funded multiple analyzed wallets:
- Funder address with label (if known exchange)
- List of funded wallets with SOL amounts and transaction counts
- Total SOL funded across all targets
- Analyst notes highlighting suspicious patterns

### 4.6 Token Launches
Shows token deployments by analyzed wallets:
- Deployer wallet, token name/symbol, launch platform
- Initial liquidity amount
- List of buyers from the analyzed wallet set
- Buy timing relative to launch (sniper detection)
- Links to Pump.fun, DexScreener, Birdeye

### 4.7 Funding Sources
Shows where each analyzed wallet received its initial funding:
- Source wallet address with exchange label (if applicable)
- Funding amount in SOL
- Timestamp and total unique funders
- Sources found via Deep Discovery are marked

### 4.8 DEX Activity
Shows decentralized exchange interactions:
- Protocol name and interaction count per wallet
- Trading volume estimates where available
- Covers Jupiter, Raydium, Orca, Phoenix, Meteora, Pump.fun, Serum

### 4.9 Shared Token Activity *(NEW)*
Shows when multiple wallets traded the same token:
- Token name, symbol, and image (auto-fetched metadata)
- Confidence score (High/Medium/Low/Weak) based on temporal proximity
- Per-wallet activity breakdown (buys, sells, transaction count)
- Links to Pump.fun, DexScreener, Birdeye for further analysis
- Evidence transaction signatures

### 4.10 Deep Discovery — Discovered Connections *(NEW)*
Shows hidden connections found by scanning counterparties:
- Visual path: Wallet A → Discovery Wallet → Wallet B
- Connection type badge (Mutual Contact, Fund Relay, Shared Recipient, Shared Funder, Chain Connection)
- SOL amount and transaction count
- Full addresses with copy buttons and Solscan links
- Evidence transaction signatures

### 4.11 Recent Transfers
Table of the most recent transfers between analyzed wallets:
- Transfer type (SOL or Token), from/to addresses
- Amount, source protocol, transaction signature

---

## 5. Exporting Results

- Click **"Export JSON"** in the results header
- Downloads a complete JSON file with ALL analysis data
- Includes: summary, direct links, intermediate links, common funders, funding sources, DEX activity, token launches, shared tokens, discovered connections, network graph, recent transactions
- Wallet labels are preserved in the export
- Timestamped filename for report management

---

## 6. Pricing Plans

### Free Trial (7 days)
- All core analysis modules
- Bring Your Own Helius API Key
- Deep Discovery locked
- No payment required

### Monthly Flatrate — 0.5 SOL
- Unlimited queries
- All modules including Deep Discovery
- Helius API included

### Yearly Flatrate — 4.0 SOL (save 33%)
- Unlimited queries
- All modules including Deep Discovery
- Helius API included

### Pay-per-Use Credits
- 10 credits per standard query
- 30 credits per Deep Discovery scan
- Credits never expire
- Helius API included

| Amount | Credits | Queries | Deep Discovery Scans |
|--------|---------|---------|---------------------|
| 0.10 SOL | 500 | 50 | ~16 |
| 0.20 SOL | 1,250 | 125 | ~41 |
| 0.30 SOL | 2,250 | 225 | ~75 |
| 0.40 SOL | 3,500 | 350 | ~116 |

---

## 7. Making a Payment

1. Go to **Account** page
2. Make sure your Solana wallet address is set
3. Send the exact SOL amount to the payment wallet:
   ```
   ADwDdN9EJvRhwZk1kv8WcmAbh973QoaBhc4johxNYNiM
   ```
4. Payment is detected automatically within ~60 seconds
5. Your plan activates immediately
6. Overpayment is stored as credit balance
7. Underpayment shows remaining balance needed

**Important:** Send from your registered wallet address for automatic matching.

---

## 8. Referral Program

- Earn **10% commission** on all SOL payments from users you refer
- Get your unique referral code and share link from the Account page
- Share your link: `https://solanalyze.com/tracer?ref=YOUR_CODE`
- Track referred users, total earned, and pending balance
- Payouts processed by admin

---

## 9. Tips for Effective Investigations

1. **Start with known wallets** — Enter wallets you already suspect are connected
2. **Use labels** — Name your wallets for much easier result interpretation
3. **Enable Deep Discovery** — The hidden connections it finds are often the most valuable
4. **Check token launches** — Insider buying patterns are strong evidence of coordination
5. **Look at shared tokens** — If wallets trade the same obscure token, they're likely related
6. **Follow the funding** — Common funders are the strongest indicator of shared ownership
7. **Verify on-chain** — Click transaction signatures to verify findings on Solscan
8. **Export and save** — Download JSON reports for record-keeping and sharing

---

## 10. FAQ

**Q: How many wallets can I analyze at once?**  
A: Up to 10 wallet addresses per analysis.

**Q: What is Deep Discovery?**  
A: Deep Discovery scans the significant counterparties of your analyzed wallets to find hidden connections that standard analysis would miss. It's the most powerful feature for uncovering coordinated wallet clusters.

**Q: Why is Deep Discovery locked on the free trial?**  
A: Deep Discovery requires additional API calls and server resources. It's available on all paid plans (Monthly, Yearly, Credits).

**Q: How much does Deep Discovery cost on Pay-per-Use?**  
A: 30 credits per Deep Discovery scan, in addition to the 10 credits for the base query.

**Q: Do credits expire?**  
A: No, credits never expire.

**Q: What is Shared Token Activity?**  
A: It detects when multiple analyzed wallets traded the same token. This is especially suspicious when trades happened close in time, indicating coordinated activity.

**Q: Can I use Solanalyze without a Helius API key?**  
A: Yes, on paid plans (Monthly, Yearly, Credits) the Helius API is included. Only free trial users need to provide their own key.

**Q: How do I get a free Helius API key?**  
A: Visit [helius.dev](https://www.helius.dev/) and create a free account.

**Q: Is my data stored?**  
A: Analysis results are computed in real-time and displayed in your browser. We store account data (email, wallet, subscription) but not your analysis results.

**Q: Can I export my results?**  
A: Yes, click "Export JSON" to download a complete report with all findings.

---

## 11. Support

- **Website:** [solanalyze.com](https://solanalyze.com)
- **Telegram:** [@0xnynim](https://t.me/xNynim)
- **Twitter/X:** [@xNynim](https://x.com/0xNynim)
- **Developer Collective:** [0xUnstable.world](https://0xunstable.world)
