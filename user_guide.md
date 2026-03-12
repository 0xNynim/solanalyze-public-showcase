# [SOLANALYZE] — User Guide

> **Advanced Wallet Forensics on Solana**  
> 🌐 [solanalyze.com](https://solanalyze.com)

---

## Table of Contents

1. [What is Solanalyze?](#1-what-is-solanalyze)
2. [Registration](#2-registration)
3. [Email Verification](#3-email-verification)
4. [Free Trial (7 Days)](#4-free-trial-7-days)
5. [Getting a Free Helius API Key](#5-getting-a-free-helius-api-key)
6. [Adding Your Helius API Key](#6-adding-your-helius-api-key)
7. [Pricing & Plans](#7-pricing--plans)
8. [How to Pay (SOL Payment)](#8-how-to-pay-sol-payment)
9. [Automatic Plan Activation](#9-automatic-plan-activation)
10. [Using the Tracer](#10-using-the-tracer)
11. [FAQ](#11-faq)

---

## 1. What is Solanalyze?

Solanalyze is an on-chain wallet forensics tool for the Solana blockchain. The **Tracer** feature allows you to analyze up to **10 wallets simultaneously** and uncover:

- 🔗 **Direct Links** — Direct SOL/token transfers between analyzed wallets
- 🕵️ **Intermediate Links** — Indirect connections via third-party wallets (A → X → B)
- 💰 **Common Funders** — External wallets that funded multiple analyzed wallets
- 🚀 **Token Launches** — Pump.fun / Raydium pool creations by analyzed wallets
- 📊 **DEX Activity** — Trading activity across Jupiter, Raydium, Orca, and more
- 🌐 **3D Network Graph** — Visual representation of all wallet connections

---

## 2. Registration

Go to **[solanalyze.com](https://solanalyze.com)** and click **Sign Up**.

You will need to provide:

| Field | Description |
|---|---|
| **Email** | Your real email address (no disposable/temp emails) |
| **Password** | A secure password of your choice |
| **Solana Wallet Address** | Your Solana wallet (e.g. from Phantom, Backpack, Solflare) |

> ⚠️ **Important — Wallet Address:**  
> Your Solana wallet address is **required** for payment processing. When you send SOL to upgrade your plan, Solanalyze automatically detects the transaction and matches it to your account **based on the sending wallet address**.  
>
> **If you pay from a wallet that is NOT registered in your account, the payment cannot be attributed to you and your plan will NOT be activated.**  
>
> You can update your wallet address later in your profile settings if needed.

---

## 3. Email Verification

After submitting the registration form, Solanalyze will send a **6-digit verification code** to your email address.

**Steps:**
1. Check your inbox for an email from `noreply@solanalyze.com`
2. **Also check your spam/junk folder** — verification emails can sometimes be filtered
3. Enter the 6-digit code on the verification page
4. The code is valid for **10 minutes** — request a new one if it expires

Once verified, your account is active and your **7-day free trial begins immediately**.

---

## 4. Free Trial (7 Days)

After successful registration, you get **7 days of free access** to the Solanalyze Tracer.

**Trial limitations:**
- ✅ Full access to all Tracer features
- ✅ Up to 10 wallets per query
- ⚠️ **Bring Your Own API Key** — You must provide your own Helius API key (free to get, see below)

---

## 5. Getting a Free Helius API Key

During the trial, you need a **free Helius API key** to use the Tracer.

**Steps to get your free key:**

1. Go to **[dev.helius.xyz](https://dev.helius.xyz)**
2. Click **"Get Started for Free"** or **"Sign Up"**
3. Create an account with your google account or github account. (important, only those will get a free API Key!)
4. Once logged in, navigate to **"API Keys"** in the dashboard
5. Your default API key is shown — copy it (it looks like: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`)

---

## 6. Adding Your Helius API Key

Once you have your Helius API key:

1. Log in to **[solanalyze.com](https://solanalyze.com)**
2. Click on your **Profile / Account** (top right)
3. Find the **"Helius API Key"** section
4. Paste your API key and save

Your key is now linked to your account and will be used automatically when you run Tracer queries.

---

## 7. Pricing & Plans

After your trial ends (or at any point during the trial), you can upgrade to a paid plan.

### 🔄 Pay-Per-Use Credits

Send exact amounts to receive credits. Each Tracer query costs **10 credits**.

| SOL Amount | Credits Received | Queries Included |
|---|---|---|
| **0.10 SOL** | 500 credits | ~50 queries |
| **0.20 SOL** | 1,250 credits | ~125 queries |
| **0.30 SOL** | 2,250 credits | ~225 queries |
| **0.40 SOL** | 3,500 credits | ~350 queries |

> Credits do not expire and accumulate — send multiple times to top up.

### ♾️ Flat Rate Plans

|    Plan     |  SOL Amount | Duration |   API Key   |
|-------------|-------------|----------|-------------|
| **Monthly** | **0.5 SOL** | 1 Month  | ✅ Included |
| **Yearly**  |  **4 SOL**  | 1 Year   | ✅ Included |

- **Unlimited queries** during the subscription period
- **No Helius API key required** — Solanalyze provides the API access
- Yearly plan saves ~33% compared to monthly

---

## 8. How to Pay (SOL Payment)

Payments are made directly on the **Solana blockchain** — no credit card, no KYC.

**Payment Wallet Address:**
```
ADwDdN9EJvRhwZk1kv8WcmAbh973QoaBhc4johxNYNiM
```

**Steps:**

1. Open your Solana wallet (Phantom, Backpack, Solflare, etc.)
2. Send the **exact SOL amount** for your desired plan to the address above
3. **Send from the wallet address registered in your Solanalyze account**
4. Wait **30–60 seconds** for automatic activation

> ⚠️ **Critical:** You MUST send from the wallet address that is saved in your Solanalyze profile. Payments from unregistered wallets cannot be matched to your account.

> 💡 **Tip:** Double-check the wallet address in your profile before sending. You can update it under **Account Settings** if needed.

---

## 9. Automatic Plan Activation

Solanalyze monitors the payment wallet on-chain in real time.

**What happens after you send SOL:**

1. Solanalyze detects your transaction within **30–60 seconds**
2. Your sending wallet is matched against registered accounts
3. Your plan is **automatically activated** — no manual action needed.
4. You will see your updated plan status in your **Account / Profile** page. 
Press F5 or refresh your tab if needed to see the updated plan details.

**Activation logic:**
- `0.10 – 0.49 SOL` → Credits added to your account (pay-per-use)
- `0.50 SOL` → Monthly flat rate activated
- `4.00 SOL` → Yearly flat rate activated
- Amounts accumulate — e.g. sending `0.20 SOL` twice = `0.40 SOL` total credit

---

## 10. Using the Tracer

Once your account is active (trial or paid):

1. Navigate to **Tracer** in the top menu
2. Enter up to **10 Solana wallet addresses** (comma, space, or newline separated)
3. *(Trial users only)* Your Helius API key is pre-filled from your profile
4. Click **"Analyze"**
5. Wait for the analysis to complete (typically 10–30 seconds depending on wallet activity)

**Results include:**
- **Summary** — Overview of connections found
- **Direct Links** — Wallets that transacted directly with each other
- **Common Funders** — Shared funding sources
- **Intermediate Links** — Indirect connection paths
- **Token Launches** — Pump.fun / Raydium launches
- **DEX Activity** — Trading platform breakdown
- **3D Network Map** — Interactive visual graph of all connections

---

## 11. FAQ

**Q: Can I change my registered wallet address?**  
A: Yes. Go to **Account Settings** and update your wallet address. Make sure to use the new address for future payments.

**Q: I sent SOL but my plan wasn't activated. What do I do?**  
A: Check that you sent from the wallet address registered in your account. If the wallet doesn't match, the payment cannot be attributed. Contact support if the issue persists.

**Q: Do credits expire?**  
A: No. Pay-per-use credits accumulate and do not expire.

**Q: Can I use a hardware wallet (Ledger) to pay?**  
A: Yes, as long as the sending address matches the one registered in your Solanalyze account.

**Q: Is my Helius API key stored on Solanalyze servers?**  
A: During the trial, your key is stored securely in your account profile and used server-side for proxied requests. It is never exposed publicly.

**Q: How many wallets can I analyze at once?**  
A: Up to **10 wallets** per query.

**Q: How many credits does one query use?**  
A: **10 credits** per query.

---

## Support

For questions or issues, reach out via the community channels listed on [solanalyze.com](https://solanalyze.com).

---

*© 2026 Solanalyze by 0xUnstable.World & 0xNynim — Advanced Wallet Forensics on Solana*
