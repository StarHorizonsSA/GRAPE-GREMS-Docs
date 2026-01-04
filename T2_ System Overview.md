# <span id="_qu46oa6rp573"></span> **T2: System Overview**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO.

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

## <span id="_hfztlieen0t0"></span> GRIPv2 Emissions & VINE Rewards Spreadsheets

Together, the **GRIPv2 Emission** and **VINE Rewards** spreadsheets form the operational foundation of GREMS (also referred to as the **Graperators Emissions Pool Management System**).

This collection of interconnected sheets enables the **DAO Quality Control Group (QCG)** and the broader community to review completed tasks, validate contributions, and confirm earned rewards. Reviews are open to any DAO member who attends regular meetings, supporting a transparent process. The spreadsheets share input data and reference tables to automatically calculate rewards based on approved budgets, task rules, participation level, attendance, engagement level, and cap constraints.

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" width="624" height="2" alt="Shape2" />

## <span id="_phexymohv3up"></span> **1. Document Purpose and Scope**

### <span id="_6dkiqxpe2xaj"></span> **1.1 Purpose**

This document explains how data flows across GREMS and provides an operator-friendly procedure to execute monthly and period-based reward cycles with consistent, auditable outputs.

### <span id="_t7lwuj2c4hn8"></span> **1.2 Primary Audience**

Community members, contributors, and the general public who seek to understand how rewards are calculated, assembled for payment, and reported.

### <span id="_5ownjc7t9tlv"></span> **1.3 Scope**

GREMS consists of four parallel reward pipelines:

1.  **Emission Results - Performance** (Monthly) Rewards

2.  **Recurring Payments (Monthly)** — Proposal Architect + Discord Boost + Infrastructure/Tool Costs

3.  **Emission Results - Merit** (Period) Rewards

4.  **Governance Participation Rewards** (VINE & GRAPE + other prizes)  
      
      

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" width="624" height="2" alt="Shape3" />

## <span id="_zih47dxi6ovh"></span> **2. System Components**

### <span id="_rpq87et0m090"></span> **2.1 Upstream Inputs (Source Data)**

**A) Budget Pools per Category**

- Defines the approved reward budgets for each category (per cycle).  
    

- Serves as the primary constraint for distribution calculations.  
    
    

**B) GRAPE MEMBERS (Member Roster / Identifiers)**

- Canonical roster for identity mapping (e.g., handles, wallet addresses, unique identifiers).  
    

- Ensures payout totals are attributed correctly and reduces mismatches.  
    
    

**C) Member Participation & Eligibility Spreadsheets**

- External/parallel spreadsheets used to capture governance participation signals (e.g., eligibility, voting, calls, raffles).  
    

- Used exclusively to produce governance participation outcomes and VINE reward derivations.  
    
    

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" width="624" height="2" alt="Shape4" />

### <span id="_gh0p1gb2o4c"></span> **2.2 Core Calculation and Reference Sheets**

#### <span id="_skdsagakgbm9"></span> **Performance (Monthly)**

- **SCORE: PERFORM & GUBA EMIT** — calculates **GRAPE / USDC / SOL** based on budgets and monthly performance levels.  
    

- **REF: PERFORM** — tabulates final monthly **GRAPE totals** per member.  
    

- **REF: GUBA** — tabulates final monthly **USDC + SOL totals** per member.

#### <span id="_bxi18kp61uq2"></span> **Recurring (Monthly)**

- Together**,** **REF: PROPOSAL ARCHITECT** and **REF: DISCORD BOOST** provide the data necessary to create monthly proposals rewarding proposal architects and Discord boosters.

- **REF: PROPOSAL ARCHITECT** — computes **SOL refunds + rewards** for proposal architects.  
    

- **REF: DISCORD BOOST** — computes **USDC rewards** for Discord boosts.  
    
    

#### <span id="_8mjw4b6qr23"></span> **Merit (Period)**

- **SCORE: MERIT EMIT & GUBA MERIT** — calculates **GRAPE / USDC** based on budgets and period performance levels.  
    

- **REF: MERIT** — tabulates final period **GRAPE totals** per member.  
    

- **REF: GUBA MERIT** — tabulates final period **USDC totals** per member.  
    
    

#### <span id="_847rb4zd92t"></span> **Governance Participation**

- **GOV PARTICIPATION** — evaluates governance eligibility and participation outcomes (voting, calls, raffles).  
    

- **VINE Rewards** — derived from GOV PARTICIPATION outcomes.  
    
    

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" width="624" height="2" alt="Shape5" />

### <span id="_qbpr3xse4pz8"></span> **2.3 Payments and Reporting Outputs**

#### <span id="_6gwom4l9ahjm"></span> **The totals from these sheets serve as input for payment and reward proposals.**

- **RECURRING PAYMENTS** — monthly consolidated payout instruction list (assembled from monthly REF sources + infrastructure and tool costs).  
    

- **GOVERNMENT PARTICIPATION REWARDS** — governance participation payout artifact (standalone; not part of emissions rollups).  
    
    

#### <span id="_xmn9c56m8pva"></span>  

- **EMISSIONS RESULTS - Performance (Monthly Rollup Report)** — monthly reporting derived from performance payout totals.  
    

- **EMISSIONS RESULTS - Merit (Period Rollup Report)** — period reporting derived from finalized merit payout totals.  
    
    

<img src="assets/T2_ System Overview_html_8fe9a01.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="591" />

[*<u>**GRAPE Rewards & Emissions Management System (GREMS)**</u>*](https://www.mermaidchart.com/view/6e573211-7f69-47c0-a81c-71795f1dd3c3)<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="3" width="624" height="2" alt="Shape6" />

## <span id="_ib2eaq7peqk6"></span>  

## <span id="_gij5o5o3wufo"></span>**3. Data Flow: Performance (Monthly) Pipeline**

### <span id="_yh79rn1dvm7p"></span> **3.1 Inputs to Monthly Scoring**

**Monthly** **Budget Pools for the month → SCORE: PERFORM & GUBA EMIT** Approved budgets constrain monthly distribution for each category.

**Monthly performance levels (entered into SCORE) → SCORE: PERFORM & GUBA EMIT  **
During review, the QCG records each member’s monthly performance level in each category for the prior month.

**GRAPE MEMBERS → SCORE / REF sheets  **
Member identifiers map through GRAPE MEMBERS to ensure consistent identity attribution across payout outputs.

### <span id="_ur85aim08ckr"></span> **3.2 Calculation Output: Monthly Member Reward Totals**

**SCORE: PERFORM & GUBA EMIT → REF: PERFORM  **
Produces final **GRAPE totals** per member in payout-ready format.

**SCORE: PERFORM & GUBA EMIT → REF: GUBA  **
Produces final **USDC + SOL totals** per member in payout-ready format.

  

### <span id="_7gg5a39ldibz"></span> **3.3 Monthly Add-On Reward Streams**

**REF: PROPOSAL ARCHITECT → RECURRING PAYMENTS  **
SOL refunds + rewards for proposal architect activities appear on the monthly payment list.

**REF: DISCORD BOOST → RECURRING PAYMENTS  **
USDC rewards for Discord boosts appear on the monthly payment list.

### <span id="_pzf8cm19f6s5"></span> **3.4 Consolidation and Monthly Reporting**

**Performance emissions (monthly rollup)  **
REF: PERFORM + REF: GUBA → **EMISSIONS RESULTS – Performance (Monthly Rollup Report)  **
These REF sheets consolidate monthly **Performance** payout totals only (GRAPE totals from REF: PERFORM and USDC + SOL totals from REF: GUBA).

**Recurring payments (monthly payment list)  **
REF: PROPOSAL ARCHITECT + REF: DISCORD BOOST (+ infrastructure/tool costs, if applicable) → **RECURRING PAYMENTS (Monthly Payment List)  **
These sources consolidate monthly **Recurring Payment** totals only (SOL refunds + rewards, USDC boost rewards, and approved operating costs).

**Control: no consolidation between artifacts  **
RECURRING PAYMENTS and EMISSIONS RESULTS – Performance are **separate artifacts/proposals** and are not merged into a single execution list.

**Note:** Governance Participation rewards are tracked separately via **GOVERNMENT PARTICIPATION REWARDS** and do not flow into **EMISSIONS RESULTS – Performance** nor **RECURRING PAYMENTS**.<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_u74sdiv8rhw"></span>**4. Data Flow: Merit (Period) Pipeline**

### <span id="_4e2o7hqc3gw6"></span> **4.1 Inputs to Period Scoring**

**Monthly Budget Pools for period → SCORE: MERIT EMIT & GUBA MERIT**

Approved budgets constrain period distributions for each category.

**  
Period performance levels (entered into SCORE) → SCORE: MERIT EMIT & GUBA MERIT  **
During review, the QCG records each member’s prior-period performance level per category.

**GRAPE MEMBERS → SCORE / REF sheets  **
Ensures correct identity mapping for merit-period payouts.

### <span id="_cvbc4zw7ez8q"></span> **4.2 Calculation Output: Period Member Totals**

**SCORE: MERIT EMIT & GUBA MERIT → REF: MERIT  **
Produces final **GRAPE totals** per member for the merit period.

**SCORE: MERIT EMIT & GUBA MERIT → REF: GUBA MERIT  **
Produces final **USDC totals** per member for the merit period.

### <span id="_tuw3hq7igx62"></span> **4.3 Period Reporting**

**REF: MERIT + REF: GUBA MERIT → EMISSIONS RESULTS - Merit (Period Rollup Report)  **
Period rollup reporting is derived from the finalized merit payout totals.

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" width="624" height="2" alt="Shape8" />

## <span id="_3trt4nt7jti3"></span> **5. Data Flow: Governance Participation Pipeline (Standalone)**

### <span id="_qbjqgpdl9p7u"></span> **5.1 Participation Inputs**

**Member Participation & Eligibility Spreadsheets → GOV PARTICIPATION  **
Tracking participation enables the calculation of governance eligibility and participation outcomes.

*Note: Participation spreadsheets do not feed VINE Rewards directly.*

### <span id="_mxffzoetoc3u"></span> **5.2 VINE Reward Derivation**

**GOV PARTICIPATION → VINE Rewards  **
Governance participation outcomes determine VINE reward totals.

### <span id="_h21oc8pyk11r"></span> **5.3 Governance Payout Artifact**

**GOV PARTICIPATION + VINE Rewards → GOVERNMENT PARTICIPATION REWARDS  **
Governance participation and VINE outputs consolidate into a payout-ready artifact/proposal.

*Note: This artifact does not flow into either of the EMISSIONS RESULTS.*

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" width="624" height="2" alt="Shape9" />

## <span id="_2320hvo4mol8"></span> **6. Recommended Operating Procedure (Run Order)**

### <span id="_4um5hpauo36s"></span> **6.1 Pre-Run Validation (Required)**

Confirm any updates to the Budget Pools per Category for the cycle.

Confirm the GRAPE MEMBERS roster is up to date (identifiers and payout fields).

When issuing governance rewards, update governance participation inputs in the Member Participation & Eligibility Spreadsheets.

Confirm completion of QCG/community review before submitting any proposal to the community.

### <span id="_7wmhllbkwnur"></span> **6.2 Monthly Cycle Execution**

Update **SCORE: PERFORM & GUBA EMIT** with monthly performance levels.

Review **REF: PERFORM** and **REF: GUBA** for completeness and consistency.

Update **REF: PROPOSAL ARCHITECT** (if applicable).

Update **REF: DISCORD BOOST** (if applicable).

Update infrastructure and tool cost list (if applicable).

Consolidate the outputs from **REF: PROPOSAL ARCHITECT and REF: DISCORD BOOST (+ any infrastructure and tool costs)** to create a single composite **RECURRING PAYMENTS** proposal paying/rewarding USDC and/or SOL.

Consolidate the outputs from **REF: PERFORM** and **REF: GUBA** into **EMISSIONS RESULTS (Performance)** to create two separate proposals: one to reward GRAPE and another to reward USDC & SOL.

### <span id="_ewsb7xyoov1h"></span> **6.3 Merit (Period) Cycle Execution**

Update **SCORE: MERIT EMIT & GUBA MERIT** with period performance levels.

Review **REF: MERIT** and **REF: GUBA MERIT** for completeness and consistency.

Consolidate the outputs from **REF: MERIT** and **REF: GUBA MERIT into EMISSIONS RESULTS - Merit** to create two separate proposals: one to reward USDC and another to reward GRAPE.

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape10" data-align="bottom" width="624" height="2" alt="Shape10" />

### <span id="_iqqggr4s82pk"></span> **6.4 Governance Participation Execution**

Import/update Member Participation & Eligibility Spreadsheets inputs.

Review **GOV PARTICIPATION** outputs (eligibility, voting, calls, raffles).

Confirm **VINE Rewards** reflect governance participation outcomes.

Confirm **GRAPE** rewards reflect governance participation outcomes.

Publish **GOVERNMENT PARTICIPATION REWARDS** payout artifact/proposals: one to reward VINE and another to reward GRAPE.

  
  

<img src="assets/T2_ System Overview_html_ddc2c6d4.gif" id="Shape11" data-align="bottom" width="624" height="2" alt="Shape11" />

## <span id="_26m093myqoc5"></span> **7. Notes and Controls (Best Practice)**

- **Identity integrity:** All totals should map through **GRAPE MEMBERS** to reduce payout errors.  
    

- **Separation of concerns:** Governance participation rewards remain separate from emissions rollups for clearer auditing.  
    

- **Monthly reporting source of truth:** Monthly **RECURRING PAYMENTS** can only come from **REF: PROPOSAL ARCHITECT** and **REF: DISCORD BOOST** sheets (+ any infrastructure and tool cost), and **EMISSIONS RESULTS - Performance** can only come from **REF: PERFORM** and **REF: GUBA** sheets.  
    

- **Transparency:** Reviews are open and verifiable by the QCG and the community before the final payout recommendation occurs. This design helps maintain transparency during the process.
