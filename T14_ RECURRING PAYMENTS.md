# <span id="_fc8gbqcowzv8"></span> **T14: RECURRING PAYMENTS**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" width="624" height="2" alt="Shape1" />

### <span id="_n581rj3bgg1x"></span> **1. Purpose**

The **REF: RECURRING PAYMENTS** tab is the DAO’s **monthly payment list** for operational expenses and recurring reward streams. It aggregates **USDC and SOL** amounts that are paid on a recurring cadence and supports monthly proposal creation by providing a clear, auditable breakdown of:

- What is being paid (service/tool/role)  
    

- Who is being paid (recipient wallet)  
    

- How much is being paid each month (USDC + SOL)  
    

- Monthly totals used in proposal summaries (GIST / public reporting)  
    
    

**Control:** This tab is a **Recurring Payments artifact**. It is separate from the **Emissions Results Interface** rollups and does not include performance/merit emissions totals.

<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

### <span id="_hmxd8bp25lg4"></span> **2. What This Tab Includes**

Recurring payments typically include:

- **Operational tools / infrastructure** (subscriptions or services)  
    

- **Standing reimbursements or fixed operating costs** (where approved)  
    

- **Monthly add-on reward streams** that are paid outside emissions rollups, such as:  
    

  - **Discord Boost rewards  **
      

  - **Proposal Architect rent/refunds + rewards  **
      
      

<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

### <span id="_fu283c9k15o1"></span> **3. Tab Layout and Structure**

#### <span id="_oycuaedav29l"></span> **3.1 Columns A–B: Payment Entries and Recipient Wallets**

|  |  |  |
|----|----|----|
| **Column** | **Field** | **Meaning** |
| A | Item / Service Description | A short label describing what is being paid (example: “RPC Infrastructure – Shyft”) |
| B | Wallet | Recipient wallet address for the payment |

#### <span id="_nd6s2fekykuh"></span> **3.2 Standard Recurring Line Items (Rows A7+)**

The tab maintains a consistent set of recurring rows. Typical entries include:

- RPC Infrastructure – Shyft  
    

- Discord Boost Rewards for Contributors  
    

- Discourse – Standard Monthly Plan  
    

- Render Forest – Yearly Plan (Nov 2024 – Nov 2025) *(recorded in the month(s) it is paid or allocated, per DAO practice)  *
    

- DAO Compliance Representative *(if applicable)  *
    

- Symmetry Challenge Basket *(if applicable)  *
    

- Proposal Architect Creation

<img src="assets/T14_ RECURRING PAYMENTS_html_eb5aa1e3.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="239" />

**Figure 1.** *REF: 2025 RECURRING PAYMENTS (Monthly + Yearly payment grid, USDC/SOL)*<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

### <span id="_3j7azx4pnwn7"></span> **4. Monthly Payment Columns (USDC + SOL)**

Each month is represented by **two adjacent columns**:

- **USDC** amount for the month  
    

- **SOL** amount for the month  
    
    

Example mapping (typical pattern):

- **January** = Columns **C–D  **
    

- **February** = Columns **E–F  **
    

- …continuing through the year in repeating USDC/SOL pairs.  
    
    

<img src="assets/T14_ RECURRING PAYMENTS_html_a77bcc03.png" id="image1.png" data-align="bottom" data-border="0" width="645" height="370" />

**Figure 2**. *REF: 2025 RECURRING PAYMENTS — Example Month View (January-February)*

<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

### <span id="_lqluutim4259"></span> **5. Data Entry and Update Method**

Recurring payments are populated using **two methods**, depending on the item type:

#### <span id="_7no7pap9ekyk"></span> **5.1 Manual Entries (Fixed Costs / Known Amounts)**

Some payments are entered directly because they are fixed, invoice-based, or otherwise known:

- RPC Infrastructure – Shyft  
    

- Discourse – Standard Monthly Plan  
    

- Render Forest – Yearly Plan (Nov 2024 – Nov 2025)  
    

- DAO Compliance Representative (if applicable)  
    

- Symmetry Challenge Basket (if applicable)  
    
    

**Operator rule:** Enter the correct **wallet (Column B)** and the month amount in the appropriate **USDC/SOL month columns**.

#### <span id="_h1dizx5ck55z"></span> **5.2 Auto-Imported Entries (Linked Reward Streams)**

Other rows are formula-linked to their source tabs so they update automatically:

- **Discord Boost Rewards for Contributors** → sourced from **REF: DISCORD BOOST  **
    

- **Proposal Architect Creation** → sourced from **REF: PROPOSAL ARCHITECT  **
    
    

**Control:** Do not overwrite cells that contain import formulas.

<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

### <span id="_tiqa2bl4s5ho"></span> **6. Monthly Totals (Row Totals for Proposals)**

A totals row (commonly near the bottom, e.g., “TOTAL USDC & Solana”) contains **SUM formulas** for each month that calculate:

- Total monthly **USDC** spend  
    

- Total monthly **SOL** spend  
    
    

These totals are commonly copied into proposal summaries (GIST tables) for transparent reporting.

<img src="assets/T14_ RECURRING PAYMENTS_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

### <span id="_vpwctiv4ck0j"></span>  

### <span id="_sqpqp5dcdas7"></span> **7. Operating Controls and Review Checklist**

Before publishing a Recurring Payments proposal:

- Confirm all **manual line items** have the correct wallet and correct month amounts.  
    

- Confirm **auto-imported rows** (Discord Boost + Proposal Architect) are syncing and populating correctly.  
    

- Confirm monthly **USDC/SOL totals** match expectations for the cycle.  
    

- Ensure this tab is used only for **Recurring Payments** and is not mixed with emissions rollup reporting.

  
  

  
  
