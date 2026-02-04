#  Liability-Driven Investment (LDI) Optimization

###  Executive Summary
**The Business Challenge:**
A firm faces a mandatory, court-ordered liability schedule totaling **$330,000+** over the next 15 years. [cite_start]The payments are "back-loaded," meaning they start small ($10k) and grow significantly over time ($36k by Year 14)[cite: 13, 14].

**The Objective:**
[cite_start]Determine the absolute minimum *initial capital* required today to guarantee 100% solvency for all future payments[cite: 23].

**The Solution:**
I engineered a **Cash Flow Matching (Dedication)** strategy using Linear Programming. The model constructs a custom portfolio using:
* [cite_start]**Bond 1:** 5-Year maturity, ~6.5% effective yield[cite: 16].
* [cite_start]**Bond 2:** 12-Year maturity, ~6.9% effective yield[cite: 16].
* [cite_start]**Savings Account:** Highly liquid account (4% APY) for short-term gaps[cite: 16].

---

###  Technical Approach
* **Tools:** Python, Gurobi Optimizer.
* [cite_start]**Methodology:** Modeled as a Linear Programming (LP) problem to minimize $C_0$ (Initial Cost) subject to annual cash flow constraints[cite: 24, 30].
* **Constraint Handling:**
    * *Scenario A:* Continuous variables (fractional bond purchases allowed).
    * [cite_start]*Scenario B:* Integer constraints (strict whole-number trading lots)[cite: 73, 95].

---

###  Key Results & Insights

| Metric | Cash-Only Strategy | Optimized Portfolio (My Model) | Savings |
| :--- | :--- | :--- | :--- |
| **Capital Required** | ~$330,000 | **$195,683** | **~$134,000 (40%)** |

**Strategic Findings:**
1.  **Bond Laddering:** The optimal solution heavily leverages **Bond 2** (12-year) to cover the expensive late-stage liabilities, locking in higher yields early.
2.  **Active Liquidity Management:** The model does not let cash sit idle. [cite_start]It strategically deposits coupon payments into the savings account in Years 0-5 to accrue interest, withdrawing funds precisely when liabilities spike in Year 13[cite: 66, 68].
3.  **Integer Impact:** restricting trades to "whole units" (Real-World Scenario) increased the cost to **$230,437**, highlighting the "cost of granularity" in financial markets.

---

### 📷 Visual Output
<img width="1936" height="2160" alt="195 K carbon" src="https://github.com/user-attachments/assets/96f46a00-b7be-45b1-b791-70d32e89c189" />


