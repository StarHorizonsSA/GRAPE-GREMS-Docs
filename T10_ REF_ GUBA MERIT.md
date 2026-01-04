# <span id="_qu46oa6rp573"></span> **T10: REF: GUBA MERIT**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

## <span id="_bkq51a3ikbn1"></span> **1. Purpose**

The **REF: GUBA MERIT** tab consolidates **Merit-cycle USDC rewards** for each member into a payout-ready list. It aggregates the results produced by **SCORE: MERIT EMIT & GUBA MERIT** and applies the Merit-cycle controls (pool totals, per-member caps, and candidate counts) used for:

- **Merit payout proposals (USDC)  **
    

- **Emissions Results Interface** rollup reporting for the **GUBA MERIT** column

### <span id="_q3d7t9dt6n"></span> **1.1 Where This Tab Fits in GREMS**

**Merit (Period) Pipeline  **
Budget Pools + GRAPE MEMBERS  
→ **SCORE: MERIT EMIT & GUBA MERIT** (calculates GRAPE + USDC)  
→ **REF: MERIT** (GRAPE totals)  
→ **REF: GUBA MERIT** (USDC totals)  
→ **Emissions Results Interface – Merit** (period rollup reporting)

**Control:** REF: GUBA MERIT is **Merit-only**. It does **not** include Performance rewards, Recurring Payments (Proposal Architect / Discord Boost / infra costs), or Governance Participation (VINE).

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_rc5a43k4m8d"></span> **2. Data Sources and Outputs**

### <span id="_51vgm818a1sx"></span> **2.1 Upstream Inputs (Sources)**

- **SCORE: MERIT EMIT & GUBA MERIT  **
  Provides per-row Merit scoring outputs that roll up into member totals.  
    

- **GRAPE MEMBERS  **
  Canonical roster for **Discord ID + wallet address** mapping.  
    
    

### <span id="_f17zoajpn8ap"></span> **2.2 Downstream Outputs (Grapeators)**

- **Merit payout artifacts/proposals (USDC)  **
    

- **Emissions Results Interface – Merit** (rollup reporting)  
    

  - **GUBA MERIT totals** (USDC)  
      

  - Candidate counts, max emission, utilization, and validation inputs (as configured)  
      
      

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_uhr8kxqb50v7"></span> **3. Tab Layout Overview**

REF: GUBA MERIT is organized into four functional blocks:

1.  **Merit Rewards Total Pivot Table** (member totals)  
      

2.  **Member Lookup + Final Rewards** (wallet mapping + cap enforcement)  
      

3.  **Merit Category Pool Lookup** (category IDs + pool amounts)  
      

4.  **Summary Metrics / Controls** (totals, utilization, caps, candidates, months)  
      
      

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_ajeuouo0lbdt"></span> **4. Merit Rewards Total Pivot Table (Member Totals)**

This section provides the **raw per-member USDC totals** (before any optional caps/controls are applied in the payout list).

- **Column A:** Discord Name  
    

- **Column B:** Discord ID (QA)  
    

- **Column C:** Sum of Total Rewards (USDC)  
    
    

**What it does:**

- Aggregates member totals from the Merit scoring outputs (via pivot rules referencing the Merit scoring/calc pipeline).  
    

- Serves as the **source-of-truth lookup table** for the payout block in Section 5.  
    
    

<img src="assets/T10_ REF_ GUBA MERIT_html_9eb729fe.png" id="image4.png" data-align="bottom" data-border="0" width="416" height="340" />

**Figure 1:** *Merit Rewards Total Pivot Table (REF: GUBA MERIT)*

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

## <span id="_c0fyt0wc1p3o"></span> **5. Member Lookup, Wallet Mapping, and Final Rewards (Payout-Ready)**

This block converts pivot totals into a **payout-ready list** by binding each member to a wallet address (via GRAPE MEMBERS) and calculating **Final Rewards**.

- **Column E:** Discord Name *(selected from GRAPE MEMBERS)  *
    

- **Column F:** Discord ID *(auto-filled from GRAPE MEMBERS)  *
    

- **Column G:** Wallet Address *(auto-filled from GRAPE MEMBERS)  *
    

- **Column H:** Final Rewards (Month / Cycle) *(USDC)  *
    
    

**Final Rewards behavior (expected):**

- Looks up the member’s total from the Pivot Table (Section 4).  
    

- Applies the Merit-cycle controls (e.g., per-member cap) if configured.  
    

- Returns **0** when the member has no Merit rewards (or lookup fails).  
    
    

**Control:** All payouts should map through **GRAPE MEMBERS** to prevent wallet mismatches.

<img src="assets/T10_ REF_ GUBA MERIT_html_41919323.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="356" />

**Figure 2.** ** *Member Lookup + Wallet Mapping + Final Rewards (REF: GUBA MERIT)*

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_5emjetan9vhp"></span> **6. Merit Category List, IDs, and Pool Lookup**

This block is the reference table for **Merit subcategories** (e.g., Mentorship, Treasury Growth, Tool Building, etc.), including:

- **Merit List** (category name)  
    

- **MERIT ID** (canonical ID used by the scoring pipeline)  
    

- **Total Pool** (USDC amount for that category)  
    

- **Pool Share (%)** (where shown)  
    
    

**What it’s used for:**

- Transparent audit trail: reviewers can see which categories exist and how much pool is assigned to each.  
    

- Ensures category naming and IDs remain consistent across Merit scoring → Merit emissions → REF outputs.  
    
    

<img src="assets/T10_ REF_ GUBA MERIT_html_3a9fca3.png" id="image3.png" data-align="bottom" data-border="0" width="462" height="461" />

**Figure 3.** *Merit List + Merit IDs + Pool Lookup (REF: GUBA MERIT)*

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_b5cvvi7gd278"></span> **7. Summary Metrics and Merit-Cycle Controls**

This section provides the rollup values used to verify the cycle and align with the **Emissions Results Interface**.

Typical metrics shown:

- **FINAL REWARDS:** Sum of all Final Rewards in the payout list  
    

- **TOTAL POOL:  **
    

  - **Monthly pool value** (as displayed)  
      

  - **Period total** = Monthly Pool × **Number of Months** (when applicable)  
      

- **PRODUCTIVITY / UTILIZATION:** Final Rewards ÷ Period Total Pool (or the configured denominator)  
    

- **MAX EMISSION per (Eligible Member):** cap value used to limit per-wallet rewards (if enforced)  
    

- **TOTAL CANDIDATES:** number of members receiving non-zero rewards  
    

- **AVG REWARD:** average rewards per candidate (often shown as monthly + period equivalent)  
    

- **Number of Months:** multiplier applied to period-based pools (e.g., 3)  
    
    

**Important control (GREMS alignment):  **
Merit is period-based. When a **Number of Months** parameter is present, the sheet should treat:

- **Displayed pool** as the **monthly** amount, and  
    

- **Period pool** as **Monthly Pool × Number of Months**.  
    
    

<img src="assets/T10_ REF_ GUBA MERIT_html_ce6f3b28.png" id="image2.png" data-align="bottom" data-border="0" width="435" height="268" />

**Figure 4:** *Summary Metrics (Total Pool, Productivity, Caps, Candidates, Number of Months) – REF: GUBA MERIT*

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape8" />

## <span id="_1oqtf9slu6rh"></span> **8. Operator Run Steps (Merit USDC)**

1.  Confirm **GRAPE MEMBERS** is up to date (Discord IDs + wallets).  
      

2.  Confirm Merit scoring is complete upstream (**SCORE: MERIT EMIT & GUBA MERIT** finalized).  
      

3.  Validate the Pivot Totals (Section 4) reflect the expected Merit outcomes.  
      

4.  In the payout list (Section 5), ensure every rewarded member has a valid wallet populated from GRAPE MEMBERS.  
      

5.  Review Summary Metrics (Section 7):  
      

    - pool totals (monthly vs period)  
        

    - candidate count  
        

    - utilization  
        

    - max emission (if used)  
        

6.  Use **Final Rewards (USDC)** as the source to build the **Merit USDC payout proposal** and to support **Emissions Results Interface – Merit** reporting.  
      
      

<img src="assets/T10_ REF_ GUBA MERIT_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape9" />

## <span id="_agrldrbyuf50"></span> **9. Notes and Controls**

- **Separation of concerns:** REF: GUBA MERIT feeds **Merit** reporting only; do not mix with Performance or Recurring Payments.  
    

- **Identity integrity:** Wallet addresses must map through **GRAPE MEMBERS**.  
    

- **Auditability:** Category IDs and pools should match the Merit category definitions and the Merit scoring pipeline inputs.  
    

- **Period scaling:** If **Number of Months** is used, ensure totals and “remaining” logic reflect **period pool**, not just monthly.
