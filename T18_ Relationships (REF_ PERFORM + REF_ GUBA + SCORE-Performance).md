# <span id="_qu46oa6rp573"></span> **T18: Performance Pipeline Relationships (SCORE → REF → Emissions Results Interface)**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

### <span id="_oatkjhv49uc1"></span> **1. Overview**

This document explains how the **SCORE: PERFORM & GUBA EMIT** tab works with the **REF** tabs to produce payout-ready outputs for the **Performance (Monthly) pipeline** in GREMS.

At a high level:

- **Grape Members** provides **identity + wallet mapping** (and the eligibility list used by scoring + payout sheets).  
    

- **Budgets** constrain how much can be distributed in each pool.  
    

- **SCORE: PERFORM & GUBA EMIT** performs the weighted calculations for:  
    

  - **PERFORM EMIT (GRAPE)  **
      

  - **GUBA EMIT (USDC)  **
      

  - **SOL EMIT (SOL)  **
      

- **REF: PERFORM** and **REF: GUBA** consolidate results into **payout lists**.  
    

- **Emissions Results Interface** pulls totals for **rollup + validation**, and supports proposal totals verification.  
    

- Final payouts are executed via **two proposals**:  
    

  - **Proposal (GRAPE)  **
      

  - **Proposal (USDC & SOL)  **
      
      

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

### <span id="_40dqj1234ek0"></span> **2. Scope and Tabs Covered**

This document covers the Performance pipeline tabs only:

|  |  |
|----|----|
| **Tab** | **Role in the System** |
| **Grape Members** | Member identity source (Discord name/ID, wallet); eligibility list used by scoring + payouts |
| **Budgets** | Budget caps / pool totals that constrain emissions |
| **SCORE: PERFORM & GUBA EMIT** | Main calculation tab (weights → allocations) for GRAPE, USDC, SOL |
| **REF: PERFORM** | Consolidated GRAPE payout list + task pool totals |
| **REF: GUBA** | Consolidated USDC + SOL payout list + task pool totals |
| **Emissions Results Interface** | Rollup/validation layer that references REF totals (and validation cross-checks) |

**Out of scope**: Merit pipeline, governance participation pipeline, recurring payments tabs.

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

### <span id="_kpxcv0awk3fw"></span> **3. GREMS Data Flow (Performance Pipeline)**

**Figure 0** shows the simplified GREMS flow for Performance:

- **Grape Members + Budgets → SCORE: PERFORM & GUBA EMIT → REF: PERFORM + REF: GUBA → Emissions Results Interface  **
    

- **REF payout lists → Proposals  **
    

- **Emissions Results Interface totals/validation → Proposal verification  **
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_1aedffa1.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="180" />

**Figure 0 (Flowchart):** *Performance Pipeline (PERFORM + GUBA + SOL)*

  
  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

### <span id="_4vl2j4rtzocz"></span> **4. Key Concepts**

#### <span id="_o8wwintpnp57"></span> **4.1 What “REF” means in GREMS**

REF tabs are **payout-ready consolidation layers**:

- They aggregate member totals into a clean list (name, ID, wallet, final reward).  
    

- They apply caps (if configured).  
    

- They summarize pool totals used by **Emissions Results Interface** and proposal preparation.  
    
    

#### <span id="_n10oxub1w7cg"></span> **4.2 What “SCORE” means in GREMS**

SCORE tabs are the **calculation engines**:

- Reviewers enter levels/scores.  
    

- Formulas compute weights, allocations, and totals across pools.  
    

- SCORE outputs are then consolidated into REF tabs.  
    
    

#### <span id="_ryhgtex46bpl"></span> **4.3 Does SCORE use Grape Members verification?**

**Yes.** SCORE depends on **Grape Members** for identity mapping (Discord name → Discord ID → wallet) and for controlling who can appear in scoring/payout lists. In practice:

- **Member identity fields** in SCORE are validated/filled via lookups from Grape Members.  
    

- REF tabs also use Grape Members to ensure payouts map to the correct wallet.  
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

### <span id="_7y55dg8zqj5g"></span> **5. TAB: SCORE: PERFORM & GUBA EMIT**

#### <span id="_mc7dvm66blgz"></span> **5.1 Purpose**

This is the main operational sheet where scoring inputs are transformed into token allocations for:

- **PERFORM EMIT (GRAPE)  **
    

- **GUBA EMIT (USDC)  **
    

- **SOL EMIT (SOL)  **
    
    

#### <span id="_ma6e20p7jvhc"></span> **5.2 What Reviewers Update**

Reviewers only touch **input cells** (commonly highlighted). Typical inputs per row include:

- **Discord Name  **
    

- **Task Name  **
    

- **Perform Level** (LEVEL 0–3 or equivalent scoring)  
    
    

Note: Your implementation uses dropdowns for selection in this sheet. (Other pipelines may use manual scoring sources, but this SCORE tab includes dropdown-driven inputs.)

#### <span id="_2u1i14a7me7t"></span> **5.3 Output Sections Inside SCORE**

SCORE is typically organized into these blocks:

|  |  |
|----|----|
| **Block** | **Output** |
| **Input grid + grand totals** | Shows totals for GRAPE / USDC / SOL |
| **PERFORM EMIT section** | Weighted GRAPE calculations by member-task |
| **GUBA EMIT section** | Weighted USDC calculations by member-task |
| **SOL EMIT section** | Weighted SOL calculations by member-task |
| **Weights + task summaries** | Level weights, aggregated task totals, averages |

  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_eb6dce7a.png" id="image7.png" data-align="bottom" data-border="0" width="624" height="225" />

**Figure 1:** *SCORE Input Grid + Grand Totals (GRAPE/USDC/SOL)*  
  
  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_7b3a192a.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="255" />

**Figure 2:** *SCORE PERFORM EMIT calculation block*

  
<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_11a5ed3a.png" id="image9.png" data-align="bottom" data-border="0" width="624" height="253" />

**Figure 3:** *SCORE GUBA EMIT calculation block*  
  
  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_b6f0d390.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="219" />

**Figure 4:** *SCORE SOL EMIT calculation block*  
  
  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_7a96820.png" id="image5.png" data-align="bottom" data-border="0" width="624" height="335" />

**Figure 5:** *SCORE Weight Levels + Task Summary/Distribution table*  
**5.4 Controls**

- **Budget constraints** should ensure totals do not exceed pool budgets.  
    

- SCORE totals are later cross-checked by the **Emissions Results Interface** validation logic.  
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

### <span id="_vw589ab0c7eg"></span> **6. TAB: REF: PERFORM**

#### <span id="_kegy5flweg7a"></span> **6.1 Purpose**

REF: PERFORM consolidates the **final GRAPE rewards per member** produced by SCORE into a payout list.

#### <span id="_r0rq52i4z95h"></span> **6.2 Outputs**

REF: PERFORM produces:

- **Member payout list (GRAPE)  **
    

  - Discord name  
      

  - Discord ID  
      

  - Wallet  
      

  - Final GRAPE reward  
      

  - Optional metrics (task count, average level)  
      

- **Task pool summary totals  **
    

- **Final totals** used by **Emissions Results Interface** and proposal prep  
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_98bb3203.png" id="image8.png" data-align="bottom" data-border="0" width="624" height="153" />

**Figure 6:** *REF: PERFORM tab layout (payout list + pool summaries + totals panel)*  
  
  

#### <span id="_83y2y3skr18w"></span> **6.3 How REF: PERFORM is used**

- **Payout List → Proposal (GRAPE)** (execution artifact)  
    

- **Totals → Emissions Results Interface** (rollup and validation)  
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

### <span id="_vrpiwtx554e3"></span> **7. TAB: REF: GUBA**

#### <span id="_el99rslsm381"></span> **7.1 Purpose**

REF: GUBA consolidates **final USDC and SOL rewards per member** produced by SCORE into a payout list.

### <span id="_hixk5swmmw1v"></span> **7.2 Outputs**

REF: GUBA produces:

- **Member payout list (USDC + SOL)  **
    

  - Discord name  
      

  - Discord ID  
      

  - Wallet  
      

  - Final USDC reward  
      

  - Final SOL reward  
      

- **Task pool summary totals** (USDC + SOL)  
    

- **Final totals** used by **Emissions Results Interface** and proposal prep  
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_62606bd.png" id="image6.png" data-align="bottom" data-border="0" width="624" height="155" />

**Figure 7:** *REF: GUBA tab layout (USDC/SOL payout list + pool summaries + totals panel)*  
  
  

### <span id="_kk6rxdx2nlnw"></span> **7.3 How REF: GUBA is used**

- **Payout List → Proposal (USDC & SOL)** (execution artifact)  
    

- **Totals → Emissions Results Interface** (rollup and validation)  
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape8" />

### <span id="_76tpvnbjs151"></span>  

### <span id="_knlz4by3vm87"></span> **8. TAB: Emissions Results Interface (Role in Performance)**

### <span id="_sh0tiubqpka"></span> **8.1 Purpose in this pipeline**

The Emissions Results Interface is the **rollup + validation layer**. For the Performance pipeline, it:

- Pulls **distributed totals** from:  
    

  - **REF: PERFORM** (GRAPE)  
      

  - **REF: GUBA** (USDC + SOL)  
      

- Compares distributed totals to budgets (Remaining)  
    

- Performs validation cross-checks (where configured)  
    
    

### <span id="_deki4oalnukz"></span> **8.2 Key rule from GREMS**

For Performance rollups, the Emissions Results Interface derives its totals from:

- **REF: PERFORM + REF: GUBA  **
  (not from SCORE directly)  
    
    

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape9" />

### <span id="_nb1reffcxjfe"></span> **9. Proposal Outputs (Execution Artifacts)**

### <span id="_1pj6lbmdbzm9"></span> **9.1 Two proposal model (required)**

Performance payouts are executed via **two separate proposals**:

1.  **Proposal (GRAPE)  **
      

    - Primary source: **REF: PERFORM payout list  **
        

    - Verified by: **Emissions Results Interface totals/validation  **
        

2.  **Proposal (USDC & SOL)  **
      

    - Primary source: **REF: GUBA payout list  **
        

    - Verified by: **Emissions Results Interface totals/validation  **
        

This separation is a GREMS control: **do not consolidate these into a single proposal artifact**.<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_ddc2c6d4.gif" id="Shape10" data-align="bottom" width="624" height="2" alt="Shape10" />

### <span id="_ruklnnae4e52"></span> **10. Common Issues and Troubleshooting**

|  |  |  |
|----|----|----|
| **Issue** | **Likely Cause** | **Fix** |
| Member missing from payout list | Not present in **Grape Members** / ID-wallet mapping missing | Add/update member in Grape Members; reselect in SCORE/REF |
| Totals don’t match | REF totals not refreshed / formulas broken / SCORE incomplete | Refresh pivots (if used), verify formula ranges, confirm all rows scored |
| Validation shows FALSE | Mismatch between REF totals and expected totals | Trace totals: SCORE → REF → Emissions Results Interface |
| Unexpected 0 rewards | Member scored LEVEL 0 or lookup failure | Confirm SCORE inputs; confirm name matches and lookups resolve |

### <span id="_5udig6f0yyri"></span> **12. Summary**

The Performance emissions system uses **Grape Members + Budgets** as inputs to **SCORE: PERFORM & GUBA EMIT**, then consolidates results into **REF: PERFORM** (GRAPE) and **REF: GUBA** (USDC + SOL). The **Emissions Results Interface** pulls totals from REF tabs for rollup and validation. Final payouts are executed through **two separate proposals**: **Proposal (GRAPE)** and **Proposal (USDC & SOL)**.

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

<img src="assets/T18_ Relationships (REF_ PERFORM + REF_ GUBA + SCORE-Performance)_html_8c50d0fe.png" id="image4.png" data-align="bottom" data-border="0" width="624" height="191" />

  
  

  
  
