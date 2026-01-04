# <span id="_qu46oa6rp573"></span> **T20: Understanding the Emissions Results Interface**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

### <span id="_a0xh2rrtacqs"></span> **Overview**

The **Emissions Results Interface** is the rollup/dashboard tab for GREMS. It **does not store raw scoring**. Instead, it:

- **Displays budgets** (set by governance / admin inputs)  
    

- **Pulls distributed totals from REF tabs** (payout-ready totals)  
    

- **Runs validation checks vs SCORE tabs** (to catch mismatches)  
    

- **Applies “period scaling”** for multi-month pools using **Number of Months (F2)  **
    
    

**GREMS alignment note:** The Emissions Results Interface is a *reporting layer*. In the system flow, **Performance rollups come from REF: PERFORM + REF: GUBA**, and **Merit rollups come from REF: MERIT + REF: GUBA MERIT**. Add-ons and operational costs roll into **Recurring Payments**, not into emissions rollups.

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_66bce84d.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="268" />

**Figure 1.** *Emissions Results Interface — example view (budgets, distributed, remaining, validation, caps, utilization)  *
<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_pulwyuio0if2"></span> **1) What each pool represents (Interface columns)**

The Emissions Results Interface is organized as **one column per pool**, typically across **Columns B–G**.

|  |  |  |  |
|----|----|----|----|
| **Interface Column** | **Pool Name (Header)** | **Token** | **Rollup Source in GREMS (distributed totals)** |
| **B** | PERFORM EMIT | GRAPE | **REF: PERFORM** (GRAPE totals) |
| **C** | GUBA EMIT | USDC | **REF: GUBA** (USDC totals) |
| **D** | SOL EMIT | SOL | **REF: GUBA** (SOL totals) |
| **E** | MERIT EMIT | GRAPE | **REF: MERIT** (GRAPE totals) |
| **F** | GUBA MERIT | USDC | **REF: GUBA MERIT** (USDC totals) |
| **G** | SOL other | SOL | **REF: SOL** (SOL totals, if used) |

## <span id="_fhv2bu5u4qji"></span> **2) Key parameter: Number of Months (F2)**

**Cell F2:** **Number of Months** controls how the Interface treats “period pools.”

|  |  |  |  |
|----|----|----|----|
| **Parameter** | **Location** | **Used For** | **Notes** |
| **Number of Months** | **F2** | **MERIT EMIT** and **GUBA MERIT** | These pools commonly show a **monthly budget** in Row 6, but must be interpreted as **period budget = monthly × months** for utilization and remaining. |

**Rule of thumb (GREMS):**

- **Performance pools** (PERFORM / GUBA / SOL) are typically **monthly** (no scaling).  
    

- **Merit pools** (MERIT EMIT / GUBA MERIT) are **period-based** and use **F2 scaling** where indicated.  
    
    

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape4" />

## <span id="_mjtr962x4ozb"></span> **3) Row-by-row breakdown (what each row means)**

### <span id="_bobp6i13s92f"></span> **Row 6 — Total Budget**

**Type:** Manual input (governance/admin-set budget amounts)

|  |  |  |
|----|----|----|
| **Row** | **Meaning** | **What it’s used for** |
| **Row 6** | Budget per pool | Drives caps (Row 12) and utilization (Row 16); Merit pools may be *monthly budgets* that scale by F2 for the period. |

### <span id="_z86yk79ntp25"></span> **Row 7 — FINAL REWARDS (Distributed)**

**Type:** Formula (pulls totals from **REF** tabs)

These cells represent **what will actually be paid** (or already computed for payout), because REF tabs are “payout-ready.”

|          |                 |                                       |
|----------|-----------------|---------------------------------------|
| **Cell** | **Pulls From**  | **Meaning**                           |
| **B7**   | REF: PERFORM    | Total GRAPE distributed (Performance) |
| **C7**   | REF: GUBA       | Total USDC distributed (Performance)  |
| **D7**   | REF: GUBA       | Total SOL distributed (Performance)   |
| **E7**   | REF: MERIT      | Total GRAPE distributed (Merit)       |
| **F7**   | REF: GUBA MERIT | Total USDC distributed (Merit)        |
| **G7**   | REF: SOL        | Total SOL distributed (Other)         |

### <span id="_owxpea277ty7"></span> **Row 8 — Remaining (Unallocated)**

**Type:** Formula (budget minus distributed)

**Performance pools:**

- Remaining is typically: Row6 − Row7  
    
    

**Merit pools (period pools):**

- Remaining should reflect: **(Row6 × Number of Months) − Row7  **
    
    

|                       |                                         |
|-----------------------|-----------------------------------------|
| **Pool Type**         | **Correct Remaining Logic**             |
| Performance (Monthly) | Remaining = Budget − Distributed        |
| Merit (Period)        | Remaining = (Budget × F2) − Distributed |

**Important (based on your screenshot):** If Remaining for MERIT EMIT / GUBA MERIT looks unusually large, it may indicate the sheet is using a **legacy multiplier** (e.g., hardcoded factor) instead of **F2**. The Interface *should* be GREMS-consistent and scale by **Number of Months** for period pools.

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape7" />

### <span id="_wqbr3zwxhexh"></span> **Row 9 — Validation (Cross-checks)**

**Type:** Formula (sanity checks)

Validation behavior differs by pool:

|  |  |  |
|----|----|----|
| **Pool** | **What validation is doing** | **Typical Output** |
| PERFORM / GUBA / SOL / SOL other | Compares REF totals to SCORE totals (or SCORE control cells) | TRUE / FALSE |
| MERIT EMIT / GUBA MERIT | Often displays **unique eligible member count** (or similar) as a check | A number (e.g., **19**) |

**Interpretation guidance:**

- **FALSE** = mismatch between the REF rollup and the SCORE system → investigate before proposing payouts.  
    

- A **number** (Merit) = count-based control; confirm it matches your intended eligible member set for the period.  
    
    

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape8" />

## <span id="_ag2xkxcjkut6"></span> **4) Caps and averages (lower section)**

### <span id="_v22mtz3j1lbl"></span> **Section: “Max Emission Per Eligible Member” (Rows 12–13)**

This section is a *policy/control view* of per-member limits and averages.

#### <span id="_er1shhxhzbqn"></span> **Row 12** **— Max emission per eligible member**

**Type:** Formula (budget × max reward %)

- Performance caps usually follow: Budget × Max Reward % (from the relevant SCORE tab control cell)  
    
    

#### <span id="_dgjx1a2fw2wu"></span> **Row 13** **— Average budget per eligible member**

In your Interface screenshot, Row 13 values match:  
Budget ÷ eligible member count  
(Despite the left label showing “FINAL REWARDS” in some templates, it behaves like an **average-per-member** statistic.)

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape9" />

## <span id="_1y4drbadbjn"></span> **5) Pool utilization (Row 16)**

### <span id="_fqflb8xcjt4d"></span> **Row 16 — Emissions Pool Utilized %**

**Type:** Formula (distributed ÷ budget)

|                       |                                          |
|-----------------------|------------------------------------------|
| **Pool Type**         | **Correct Utilization Logic**            |
| Performance (Monthly) | Utilized % = Distributed ÷ Budget        |
| Merit (Period)        | Utilized % = Distributed ÷ (Budget × F2) |

This is why Merit utilization can be meaningfully below 100% even when monthly budgets look large—because the denominator is the **full period budget**.

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape10" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape10" />

## <span id="_xzxvvxluetrc"></span> **6) GREMS-aligned data flow**

### <span id="_tlr3ok3sc7hf"></span> **Performance pipeline → Emissions Results Interface**

- **SCORE: PERFORM & GUBA EMIT** calculates per-task distributions  
    

- Outputs roll into:  
    

  - **REF: PERFORM** (GRAPE totals)  
      

  - **REF: GUBA** (USDC + SOL totals)  
      

- Emissions Results Interface pulls distributed totals from REF tabs (Row 7)  
    
    

**Flow (conceptual):  **
SCORE: PERFORM & GUBA EMIT → REF: PERFORM + REF: GUBA → **Emissions Results Interface**

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape11" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape11" />

### <span id="_y4f4grb4c6d2"></span> **Merit pipeline → Emissions Results Interface**

- **SCORE: MERIT SCORING** provides the scoring inputs (human decisions)  
    

- **SCORE: MERIT EMIT & GUBA MERIT** computes allocations (no manual dropdowns on the emit sheet)  
    

- Outputs roll into:  
    

  - **REF: MERIT** (GRAPE totals)  
      

  - **REF: GUBA MERIT** (USDC totals)  
      
      

**Flow (conceptual):  **
SCORE: MERIT SCORING → SCORE: MERIT EMIT & GUBA MERIT → REF: MERIT + REF: GUBA MERIT → **Emissions Results Interface**

  
  

  
  

  
  

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape12" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape12" />

### <span id="_ox8olxjtxryf"></span> **Separation controls (GREMS)**

The Interface is *emissions reporting only*. It should **not** merge these:

|  |  |  |
|----|----|----|
| **Separate System** | **Where it rolls up** | **Should it flow into Emissions Results Interface?** |
| **Recurring Payments** (Proposal Architect, Discord Boost, infra/tools) | **RECURRING PAYMENTS** artifact/proposal | **No** |
| **Governance Participation** (VINE) | **GOV PARTICIPATION → VINE Rewards → GOV PARTICIPATION REWARDS** | **No** |

  
  

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape13" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape13" />

## <span id="_ueitkvwg9tsa"></span> **7) Dependency map (what this tab relies on)**

|  |  |  |
|----|----|----|
| **Depends On Tab** | **Why** | **Used For** |
| Grape Members | identity + wallets | upstream identity consistency |
| REF: PERFORM | distributed GRAPE totals | Row 7 (PERFORM) |
| REF: GUBA | distributed USDC + SOL totals | Row 7 (GUBA + SOL) |
| REF: MERIT | distributed GRAPE totals | Row 7 (MERIT) |
| REF: GUBA MERIT | distributed USDC totals + months parameter | Row 7 (GUBA MERIT), **F2** |
| REF: SOL (if used) | SOL-other totals | Row 7 (SOL other) |
| SCORE tabs | validation + cap % inputs | Row 9 checks, Row 12 cap calcs |

## <span id="_vgiih5goqvnu"></span> **8) Troubleshooting (fast)**

**Validation shows FALSE (Performance pools):**

- Ensure SCORE totals match REF totals (pivot refresh may be needed)  
    

- Confirm no renamed tabs/ranges breaking lookups  
    

- Check for \#REF!/VALUE errors upstream  
    
    

**Merit “Remaining” looks wrong:**

- Confirm Remaining uses **(Budget × F2) − Distributed  **
    

- If a hardcoded factor exists (legacy), replace with **F2** to stay GREMS-consistent  
    
    

**Utilization \> 100%:**

- Duplicate entries in SCORE or REF  
    

- Wrong months scaling applied (or applied twice)  
    

- Budget row not updated to the current period  
    
    

<img src="assets/T20_ Using the EMISSIONS RESULTS Sheet_html_ddc2c6d4.gif" id="Shape15" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape15" />

## <span id="_slxe3hrs45k2"></span> **Summary**

The **Emissions Results Interface** is the **aggregation + validation layer** of GREMS. It reports budgets (Row 6), pulls distributed totals from **REF** tabs (Row 7), calculates remaining and utilization (Rows 8 & 16), and flags mismatches via validation (Row 9). Merit pools must be interpreted as **period-based** using **Number of Months (F2)** where required—this is a key control to prevent budget/utilization confusion.
