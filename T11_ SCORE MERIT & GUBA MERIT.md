# <span id="_qu46oa6rp573"></span> **T11: SCORE: MERIT & GUBA MERIT**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

### <span id="_fwqeu5yv9v0h"></span> **1. Purpose**

The **SCORE: MERIT EMIT & GUBA MERIT** tab is the **Merit-period calculation engine** in GREMS. It converts the *community-decided Merit scores* (captured upstream in **SCORE: MERIT SCORING**) into:

- **MERIT EMIT (GRAPE)** — payout calculations for Merit GRAPE rewards  
    

- **GUBA MERIT (USDC)** — payout calculations for Merit USDC rewards  
    
    

This tab is designed to provide a transparent, formula-driven bridge between **Merit scoring decisions** and the **payout-ready REF sheets** used for proposals and reporting.

**Control:** This tab **does not collect scoring decisions**. It **only calculates** emissions from data sourced upstream.

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape2" />

### <span id="_ut65089r7pc4"></span> **2. Role in GREMS Data Flow**

**Budget Pools + GRAPE MEMBERS  **
→ **SCORE: MERIT SCORING** *(community inputs / scoring decisions)  *
→ **SCORE: MERIT EMIT & GUBA MERIT** *(this tab: converts scoring into GRAPE + USDC)  *
→ **REF: MERIT** *(GRAPE totals by member)  *
→ **REF: GUBA MERIT** *(USDC totals by member)  *
→ **Emissions Results Interface – Merit** *(period rollup reporting)*

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape3" />

### <span id="_qc5dkip0ugqd"></span> **3. Source of Truth for Scoring Data**

There are **no dropdown menus** on this sheet.

All member scoring rows (Discord Name, Merit Type, Performance Level / weight level) are **pulled from**:

- **SCORE: MERIT SCORING** (the sheet where scoring decisions are entered and reviewed)  
    
    

This means the operational rule is:

- **Edit scoring only in SCORE: MERIT SCORING  **
    

- **Do not hand-edit the member scoring rows in this tab  **
    
    

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape4" />

### <span id="_rbpnb7rxid73"></span> **4. What Gets Updated in This Tab**

This sheet is primarily formula-driven, but it may include limited **operator-maintained parameters** (per the on-sheet instruction “ONLY UPDATE CELLS WITH YELLOW or GREEN BACKGROUND”).

Typical update areas (when present in the template) include:

- **Weight level % mapping** (Level 0–3 → 0% / 33% / 66% / 100%)  
    

- **Max reward per user** (cap rule for the Merit period)  
    

- **Period scaling / quarterly handling** (if the template includes Quarterly Total fields)  
    

- **Pool allocation constants** tied to the period’s approved budgets  
    
    

**Control:** If a value changes DAO-wide (caps, level ratios), update it **once** in the designated parameter cells—never inside calculated columns.

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape5" />

### <span id="_6q56omqk7mdo"></span> **5. Sheet Sections (How to Read It)**

#### <span id="_vdeuzyp3hfv8"></span> **5.1 Imported Scoring Rows (Top Input Block)**

This block is a **read-only view** of scored entries coming from **SCORE: MERIT SCORING**, typically showing:

- Discord Name  
    

- Merit Type (category/subcategory)  
    

- Performance/weight level  
    

- Calculated outputs (GRAPE and/or USDC totals per row)  
    
    

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_9f588cb2.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="240" /> **Figure 1.** *SCORE: MERIT EMIT & GUBA MERIT — Imported Scoring Rows (from SCORE: MERIT SCORING) and Row-Level Totals (GRAPE + USDC)*  
  
  

#### <span id="_lsyf6hmvea0z"></span> **5.2 MERIT EMIT Block (GRAPE Calculation)**

This section calculates **GRAPE** Merit emissions from the imported scoring rows, applying:

- Weight level percentages  
    

- Task/category pool allocations  
    

- Candidate counts (active members with non-zero weights)  
    

- Max reward per user (cap), where configured  
    

- Period totals (and “Quarterly Total” if the period is multi-month)  
    
    

Outputs here are the basis for downstream **REF: MERIT** totals.

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_949532.png" id="image4.png" data-align="bottom" data-border="0" width="624" height="304" />

**Figure 2*****.*** *MERIT EMIT (GRAPE) — Merit Period Calculation Block (weights, candidate counts, task pool allocation, totals)*  
  
  

#### <span id="_gzqjqqmrotpv"></span> **5.3 GUBA MERIT Block (USDC Calculation)**

This section calculates **USDC** Merit emissions using the same structure, but against the **GUBA MERIT** pools and constraints.

Outputs here are the basis for downstream **REF: GUBA MERIT** totals.

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_b7957fe0.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="225" />

**Figure 3.** *GUBA MERIT (USDC) — Merit Period Calculation Block (weights, candidate counts, task pool allocation, totals)*

#### <span id="_9ycpeq5rk64c"></span>  

#### <span id="_l60p8okbfbm7"></span> **5.4 Category Summary / Totals (Right-Side Summary)**

This block provides rollups (typically by Merit Type) so reviewers can sanity-check:

- Total distributed vs pool  
    

- Remaining amounts (if tracked)  
    

- Average weight behavior  
    

- Distribution by category (helps detect scoring anomalies)  
    
    

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_41682a75.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="288" />

**Figure 4.** *Merit Type Summary — Category Rollup Table (SUM of Perform, SUM of Remaining, AVERAGE of Perform)*

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape6" />

### <span id="_76uiepld84t5"></span> **6. Controls and Best Practices**

- **No scoring inputs here:** all scoring is done upstream in **SCORE: MERIT SCORING**.  
    

- **Do not overwrite formulas:** only adjust designated parameter cells (yellow/green).  
    

- **Identity integrity:** all member identity mapping must reconcile through **GRAPE MEMBERS** downstream.  
    

- **Merit does not include SOL in GREMS design:** this sheet’s Merit outputs are **GRAPE + USDC**.  
    

- **Auditability:** this sheet should be reproducible solely from (a) approved budgets + (b) SCORE: MERIT SCORING inputs.  
    
    

<img src="assets/T11_ SCORE MERIT &amp; GUBA MERIT_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape7" />

### <span id="_e6tcpijjf5c3"></span> **7. Recommended Merit Run Order (Operator View)**

1.  Confirm Merit period budgets are approved (Budget Pools).  
      

2.  Confirm GRAPE MEMBERS is current.  
      

3.  Enter / finalize scoring decisions in **SCORE: MERIT SCORING** during open review.  
      

4.  Verify this tab updates correctly:  
      

    - MERIT EMIT totals (GRAPE)  
        

    - GUBA MERIT totals (USDC)  
        

    - Any caps / candidate counts / totals  
        

5.  Confirm downstream payout tabs:  
      

    - REF: MERIT  
        

    - REF: GUBA MERIT  
        

6.  Confirm results in the **Emissions Results Interface – Merit** rollup/report.
