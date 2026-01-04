# <span id="_mqyx59joeum"></span> **T12: PROPOSAL ARCHITECT**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape1" />

## <span id="_ubkmhcd9b5ri"></span> ***1. Purpose***

*The* ***REF: PROPOSAL ARCHITECT*** *tab is the* ***master log*** *for tracking proposal-architect activity and calculating* ***SOL “rent” rewards*** *earned through proposal creation and execution work. It captures proposal metadata from* ***governance.so**, calculates a per-proposal SOL amount, and produces* ***monthly wallet totals*** *used to build the* ***RECURRING PAYMENTS*** *payout proposal.*

***It enables reviewers and operators to:***

- *Maintain a transparent, auditable record of DAO proposals  *
    

- *Attribute proposal work to* ***wallets + Discord names  ***
    

- *Calculate SOL rent consistently using DAO-defined constants  *
    

- *Produce monthly totals for payout proposals  *
    
    

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_a5kqmaaqtvma"></span> ***2. Scope and Controls***

***Control: Separation from emissions rollups  ***
*REF: PROPOSAL ARCHITECT is a* ***Recurring Payments source**. It* ***does not*** *roll into the* ***Emissions Results Interface*** *and* ***does not*** *affect Performance/Merit emissions rollup reporting.*

***Downstream usage***

- ***REF: PROPOSAL ARCHITECT → RECURRING PAYMENTS*** *(SOL refunds + rewards)  *
    
    

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_w0g33lqk7b"></span>  

## <span id="_1zrcm8y5atl9"></span> ***3. Inputs (Source of Truth)***

*All proposal records in Columns* ***A–I*** *are sourced from* [*<u>**governance.so**</u>*](http://governance.so/) *proposal pages:*

***Required fields captured per proposal***

- *Proposal title  *
    

- *Signed-off timestamp  *
    

- *End timestamp (used for month grouping)  *
    

- *Proposal URL  *
    

- *Author wallet  *
    

- *Discord name attribution  *
    

- *Instruction counts (Token Transfer + Grant Voting Power)  *
    
    

<img src="assets/T12_ PROPOSAL ARCHITECT_html_2064876c.png" id="image4.png" data-align="bottom" data-border="0" width="624" height="391" />

***Figure 1:*** *Where to copy proposal fields for Columns A–I (governance.so proposal details)*

  
  

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

## <span id="_na6mn0h0rlsb"></span> ***4. Tab Layout and Column Definitions***

### <span id="_zggk4wfa53s2"></span> ***4.1 Constants (Cells A2–B5)***

*This block defines the* ***unit costs*** *used to compute “rent” in SOL.*

|  |  |  |
|----|----|----|
| ***Cell*** | ***Parameter*** | ***Meaning*** |
| ***B2*** | *Proposal Creation Cost* | *SOL cost per proposal created* |
| ***B3*** | *Token Transfer Instruction Cost* | *SOL cost per token-transfer instruction* |
| ***B4*** | *Grant Voting Power Instruction Cost* | *SOL cost per grant-voting-power instruction* |
| ***B5*** | *Bonus SOL* | *Bonus multiplier applied later in the monthly totals section* |

***Control:*** *These constants are DAO-wide reward parameters. Update only when the DAO updates reward rules.*

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

### <span id="_io94udk16ync"></span> ***4.2 Proposal Log (Columns A–J)***

<img src="assets/T12_ PROPOSAL ARCHITECT_html_8635899d.png" id="image3.png" data-align="bottom" data-border="0" width="624" height="335" />

***Figure 2:*** *REF: PROPOSAL ARCHITECT tab after data is entered (proposal log view)*

  
  

  
  

*This is the main, row-by-row proposal ledger.*

|  |  |  |
|----|----|----|
| ***Column*** | ***Field*** | ***Meaning / How to Populate*** |
| ***A*** | *Proposal Title* | *Copy from governance.so proposal page* |
| ***B*** | *Signed Off At* | *Copy from* [*<u>governance.so</u>*](http://governance.so/) |
| ***C*** | *Ends At* | *Copy from* [*<u>governance.so</u>*](http://governance.so/) *(determines which month the proposal is counted in)* |
| ***D*** | *Proposal URL* | *Copy URL* |
| ***E*** | *Wallet* | *Author wallet address* |
| ***F*** | *Discord Name* | *Contributor attribution* |
| ***G*** | *Proposal Creation Count* | *Typically* ***1*** *per proposal row* |
| ***H*** | *Token Transfer Instructions* | *Count shown in proposal “Instructions” list* |
| ***I*** | *Grant Voting Power Instructions* | *Count shown in proposal “Instructions” list* |
| ***J*** | *Proposal Rent in SOL* | *Auto-calculated rent value* |

***Column J formula***

- *=(G8\*\$B\$2)+(H8\*\$B\$3)+(I8\*\$B\$4)*

*This computes* ***base rent*** *only. Bonus SOL is applied in the monthly totals summary.*

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

### <span id="_6uqp03c8htix"></span>  

### <span id="_wqu6yyyj1ix4"></span> ***4.3 Monthly Wallet Summary - RENT (Columns N–U)***

*This section aggregates proposal rent* ***per wallet / per month**.*

<img src="assets/T12_ PROPOSAL ARCHITECT_html_fef746ee.png" id="image2.png" data-align="bottom" data-border="0" width="624" height="353" />

**Figure 3:** “Proposal Rent TOTALS” monthly summary output (wallet totals)

  

|  |  |  |
|----|----|----|
| ***Column*** | ***Function*** | ***Meaning*** |
| ***N*** | *UNIQUE()* | *Unique wallets for the month’s proposal block* |
| ***O*** | *UNIQUE()* | *Discord names corresponding to wallets* |
| ***P*** | *SUMIF()* | *Base rent total (sum of Column J for that wallet)* |
| ***Q*** | *P + (S \* Bonus)* | *Base rent + bonus SOL* |
| ***R*** | *Q - P* | *Bonus portion only* |
| ***S*** | *SUMIF()* | *Proposal count total* |
| ***T*** | *SUMIF()* | *Token transfer instruction total* |
| ***U*** | *SUMIF()* | *Grant voting power instruction total* |

***Important maintenance note (range updates)  ***
*When you add a new month section, copy the formulas from a prior month and* ***update the referenced row ranges*** *so the* *SUMIF()* *and* *UNIQUE()* *logic reflects the correct month block. Incorrect ranges will produce incorrect totals.*

  

<img src="assets/T12_ PROPOSAL ARCHITECT_html_5296dfc1.png" id="image1.png" data-align="bottom" data-border="0" width="624" height="527" />

***Figure 4:*** *Where to find the “Instructions” count (token transfer vs grant voting power)*

  

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_de6bpuuav3yp"></span>  

## <span id="_iewl6qz4zllp"></span> ***5. Monthly Operating Procedure (Run Steps)***

1.  *Open the governance.so DAO page and list proposals for the target month.  *
      

2.  *For each proposal:  *
      

    - *Copy/paste* ***A–F*** *from the proposal page  *
        

    - *Set* ***G = 1*** *(standard)  *
        

    - *Count* ***H*** *(Token Transfer instructions) and* ***I*** *(Grant Voting Power instructions) from the proposal instructions list  *
        

3.  *Confirm Column* ***J*** *calculates automatically (base rent).  *
      

4.  *Group proposals into the correct month using* ***Ends At (Column C)**.  *
      

5.  *In Columns* ***N–U**, confirm the monthly totals populate correctly (and ranges are correct).  *
      

6.  *Use the monthly wallet totals as the source for the* ***RECURRING PAYMENTS*** *proposal build.  *
      
      

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape8" />

## <span id="_shzgfvqdbice"></span> ***6. Outputs and Downstream Usage***

***Primary output***

- *Monthly per-wallet SOL totals (Columns* ***P–Q**, plus supporting counts* ***S–U**)  *
    
    

***Used for***

- *Building the* ***RECURRING PAYMENTS*** *payout artifact (SOL refunds + rewards)  *
    
    

***Not used for***

- *Emissions Results Interface reporting  *
    

- *Performance/Merit emissions proposals  *
    

- *Governance Participation payouts  *
    
    

<img src="assets/T12_ PROPOSAL ARCHITECT_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape9" />

## <span id="_jsvp0sghat4b"></span> ***7. Quality Checks (Recommended)***

- ***Month alignment:*** *Ensure “Ends At” dates match the intended payout month grouping.  *
    

- ***Instruction counts:*** *Spot-check a few proposals against governance.so to confirm H/I are correct.  *
    

- ***Attribution:*** *Wallet + Discord name should match the author/contributor record.  *
    

- ***Totals sanity:*** *If a month seems unusually high/low, verify no proposals were missed and that formula ranges match the month block.*
