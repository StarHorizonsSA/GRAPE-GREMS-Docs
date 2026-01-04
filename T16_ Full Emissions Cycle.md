# <span id="_qu46oa6rp573"></span> **T16: Full Emissions Cycle**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

## <span id="_lmxrusqjszx1"></span> **1. Purpose**

This document provides a complete walkthrough of how GREMS moves from **approved budgets** and **validated scoring** to **payout-ready artifacts/proposals**. It is written for contributors, reviewers, and operators who want a clear, auditable view of what happens each month and each merit period.

GREMS supports **three parallel reward pipelines**:

1.  **Performance Rewards (Monthly)  **
      

2.  **Merit Rewards (Period-Based)  **
      

3.  **Governance Participation Rewards (Standalone payout artifact)  **
      
      

**Control:** Governance Participation (VINE, raffles, eligibility signals) is processed in a standalone pipeline and **does not roll into emissions rollup reporting**.

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_9xye6lleekdp"></span> **2. Definitions**

### <span id="_gj4diq5pgj60"></span> **2.1 What “Emissions” Means in GREMS**

In GREMS, “emissions” refers to rewards distributed from emission-based pools (typically **GRAPE, USDC, and SOL**) to eligible contributors based on validated scoring and budget constraints.

### <span id="_mnv0o5ufqmcc"></span> **2.2 Key Output Artifacts**

GREMS produces separate outputs that should not be consolidated:

- **EMISSIONS RESULTS – Performance** (artifact/proposals for monthly Performance totals)  
    

- **EMISSIONS RESULTS – Merit** (artifact/proposals for period Merit totals)  
    

- **RECURRING PAYMENTS** (monthly payment list for Proposal Architect + Discord Boost + infra/tool costs)  
    

- **GOVERNMENT PARTICIPATION REWARDS** (standalone governance participation payout artifact)  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_5430c61hvdxr"></span> **3. Pools and Where They Belong**

### <span id="_fqz1xj9i0jjl"></span> **3.1 Emissions Results Interface (Rollup View)**

The **Emissions Results Interface** tab is a rollup view of emission pools and summary metrics (budget, final rewards, remaining, max per member, utilization, validation).

Typical columns include:

- **PERFORM EMIT (GRAPE)  **
    

- **GUBA EMIT (USDC)  **
    

- **SOL EMIT (SOL)  **
    

- **MERIT EMIT (GRAPE)  **
    

- **GUBA MERIT (USDC)  **
    

- **SOL other (SOL)** *(if configured; project-specific usage)  *
    
    

**Control:** The Emissions Results Interface is a reporting/rollup surface. It does **not** include Recurring Payments sources (Proposal Architect, Discord Boost, infra/tool costs) and does **not** include governance participation (VINE).

### <span id="_elkvtqr62myd"></span> **3.2 What Each Pool Represents**

**Performance (Monthly)**

- **PERFORM EMIT:** GRAPE rewards for monthly tasks/roles  
    

- **GUBA EMIT:** USDC rewards tied to monthly performance categories  
    

- **SOL EMIT:** SOL rewards tied to monthly performance categories  
    
    

**Merit (Period-Based)**

- **MERIT EMIT:** GRAPE merit rewards (period-based recognition)  
    

- **GUBA MERIT:** USDC merit rewards (period-based)  
    
    

**Other / Optional**

- **SOL other:** Additional SOL distributions (only if explicitly configured and governed)  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_gf518wq38ths"></span> **4. End-to-End Cycle**

GREMS runs on two main cadences (plus a standalone governance participation payout stream):

- **Monthly cycle:** Performance + Recurring Payments  
    

- **Merit cycle:** Period-based (often multi-month)  
    

- **Governance participation:** Standalone (tracked and paid separately)  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

## <span id="_icwysujt8u42"></span> **5. Performance Cycle (Monthly)**

### <span id="_61gq2h2a933"></span> **5.1 Inputs**

- **Budget Pools per Category** (approved monthly budgets)  
    

- **GRAPE MEMBERS** (canonical roster / identity mapping)  
    

- **Monthly scoring inputs** (performance levels validated in open review)  
    
    

### <span id="_afezv4kgpq4r"></span> **5.2 Scoring and Calculation**

1.  QCG/community review confirms performance levels by category.  
      

2.  Operators enter monthly scoring in:  
      

    - **SCORE: PERFORM & GUBA EMIT  **
        

3.  The sheet calculates payout-ready totals across:  
      

    - GRAPE (PERFORM EMIT)  
        

    - USDC (GUBA EMIT)  
        

    - SOL (SOL EMIT)  
        
        

### <span id="_fbld6t8oe3xt"></span> **5.3 Reference Totals (Payout-Ready)**

- **REF: PERFORM** = GRAPE totals per member (monthly)  
    

- **REF: GUBA** = USDC + SOL totals per member (monthly)  
    
    

### <span id="_q60piwwbu3n5"></span> **5.4 Reporting and Proposals**

- **REF: PERFORM + REF: GUBA → EMISSIONS RESULTS – Performance** (monthly rollup artifact)  
    

- Operators typically generate **separate execution proposals** for:  
    

  - GRAPE payout proposal (from REF: PERFORM)  
      

  - USDC + SOL payout proposal (from REF: GUBA)  
      
      

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_hu454l55zpn1"></span> **6. Merit Cycle (Period-Based)**

### <span id="_pj46o55tigyr"></span> **6.1 Inputs**

- **Budget Pools per Category** (approved budgets for the merit period)  
    

- **GRAPE MEMBERS** (identity mapping)  
    

- **Merit scoring decisions** (validated in open review)  
    
    

### <span id="_g2gpe6izlbud"></span> **6.2 Scoring Entry**

1.  Merit category definitions and scoring happens in:  
      

    - **SCORE: MERIT SCORING** *(category assignment + levels)  *
        

2.  Scoring data feeds into calculation in:  
      

    - **SCORE: MERIT EMIT & GUBA MERIT** *(no manual dropdowns here; it consumes the scoring sheet outputs)  *
        
        

### <span id="_z6z2djlfzzlo"></span> **6.3 Reference Totals (Payout-Ready)**

- **REF: MERIT** = GRAPE totals per member (period)  
    

- **REF: GUBA MERIT** = USDC totals per member (period)  
    
    

### <span id="_7id67mro3vnk"></span> **6.4 Reporting and Proposals**

- **REF: MERIT + REF: GUBA MERIT → EMISSIONS RESULTS – Merit** (period rollup artifact)  
    

- Operators typically generate **separate execution proposals** for:  
    

  - GRAPE payout proposal  
      

  - USDC payout proposal  
      
      

### <span id="_akp1f4gmipes"></span> **6.5 Control: Number of Months Scaling**

Some merit pools are configured as **multi-month** cycles and use a **Number of Months** parameter in the Emissions Results Interface. In those cases:

- Displayed “Total Budget” may represent a **monthly budget  **
    

- Period budget = **Total Budget × Number of Months  **
    

- Utilization should be evaluated against the **period budget  **
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_3j0s8hs91pr8"></span> **7. Governance Participation (Standalone)**

Governance participation rewards are handled outside emissions rollups.

### <span id="_ieelcep7ght2"></span> **7.1 Inputs and Processing**

- Member Participation & Eligibility Spreadsheets  
  → **GOV PARTICIPATION** (eligibility/voting/calls/raffles)  
  → **VINE Rewards** (derived from GOV PARTICIPATION outcomes)  
  → **GOVERNMENT PARTICIPATION REWARDS** (standalone payout artifact)  
    
    

### <span id="_i44hwl8zgz1g"></span> **7.2 Control**

Governance Participation rewards:

- **do not** feed Performance emissions reporting  
    

- **do not** feed Merit emissions reporting  
    

- are distributed via their own standalone artifact/proposals (often separate VINE vs GRAPE proposals)  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape8" />

## <span id="_34nbo7zhrub7"></span> **8. Recurring Payments (Monthly Payment List)**

Recurring Payments are not emissions rollups.

### <span id="_s1bu2jld3ii9"></span> **8.1 Sources**

- **REF: PROPOSAL ARCHITECT** (SOL refunds + rewards)  
    

- **REF: 2025 DISCORD BOOST** (USDC boost rewards)  
    

  - **infrastructure/tool costs** (as applicable)  
      
      

### <span id="_itxobnebswou"></span> **8.2 Output**

- **REF: PROPOSAL ARCHITECT + REF: DISCORD BOOST (+ infra/tool costs) → RECURRING PAYMENTS  **
  **Control:** RECURRING PAYMENTS is a separate artifact/proposal from EMISSIONS RESULTS – Performance.  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape9" />

## <span id="_nblzmk1lpxx0"></span> **9. Validation and Review**

Before publishing proposals, reviewers use the **Emissions Results Interface** and REF tabs to confirm:

- **Final Rewards** totals are consistent with REF sheets  
    

- **Remaining** values make sense (budget caps enforced)  
    

- **Max Emission per eligible member** caps are applied  
    

- **Wallet count validation** checks pass where implemented  
    

- Merit multi-month utilization is interpreted using **Number of Months** when applicable  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape10" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape10" />

## <span id="_xxxvhf678ije"></span> **10. GREMS Relationships**

### <span id="_70494irobq6o"></span> **10.1 Performance (Monthly)**

Budget Pools + GRAPE MEMBERS  
→ SCORE: PERFORM & GUBA EMIT  
→ REF: PERFORM + REF: GUBA  
→ EMISSIONS RESULTS – Performance (artifact)

### <span id="_g77w0yag4jdl"></span> **10.2 Merit (Period)**

Budget Pools + GRAPE MEMBERS  
→ SCORE: MERIT SCORING  
→ SCORE: MERIT EMIT & GUBA MERIT  
→ REF: MERIT + REF: GUBA MERIT  
→ EMISSIONS RESULTS – Merit (artifact)

### <span id="_pxkw2l4tdliq"></span> **10.3 Add-Ons (Monthly Recurring Payments)**

REF: PROPOSAL ARCHITECT + REF: DISCORD BOOST (+ infra/tool costs)  
→ RECURRING PAYMENTS (artifact)

### <span id="_l43ly0vioe60"></span> **10.4 Governance Participation (Standalone)**

Member Participation & Eligibility Spreadsheets  
→ GOV PARTICIPATION  
→ VINE Rewards  
→ GOVERNMENT PARTICIPATION REWARDS (artifact)

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape11" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape11" />

## <span id="_xi9rgymadlcj"></span> **11. Common Issues and Controls**

- **Member missing from payout:** confirm GRAPE MEMBERS roster entry and identifiers.  
    

- **Unexpected zeros:** verify pool budgets and correct source REF tab mappings.  
    

- **Validation failing:** check wallet count checks, formula ranges, and period scaling (Number of Months).  
    

- **Remaining too high:** confirm eligible members were scored and the right pools are being evaluated (monthly vs period).  
    
    

<img src="assets/T16_ Full Emissions Cycle_html_ddc2c6d4.gif" id="Shape12" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape12" />

## <span id="_17f1m27trarx"></span> **12. Summary**

GREMS converts approved budgets and validated scoring into **payout-ready artifacts** with clear separation between:

- **Performance emissions (monthly)  **
    

- **Merit emissions (period-based)  **
    

- **Recurring Payments (monthly add-ons + infra/tool costs)  **
    

- **Governance Participation rewards (standalone)  **
    
    

This separation is a core control for auditability and proposal clarity.
