# <span id="_qu46oa6rp573"></span> **T4: Troubleshooting Checklist**

**GRAPE Rewards & Emissions Management System (GREMS)  **
Version 1.0 \| Last Updated: 2025-12-30

Rewarding contributions, participation, and impact across the GRAPE DAO

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape1" data-align="bottom" data-vspace="7" width="624" height="2" alt="Shape1" />

  
  

1.  ## <span id="_d5ae6od2gjf6"></span> **Purpose**

Use this checklist to confirm that **wallet addresses, eligibility, reward totals, categories, and token types** are correct before publishing a draft payout proposal/artifact.

  
  

2.  ## <span id="_9mribzt3acw9"></span> **Scope**

**  **
This checklist supports GREMS’ four payout paths:

1.  **RECURRING PAYMENTS (Monthly)** — USDC / SOL via **REF: PROPOSAL ARCHITECT, REF: DISCORD BOOST,** and infrastructure/tool costs**)**

2.  **EMISSIONS RESULTS - Performance (Monthly)**— GRAPE / USDC / SOL **(REF: GUBA and REF: PERFORM)  **
      

3.  **EMISSIONS RESULTS - Merit (Period)** — GRAPE / USDC via **REF: MERIT** and **REF: GUBA MERIT  **
      

4.  **Governance Participation (Standalone)** — VINE + GRAPE (+ possible prizes) via **GOVERNMENT PARTICIPATION REWARDS (VINE Rewards and GOV PARTICIPATION sheets)** *(separate from emissions rollups)  *
      
      

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape2" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape2" />

## <span id="_ng6b1gwwpria"></span> **3. Quick Validation (10 Bullets)**

Use this as a fast pass/fail before you review details.

1.  **Correct payout path selected:** Performance (Monthly) vs Merit (Period) vs Governance Participation (Standalone).  
      

2.  **Correct source sheet(s):** Monthly uses **RECURRING PAYMENTS and EMISSIONS RESULTS**; Merit uses **REF: MERIT + REF: GUBA MERIT**; Governance Participation uses **GOVERNMENT PARTICIPATION REWARDS** **(VINE Rewards and GOV PARTICIPATION sheets)**  
      

3.  **Roster check:** Every recipient wallet/identifier maps correctly through **GRAPE MEMBERS**.  
      

4.  **Eligibility check:** Governance Participation recipients are validated via **GOV PARTICIPATION** outputs (not direct attendance/VINE inputs).  
      

5.  **No manual edits:** Amounts are copied exactly from sheet outputs—no overrides.  
      

6.  **No missing recipients:** Everyone who earned rewards appears; no one is omitted due to filtering or sorting.  
      

7.  **No extra recipients:** No wallets appear that are not present in the relevant sheet outputs.  
      

8.  **Category alignment (Performance/Merit):** Member payouts match the category work recorded in the relevant **SCORE** sheet version.  
      

9.  **Token hygiene:** Only the token types appropriate to the payout path are included (do not mix VINE into emissions rollups).  
      

10. **Totals match the source-of-truth:** Proposal totals equal the sheet totals for that payout path; labels/date ranges match the cycle being paid.  
      
      

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape3" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape3" />

## <span id="_sfavacpq4cbb"></span> **4. Confirm You Are Using the Correct Payout Path**

Before drafting anything on governance.so, confirm your draft matches the correct GREMS pipeline and source sheet(s).

**Checklist Question  **
Does the draft proposal/artifact match the correct GREMS payout path **based on the sheet outputs you are using**?

### <span id="_9yculwcl9r2b"></span> **A. Performance (Monthly) — Source of Truth:** **RECURRING PAYMENTS (REF: PROPOSAL ARCHITECT, REF: DISCORD BOOST, and infrastructure costs) & EMISSIONS RESULTS - Performance (REF: GUBA and REF: PERFORM)**

- **What gets paid:** Monthly GRAPE / USDC / SOL (including add-ons)  
    

- **Use these sources for EMISSIONS RESULTS - Performance:  **
    

  - **REF: PERFORM** (GRAPE totals)  
      

  - **REF: GUBA** (USDC + SOL totals)

<!-- -->

- **Use these sources for RECURRING PAYMENTS:**  
    

<!-- -->

- - **REF: PROPOSAL ARCHITECT** (SOL refunds + rewards, if applicable)  
      

  - **REF: DISCORD BOOST** (USDC rewards, if applicable)

  - Add infrastructure, Content Tools costs  
      

- **RECURRING PAYMENTS and EMISSIONS RESULTS - Performance** are not consolidated. Each is handled with a separate proposal.**  **
    
    

**Rule:** If it’s a monthly payout, the proposal should align with the appropriate sheet as described above.

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape4" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape4" />

### <span id="_73d4keendh9n"></span> **B. Merit (Period) — Source of Truth: REF Totals + Period Rollup**

- **What gets paid:** Merit-period GRAPE + USDC (in this system design)  
    

- **Use these sources:  **
    

  - **REF: MERIT** (GRAPE totals)  
      

  - **REF: GUBA MERIT** (USDC totals)  
      

- **Period reporting:** **EMISSIONS RESULTS - Merit (Period Rollup)** derives from these REF totals as shown in the list above.  
    
    

**Rule:** Merit payout drafts should match **REF: MERIT + REF: GUBA MERIT** totals exactly.

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape5" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape5" />

### <span id="_8sze3yb4pby4"></span> **C. Governance Participation (Standalone) — Separate Artifact**

- **What gets paid:** Governance participation outcomes, including VINE and GRAPE (and possibly prizes through raffles)  
    

- **Use these sources:  **
    

  - **GOV PARTICIPATION** sheets (eligibility/voting/calls/raffles)  
      

  - **VINE Rewards** sheet (derived from GOV PARTICIPATION)  
      

- **Standalone payout artifact:** **GOVERNMENT PARTICIPATION REWARDS  **
    
    

**Rule:** Governance Participation payouts **do not roll into EMISSIONS RESULTS**.

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape6" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape6" />

## <span id="_qc6a1zsamhc3"></span> **5. Confirm Eligible Participants (Identity + Eligibility)**

**Checklist Question  **
Is every wallet address listed in the draft artifact present in **GRAPE MEMBERS** and valid for the specific reward path?

### <span id="_5l3b14yd91vt"></span> **Identity source of truth**

- **GRAPE MEMBERS (member roster/identifiers)** is the canonical mapping layer.  
    

- Any payout list should match roster identifiers and payout fields.  
    
    

### <span id="_dghu58occa60"></span> **Eligibility validation by pipeline**

**Governance Participation (Standalone)**

- Validate using **GOV PARTICIPATION** outputs (derived from participation inputs)  
    

- Confirm the member’s status and statistics for:  
    

  - Eligibility to receive rewards  
      

  - Number of times voting

  - Calls attended

  - Raffles won

**Performance (Monthly)**

- Validate that contributors appear in:  
    

  - **SCORE: PERFORM & GUBA EMIT** (monthly scoring input/output)  
      

  - AND the corresponding **REF totals** that feed **RECURRING PAYMENTS**  
      
      

**Merit (Period)**

- Validate that recipients appear in:  
    

  - **SCORE: MERIT EMIT & GUBA MERIT  **
      

  - **REF: MERIT** and/or **REF: GUBA MERIT  **
      
      

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape7" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape7" />

## <span id="_7o7t7zg7q0qm"></span> **6. Verify Reward Amounts (No Manual Overrides)**

**Checklist Question  **
Do all reward amounts in the draft match the computed values in the correct sheet outputs **with zero manual edits**?

**Confirm the following:**

- Budget pools per category were updated/confirmed for the cycle.  
    

- No wallet is missing from the payout list.  
    

- No extra wallets were added outside the validated sheet outputs.  
    

- Totals match the sheet totals exactly.

**Rule:** Draft proposals must be **sheet-derived**, not edited by hand.

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape8" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape8" />

## <span id="_a5vkjeyjpeg"></span> **7. Confirm Category Mapping (Performance & Merit Only)**

**Checklist Question  **
Does each member’s payout correspond to the category of work actually recorded in the scoring sheet?

**Performance (Monthly)**

- Confirm the member has a performance level recorded in **SCORE: PERFORM & GUBA EMIT** for the relevant category.  
    
    

**Merit (Period)**

- Confirm the member has a merit scoring entry in **SCORE: MERIT EMIT & GUBA MERIT** for the relevant category.  
    
    

**Rule:** Participation categories (attendance/voting/raffles) belong to **Governance Participation**, not Performance/Merit.

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape9" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape9" />

## <span id="_k77d8nob7c80"></span> **8. Validate Token Type and Purpose (Do Not Mix)**

**Checklist Question  **
Does this draft contain only the token types for this payout path?

### <span id="_38fo4voz8f0f"></span> **Token usage guide (GREMS-aligned)**

- **VINE  **
    

  - Governance Participation outcomes only  
      

  - Derived from **GOV PARTICIPATION → VINE Rewards  **
      

- **GRAPE  **
    

  - Performance GRAPE totals (monthly) and Merit GRAPE totals (period)  
      

- **USDC + SOL  **
    

  - Performance monthly outputs (where configured)  
      

  - Proposal Architect SOL refunds + rewards (monthly add-on stream)  
      

  - Discord Boost USDC (monthly add-on stream)  
      

- **Other tokens (BONK, JUP, ME, NFTs, etc.)  **
    

  - Only when explicitly included as a DAO-defined bonus or raffle prize and represented in the approved payout artifact  
      
      

**Rule:** Don’t combine Governance Participation (VINE) with monthly emissions rollup logic.

<img src="assets/T4_ Troubleshooting Checklist_html_ddc2c6d4.gif" id="Shape10" data-align="bottom" data-vspace="8" width="624" height="2" alt="Shape10" />

## <span id="_7ldi0du3nwf3"></span> **9. Final Pre-Publish Checks (Totals + Period Labeling)**

**Checklist Question  **
Do the totals, date ranges, and labels match the cycle being paid?

### <span id="_f8wsw5ewi2aw"></span> **For Performance (Monthly)**

- Title matches the correct month + payout type.  
    

- Amounts match **RECURRING PAYMENTS.  **
    

- If reporting is included, confirm **EMISSIONS RESULTS (Monthly Rollup)** and **RECURRING PAYMENTS** totals align with corresponding sheets. Handle each separately.  
    
    

### <span id="_wz9ba4und45a"></span> **For Merit (Period)**

- Title matches the correct merit period.  
    

- Amounts match **REF: MERIT + REF: GUBA MERIT  **
    

- Period rollup (if referenced) matches **EMISSIONS RESULTS (Period Rollup)  **
    
    

### <span id="_kk5yoxmbtxbf"></span> **For Governance Participation (Standalone)**

- Title matches the governance participation window (cycle/date range)  
    

- Amounts match **GOVERNMENT PARTICIPATION REWARDS.  **
    

- Confirm you are **not** attempting to reconcile this to EMISSIONS RESULTS (because it’s standalone)  
    
    

## <span id="_99elhwno29g"></span> **Final Rule (Non-Negotiable)**

**If the spreadsheet does not show it, the proposal must not include it.  **
All rewards must be based on **sheet-validated data**, not assumptions, memory, or manual edits.

  
  
