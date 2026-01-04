# <span id="_qu46oa6rp573"></span> **T9: REF: MERIT**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T9_ REF MERIT_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

### <span id="_9g6k4zm7hxq9"></span> **1. Purpose**

The **REF: MERIT** tab consolidates **Merit-cycle GRAPE rewards** into a payout-ready, per-member format. It aggregates Merit scoring outputs from **SCORE: MERIT EMIT & GUBA MERIT**, applies caps and period scaling where applicable, and produces totals used for:

- **Merit payout proposals (GRAPE)  **
    

- **Emissions Results Interface (Merit) rollup reporting  **
    

- **Validation checks (wallet counts, candidate counts, pool utilization)  **
    
    

**Control:** REF: MERIT is part of the **Merit (Period)** pipeline only. It does **not** include Performance (Monthly) rewards, Recurring Payments, or Governance Participation rewards.

<img src="assets/T9_ REF MERIT_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape2" />

### <span id="_78p9zwm3hore"></span> **2. Inputs and Dependencies**

REF: MERIT is driven by these upstream sources:

- **SCORE: MERIT EMIT & GUBA MERIT** (primary source)  
    

  - Provides the member-level Merit scoring outcomes that determine GRAPE allocations.  
      

- **GRAPE MEMBERS** (identity source of truth)  
    

  - Provides canonical mappings for **Discord Name → Discord ID → Wallet Address**.  
      

- **Emissions Results Interface** (rollup parameters / caps)  
    

  - Provides Merit-pool reporting totals and key parameters such as **Max Emission per Eligible Member** and (when used) **Number of Months** for period scaling.  
      
      

<img src="assets/T9_ REF MERIT_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape3" />

### <span id="_rysdmnw1c0om"></span> **3. Sheet Layout (What Each Section Does)**

REF: MERIT is typically organized into four functional blocks:

#### <span id="_jp4oe2ny0lce"></span> **3.1 Merit Rewards Total Pivot Table (Columns A–C)**

A Pivot Table consolidates Merit GRAPE totals by member:

- **Column A:** Discord Name  
    

- **Column B:** Discord ID (QA)  
    

- **Column C:** **Sum of Total Rewards** (calculated Merit GRAPE total)  
    
    

This block is the **raw consolidated output** sourced from the scoring/emission calculations.

<img src="assets/T9_ REF MERIT_html_f2e8249f.png" id="image4.png" data-align="bottom" data-border="0" width="415" height="364" />

**Figure 1.** *Merit Rewards Total Pivot Table (REF: MERIT, Columns A–C)*

#### <span id="_1425c5urnt7f"></span>  

#### <span id="_fux8aj43xey4"></span> **3.2 Member Lookup and Final Rewards (Columns E–H)**

This block turns the Pivot Table totals into a **payout-ready list** by mapping identity + wallets and calculating **final rewards**:

- **Column E:** Discord Name (selected from GRAPE MEMBERS)  
    

- **Column F:** Discord ID (auto-filled from GRAPE MEMBERS)  
    

- **Column G:** Wallet Address (auto-filled from GRAPE MEMBERS)  
    

- **Column H:** **Final Rewards (Monthly / Period)** (final GRAPE payout amount)  
    
    

**Typical logic (high-level):**

- Look up the member’s calculated reward total from the Pivot Table.  
    

- Apply **Max Emission per Eligible Member** (cap), if configured.  
    

- Return **0** if the member is not found or has no eligible rewards.  
    
    

<img src="assets/T9_ REF MERIT_html_58373ca7.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="347" />

**Figure 2.** *Member Lookup + Final Rewards (REF: MERIT, Columns E–H)*

  
  

#### <span id="_1uwi0yu17a0t"></span> **3.3 Merit Category Pool Lookup (Columns J–M)**

This section lists the Merit categories (or subcategories) used in the merit cycle and their pool sizing:

- **Merit List  **
    

- **MERIT ID  **
    

- **Total Pool** (per category/subcategory)  
    

- **Total Pool (%)  **
    
    

This block is used as a **reference table** for how the Merit pool is partitioned across categories.

<img src="assets/T9_ REF MERIT_html_2796631e.png" id="image1.png" data-align="bottom" data-border="0" width="461" height="481" />

**Figure 3.** *Merit List, IDs, and Pools (REF: MERIT, Columns J–M)*

  
  

#### <span id="_2aqe9kx0u65c"></span> **3.4 Summary Metrics (Final Rewards / Pool / Validation Box)**

This block provides the at-a-glance rollup for the current Merit cycle:

- **FINAL REWARDS** (total GRAPE distributed)  
    

- **TOTAL POOL** (GRAPE pool available for the merit cycle)  
    

- **PRODUCTIVITY** (utilization rate)  
    

- **MAX EMISSION per** (cap per eligible member)  
    

- **TOTAL CANDIDATES** (count of eligible recipients)  
    

- **AVG REWARD  **
    

- **Number of Months** (if the merit cycle spans multiple months)  
    
    

**Important nuance (period scaling):  **
If **Number of Months** is used for the Merit cycle, the “pool for the period” is commonly treated as:

- **Period Pool = (Monthly Pool) × (Number of Months)  **
    
    

…and utilization/productivity should reflect the period pool when the cycle spans multiple months.

<img src="assets/T9_ REF MERIT_html_7923d593.png" id="image2.png" data-align="bottom" data-border="0" width="458" height="270" />

**Figure 4.** *Merit Summary Metrics (Final Rewards / Pool / Utilization / Caps / Number* *of Months)*

<img src="assets/T9_ REF MERIT_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape4" />

### <span id="_nplxnsvo83he"></span> **4. Data Flow Alignment (GREMS Merit Pipeline)**

REF: MERIT sits in the **Merit (Period)** pipeline:

**Budget Pools + GRAPE MEMBERS → SCORE: MERIT EMIT & GUBA MERIT → REF: MERIT → Emissions Results Interface (Merit) + GRAPE payout proposal**

**Control:** REF: MERIT contributes to **Merit reporting** and **Merit payout proposals** only. It does **not** feed **Recurring Payments** or **Performance** reporting.

<img src="assets/T9_ REF MERIT_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape5" />

### <span id="_ozk8iq8q345b"></span> **5. Operating Procedure (How to Run It)**

1.  Confirm **GRAPE MEMBERS** is current (Discord names, IDs, wallets).  
      

2.  Confirm the Merit cycle inputs are complete in **SCORE: MERIT EMIT & GUBA MERIT**.  
      

3.  Refresh/confirm the **Pivot Table** in REF: MERIT (Columns A–C).  
      

4.  In the **Member Lookup** block (Columns E–H), ensure:  
      

    - Every eligible member is selected/mapped correctly,  
        

    - Wallets populate correctly,  
        

    - Final rewards reflect caps/parameters.  
        

5.  Confirm the **Summary Metrics** match expectations (pool totals, candidate count, utilization).  
      

6.  Use **Final Rewards** outputs to prepare the **Merit GRAPE payout proposal**, and ensure the **Emissions Results Interface (Merit)** rollup matches REF outputs.  
      
      

<img src="assets/T9_ REF MERIT_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape6" />

### <span id="_mgvene3xy11l"></span> **6. Controls and Validation Checks (Required)**

- **Identity integrity:** all payouts must map through **GRAPE MEMBERS**.  
    

- **Cap enforcement:** confirm Max Emission per Eligible Member is applied consistently.  
    

- **Candidate count:** ensure **TOTAL CANDIDATES** matches the number of unique wallets receiving non-zero rewards.  
    

- **Period scaling:** if **Number of Months** is used, confirm pool/utilization calculations reflect the intended period logic.
