# Blendy — Zero-Cost Borrowing via Yield Streaming

Blendy is a modular liquidity infrastructure layer that enables **zero-cost borrowing** by letting users deposit Liquid Staked Tokens (LSTs) and yield-bearing assets (like xUSD) as collateral. Instead of paying interest out of pocket, borrowers stream a portion of their staking yield directly to lenders. In favorable conditions, loans can self-repay over time.

---

## Why Blendy

- **Zero-Cost Borrowing**: Collateral yield subsidizes borrowing costs.  
- **Self-Repaying Loans**: Yield is automatically applied to interest and/or principal.  
- **Built-In Risk Controls**:  
  - **Dynamic LTV & rates** based on real-time yields and asset prices.  
  - **Tiered liquidations** with Dutch auctions.  
  - **Oracle redundancy** (Pyth + Switchboard with capped adjustments).  
- **Simple UX**: Deposit → Borrow → Monitor. Yield streaming handles repayments.  

> Note: Zero-cost outcome depends on yields exceeding borrowing rates. In low-yield or high-volatility regimes, an effective cost may apply.

---

## How It Works

1. **Deposit collateral** (LSTs or yield-bearing assets).  
2. **Protocol validates** asset type, risk parameters, and LTV.  
3. **Borrow stable assets** (e.g., USDC).  
4. **Yield streaming**: A portion of staking yield covers interest; surplus flows to borrower.  
5. **Risk modules** manage LTV, liquidations, and yield calibration.  

---

## Core Features

- **Interest Subsidy Engine**: Collateral yield offsets borrow cost.  
- **Self-Repayment Toggle**: Auto-apply yield to interest/principal.  
- **Adaptive Risk Modules**: Dynamic adjustments for asset type and yield.  
- **Global Yield Calibration**: Weighted LST yield updates only on ±5% shifts, ensuring yield > borrow rate.  
- **Oracle-Backed Pricing**: Pyth and Switchboard integration with capped adjustments.  
- **Treasury Sustainability**: Fixed 15% fee on lender interest and borrower surplus yield.  

---

## Tech Stack

- **Smart Contracts**: Rust, Anchor  
- **Frontend**: React, Next.js, Tailwind  
- **Backend/Indexing**: Node.js with RPC/indexers  
- **Infra/Oracles**: Pyth, Switchboard  
- **Automation**: TukTuk Crank (yield distribution)  
- **Hosting**: Vercel  

---

## Getting Started

Prerequisite: A supported Web3 wallet (e.g., Phantom).

1. Connect wallet and deposit supported collateral.  
2. Choose borrowing amount and (optional) self-repayment toggle.  
3. Confirm transaction and monitor position.  
4. Repay anytime, or let yield stream reduce debt.  

---

## Risk & Disclaimers

- Collateral value can drop; hedging/liquidations reduce but do not remove risk.  
- Zero-cost borrowing depends on yield ≥ borrowing rate.  
- Smart contract risk exists despite audits and best practices.  

---

## Roadmap (High-Level)

- MVP with yield streaming  
- External audits  
- Mainnet hardening and SDK release  
- Expanded asset support and strategies  
- Cross-chain expansion (future roadmap)  

---

## Contributing

Pull requests and issues are welcome. Please open a discussion before major changes.

---

## License

© Blendy. All rights reserved. Licensing details to be finalized at mainnet.
