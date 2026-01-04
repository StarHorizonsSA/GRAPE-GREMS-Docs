# <span id="_fc8gbqcowzv8"></span> **T21: VINE Attendance Sheet**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape1" data-align="bottom" width="624" height="2" alt="Shape1" />

## <span id="_qh1yj48eo379"></span> **1. Purpose**

The **ATTENDANCE VINE** spreadsheet tracks member participation in GRAPE DAO calls and converts participation status into **standardized points**. These points are used to produce **monthly VINE participation totals** that can be referenced in the Governance Participation reward pipeline.

This spreadsheet exists to ensure:

- Consistent scoring across calls

- Transparent review of who participated and how

- A repeatable cycle structure (fixed number of events per cycle)

**Control:** This spreadsheet is an **upstream participation tracker**. It does **not** pay rewards by itself. It supports the **Governance Participation** pipeline by producing auditable attendance/participation totals that are used in downstream reward derivations and payout artifacts.

<img src="assets/T21_ VINE Attendance _html_646f60bc.png" id="image4.png" data-align="bottom" data-border="0" width="624" height="371" />

***Figure 1. ATTENDANCE VINE monthly tab example (TAB:APR2025)***

<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_1ziojbntsmzx"></span> **2. Participation Status Codes (Scoring Rules)**

Each call records one participation status per member:

- **S — Speaker on Stage:** **1.5 points**

- **A — Active in Live Chat:** **1.0 points**

  - Must be meaningful participation (not just emojis/greetings)

- **P — Participation token only:** **0 points**

**Control:** Status assignment is the human-reviewed input. Points are formula-derived and should not be edited manually.

<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_5sx9g0r4pqnz"></span> **3. Monthly Tab Structure (9-Call Cycle Model)**

Each monthly tab is labeled by month (e.g., **TAB:APR2025**, **TAB:MAY2025**) but follows a **fixed-cycle rule**:

- Each tab contains **9 DAO calls** (a fixed number of events)

- Tabs are **not strict calendar months**

- A tab may span dates that start/end in neighboring months

Examples:

- **TAB:APR2025** might start on **May 20**

- **TAB:MAY2025** might end on **June 29**

This design keeps reward cycles consistent by anchoring them to **9 events**, not to month boundaries.

<img src="assets/T21_ VINE Attendance _html_2e92bf39.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="531" />

***Figure 2. Monthly tab example (TAB:MAY2025)*****  **
  
  

<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_c31ketm1v92u"></span> **4. Participation Tracking Within Each Monthly Tab**

Within each monthly tab:

1.  Each member receives a status (**S / A / P**) for each of the 9 calls

2.  Points are calculated automatically using formulas linked to status

3.  Monthly totals (per member) are computed for that 9-call cycle

**Control:** Do not overwrite formulas. If a correction is needed, update the **status** (S/A/P), not the numeric outputs.

<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

  
  

## <span id="_b8vd9aowavle"></span> **5. Master Consolidation Tab: TAB:2025 VINE MONTHLYS**

The tab **TAB:2025 VINE MONTHLYS** consolidates totals from each monthly tab into a single annual view.

Each month/cycle is represented as:

- A clearly labeled **Start Date** and **End Date** (the reward window)

- A **pair of columns** per cycle:

  - **Name**

  - **Score** (the calculated total points)

This enables:

- Side-by-side cycle comparison

- Easy extraction for downstream reporting/proposal prep

- A consistent audit trail across the year

<img src="assets/T21_ VINE Attendance _html_eb298d28.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="508" />

**Figure 3. Annual rollup example (TAB:2025 VINE MONTHLYS)  **
<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_kpz5kzt1umat"></span> **6. GIST Tab Workflow (Monthly Reward Proposal Export)**

To prepare a clean, public-facing proposal artifact:

#### <span id="_hkikmit6uk7q"></span> **6.1 Create a new GIST tab for the cycle**

- Example tab name: **TAB:2025 GIST-PDF: May20–Jun29**

- Pull in the relevant **Name + Score** range from **TAB:2025 VINE MONTHLYS**

#### <span id="_d8h5cni7qtb0"></span> **6.2 Reduce clutter**

- Hide older GIST tabs after the cycle is completed

#### <span id="_3z2h1nf4gojm"></span> **6.3 Export**

- Export the current GIST tab as **PDF** for public posting / proposal presentation

**Tip (Required):** Before exporting, spot-check that each participant’s **S/A/P** status is accurate for all 9 calls—this is the highest-impact source of errors.

<img src="assets/T21_ VINE Attendance _html_defb4bc6.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="453" />

***Figure 4. GIST export tab example (cycle-range view)*****  **
  
  

<img src="assets/T21_ VINE Attendance _html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_5v86dw5lcbi9"></span> 7. Controls and Best Practices

- - **Cycle integrity:** Each “month” tab must contain **exactly 9 calls** (do not add/remove events mid-cycle).

  - **Status-first corrections:** Fix errors by changing **S/A/P**, not by editing point totals.

  - **Transparency:** Keep the cycle date range visible in the master tab and the GIST export.

  - **No manual overrides:** Proposal-facing totals must match the exported GIST values exactly.

  - **Separation of concerns:** Attendance/VINE participation tracking remains part of the **Governance Participation** track and should not be merged into Performance/Merit emissions rollups.

  
  

  
  
