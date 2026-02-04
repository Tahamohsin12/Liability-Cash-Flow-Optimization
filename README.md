#  Liability-Driven Investment (LDI) Optimization

###  Executive Summary
**The Business Challenge:**
A firm faces a mandatory, court-ordered liability schedule totaling **$330,000+** over the next 15 years. The payments are "back-loaded," meaning they start small ($10k) and grow significantly over time ($36k by Year 14).

**The Objective:**
Determine the absolute minimum *initial capital* required today to guarantee 100% solvency for all future payments.

**The Solution:**
I engineered a **Cash Flow Matching (Dedication)** strategy using Linear Programming. The model constructs a custom portfolio using:
* **Bond 1:** 5-Year maturity, ~6.5% effective yield.
* **Bond 2:** 12-Year maturity, ~6.9% effective yield.
* **Savings Account:** Highly liquid account (4% APY) for short-term gaps.

---

### Technical Approach
* **Tools:** Python, Gurobi Optimizer.
* **Methodology:** Modeled as a Linear Programming (LP) problem to minimize Initial Cost subject to annual cash flow constraints.
* **Constraint Handling:**
    * *Scenario A:* Continuous variables (fractional bond purchases allowed).
    * *Scenario B:* Integer constraints (strict whole-number trading lots).

---

###  Key Results & Insights

| Metric | Cash-Only Strategy | Optimized Portfolio (My Model) | Savings |
| :--- | :--- | :--- | :--- |
| **Capital Required** | ~$330,000 | **$195,683** | **~$134,000 (40%)** |

**Strategic Findings:**
1.  **Bond Laddering:** The optimal solution heavily leverages **Bond 2** (12-year) to cover the expensive late-stage liabilities, locking in higher yields early.
2.  **Active Liquidity Management:** The model does not let cash sit idle. It strategically deposits coupon payments into the savings account in Years 0-5 to accrue interest, withdrawing funds precisely when liabilities spike in Year 13.
3.  **Integer Impact:** restricting trades to "whole units" (Real-World Scenario) increased the cost to **$230,437**, highlighting the "cost of granularity" in financial markets.

---


### 📷 Visual Output
<img width="1936" height="2122" alt="carbon (2)" src="https://github.com/user-attachments/assets/6806993a-c294-47b4-84a6-869359953e18" />



