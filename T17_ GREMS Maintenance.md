# <span id="_qu46oa6rp573"></span> **T17: Maintenance of RECURRING PAYMENTS**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

## <span id="_9d1tnppuhgyc"></span> **1. Purpose**

This document explains how to maintain the **GREMS “maintenance / ops” tabs** that support **monthly operational payments and auxiliary reward streams** that are **not part of Performance or Merit emissions or Governance Participation rollups.**.

These tabs feed the **RECURRING PAYMENTS** artifact/proposal (monthly payment list) and help ensure monthly payments remain accurate, auditable, and easy to reproduce.

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_cdr3awdd7ped"></span> **2. Naming Standard**

To avoid confusion and keep documentation reusable:

- **In documentation:** use 20XX (evergreen template)  
    

- **In the live workbook:** use the real year (2025, 2026, etc.)  
    
    

Examples:

- REF: 20XX DISCORD BOOST *(example:* *REF: 2025 DISCORD BOOST)  *
    

- REF: 20XX RECURRING PAYMENTS *(example:* *REF: 2025 RECURRING PAYMENTS)  *
    
    

  
  

  
  

  
  

  
  

  
  

  
  

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_zdelbl2u8oeo"></span> **3. Scope and Controls**

#### <span id="_mhfatso7spmr"></span> **3.1 What this guide covers**

These tabs support **Recurring Payments** and auxiliary rewards:

| **Tab** | **What it tracks** | **Output relevance in GREMS** |
|----|----|----|
| **REF: PROPOSAL ARCHITECT** | SOL “rent” reimbursement + bonus for proposal authors | Feeds **RECURRING PAYMENTS** (SOL) |
| **REF: 20XX DISCORD BOOST** | USDC rewards for Discord boosters | Feeds **RECURRING PAYMENTS** (USDC) |
| **REF: 20XX RECURRING PAYMENTS** | Monthly operational payments (infra/tools/subscriptions + auto-linked reward totals) | Becomes the **RECURRING PAYMENTS** payment list proposal |

#### <span id="_hzw9xxoit14f"></span> **3.2 Separation-of-artifacts (GREMS Control)**

- **RECURRING PAYMENTS** is **separate** from **Emissions Results – Performance** and **Emissions Results – Merit** rollups.  
    

- **RECURRING PAYMENTS** can only consolidate from:  
    

  - REF: PROPOSAL ARCHITECT (SOL)  
      

  - REF: DISCORD BOOST (USDC)  
      

  - approved **infrastructure/tool costs** (USDC and/or SOL)  
      

- It must **not** be merged into Performance and Merit emissions, or Governance Participation Rewards reporting/proposals.  
    
    

  
  

  
  

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_59k2f575dkta"></span> **4. TAB: REF: PROPOSAL ARCHITECT (Maint. + Payout Basis)**

### <span id="_ryf7k75x7k1g"></span> **4.1 Purpose**

REF: PROPOSAL ARCHITECT is the **master log of governance proposal activity**, capturing proposal metadata and calculating **SOL rent reimbursement** (and bonus SOL) for proposal architects.

### <span id="_vqwjhuyv2mv"></span> **4.2 Source (where data comes from)**

Proposal information is copied from the DAO’s governance portal (e.g., governance.so / Realms).

### <span id="_2sknpxv2bvu8"></span> **4.3 Constants (Cost Parameters)**

These values drive the SOL reimbursement calculation and can be updated DAO-wide when parameters change.

|  |  |  |  |
|----|----|----|----|
| **Cell** | **Parameter** | **Meaning** | **Example value (SOL)** |
| **B2** | Proposal Creation Cost | SOL cost per proposal created | 0.00543576 |
| **B3** | Token Transfer Instruction Cost | SOL cost per token transfer instruction | 0.00238236 |
| **B4** | Grant Voting Power Instruction Cost | SOL cost per grant instruction | 0.00402984 |
| **B5** | Bonus SOL | Bonus applied later per proposal | 0.05 |

### <span id="_prt4x26uf8bp"></span>  

### <span id="_da9gcu1dyhkj"></span>  

### <span id="_z63zpzula3ex"></span>  

### <span id="_xddi3ny6j0oh"></span> **4.4 Proposal Log Columns (A–J)**

|  |  |  |
|----|----|----|
| **Column** | **Field** | **Description** |
| A | Proposal Title | Title/label of the proposal |
| B | Signed Off At | Timestamp the proposal was signed off |
| C | Ends At | End timestamp (used to group by month) |
| D | Proposal URL | Direct link to proposal page |
| E | Wallet | Proposal author wallet |
| F | Discord Name | Author attribution |
| G | Proposal Creation Count | Typically “1” per proposal row |
| H | Token Transfer Instructions | Count visible in proposal details |
| I | Grant Voting Power Instructions | Count visible in proposal details |
| J | Proposal Rent (SOL) | Calculated SOL reimbursement |

### <span id="_hddaugvxxrft"></span>  

### <span id="_71zq0g7m7hac"></span>  

### <span id="_tqmy2w7euhb"></span> **4.5 Core Formula (Column J)**

Proposal Rent (SOL) is calculated as:

|                     |                                         |
|---------------------|-----------------------------------------|
| **Field**           | **Formula**                             |
| Proposal Rent (SOL) | =(Gx\*\$B\$2)+(Hx\*\$B\$3)+(Ix\*\$B\$4) |

### <span id="_f505syfhmrcc"></span> **4.6 Monthly Wallet Summary (N–U)**

This section aggregates totals per wallet/Discord for the selected month.

|  |  |  |
|----|----|----|
| **Column** | **Output** | **What it does** |
| N | Unique Wallets | Lists unique wallets for the month |
| O | Discord Names | Maps wallet → Discord name |
| P | Base Rent (SOL) | Sum of Column J per wallet |
| S | Proposal Count | Sum of proposals created |
| Q | Total + Bonus (SOL) | Base rent + (Proposal Count × Bonus SOL) |
| R | Bonus Only (SOL) | Total+Bonus minus Base |
| T | Transfer Instruction Total | Total token transfer instructions |
| U | Grant Instruction Total | Total grant voting power instructions |

**Maintenance note (important):** When creating a new month block, copy formulas from a prior month and **update the ranges** so the month summarizes the correct row set. Incorrect ranges = incorrect payouts.

### <span id="_ksksb376mam2"></span> **4.7 Maintenance Checklist (REF: PROPOSAL ARCHITECT)**

- Add new row(s) for each new proposal.  
    

- Copy/paste: Title, dates, URL, wallet, Discord name.  
    

- Count instructions (token transfer + voting power grant).  
    

- Confirm Column J auto-calculates.  
    

- Confirm the monthly summary block totals match expected activity.  
    
    

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

  
  

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

## <span id="_thz7u29mu00r"></span> **5. TAB: REF: 20XX DISCORD BOOST (Booster Rewards → Recurring Payments)**

### <span id="_o0ggkk7drjft"></span> **5.1 Purpose**

Tracks Discord server boosts per member and calculates USDC rewards based on a fixed per-boost rate (example: **\$5 USDC / boost**).

### <span id="_83xm621pv4dz"></span> **5.2 Reward Rate**

|              |                   |                                  |
|--------------|-------------------|----------------------------------|
| **Cell**     | **Parameter**     | **Meaning**                      |
| (example) C3 | Boost Reward Rate | USDC paid per boost (e.g., 5.00) |

### <span id="_b2068xeypwwt"></span> **5.3 Core Columns (Identity)**

|            |                |                          |
|------------|----------------|--------------------------|
| **Column** | **Field**      | **Description**          |
| A          | Discord Name   | Booster’s Discord handle |
| B          | Discord ID     | Booster’s Discord ID     |
| C          | Wallet Address | Payment wallet           |

### <span id="_wejvc2nsk79a"></span>  

### <span id="_zf6hojvkrybk"></span> **5.4 Monthly Tracking Layout (Jan–Dec)**

Each month is a **two-column pair**:

|                |                  |                   |
|----------------|------------------|-------------------|
| **Month Pair** | **First Column** | **Second Column** |
| JAN            | \# Boosts        | Reward (USDC)     |
| FEB            | \# Boosts        | Reward (USDC)     |
| …              | …                | …                 |
| DEC            | \# Boosts        | Reward (USDC)     |

### <span id="_jjsv9kqm9usq"></span> **5.5 Reward Formula**

|                       |                             |
|-----------------------|-----------------------------|
| **Field**             | **Formula**                 |
| Monthly Reward (USDC) | =Boosts \* \$RewardRateCell |

### <span id="_j3nof6if5ydk"></span> **5.6 Boost Logging Procedure**

1.  Open Discord → GRAPE server → **Server Settings** → **Server Boost Status**.  
      

2.  Record/update each booster’s name/ID/wallet.  
      

3.  Enter the **\# of boosts** for the current month.  
      

4.  Confirm reward cells auto-calculate.  
      
      

### <span id="_jm1o47swnivm"></span> **5.7 Output Use**

Monthly totals from this tab are pulled into the **RECURRING PAYMENTS** payment list as the USDC component of “Discord Boost Rewards.”

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_gzdrlrtzesnj"></span> **6. TAB: REF: 20XX RECURRING PAYMENTS (Monthly Payment List)**

### <span id="_it4kql5xrwco"></span> **6.1 Purpose**

This tab is the **monthly ledger** for operational expenses and auxiliary rewards paid by the DAO. It becomes the payout-ready structure for the **RECURRING PAYMENTS** proposal.

### <span id="_appm48sqo7kl"></span> **6.2 Core Layout**

**Columns A–B: Payment item + recipient wallet**

|            |                          |                            |
|------------|--------------------------|----------------------------|
| **Column** | **Field**                | **Description**            |
| A          | Item/Service Description | What is being paid and why |
| B          | Wallet Address           | Recipient wallet           |

**Columns C–Z (and beyond): Monthly currency pairs  **
Each month is a two-column pair: **USDC** then **SOL**.

<table width="296" data-cellpadding="7" data-cellspacing="0">
<tbody>
<tr data-valign="top">
<td width="83" height="17" data-bgcolor="#6fa8dc" style="background: #6fa8dc; border-top: 2.25pt solid #000000; border-bottom: 1.50pt solid #000000; border-left: 2.25pt solid #000000; border-right: 2.25pt solid #000000; padding: 0.07in"><p><strong>Month</strong></p></td>
<td width="80" data-bgcolor="#6fa8dc" style="background: #6fa8dc; border-top: 2.25pt solid #000000; border-bottom: 1.50pt solid #000000; border-left: 2.25pt solid #000000; border-right: 2.25pt solid #000000; padding: 0.07in"><p><strong>USDC Column</strong></p></td>
<td width="91" data-bgcolor="#6fa8dc" style="background: #6fa8dc; border-top: 2.25pt solid #000000; border-bottom: 1.50pt solid #000000; border-left: 2.25pt solid #000000; border-right: 2.25pt solid #000000; padding: 0.07in"><p><strong>SOL Column</strong></p></td>
</tr>
<tr data-valign="top">
<td width="83" height="19" style="border: 1.50pt solid #000000; padding: 0.07in"><p>January</p></td>
<td width="80" style="border: 1.50pt solid #000000; padding: 0.07in"><p>C</p></td>
<td width="91" style="border: 1.50pt solid #000000; padding: 0.07in"><p>D</p></td>
</tr>
<tr data-valign="top">
<td width="83" height="19" style="border: 1.50pt solid #000000; padding: 0.07in"><p>February</p></td>
<td width="80" style="border: 1.50pt solid #000000; padding: 0.07in"><p>E</p></td>
<td width="91" style="border: 1.50pt solid #000000; padding: 0.07in"><p>F</p></td>
</tr>
<tr data-valign="top">
<td width="83" height="19" style="border: 1.50pt solid #000000; padding: 0.07in"><p>March</p></td>
<td width="80" style="border: 1.50pt solid #000000; padding: 0.07in"><p>G</p></td>
<td width="91" style="border: 1.50pt solid #000000; padding: 0.07in"><p>H</p></td>
</tr>
<tr data-valign="top">
<td width="83" height="19" style="border-top: 1.50pt solid #000000; border-bottom: none; border-left: none; border-right: none; padding-top: 0.07in; padding-bottom: 0in; padding-left: 0in; padding-right: 0in"><p>..and so on.</p></td>
<td width="80" style="border-top: 1.50pt solid #000000; border-bottom: none; border-left: none; border-right: none; padding-top: 0.07in; padding-bottom: 0in; padding-left: 0in; padding-right: 0in"><p><br />
</p></td>
<td width="91" style="border-top: 1.50pt solid #000000; border-bottom: none; border-left: none; border-right: none; padding-top: 0.07in; padding-bottom: 0in; padding-left: 0in; padding-right: 0in"><p><br />
</p></td>
</tr>
</tbody>
</table>

### <span id="_wk5t4gx2fop6"></span> **6.3 Common Payment Rows (Examples)**

These are typical recurring items (the list may evolve based on DAO needs):

|  |  |  |
|----|----|----|
| **Item / Category** | **Example type** | **Entry method** |
| RPC Infrastructure (e.g., Shyft) | Infra/tool cost | Manual |
| Discourse subscription | Service | Manual |
| RenderForest (yearly) | Service | Manual (single month) |
| DAO Compliance Representative | Internal role | Manual |
| Symmetry Challenge Basket | Program cost | Manual |
| Discord Boost Rewards | Auxiliary reward stream | **Auto-linked** from REF: 20XX DISCORD BOOST |
| Proposal Architect Creation | Auxiliary reward stream | **Auto-linked** from REF: PROPOSAL ARCHITECT |

### <span id="_l6gr2wlxhswb"></span>  

### <span id="_90vn31x5geh1"></span> **6.4 Totals Row (Monthly Totals)**

A totals row contains SUM formulas to compute total USDC and SOL per month. These totals are often used in proposal summaries for transparency.

### <span id="_jjznjvky3u9c"></span> **6.5 Key Control: Don’t overwrite formulas**

Auto-linked rows must remain formula-driven (Discord Boost + Proposal Architect). Manual edits in those cells can silently break monthly totals.

### <span id="_shvndbwmx8dw"></span> **6.6 Monthly Maintenance Checklist (RECURRING PAYMENTS)**

- Verify each ongoing service is still active and priced correctly.  
    

- Confirm wallet addresses for vendors/recipients.  
    

- Confirm Discord boost totals pulled correctly for the month.  
    

- Confirm proposal architect totals pulled correctly for the month.  
    

- Confirm totals row matches the visible line items.  
    
    

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_y8wig8x07cjn"></span> **7. Recommended Update Cadence**

|  |  |  |
|----|----|----|
| **Frequency** | **What to update** | **Why** |
| Weekly / as proposals occur | REF: PROPOSAL ARCHITECT | Keeps SOL reimbursements current |
| Monthly (start of month) | REF: 20XX DISCORD BOOST | Captures active boosters accurately |
| Monthly (before proposal publication) | REF: 20XX RECURRING PAYMENTS | Ensures payment list is correct before execution |

  
  

  
  

  
  

  
  

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape8" />

## <span id="_13ms3ok8k324"></span> **8. Year Transition Procedure (End-of-Year)**

1.  Duplicate year-based sheets (e.g., REF: 2025 DISCORD BOOST → REF: 2026 DISCORD BOOST).  
      

2.  Duplicate REF: 2025 RECURRING PAYMENTS → REF: 2026 RECURRING PAYMENTS.  
      

3.  Update formula links in the new recurring payments tab to point to the **new year** tabs.  
      

4.  Archive old year tabs (keep them read-only for auditability).  
      

5.  Validate January totals in the new year before publishing the first proposal.  
      
      

<img src="assets/T17_ GREMS Maintenance_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape9" />

## <span id="_cvn56q9rz0xp"></span> **9. Glossary (Quick Reference)**

- **RECURRING PAYMENTS:** Monthly payment list artifact/proposal (ops costs + auxiliary rewards).  
    

- **REF: PROPOSAL ARCHITECT:** Proposal activity log → SOL reimbursements/bonuses.  
    

- **REF: 20XX DISCORD BOOST:** Boosters log → USDC booster rewards.  
    

- **Separation-of-artifacts control:** Recurring Payments is **not** merged into emissions rollup reporting/proposals.
