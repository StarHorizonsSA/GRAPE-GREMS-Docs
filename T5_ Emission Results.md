# <span id="_fc8gbqcowzv8"></span> **T5: Emissions Results Interface**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T5_ Emission Results _html_ddc2c6d4.gif" id="Shape1" data-align="bottom" width="624" height="2" alt="Shape1" />

## <span id="_3dcsrkj77vmi"></span> **1. Purpose**

The **Emissions Results Interface** tab provides a single rollup view of **emission-based reward pools** for the active cycle (monthly or merit period). It allows reviewers and contributors to confirm, at a glance:

- Total budget allocated (and period scaling where applicable)

- Final rewards issued

- Remaining budget

- Validation / integrity checks

- Max emission per eligible member

- Pool utilization rates

**Control:** The Emissions Results Interface is an emissions rollup report. It excludes **RECURRING PAYMENTS** sources (Proposal Architect, Discord Boost, infra/tool costs) and excludes governance participation (VINE).

<img src="assets/T5_ Emission Results _html_5c247021.png" id="image1.png" data-align="bottom" data-border="0" width="606" height="277" />

***Figure 1. Emissions Results Interface (November 2025 GRIPv2 Emissions Templates)***

***Note: “Number of Months” is used to scale merit-period pools when the merit window spans multiple months.***

<img src="assets/T5_ Emission Results _html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

  
  

## <span id="_hukclpxc0nnm"></span> **2. Pools Represented in This Tab (By Column)**

Each column represents a separate emission pool. Pools map to GREMS pipelines and their **REF source sheets**.

#### <span id="_jxilv4dpl7pa"></span> **2.1 Performance (Monthly) Pools**

**PERFORM EMIT (GRAPE)**

- **Source of truth:** **REF: PERFORM  **
    

- **Token:** GRAPE  
    

- **Meaning:** Monthly performance emissions tied to activity-based contributions.  
    
    

**GUBA EMIT (USDC)**

- **Source of truth:** **REF: GUBA  **
    

- **Token:** USDC  
    

- **Meaning:** Monthly performance emissions paid in USDC (where configured).  
    
    

**SOL EMIT (SOL)**

- **Source of truth:** **REF: GUBA  **
    

- **Token:** SOL  
    

- **Meaning:** Monthly performance emissions paid in SOL (where configured).  
    
    

#### <span id="_za1p3ueytxal"></span> **2.2 Merit (Period) Pools**

**MERIT EMIT (GRAPE)**

- **Source of truth:** **REF: MERIT  **
    

- **Token:** GRAPE  
    

- **Meaning:** Merit-period emissions based on merit scoring for the defined period window.  
    
    

**GUBA MERIT (USDC)**

- **Source of truth:** **REF: GUBA MERIT  **
    

- **Token:** USDC  
    

- **Meaning:** Merit-period emissions paid in USDC for the defined period window.  
    
    

#### <span id="_932nhdpd2ibo"></span> **2.3 Optional / Template-Dependent Pools**

**SOL other (SOL)**

- Optional pool shown in some templates. If used, it must be explicitly defined in-template and should not be confused with RECURRING PAYMENTS.  
    
    

<img src="assets/T5_ Emission Results _html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_f2oj1jprke5i"></span> **3. Emissions Pool Summary (Top Section)**

This section summarizes budget and distribution totals for each pool.

#### <span id="_115bmlzbhht4"></span> **3.1 Metrics and Meaning**

**Total Budget**

- Total tokens allocated to the pool for the cycle.  
    

- In templates using a multi-month merit period, merit pools may display a **monthly budget**, scaled by the **Number of Months** parameter.  
    
    

**FINAL REWARDS**

- Total tokens distributed to eligible members from the pool.  
    
    

**Remaining**

- Unused budget after distributions.  
    
    

**Validation**

- Integrity checks to confirm totals and constraints are consistent with the pool’s rules and source totals.  
    
    

**Number of Months (template parameter)**

- Used when the cycle spans multiple months (commonly for merit periods).  
    

- For merit-period pools, the **period budget** is calculated as:  
    
    

**Period Budget = Total Budget × Number of Months**

<img src="assets/T5_ Emission Results _html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_qohimrxyvdvg"></span> **4. Max Emission Per Eligible Member (Middle Section)**

This section shows a diagnostic maximum per eligible member (cap view), based on pool budgets and eligibility counts.

#### <span id="_oozqyywwdls3"></span> **4.1 Metrics and Meaning**

- **Total Budget:** The pool amount used for the max-per-eligible calculation.  
    

- **FINAL REWARDS:** The realized distribution shown for comparison.  
    
    

**Control:** This is a diagnostic limit view. Payout truth remains the REF totals.

<img src="assets/T5_ Emission Results _html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

## <span id="_ifou8u7wh7fg"></span> **5. Emissions Pool Utilized (Bottom Section)**

This section shows how much of each pool was used.

#### <span id="_9rksold6r8y5"></span> **5.1 Utilization Logic**

- **Performance (Monthly) pools:  **
  **Utilized = Final Rewards ÷ Total Budget  **
    

- **Merit (Period) pools when Number of Months applies:  **
  **Utilized = Final Rewards ÷ (Total Budget × Number of Months)  **
    
    

<img src="assets/T5_ Emission Results _html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_jbz4wa1nztt8"></span> **6. Source-of-Truth Controls (GREMS-Aligned)**

#### <span id="_r9xvnwl5ftz1"></span> **6.1 Performance Rollup Sources**

The Emissions Results Interface (Performance pools) can only be derived from:

- **REF: PERFORM (GRAPE totals)  **
    

- **REF: GUBA (USDC + SOL totals)  **
    
    

#### <span id="_gv623p6owqz9"></span> **6.2 Merit Rollup Sources**

The Emissions Results Interface (Merit pools) can only be derived from:

- **REF: MERIT (GRAPE totals)  **
    

- **REF: GUBA MERIT (USDC totals)  **
    
    

#### <span id="_51t8uo1piizu"></span> **6.3 Controls and Prohibitions**

- **Do not mix pipelines:** Governance Participation (VINE) and RECURRING PAYMENTS sources must not appear in the Emissions Results Interface.  
    

- **No manual overrides:** Totals must match computed REF outputs exactly. If the spreadsheet does not show it, the proposal must not include it.
