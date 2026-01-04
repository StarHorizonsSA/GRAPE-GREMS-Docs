# <span id="_48bsf5tv7d35"></span> **T19: Emissions (Merit) Tab Relationships (SCORE → REF → Reporting)**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

## <span id="_3tf4edw34aol"></span> **1. Purpose**

This document explains how the **Merit-cycle** scoring and reference tabs work together to calculate and prepare **Merit-period emissions**:

- **MERIT EMIT (GRAPE)** payouts (via **REF: MERIT**)  
    

- **GUBA MERIT (USDC)** payouts (via **REF: GUBA MERIT**)  
    

- **Emissions Results Interface – Merit** totals + validation (rollup reporting)  
    
    

**Control:** This document covers the **Merit (Period)** pipeline only. It does **not** include:

- Performance (Monthly) rewards (PERFORM / GUBA / SOL)  
    

- Recurring Payments (Proposal Architect, Discord Boost, infra/tools)  
    

- Governance Participation rewards (VINE)  
    
    

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_wdnpfmumr56"></span> **2. Where This Fits in GREMS**

Merit is a **period-based** cycle (commonly quarterly). The Merit pipeline follows this logic:

- **SCORE: MERIT SCORING** is the *scoring input sheet* (review decisions).  
    

- **SCORE: MERIT EMIT & GUBA MERIT** is the *calculation engine* (converts scoring → payouts).  
    

- **REF: MERIT** and **REF: GUBA MERIT** are the *payout-ready outputs* (per member).  
    

- **Emissions Results Interface – Merit** is the *rollup + validation interface* used for reporting and proposal reconciliation.  
    
    

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_gnx33yx1zgzi"></span> **3. Data Flow Alignment**

This is the end-to-end Merit flow used in GREMS.

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_49f17ec8.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="223" />

**Figure 0.** *MERIT (Period) Pipeline — Data Flow (Identity, Budget Constraints, Member Totals, Proposals)***  **
  
  

### <span id="_9fgsm2omhjtt"></span> **3.1 What each arrow label means (in practice)**

- **Budget Constraints:** Approved budgets constrain category pool totals (no manual overrides).  
    

- **Identity Validation:** Scoring inputs are constrained to valid members (Discord name/ID integrity).  
    

- **Identity Map (Discord ID + Wallet):** All payout outputs map through **GRAPE MEMBERS** to ensure correct wallets.  
    

- **Scoring Inputs:** Review decisions (name + merit type + performance level) feeding the calc engine.  
    

- **Member Totals:** Per-member totals produced by the calc engine and consumed by REF tabs.  
    

- **Totals + Validation:** Rollup totals and consistency checks used by the Emissions Results Interface.  
    

- **Payout List:** Final per-wallet payout outputs used to create proposals.  
    
    

  
  

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_r2s2qtbopa07"></span> **4. Tabs Covered in This Document**

|  |  |  |
|----|----|----|
| **Tab** | **Role in Merit Pipeline** | **Output Type** |
| **SCORE: MERIT SCORING** (T22) | Scoring input interface (review decisions) | Member/category/level inputs |
| **SCORE: MERIT EMIT & GUBA MERIT** (T11) | Calculation engine (GRAPE + USDC) | Row-level + totals |
| **REF: MERIT** (T9) | Payout-ready GRAPE totals by member | GRAPE payout list |
| **REF: GUBA MERIT** (T10) | Payout-ready USDC totals by member | USDC payout list |
| **Emissions Results Interface – Merit** | Rollup reporting + validation | Totals, remaining, utilization |

**Control:** Merit outputs in GREMS are **GRAPE + USDC only** (no SOL in the Merit pipeline).

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

## <span id="_amng1zqm3r6b"></span> **5. How the Tabs Connect (Merit Cycle Logic)**

### <span id="_j8ph2d7tssft"></span> **5.1 Scoring layer (inputs)**

**SCORE: MERIT SCORING** is where reviewers enter/confirm Merit scoring decisions:

- Discord Name  
    

- Merit Category / Merit Type  
    

- Performance Level (Level 0–3 or equivalent weights)  
    
    

Those decisions are the only “human input” source for Merit scoring.

### <span id="_idggygm47qr2"></span> **5.2 Calculation layer (emissions engine)**

**SCORE: MERIT EMIT & GUBA MERIT** converts the scoring inputs into:

- **MERIT EMIT (GRAPE)** calculations  
    

- **GUBA MERIT (USDC)** calculations  
    
    

**Control (per T11):** This tab is **not** where scoring decisions are made; it is formula-driven from **SCORE: MERIT SCORING**.

### <span id="_fozktm6fzcss"></span> **5.3 Reference layer (payout-ready totals)**

The REF tabs convert calculated outputs into payout-ready lists:

- **REF: MERIT** consolidates GRAPE totals per member and prepares the GRAPE payout list.  
    

- **REF: GUBA MERIT** consolidates USDC totals per member and prepares the USDC payout list.  
    
    

Both REF tabs enforce identity mapping through **GRAPE MEMBERS** (Discord ID + Wallet).

### <span id="_lanzcoqkw0c8"></span> **5.4 Rollup and validation layer**

The **Emissions Results Interface – Merit** pulls totals from REF outputs to support:

- rollup reporting (final totals, remaining, utilization)  
    

- validation checks (candidate counts, totals reconciliation)  
    
    

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_1cn4wc3u682v"></span> **6. Operator Run Order (Merit Cycle)**

1.  **Confirm budgets** are approved for the period (Budget Pools per Category).  
      

2.  **Confirm GRAPE MEMBERS** is current (Discord IDs + wallet addresses).  
      

3.  **Enter/finalize scoring** in **SCORE: MERIT SCORING** during the open review window.  
      

4.  Verify **SCORE: MERIT EMIT & GUBA MERIT** updates correctly (GRAPE + USDC totals).  
      

5.  Verify payout outputs in:  
      

    - **REF: MERIT** (GRAPE payout list)  
        

    - **REF: GUBA MERIT** (USDC payout list)  
        

6.  Verify rollup totals + validation in **Emissions Results Interface – Merit**.  
      

7.  Create **two proposals** (separate artifacts):  
      

    - **Proposal (GRAPE)** from **REF: MERIT** payout list  
        

    - **Proposal (USDC)** from **REF: GUBA MERIT** payout list  
        
        

<img src="assets/T19_ Relationships (REF_ MERIT + REF_ GUBA MERIT + SCORE-Merit)_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_p5xq2qnv0imj"></span> **7. Controls and Validation (Required)**

- **Separation of concerns:** Merit is period-based and separate from Performance + Recurring Payments + Governance Participation.  
    

- **Identity integrity:** All payouts must map through **GRAPE MEMBERS** (Discord ID + Wallet).  
    

- **No manual overrides:** Reward totals must be formula-derived from approved budgets + scoring inputs.  
    

- **Candidate count checks:** “Total Candidates” should match unique recipients receiving non-zero rewards.  
    

- **Period scaling:** If “Number of Months” is used, confirm pool/utilization logic reflects the intended period pool.

  
  
