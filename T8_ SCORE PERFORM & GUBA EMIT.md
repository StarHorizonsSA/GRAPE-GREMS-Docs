## <span id="_3jahsicx26c8"></span> **T8: SCORE: PERFORM & GUBA EMIT**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape1" />

## <span id="_8uegtm2j4vxq"></span> **1. Purpose**

The **SCORE: PERFORM & GUBA EMIT** tab is the **monthly scoring and allocation engine** for Performance rewards. It records member work assignments and performance levels, then uses formulas to distribute monthly reward pools across three emission types:

- **PERFORM EMIT** → **GRAPE** rewards

- **GUBA EMIT** → **USDC** rewards

- **SOL EMIT** → **SOL** rewards

This tab is designed to minimize manual input and maximize auditability: **operators only select inputs**, while **all allocations are calculated automatically**.

**Control:** This tab supports **Performance (Monthly)** emissions only. It does **not** include **RECURRING PAYMENTS** sources (Proposal Architect refunds/rewards, Discord Boost, infra/tool costs) and does **not** include governance participation (VINE).

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_mym4d21fc6gw"></span> **2. Operator Inputs (Manual / Dropdown Only)**

Only the following fields should be edited by operators:

### <span id="_u3hz1i9n6sty"></span> **2.1 Column A — Discord Name**

- Selected from a dropdown list sourced from **GRAPE MEMBERS** (or equivalent roster tab).

- Ensures identity consistency (no typos, stable mapping).

### <span id="_pa856o6zr3ak"></span> **2.2 Column B — Task Name**

- Selected from a dropdown list of approved monthly Performance tasks/categories (examples include):

  - Approved Proposal Architect

  - Call Documentation Upkeep (Discord / Recap)

  - Moderate (Discord / Calls)

  - Moderate (Discourse / Admin)

  - Product UAT DAO

  - Quality Control Quorum Committee

  - Creative Content & Videography

  - Product Updates – Code Pushes

  - Exploratory Committee

  - Partner Relationship Communications

  - Documentation: DAO & Community

  - Metrics: DAO (Track & Monitor)

  - Calendar/Event Management

  - Metrics: Syndicate (Track / Monitor / Update)

  - Workshop Organizer & Participants

  - Social Media (X/Twitter)

  - Discord Admin & Management

  - Research / Alpha / Tokens & NFTs

  - Treasury Controller & Emissions Execution

  - Community Coordinator

### <span id="_bis4u2me7qme"></span> **2.3 Column C — Perform Level**

- Selected from a dropdown of standardized levels:

  - **LEVEL 0 (0%)**

  - **LEVEL 1 (33%)**

  - **LEVEL 2 (66%)**

  - **LEVEL 3 (100%)**

**Operator rule:** Only update cells explicitly marked for input (commonly **yellow/green** fields in the template). Everything else is formula-driven.

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_9e7ba15b.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="317" />

***Figure 1. SCORE: PERFORM & GUBA EMIT — Operator Inputs (Discord Name, Task, Perform Level)***

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_16s21yseza9r"></span> **3. Reference Outputs (Operator-Readable Totals)**

These columns summarize the calculated results per row (and are used for rollups and downstream totals):

- **Column D — Total Rewards (GRAPE)** *(from PERFORM EMIT final)*

- **Column E — Total Allocation (USDC)** *(from GUBA EMIT final)*

- **Column F — Total Allocation (SOL)** *(from SOL EMIT final)*

- **Column G — Discord IDs** *(reference mapping)*

- **Column H — Task IDs** *(reference mapping)*

- \**Column I — Blank / spacing (readability)*

These outputs make it easy to filter/sum rewards by member, by task, or by emission type.

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_dq98lo522olv"></span> **4. Calculation Blocks (How Rewards Are Computed)**

### <span id="_15fdzzc0jtlf"></span> **4.1 PERFORM EMIT (GRAPE) — Columns J–P**

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_b58704dc.png" id="image4.png" data-align="bottom" data-border="0" width="624" height="200" />

***Figure 2. PERFORM EMIT (GRAPE) — Allocation Block and Totals***

This block allocates **GRAPE** from task pools.

- **J — Unique ID  **
  Combines Task ID + Discord ID (example: =H6&"\_"&G6)

- **K — Perform Weight Score  **
  Converts LEVEL selection into a % via lookup (see Weight Table).

- **L — Graperator Count  **
  Counts members assigned to the same task with a valid (\>0) weight score.

- **M — Task Pool Allocation (GRAPE)  **
  Pulls the monthly GRAPE pool for the task (source is the configured pool reference used by the system).

- **N — Perform Weight Reward  **
  Allocates the task pool proportionally to the member based on weight score and task participation.

- **O — Remaining Reward  **
  Tracks any unallocated remainder (after distribution).

- **P — Total GRAPE Rewards  **
  Final GRAPE reward for that row/task/member.

  
  

### <span id="_gu0ryfrawcn1"></span> **4.2 GUBA EMIT (USDC) — Columns R–X**

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_872b3605.png" id="image5.png" data-align="bottom" data-border="0" width="624" height="212" />

***Figure 3. GUBA EMIT (USDC) — Allocation Block and Totals***

This block allocates **USDC** from monthly USDC task pools.

- **R — Unique ID  **
  Task ID + Discord ID

- **S — Perform Weight Score  **
  LEVEL → % lookup

- **T — Graperator Count  **
  Counts members on the task

- **U — Task Pool Allocation (USDC)  **
  Pulls the USDC pool for the task (monthly config source)

- **V — Perform Weight Reward  **
  Proportional allocation by weight score and participation

- **W — Remaining Reward  **
  Leftover pool after allocation

- **X — Total Allocation (USDC)  **
  Final USDC reward for that row/task/member

  
  

  
  

  
  

### <span id="_dghlixx5iw5v"></span> **4.3 SOL EMIT (SOL) — Columns Z–AF**

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_2070fdbe.png" id="image6.png" data-align="bottom" data-border="0" width="624" height="217" />

***Figure 4. SOL EMIT (SOL) — Allocation Block and Totals***

This block allocates **SOL** from the configured SOL task pools.

- **Z — Unique ID  **
  Task ID + Discord ID

- **AA — Perform Weight Score  **
  LEVEL → % lookup

- **AB — Graperator Count  **
  Counts members on the task

- **AC — Task Pool Allocation (SOL)  **
  Pulls the SOL pool for the task (monthly config source)

- **AD — Perform Weight Reward  **
  Proportional SOL allocation

- **AE — Remaining Reward  **
  Leftover pool after allocation

- **AF — Total Allocation (SOL)  **
  Final SOL reward for that row/task/member

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

## <span id="_nwu8xrkpka7t"></span> **5. Support Tables and Summaries**

### <span id="_vxiuby7f2awk"></span> **5.1 Weight Level Lookup — Columns AH–AI**

Defines the standardized mapping used across all three emission blocks:

- **AH — Weight Level:** LEVEL 0–3 (+ optional “Average”)

- **AI — Percentage:** 0%, 33%, 66%, 100% (and 50% for Average if used)

### <span id="_pquqcam3d7n3"></span> **5.2 Pivot / Summary (Task Rollups) — Columns AK–AN**

A compact task-level rollup to help reviewers validate totals:

- **AK — Task Names**

- **AL — Sum of Perform**

- **AM — Sum of Remaining**

- **AN — Average of Perform**

This area is commonly used during review calls to confirm whether pools are distributing as expected.

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_1a99d0de.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="319" />

***Figure 5 (Image 5: pivot/summary + weights area)***

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_b5dgvqxfn0ib"></span> **6. Workflow (Monthly Use)**

1.  **During DAO call / review:  **
    Select **Discord Name (A)**, **Task (B)**, and **Perform Level (C)** for each row needed.

2.  **Let formulas compute:  **
    GRAPE totals in **P**, USDC totals in **X**, SOL totals in **AF**.

3.  **Review integrity:  **
    Use task summaries (AK–AN) and remaining columns (O/W/AE) to spot anomalies.

4.  **Downstream rollups:  **
    Results are carried forward into the system’s payout-ready reference outputs and monthly reporting.

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_cbbcf830.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="543" />

***Figure 6. Performance Scoring Workflow — From DAO Call Inputs to REF Outputs***

<img src="assets/T8_ SCORE PERFORM &amp; GUBA EMIT _html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_d80le1d3rwpf"></span> **7. Controls and System Alignment**

- **Input-only discipline:** Operators should edit **only** dropdown input cells; formula blocks should remain unchanged.

- **Identity mapping:** All member selection should resolve through the canonical roster (**GRAPE MEMBERS**) to prevent payout mismatches.

- **Separation of artifacts:** This tab supports **Performance emissions** only and remains separate from **RECURRING PAYMENTS** and **Governance Participation** pipelines.

- **Monthly reporting alignment:** The **Emissions Results Interface (Performance)** rollup must be sourced from the Performance reference outputs (not from Recurring Payments sources).

  
  
