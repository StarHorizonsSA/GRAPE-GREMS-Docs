# <span id="_fc8gbqcowzv8"></span> **T13: DISCORD BOOST**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" width="624" height="2" alt="Shape1" />

### <span id="_ik5hvnbyz7k6"></span> **1. Purpose**

The **REF: 2025 DISCORD BOOST** tab tracks **monthly Discord Server Boost** activity by GRAPE DAO community members. It links each booster to a **Discord ID** and **wallet address**, records the **number of boosts per month**, and automatically calculates **USDC rewards** using a fixed **reward-per-boost** constant (currently **\$5.00 per boost**).

This tab exists to produce a **payout-ready reference** for the **RECURRING PAYMENTS** proposal stream (Discord Boost rewards).

**Control (separation of artifacts):**

- **REF: 2025 DISCORD BOOST → RECURRING PAYMENTS** (monthly payment list).  
    

- It does **not** roll into the **Emissions Results Interface** and does **not** include governance participation (VINE).  
    
    

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

### <span id="_hvjl3jgs72gy"></span> **2. Where This Tab Fits in GREMS**

**Data source:** Discord “Server Boost Status” (manual observation).  
**Output usage:** Monthly totals are used to create a **RECURRING PAYMENTS** proposal that pays **USDC boost rewards**.

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

### <span id="_aop3s7f3ltwn"></span> **3. Tab Structure**

  

#### <span id="_ojfxab8gahi6"></span> **3.1 Booster Identity Columns (A–C)**

These columns identify each booster:

- **Column A — Discord Name  **
    

- **Column B — Discord ID  **
    

- **Column C — Wallet Address**

<img src="assets/T13_ DISCORD BOOST_html_260f6d0.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="227" />

***Figure 1*** *— Full screenshot of REF: 2025 DISCORD BOOST*

**Data entry rule:** This identity block is maintained from verified booster records. Wallets should match the canonical roster where possible (GRAPE MEMBERS).

#### <span id="_rm4hwqeuzwj6"></span> **3.2 Monthly Boost Tracking (D–AA)**

The sheet tracks boosts across **January–December**. Each month typically uses **two columns**:

- **Month: \# of Boosts  **
    

- **Month: Rewards (\$)**

**Reward calculation:  **
Rewards are computed as:  
**Rewards = Boosts × RewardPerBoost  **
Where **RewardPerBoost** is stored as a constant (e.g., **\$5.00**) in the sheet.

<img src="assets/T13_ DISCORD BOOST_html_f2a91e5a.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="229" />

***Figure 2*** *— Closeup look (Boost Amount, identity columns, and monthly fields)*

  
  

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

### <span id="_9b439b6ny3n"></span> **4. Boost Logging Process (Monthly Update)**

1.  In Discord, open:  
    **GRAPE Server → Server Settings → Server Boost Status  **
      

2.  Read the list of boosters and record/update for the current month:  
      

    - Discord Name  
        

    - Discord ID  
        

    - Wallet Address  
        

    - **Number of boosts** for the month  
        

3.  Confirm the reward-per-boost constant is correct (e.g., **\$5.00**).  
      

4.  Confirm the month’s reward column auto-calculates.

<img src="assets/T13_ DISCORD BOOST_html_58394a04.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="355" />

**Figure 3** — *Screenshot from Discord (Server Boost Status source)*  
  
  

**Best practice:** If a booster changes their Discord name, keep the **Discord ID** as the stable identifier and update the display name accordingly.

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

### <span id="_adu9r93x448b"></span>  

### <span id="_kq9a4y7bhxvn"></span> **5. GIST Export Workflow (For Proposal Presentation)**

To generate the clean “execution-ready” list used for proposal support materials:

1.  Copy the **current month** range containing **Wallet + Rewards**.  
      

2.  Paste into a dedicated GIST tab for that month (example naming pattern):  
    **TAB: 20XX GIST-PDF: \<Month\>  **
      

3.  **Paste values only** (to avoid linking formulas into the GIST export).  
      

4.  Verify totals match expected monthly sum before exporting.  
      

5.  Export the GIST tab as a PDF for the proposal package.

<img src="assets/T13_ DISCORD BOOST_html_2d01f7a0.png" id="image4.png" data-align="bottom" data-border="0" width="555" height="571" />

**Figure 4** *— For GIST usage (paste values only instructions)*

**Control:** The GIST tab is for presentation/execution formatting only—source-of-truth remains **REF: DISCORD BOOST**.

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

### <span id="_1dfllqncugq0"></span> **6. Controls and Validation Checks**

Use these checks before publishing a RECURRING PAYMENTS proposal:

- **Wallet completeness:** every paid line must have a valid wallet address.  
    

- **Non-zero filter:** ensure only members with non-zero rewards appear in the month’s payout list (unless explicitly required for reporting).  
    

- **Reward constant check:** confirm the boost reward value (e.g., \$5.00) has not changed.  
    

- **Discord proof:** retain a screenshot or reference capture of the month’s “Server Boost Status” view for auditability.  
    
    

<img src="assets/T13_ DISCORD BOOST_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

### <span id="_yam3vpzam1zl"></span> **7. Output Summary**

**Result:** This tab produces a month-by-month, wallet-mapped view of Discord boosting rewards so the DAO can publish a **RECURRING PAYMENTS** proposal paying **USDC** to boosters with transparent, auditable support.

  
  
