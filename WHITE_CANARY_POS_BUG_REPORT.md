**WHITE CANARY POS**

**Professional QA Bug & Issue Report**

Source: GitHub issue export (37 issues)

| **Repository**          | Excel-Technologies-Ltd / white-canary-POS                                                         |
|-------------------------|---------------------------------------------------------------------------------------------------|
| **Source file**         | white-canary-all-issues.json                                                                      |
| **Issues reviewed**     | 37                                                                                                |
| **Report basis**        | Issue bodies, comments, labels, assignees, states, and checklist status                           |
| **Assessment approach** | Source-grounded normalization; QA risk/priority are explicitly marked as inferred recommendations |

*Prepared for SQA review, regression planning, defect triage, and release-readiness tracking.*

# 1. Executive Summary

**This audit reviewed 37 GitHub issues: 8 open and 29 closed.** Across issue bodies and comments, 777 checklist items are marked complete and 245 remain unchecked. 16 closed issues still contain one or more unchecked items, which creates a traceability/closure risk and should be reconciled during regression or release-readiness review.

**Important scope note:** Many GitHub issues are omnibus work items that combine defects, enhancements, requirements, UI corrections, backend tasks, and validation notes. This report preserves that source structure instead of inventing separate GitHub bug IDs. QA severity and priority are recommendations inferred from impact keywords and issue state; the product owner/team should confirm them.

| **Issue** | **Title**                                                                  | **GitHub State** | **Checked** | **Unchecked** | **QA Classification**                            |
|-----------|----------------------------------------------------------------------------|------------------|-------------|---------------|--------------------------------------------------|
| \#73      | Corrections \> 23-09-2026                                                  | OPEN             | 3           | 0             | Mixed QA Defect / Correction Backlog             |
| \#72      | Corrections- 20/09/2026                                                    | CLOSED           | 3           | 0             | Mixed QA Defect / Correction Backlog             |
| \#71      | Desktop Corrections \> 10-09-2026                                          | CLOSED           | 7           | 0             | Mixed QA Defect / Correction Backlog             |
| \#70      | Corrections \> 07-09-2026                                                  | CLOSED           | 25          | 3             | Mixed QA Defect / Correction Backlog             |
| \#69      | Corrections \> 30-08-2026                                                  | CLOSED           | 13          | 0             | Mixed QA Defect / Correction Backlog             |
| \#68      | Desktop Corrections \> 18-08-2026                                          | CLOSED           | 27          | 0             | Bug / Defect                                     |
| \#67      | Corrections \> 10-08-2026                                                  | CLOSED           | 79          | 26            | Mixed QA Defect / Correction Backlog             |
| \#66      | Corrections \> 04-08-2026                                                  | CLOSED           | 21          | 0             | Mixed QA Defect / Correction Backlog             |
| \#65      | POS Web \> Corrections 29-07-2026                                          | CLOSED           | 2           | 0             | Mixed QA Defect / Correction Backlog             |
| \#64      | Backend Issue \> 25-07-2026                                                | CLOSED           | 13          | 6             | Mixed QA Work Item                               |
| \#63      | Desktop Pending Corrections- 15-07-2026                                    | CLOSED           | 16          | 0             | Mixed: Bug + Enhancement                         |
| \#62      | Desktop Application Issues- 01/07/2026                                     | CLOSED           | 3           | 0             | Bug / Defect                                     |
| \#61      | Epson TM-T81III Printer and QZ Tray Cash Drawer Setup Guide for Windows 11 | OPEN             | 0           | 0             | Documentation / Operational Setup                |
| \#60      | POS WEB \> 14-06-2026                                                      | CLOSED           | 6           | 1             | Mixed QA Work Item                               |
| \#59      | Desktop \> 08-06-2026                                                      | CLOSED           | 30          | 2             | Mixed QA Work Item                               |
| \#58      | Requirement of 04-06-2026                                                  | CLOSED           | 35          | 0             | Functional Requirement / Enhancement             |
| \#57      | POS- WEB Ordering Process - 7th June                                       | OPEN             | 47          | 8             | Bug / Defect                                     |
| \#53      | Desktop \> 23-05-2026                                                      | CLOSED           | 13          | 0             | Mixed QA Work Item                               |
| \#52      | POS Web \> 21-05-2026                                                      | CLOSED           | 80          | 53            | Mixed QA Work Item                               |
| \#51      | Desktop - 18-05-2026                                                       | CLOSED           | 6           | 1             | Mixed QA Work Item                               |
| \#50      | POS - Desktop - 14-05-2026                                                 | OPEN             | 10          | 1             | Mixed QA Work Item                               |
| \#49      | POS- Desktop Issues- After 11th May                                        | CLOSED           | 17          | 0             | Mixed: Bug + Enhancement                         |
| \#48      | Order Split Functionality                                                  | CLOSED           | 0           | 7             | Functional Requirement / Enhancement             |
| \#47      | POS WEB MODIFICATIONS- After 5th May                                       | CLOSED           | 39          | 2             | Mixed: Bug + Enhancement                         |
| \#46      | Backend Issues - After 06-05-2026                                          | OPEN             | 74          | 22            | Mixed: Bug + Enhancement                         |
| \#45      | Meeting Topics 05-05-2026                                                  | CLOSED           | 0           | 9             | Mixed: defect, requirement, and decision backlog |
| \#42      | POS- Desktop Issues- After 5th May                                         | CLOSED           | 48          | 3             | Mixed: Bug + Enhancement                         |
| \#40      | Cash Opening/Closing Feature - WC                                          | OPEN             | 0           | 26            | Functional Requirement / Enhancement             |
| \#32      | BACKEND PENDING ISSUES- POS WEB AND DESKTOP- 29th April                    | CLOSED           | 5           | 1             | Bug / Defect                                     |
| \#30      | Meeting Topics April 22, 2026                                              | CLOSED           | 18          | 4             | Mixed: defect, requirement, and decision backlog |
| \#18      | POS WEB MODIFICATIONS- After 19th April                                    | CLOSED           | 44          | 5             | Mixed QA Defect / Correction Backlog             |
| \#14      | Desktop Modifications- After 16th April                                    | CLOSED           | 42          | 1             | Mixed QA Defect / Correction Backlog             |
| \#12      | Corrections \#2 \> POS Web                                                 | CLOSED           | 4           | 0             | Mixed QA Defect / Correction Backlog             |
| \#10      | Corrections \#1 \> Desktop                                                 | CLOSED           | 14          | 2             | Mixed QA Defect / Correction Backlog             |
| \#8       | Features and Functionality - Internal                                      | OPEN             | 0           | 20            | Functional Requirement / Enhancement             |
| \#7       | Functionality 1                                                            | OPEN             | 0           | 42            | Functional Requirement / Enhancement             |
| \#6       | WC - Web - 09-04-2026                                                      | CLOSED           | 33          | 0             | Mixed: Bug + Enhancement                         |

# 2. QA Normalization Method

• Source statements were preserved as the authoritative basis. Where the source does not provide an exact reproduction path, environment, build number, or confirmed root cause, the report does not invent one.

• Checked checklist items are treated as reported complete, not independently verified by this review. Unchecked items are treated as pending/open within the source, regardless of the overall GitHub issue state.

• Issue-level risk and priority values are QA-inferred recommendations based on operational impact (payments, order state, permissions, stock, synchronization, cash controls, printing/reporting, and UI).

• Evidence references in the source (screenshots, attachments, spreadsheets, and linked comments) are noted but not re-hosted in this document.

# 3. GitHub Issue \#73: Corrections \> 23-09-2026

| **GitHub State**     | OPEN                                                 | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|------------------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                           | **Labels**               | None                                 |
| **Checklist Status** | 3 checked / 0 unchecked                              | **Evidence refs**        | 0                                    |
| **QA Risk**          | Medium-High (QA-inferred; verify with product owner) | **Recommended Priority** | P2 (recommended; verify with team)   |
| **Created**          | 2026-09-23                                           | **Last Updated**         | 2026-09-23                           |

## Professional Summary

GitHub issue \#73 is a mixed qa defect / correction backlog covering POS WEB, Stock Requisition. The source issue is currently open and contains 3 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments. All explicit checklist items are checked even though the GitHub issue remains open, so the remaining closure criteria should be confirmed.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/73</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/73)

## Affected Modules / Areas

POS WEB, Stock Requisition

## Source-Derived Actual / Observed Behavior Indicators

• When Allowing "Submit" button to the Creator, The "Edit" button is missing.

## Source-Derived Expected / Required Behavior Indicators

• Rename the "Create" button to "Save"

• When Allowing "Approve" button to the Approver, The "Edit" button will enabled/show (Check)

• I will add here new if found.............

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments. **The issue remains OPEN, so closure criteria/status should still be confirmed.**

## Completed Scope Highlights (reported in source)

✓ Rename the "Create" button to "Save"

✓ When Allowing "Submit" button to the Creator, The "Edit" button is missing.

✓ When Allowing "Approve" button to the Approver, The "Edit" button will enabled/show (Check)

## QA Impact & Retest Guidance

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 4. GitHub Issue \#72: Corrections- 20/09/2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | binshahed, dev-Anamul                         | **Labels**               | None                                 |
| **Checklist Status** | 3 checked / 0 unchecked                       | **Evidence refs**        | 0                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-09-20                                    | **Last Updated**         | 2026-09-24                           |

## Professional Summary

GitHub issue \#72 is a mixed qa defect / correction backlog covering Frontend, Backend. The source issue is currently closed and contains 3 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/72</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/72)

## Affected Modules / Areas

Frontend, Backend

## Source-Derived Actual / Observed Behavior Indicators

• For partial discount orders with a 0% discount customer, save the order as a Draft, then change the customer to one with a discount. After the first validation error occurs, the discount percentage resets back to 0%.

• For partial discount orders, when a discounted customer is selected, the following error is displayed: “No permission for discount on Sales Invoice. Ask a manager to enter their PIN for this action.”

• For partial discount orders, select a discounted customer and save the order as a Draft. Then change the customer to another discounted customer. An error is displayed, but if another SD + Discount item is added afterward, the invoice is updated according to the newly selected customer's discount.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ For partial discount orders with a 0% discount customer, save the order as a Draft, then change the customer to one with a discount. After the first validation error occurs, the discount percentage resets back to 0%.

✓ For partial discount orders, when a discounted customer is selected, the following error is displayed: “No permission for discount on Sales Invoice. Ask a manager to enter their PIN for this action.”

✓ For partial discount orders, select a discounted customer and save the order as a Draft. Then change the customer to another discounted customer. An error is displayed, but if another SD + Discount item is added afterward, the invoice is updated according to the newly selected customer's discount.

## QA Impact & Retest Guidance

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 5. GitHub Issue \#71: Desktop Corrections \> 10-09-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | None                                 |
| **Checklist Status** | 7 checked / 0 unchecked                       | **Evidence refs**        | 8                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-09-14                                    | **Last Updated**         | 2026-09-24                           |

## Professional Summary

GitHub issue \#71 is a mixed qa defect / correction backlog covering Print View, Other corrections (17-08-2026), OFFLINE Order (New/Draft), Order Details. The source issue is currently closed and contains 7 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/71</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/71)

## Affected Modules / Areas

Print View, Other corrections (17-08-2026), OFFLINE Order (New/Draft), Order Details

## Source-Derived Actual / Observed Behavior Indicators

• Payment breakdown data missing in the Receipt Print.

• Description: When an online order containing PIN-restricted fields (such as Item Issue or Discount) fails to sync due to an expired PIN session, the error message instructs the user to start a PIN session.

• Requirement: Add a direct "Enter PIN" action button within trigger sync or On click Individual "Sync" button should appear PIN modal for this type of error orders.

• - Issue 2: UI Item Disappearance on Sync Error

• Description: If a sync error occurs while staying inside the active Order view, certain items temporarily disappear from the UI. However, navigating away and re-entering the Order restores and correctly displays all items.

## Source-Derived Expected / Required Behavior Indicators

• Make the Print View (font) as like the "Swapno" print font. The fonts should be clear to see after print.

• In Any kinds of update in the Territory from frappe doctype, and evenif the Territory Counter's Last Status = Open, It's forcing to Clock-IN where should allow to Clock-OUT.

• Requirement: Add a direct "Enter PIN" action button within trigger sync or On click Individual "Sync" button should appear PIN modal for this type of error orders.

• The "Payment Information" data should fetch:

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ Make the Print View (font) as like the "Swapno" print font. The fonts should be clear to see after print.

✓ Payment breakdown data missing in the Receipt Print.

✓ In Any kinds of update in the Territory from frappe doctype, and evenif the Territory Counter's Last Status = Open, It's forcing to Clock-IN where should allow to Clock-OUT.

✓ Description: When an online order containing PIN-restricted fields (such as Item Issue or Discount) fails to sync due to an expired PIN session, the error message instructs the user to start a PIN session.

✓ Requirement: Add a direct "Enter PIN" action button within trigger sync or On click Individual "Sync" button should appear PIN modal for this type of error orders.

✓ Description: If a sync error occurs while staying inside the active Order view, certain items temporarily disappear from the UI. However, navigating away and re-entering the Order restores and correctly displays all items.

✓ The "Payment Information" data should fetch:

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 6. GitHub Issue \#70: Corrections \> 07-09-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 25 checked / 3 unchecked                      | **Evidence refs**        | 4                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-09-07                                    | **Last Updated**         | 2026-09-24                           |

## Professional Summary

GitHub issue \#70 is a mixed qa defect / correction backlog covering Backend, Frappe ERP, Validate Stock, Payment Error, BOM \> Update Cost button. The source issue is currently closed and contains 25 checked/completed checklist item(s) and 3 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 3 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/70</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/70)

## Affected Modules / Areas

Backend, Frappe ERP, Validate Stock, Payment Error, BOM \> Update Cost button, ArcPOS Settings \> Permissions, WEB, Stock Requisition + Stock Transfer & Wastage Management, Stock Requisition, Outlet change, Order List page, Recipe

## Source-Derived Actual / Observed Behavior Indicators

• - Validate the "Source Warehouse" item wise current stock. if entered Transfer qty is greater then the current stock then throw error.

• \### Payment Error

• - https://wcpos.arcapps.org/app/error-log/106806 \[But payment entry creates\]

• - https://wcpos.arcapps.org/app/error-log/99357 \[Payment entry not created\]

• When trying to force "Update Cost" manually, showing this error \`exc_type

• "PermissionError"

## Source-Derived Expected / Required Behavior Indicators

• Add new Check field \`Allow Update UOM?" under existing field "Allowed Production?"

• Add new Check field \`Validate Stock?" under existing field "Allow Update UOM?"

• Add new Check field \`Is Sales Outlet?" under existing field "Is Group".

• Add new Multi-Select (User) field POS Approvers" under existing field "Order Pay Default" + Combined Approver\` (Auto fetch from "POS Approvers" COMMA separated) to use them to send emails.

• Add new "Section Break" under items

• Add new Currency field

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 3 unchecked source item(s).**

1\. Option A

2\. If Frappe Default Stock Setting \> "Allow Negative Stock" = NO

3\. Correction of Workflow: https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/70#issuecomment-5675635237

## Completed Scope Highlights (reported in source)

✓ Add new Check field \`Allow Update UOM?" under existing field "Allowed Production?"

✓ Add new Check field \`Validate Stock?" under existing field "Allow Update UOM?"

✓ Add new Check field \`Is Sales Outlet?" under existing field "Is Group".

✓ Add new Multi-Select (User) field POS Approvers" under existing field "Order Pay Default" + Combined Approver\` (Auto fetch from "POS Approvers" COMMA separated) to use them to send emails.

✓ Add new "Section Break" under items

✓ Add new Currency field

✓ Add new Small Text field

✓ Option B \[Stock Transfer (Including Manufacturing Transfer) & Wastage Management\]

✓ Stock Entry on "SUBMIT" or "Item Qty entry from Web"

✓ Check this:

*Note: 15 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Follow-up Comments / Additional Scope

**Comment 1 - Emraz-MH (2026-09-15):** 2 checked / 0 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/70#issuecomment-5675635237)

• Add new Check field \`Draft Entry" before existing field "From Outlet".

• If Purpose = "Material Transfer" \> On "Draft" && Draft Entry = 0 \> notify-to users whose email addresses are configured under the Target Outlet/Territory's "Combined Approver" field && Combined Approver(s) who holds the role "ArcPOS Requisition Approver"

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 7. GitHub Issue \#69: Corrections \> 30-08-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 13 checked / 0 unchecked                      | **Evidence refs**        | 4                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-08-30                                    | **Last Updated**         | 2026-09-24                           |

## Professional Summary

GitHub issue \#69 is a mixed qa defect / correction backlog covering Backend, Desktop, WEB. The source issue is currently closed and contains 13 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/69</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/69)

## Affected Modules / Areas

Backend, Desktop, WEB

## Source-Derived Actual / Observed Behavior Indicators

• Split Order \> Payment breakdown data missing in the Receipt Print.

• While splitting an order, without Discount OR evenif the order does not contains BOTH type (Discount allowed or not) item also passing with Partial Discount Flag. (Make it same a like general order creation)

## Source-Derived Expected / Required Behavior Indicators

• Closing Email: All the precipitants should receive email in single email. (To and CC)

• Need to RATE column's Total as Average Rate

• When an order/invoice is submitted with trigger on "Credit Sales", so that no payment entry should not auto initiate. \[currently "With ArcPOS Payment" data in passing as 1\]

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ New Report (WEB) \> Item-wise Sales Register

✓ Print in A4 (PDF), Thermal and export in Excel file. Below is the reference:

✓ Split Order \> Payment breakdown data missing in the Receipt Print.

✓ Closing Email: All the precipitants should receive email in single email. (To and CC)

✓ When an order Rounded Total/Grand Total is 0, somehow the "Outstanding Amount" showing in amount figure.

✓ Reports (Sales Type): When report has been generated with "All" outlet, then it's showing all the active Territory/Outlet names in Print. But we need only the outlets name which outlets are linked with the generated report.

✓ Frappe Report: ArcPOS Item-wise Purchase Register

✓ Need to RATE column's Total as Average Rate

✓ When an order/invoice is submitted with trigger on "Credit Sales", so that no payment entry should not auto initiate. \[currently "With ArcPOS Payment" data in passing as 1\]

✓ While splitting an order, without Discount OR evenif the order does not contains BOTH type (Discount allowed or not) item also passing with Partial Discount Flag. (Make it same a like general order creation)

*Note: 3 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 8. GitHub Issue \#68: Desktop Corrections \> 18-08-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Bug / Defect              |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | bug                       |
| **Checklist Status** | 27 checked / 0 unchecked                      | **Evidence refs**        | 34                        |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-08-18                                    | **Last Updated**         | 2026-09-24                |

## Professional Summary

GitHub issue \#68 is a bug / defect covering OFFLINE, Clock-IN/OUT, POS, Split Order. The source issue is currently closed and contains 27 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/68</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/68)

## Affected Modules / Areas

OFFLINE, Clock-IN/OUT, POS, Split Order

## Source-Derived Actual / Observed Behavior Indicators

• Pictures are not showing in offline-

• Showing this error when ordered offline- Coffee/Discounted Cust/Credit Sales-

• When an order is paid offline and another draft order is created on the same table, the subsequent online sync fails and displays an error in ONLINE-

• This keeps loading when later is clicked in Resolve pending sync before clock in-

• Order details- Variant names are not showing here-

• In a draft order, when the customer is changed from a discount-eligible customer to a 0% discount customer and then changed back to a discount-eligible customer, the discount is incorrectly applied to the subtotal instead of recalculating based on the allowed discount-sale items.

## Source-Derived Expected / Required Behavior Indicators

• Remove Make Payment button for Order Type- Pay Later for new orders.

• Rename this to Kitchen Print and make all the button color same-

• For submitted invoice payments, the Cash payment method is pre-selected by default.

• Order details- These data doesn't show for split orders

• The Cash payment method shouldn't be pre-selected by default.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ User is logged out every time the application is closed.

✓ In smaller screen the date time looks like this-

✓ These disabled fields are not fully visible

✓ Online order workflow is showing abnormal behavior-

✓ Pictures are not showing in offline-

✓ Showing this error when ordered offline- Coffee/Discounted Cust/Credit Sales-

✓ When an order is paid offline and another draft order is created on the same table, the subsequent online sync fails and displays an error in ONLINE-

✓ This keeps loading when later is clicked in Resolve pending sync before clock in-

✓ For credit sales it shows as PAID instead of DUE-

✓ Pathao and Foodpanda shows occupied -

*Note: 17 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 9. GitHub Issue \#67: Corrections \> 10-08-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 79 checked / 26 unchecked                     | **Evidence refs**        | 6                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-08-10                                    | **Last Updated**         | 2026-09-16                           |

## Professional Summary

GitHub issue \#67 is a mixed qa defect / correction backlog covering Backend, Buying Price auto update, Draft Order update, New or Draft Order update, Final Clock-OUT. The source issue is currently closed and contains 79 checked/completed checklist item(s) and 26 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 26 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/67</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/67)

## Affected Modules / Areas

Backend, Buying Price auto update, Draft Order update, New or Draft Order update, Final Clock-OUT, Desktop, App Opening, Table View, Print, Order in Draft or Submitted, Order Payment, Order on NEW and Draft

## Source-Derived Actual / Observed Behavior Indicators

• If any item's total_cost value in BOM doctype is not same for the item's Standard Buying price OR the item does not has Standard Buyingprice, then update or set the price for the item.

• If any of Table is occupied or Any Sales Invoice docstatus is 0 for the closing period, restrict to clock-OUT and throw error to fix them first.

• Sometimes we are facing that, because of frappe rounding, its not matching with our auto rounding amount. So that payment not creating with error. What if we save the invoice on Payfirst and always take the Grandtotal and other data from the Frappe Invoice.

• - Options: Blank/Cash/Bank

• The Table border is not showing in the Print Output.

• On PDF : The Table border is not showing in the Print Output.

## Source-Derived Expected / Required Behavior Indicators

• \### Buying Price auto update:

• item wise discount allow not allow. (Some items won't be allowed to Discount)

• EXAMPLE: If in a order 2 item (each rate is 50 BDT \> Total 100 BDT), and 1 of them if Disallowed then if 10% discount then Discount amount will be 5 taka NOT 10 Taka.

• Can you do one thing, Whenever the app opens, it should open with default Full screen.

• If there are Change amount on Cash, then show this in the print receipt on Payment section.

• If the modal pop up on draft order and there is front items then the "Front" print should be default/1st otherwise Receipt print. \[This was functional earlier\]

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 26 unchecked source item(s).**

1\. 1st Trigger can be on update the BOM

2\. Item transfer to another new/existing running order. \[Ignore now\]

3\. Table color turn to Yellow if the print receipt is printed. \[Ignore now\]

4\. Order Draft: After Drafting an order, the table occupancy gets delay.

5\. Total Credit Sales = GRAND TOTAL

6\. Sales Breakdown

7\. Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1)

8\. Customer Name ------ invoice's total data

9\. SALES TOTAL (Net) = Sum of invoice's total data

10\. Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1)

11\. Sum of invoice's Discount Amount data

12\. Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1)

13\. Sum of invoice's \> Table "Sales Taxes and Charges" \> Is SD? = 1 \> Sum of Amount data

14\. Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1)

15\. Sum of invoice's \> Table "Sales Taxes and Charges" \> Is TAX/VAT? = 1 \> Sum of Amount data

16\. Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1)

17\. Sum of invoice's Rounding Adjustment data

18\. GRAND TOTAL = SALES TOTAL (Net) - Discount + VAT + SD +/- Auto Round

19\. Need to replicate "ArcPOS WEB Report":

20\. Sales Overview = ArcPOS Sales Overview

21\. Item Sales Summary = ArcPOS Item Sales Summary

22\. Payment Overview = ArcPOS Payment Overview

23\. Table & Covers PnL = ArcPOS Table & Covers PnL

24\. Order-to-Serve Lag Report = ArcPOS Order-to-Serve Lag Report

25\. Day-End Audit Summary = ArcPOS Day-End Audit Summary

26\. Same Alert on Pending/Failed Queue job on trigger on close/exit the app

## Completed Scope Highlights (reported in source)

✓ If any item's total_cost value in BOM doctype is not same for the item's Standard Buying price OR the item does not has Standard Buyingprice, then update or set the price for the item.

✓ 2nd Trigger can be a cron job at midnight

✓ item wise discount allow not allow. (Some items won't be allowed to Discount)

✓ If any of Table is occupied or Any Sales Invoice docstatus is 0 for the closing period, restrict to clock-OUT and throw error to fix them first.

✓ Can you do one thing, Whenever the app opens, it should open with default Full screen.

✓ Check why the Print out gets delay. Need more faster.

✓ If there are Change amount on Cash, then show this in the print receipt on Payment section.

✓ Make the Print Modal UI something like the attached reference: NOTE: THIS IS JUST A DEMO UI

✓ If the modal pop up on draft order and there is front items then the "Front" print should be default/1st otherwise Receipt print. \[This was functional earlier\]

✓ Table number to be highlighted/ in Big Font in all print output to highlight it.

*Note: 69 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

## Follow-up Comments / Additional Scope

**Comment 1 - Emraz-MH (2026-08-13):** 38 checked / 22 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/67#issuecomment-5276429650)

• Total Credit Sales = GRAND TOTAL

• Sales Breakdown

• Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1)

• Customer Name ------ invoice's total data

**Comment 2 - Emraz-MH (2026-08-18):** 7 checked / 0 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/67#issuecomment-5323937135)

• Preventing only if any Table is occupied, but we need also for If any Sales Invoice docstatus is 0 for the current period.

• Clock-IN & Clock-OUT Time is showing UTC

• Keep 3 sections side by side until Tablet screen

• Credit Sales button missing when Credit allowed customer is selected

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 10. GitHub Issue \#66: Corrections \> 04-08-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 21 checked / 0 unchecked                      | **Evidence refs**        | 0                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-08-09                                    | **Last Updated**         | 2026-08-10                           |

## Professional Summary

GitHub issue \#66 is a mixed qa defect / correction backlog covering Backend, ArcPOS Accounts Payable, ArcPOS Item-wise purchase register, Desktop, Print. The source issue is currently closed and contains 21 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/66</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/66)

## Affected Modules / Areas

Backend, ArcPOS Accounts Payable, ArcPOS Item-wise purchase register, Desktop, Print, Order in Draft, Report: Day-end Audit Summary, Clock-OUT Modal

## Source-Derived Actual / Observed Behavior Indicators

• Auto close if occupied table running order is paid. Sometimes the Order is Paid but order status does not turn to CLOSED! (Need to do the automation as we done on BanCan)

• Supplier Invoice Data missing!!

• On PDF print, all the columns are not showing.

## Source-Derived Expected / Required Behavior Indicators

• Auto close if occupied table running order is paid. Sometimes the Order is Paid but order status does not turn to CLOSED! (Need to do the automation as we done on BanCan)

• Auto email issue on payment section: Its taking the Date only, not validating the time! If needed add a custom field in the payment entry for Posting time (auto take the creation time and should not change on the document update/submit)

• Is there any way to auto marked the Use Letter head field when user click on PDF from a report?

• Remove Column: Purchase Receipt

• Rename the Column header "Total Tax" to "Total VAT"

• Table no show in the print receipt. Currently we are showing the service type only. Add the linked table data. LIKE Table 01-Dine-In \> Take the table data till -. dont show the Outlet name.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ Auto close if occupied table running order is paid. Sometimes the Order is Paid but order status does not turn to CLOSED! (Need to do the automation as we done on BanCan)

✓ Auto email issue on payment section: Its taking the Date only, not validating the time! If needed add a custom field in the payment entry for Posting time (auto take the creation time and should not change on the document update/submit)

✓ Sales Invoice: Parent Invoice reference on Split invoices

✓ Work Order: Invoice Reference in Work Order.

✓ Frappe Customization:

✓ Is there any way to auto marked the Use Letter head field when user click on PDF from a report?

✓ Supplier Invoice Data missing!!

✓ On PDF print, End of right side column data hiding on Portrait page mode

✓ Reduce bit of value font size on Print PDF

✓ Remove Column: Purchase Receipt

*Note: 11 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 11. GitHub Issue \#65: POS Web \> Corrections 29-07-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 2 checked / 0 unchecked                       | **Evidence refs**        | 0                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-07-29                                    | **Last Updated**         | 2026-09-16                           |

## Professional Summary

GitHub issue \#65 is a mixed qa defect / correction backlog covering Stock Requisition, Wastage Management. The source issue is currently closed and contains 2 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/65</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/65)

## Affected Modules / Areas

Stock Requisition, Wastage Management

## Source-Derived Actual / Observed Behavior Indicators

• Including all the current flow, when the data is passing to frappe then always for each item, pass the "ArcPOS Settings \> defaultwastageaccount" value in the "Difference Account" field. If the settings value is NULL then pass this as now.

## Source-Derived Expected / Required Behavior Indicators

• - Currently we have a validation that, If the logged user has Role "ArcPOS Requisition Approver" OR "System Manager" && "Source Outlet" is set as default on the web, then user can get the Edit and Approve button permission.

• But now for the "Source Outlet" is set as default on the web" \> instead of this check the user has the source outlet/territory permission and others, then allow those buttons.

• Including all the current flow, when the data is passing to frappe then always for each item, pass the "ArcPOS Settings \> defaultwastageaccount" value in the "Difference Account" field. If the settings value is NULL then pass this as now.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ But now for the "Source Outlet" is set as default on the web" \> instead of this check the user has the source outlet/territory permission and others, then allow those buttons.

✓ Including all the current flow, when the data is passing to frappe then always for each item, pass the "ArcPOS Settings \> defaultwastageaccount" value in the "Difference Account" field. If the settings value is NULL then pass this as now.

## QA Impact & Retest Guidance

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 12. GitHub Issue \#64: Backend Issue \> 25-07-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Work Item        |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                      |
| **Checklist Status** | 13 checked / 6 unchecked                      | **Evidence refs**        | 4                         |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-07-25                                    | **Last Updated**         | 2026-09-16                |

## Professional Summary

GitHub issue \#64 is a mixed qa work item covering Auto Purchase Invoice, POS Report: Order-to-Serve Lag Report, Frappe Report: Accounts Payable (Report) \[Ignore Now\], Frappe Report: Item-wise Purchase Register (Report) \[Ignore Now\]. The source issue is currently closed and contains 13 checked/completed checklist item(s) and 6 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 6 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/64</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/64)

## Affected Modules / Areas

Auto Purchase Invoice, POS Report: Order-to-Serve Lag Report, Frappe Report: Accounts Payable (Report) \[Ignore Now\], Frappe Report: Item-wise Purchase Register (Report) \[Ignore Now\]

## Source-Derived Expected / Required Behavior Indicators

• Email & Socket notification: Stage for "Requisition Approval" \> Send the notification just check if the user has the Source outlet/territory permission only. No need to check which is default. And role "ArcPOS Requisition Approver"

• Remove "System Manager" Role from all the Email & Socket notifications.

• \### - Auto Purchase Invoice

• If any purchase order has been submitted with backdate on Date, then the purchase invoice also should be created by the actual day not current date.

• Can we do this dynamically? If "ArcPOS Settings \> "Allowed to Skip Kitchen (Outlet)" has value (value= multiple outlet names separated by commas) && If any Invoice territory = {{ the value }}, then the data should not appear in this report.

• If above not possible then \> If any Invoice territory = ISD, then the data should not appear in this report.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 6 unchecked source item(s).**

1\. If above not possible then \> If any Invoice territory = ISD, then the data should not appear in this report.

2\. For Header Footer \> we will use frappe "Letter Head"

3\. Remove: Mode of Payment, Company

4\. Additionally Add: Order No, Supplier Invoice

5\. Remove: Description, Payable Account, Mode of Payment, Project, Company, Expense Account

6\. For Header Footer \> we will use frappe "Letter Head"

## Completed Scope Highlights (reported in source)

✓ Email & Socket notification: Stage for "Requisition Approval" \> Send the notification just check if the user has the Source outlet/territory permission only. No need to check which is default. And role "ArcPOS Requisition Approver"

✓ Remove "System Manager" Role from all the Email & Socket notifications.

✓ If any purchase order has been submitted with backdate on Date, then the purchase invoice also should be created by the actual day not current date.

✓ Can we do this dynamically? If "ArcPOS Settings \> "Allowed to Skip Kitchen (Outlet)" has value (value= multiple outlet names separated by commas) && If any Invoice territory = {{ the value }}, then the data should not appear in this report.

✓ Need Customized report \> ArcPOS Accounts Payable

✓ Filters: Date Range, Supplier Name, Supplier Group

✓ Columns: Posting Date, Supplier Code, Supplier Name, Supplier Group, Voucher No, Order No, Supplier Invoice, Invoice Amount, Outstanding Amount,

✓ No need any chart

✓ Print PDF \> LIKE the below image (Page can be Portrait or Landscape)

✓ Need Customized report \> ArcPOS Item-wise Purchase Register

*Note: 3 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 13. GitHub Issue \#63: Desktop Pending Corrections- 15-07-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed: Bug + Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | bug, enhancement          |
| **Checklist Status** | 16 checked / 0 unchecked                      | **Evidence refs**        | 6                         |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-07-15                                    | **Last Updated**         | 2026-09-16                |

## Professional Summary

GitHub issue \#63 is a mixed: bug + enhancement covering Order Receipt Print, Split, Reload Button, POS Order page, Order List and Details page. The source issue is currently closed and contains 16 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/63</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/63)

## Affected Modules / Areas

Order Receipt Print, Split, Reload Button, POS Order page, Order List and Details page, POS Print Issue, Void Order, POS Order \> \[this was functional earlier\]

## Source-Derived Actual / Observed Behavior Indicators

• Check the below attachment, why this error accorded?

## Source-Derived Expected / Required Behavior Indicators

• Show the preference like this-

• After completing 1 guest slot payment show the Grand total here-

• On trigger should redirect to the Home page

• If any item Status NOT = "Served" then allow to update the status to only "Served"

• On print Section: Allow only "Print Receipt"

• List page: If Docstatus NOT = 0 and Order Status NOT = "Closed" then allow to update the status to only "Closed" and on update the item status will be "Served" as well.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ Show the preference like this-

✓ After completing 1 guest slot payment show the Grand total here-

✓ On trigger should redirect to the Home page

✓ If the trigger from New Order, then pop up a warning modal first, if confirms then initiate reload.

✓ Any Item which is added to cart, the item Status will be "Ready to Serve" also for Kitchen Items.

✓ If any item Status NOT = "Served" then allow to update the status to only "Served"

✓ On print Section: Allow only "Print Receipt"

✓ List page: If Docstatus NOT = 0 and Order Status NOT = "Closed" then allow to update the status to only "Closed" and on update the item status will be "Served" as well.

✓ Details: If any item Status NOT = "Served" then allow to update the status to only "Served"

✓ Check the below attachment, why this error accorded?

*Note: 6 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

## Follow-up Comments / Additional Scope

**Comment 1 - Emraz-MH (2026-07-25):** 5 checked / 0 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/63#issuecomment-5077167152)

• Voiding remarks should pass to the invoice's "customuserremarks" field. \[this was functional earlier\]

• In DRAFT order, existing Items in the Cart \> Edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to Multiple and the "Variant Item Type" is set to Combo, then the user should NOT allowed to increase the quantity from List & POP UP.

• In NEW or DRAFT order, including existing Items in the Cart \> if the "Attribute Type for POS" or "Choice Type for POS" is set to Multiple and the "Variant Item Type" is NOT set to Combo, then the user should allowed to increase the quantity from List & POP UP as well.

• Also cab be edited the "Service Type", "Preferences", "Issue Type", "Order Note" from the POP UP as well.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 14. GitHub Issue \#62: Desktop Application Issues- 01/07/2026

| **GitHub State**     | CLOSED                                          | **Classification**       | Bug / Defect                |
|----------------------|-------------------------------------------------|--------------------------|-----------------------------|
| **Assignee(s)**      | binshahed                                       | **Labels**               | bug                         |
| **Checklist Status** | 3 checked / 0 unchecked                         | **Evidence refs**        | 0                           |
| **QA Risk**          | Medium (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: Medium |
| **Created**          | 2026-07-01                                      | **Last Updated**         | 2026-07-13                  |

## Professional Summary

GitHub issue \#62 is a bug / defect covering Cash Drawer/Print, Split Bill. The source issue is currently closed and contains 3 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/62</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/62)

## Affected Modules / Areas

Cash Drawer/Print, Split Bill

## Source-Derived Actual / Observed Behavior Indicators

• Blank space at the top of the printed receipt should be fixed.

• Create order with 1 Coffee M and 1 Coffee S → Save the order → Go to Split Order → Make payment only for Coffee M → After Coffee M payment is completed, select Coffee S from the left side → Coffee S does not appear on the right side for payment as expected.

## Source-Derived Expected / Required Behavior Indicators

• Cash drawer should not open after every print, it should open only when the payment method is Cash.

• Blank space at the top of the printed receipt should be fixed.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ Cash drawer should not open after every print, it should open only when the payment method is Cash.

✓ Blank space at the top of the printed receipt should be fixed.

✓ Create order with 1 Coffee M and 1 Coffee S → Save the order → Go to Split Order → Make payment only for Coffee M → After Coffee M payment is completed, select Coffee S from the left side → Coffee S does not appear on the right side for payment as expected.

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 15. GitHub Issue \#61: Epson TM-T81III Printer and QZ Tray Cash Drawer Setup Guide for Windows 11

| **GitHub State**     | OPEN                    | **Classification**       | Documentation / Operational Setup |
|----------------------|-------------------------|--------------------------|-----------------------------------|
| **Assignee(s)**      | Rafia232                | **Labels**               | documentation                     |
| **Checklist Status** | 0 checked / 0 unchecked | **Evidence refs**        | 0                                 |
| **QA Risk**          | N/A (documentation)     | **Recommended Priority** | P3 / Operational                  |
| **Created**          | 2026-06-30              | **Last Updated**         | 2026-06-30                        |

## Professional Summary

GitHub issue \#61 is a documentation / operational setup covering Epson TM-T81III Printer Setup for Windows 11, 1. Download Epson Driver, 2. Optional USB Driver, 3. Connect Printer Hardware, 4. Install Driver. The source issue is currently open and contains 0 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/61</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/61)

## Affected Modules / Areas

Epson TM-T81III Printer Setup for Windows 11, 1. Download Epson Driver, 2. Optional USB Driver, 3. Connect Printer Hardware, 4. Install Driver, 5. Check Printer in Windows, 6. Set Paper Size, 7. Print Test Page, Cash Drawer Setup, 1. Download QZ Tray, 2. Install QZ Tray, 3. Open QZ Tray

## Source-Derived Expected / Required Behavior Indicators

• 3. You should see the QZ Tray icon near the Windows clock/system tray.

• \## 4. Enable Auto Start

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments. **The issue remains OPEN, so closure criteria/status should still be confirmed.**

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 16. GitHub Issue \#60: POS WEB \> 14-06-2026

| **GitHub State**     | CLOSED                                               | **Classification**       | Mixed QA Work Item        |
|----------------------|------------------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | Unassigned                                           | **Labels**               | None                      |
| **Checklist Status** | 6 checked / 1 unchecked                              | **Evidence refs**        | 2                         |
| **QA Risk**          | Medium-High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-06-14                                           | **Last Updated**         | 2026-07-01                |

## Professional Summary

GitHub issue \#60 is a mixed qa work item covering Stock Transfer, Stock Requisition. The source issue is currently closed and contains 6 checked/completed checklist item(s) and 1 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 1 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/60</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/60)

## Affected Modules / Areas

Stock Transfer, Stock Requisition

## Source-Derived Actual / Observed Behavior Indicators

• On Edit, "Required By" is not updating in Backend/Frappe document.

## Source-Derived Expected / Required Behavior Indicators

• "Accept" button should enabled only if the "Target Outlet" is set as default from "POS WEB"

• "Cancel" button should enabled only for FRAPPE Role = System Manager + ArcPOS Manager

• "Edit" & "Submit" button should enabled only if the "Source Outlet" is set as default from "POS WEB"

• So, check first for the 2nd row, is there are any functionality or not? If NO, then we can remove this

• After "Approve", redirect to "Requisition" list page with latest data.

• "Create Transfer" \> the OUTLET should be pass as per selected from "POS WEB"

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 1 unchecked source item(s).**

1\. "Create Transfer" \> the OUTLET should be pass as per selected from "POS WEB"

## Completed Scope Highlights (reported in source)

✓ "Accept" button should enabled only if the "Target Outlet" is set as default from "POS WEB"

✓ "Cancel" button should enabled only for FRAPPE Role = System Manager + ArcPOS Manager

✓ "Edit" & "Submit" button should enabled only if the "Source Outlet" is set as default from "POS WEB"

✓ So, check first for the 2nd row, is there are any functionality or not? If NO, then we can remove this

✓ On Edit, "Required By" is not updating in Backend/Frappe document.

✓ After "Approve", redirect to "Requisition" list page with latest data.

## QA Impact & Retest Guidance

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 17. GitHub Issue \#59: Desktop \> 08-06-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Work Item        |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | None                      |
| **Checklist Status** | 30 checked / 2 unchecked                      | **Evidence refs**        | 20                        |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-06-08                                    | **Last Updated**         | 2026-06-24                |

## Professional Summary

GitHub issue \#59 is a mixed qa work item covering For "Rounding Adjustment", Alert redirection, Print Modal, Order Splitting, Receipt print. The source issue is currently closed and contains 30 checked/completed checklist item(s) and 2 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 2 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/59</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/59)

## Affected Modules / Areas

For "Rounding Adjustment", Alert redirection, Print Modal, Order Splitting, Receipt print, Order edit drawer, New/Draft Order

## Source-Derived Actual / Observed Behavior Indicators

• On Clock-IN, the Expected amount getting NULL/0, please collaborate with Anamul (Backend)

• Why I am getting the error when the Opening amount = 0 (backend)

## Source-Derived Expected / Required Behavior Indicators

• Implement the Item Preferences. also show in all prints. \[Reference can be BanCan Print\]

• Rename the warning text to "You have already logged in a Counter" (Backend)

• Counter options must be unique (Backend)

• Add the"Bell Icon" with functionality also on the Modal's top right corner.

• This text should be in RED color font

• If "Prepare At = Front", then show the "Remove" button in status = "Waiting/Preparing/Ready to Serve"

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 2 unchecked source item(s).**

1\. If Subtotal is less then 500 then upto .50 will be in negative and from .51 will be in positive

2\. If Subtotal is greater then 499.99 then upto .49 will be in negative and from .50 will be in positive

## Completed Scope Highlights (reported in source)

✓ Implement the Item Preferences. also show in all prints. \[Reference can be BanCan Print\]

✓ Rename the warning text to "You have already logged in a Counter" (Backend)

✓ Counter options must be unique (Backend)

✓ On Clock-IN, the Expected amount getting NULL/0, please collaborate with Anamul (Backend)

✓ Why I am getting the error when the Opening amount = 0 (backend)

✓ Add the"Bell Icon" with functionality also on the Modal's top right corner.

✓ "Mark as Read" text button/pausing the alert tone button is not stopping the ringing from this modal

✓ This text should be in RED color font

✓ Place the report in the Center and if multiple then the per row 2 reports.

✓ Make correction of the report description to: Summary of daily sales, charges, and payments.

*Note: 20 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

## Follow-up Comments / Additional Scope

**Comment 1 - Emraz-MH (2026-06-21):** 12 checked / 0 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/59#issuecomment-4760930073)

• If Grand Total value of 123.4999999 or below will result in a negative rounding adjustment

• If Grand Total value of 123.5000000 or Above will result in a Positive rounding adjustment

• If Draft order then redirect to Draft Mode of the Order from Notification

• Notification dropdown \> the ringer "Sound" button \> Keep "ON" as default. That means, if user "OFF" this and somehow the app gets reload or restart so that sound will be turned ON automatically.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 18. GitHub Issue \#58: Requirement of 04-06-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Functional Requirement / Enhancement |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 35 checked / 0 unchecked                      | **Evidence refs**        | 0                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-06-07                                    | **Last Updated**         | 2026-06-24                           |

## Professional Summary

GitHub issue \#58 is a functional requirement / enhancement covering Need to do, Print Modal options: \[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items\], Report \> Order-to-Serve Lag Report. The source issue is currently closed and contains 35 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/58</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/58)

## Affected Modules / Areas

Need to do, Print Modal options: \[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items\], Report \> Order-to-Serve Lag Report

## Source-Derived Expected / Required Behavior Indicators

• \### Need to do:

• No need to pass the "Serve" time

• No need to pass the "Ready to Serve" time

• When an order is created containing only front order items, the order status should automatically be set to Ready to Serve.

• In that draft order, when a Prepare At = Kitchen item is added, the order status should automatically be updated to Waiting.

• In a draft order, when a Prepare At = Front item is added, the item status should automatically be set to Ready to Serve.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ Only for "Prepare At = Front"

✓ If item's are "Is BOM Item = 1" then initiate Workorder and related things

✓ On success \> Pass item's order status = Served

✓ No need to pass the "Serve" time

✓ Pass item's order status = Ready to Serve

✓ No need to pass the "Ready to Serve" time

✓ When an order is created containing only front order items, the order status should automatically be set to Ready to Serve.

✓ In that draft order, when a Prepare At = Kitchen item is added, the order status should automatically be updated to Waiting.

✓ In a draft order, when a Prepare At = Front item is added, the item status should automatically be set to Ready to Serve.

✓ After Payment success + Order Details (Online)

*Note: 25 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 19. GitHub Issue \#57: POS- WEB Ordering Process - 7th June

| **GitHub State**     | OPEN                                          | **Classification**       | Bug / Defect                          |
|----------------------|-----------------------------------------------|--------------------------|---------------------------------------|
| **Assignee(s)**      | amirhamja4bd                                  | **Labels**               | bug                                   |
| **Checklist Status** | 47 checked / 8 unchecked                      | **Evidence refs**        | 40                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | P1-P2 (recommended; verify with team) |
| **Created**          | 2026-06-07                                    | **Last Updated**         | 2026-07-23                            |

## Professional Summary

GitHub issue \#57 is a bug / defect covering POS Order page, Order List and Details page, Mobile Responsiveness, Order, POS. The source issue is currently open and contains 47 checked/completed checklist item(s) and 8 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/57</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/57)

## Affected Modules / Areas

POS Order page, Order List and Details page, Mobile Responsiveness, Order, POS, KITCHEN ORDERS

## Source-Derived Actual / Observed Behavior Indicators

• Order status is not updating even when all the item status is ready to serve/served.

• When a draft order is created with a walk-in customer and later changed to a credit sales enabled customer, submitting the order with credit sales causes the item and order status to work incorrectly.

• Showing the wrong print format for Front Order prints.

• \[SKIPPED\] 1 Coffee, 1 Captain America. When coffee's status is already served and then Captain America's status is changed to Ready to serve, The order status still shows as Waiting. It doesn't update the order status accordingly.

• Browser back button-\> discard not working.

• After making payment of a credit sales order it doesn't redirect back to that order details page. Shows error- Could not load this order details. And keeps showing error- User None is disabled. Please contact your System Manager. Which fixes after clearing the cookies.

## Source-Derived Expected / Required Behavior Indicators

• If any item Status NOT = "Served" then allow to update the status to only "Served"

• On print Section: Allow only "Print Receipt"

• List page: If Docstatus NOT = 0 and Order Status NOT = "Closed" then allow to update the status to only "Closed" and on update the item status will be "Served" as well.

• Details: If any item Status NOT = "Served" then allow to update the status to only "Served"

• Item quantity should be editable when the item status = waiting.

• Remove this table part-

## Outstanding / Unchecked Items

1\. ORD-26-01617- Check the choose qty condition, it's automatically passing data when variant item choice type is single.

2\. Any Item which is added to cart, the item Status will be "Ready to Serve" also for Kitchen Items.

3\. If any item Status NOT = "Served" then allow to update the status to only "Served"

4\. On print Section: Allow only "Print Receipt"

5\. List page: If Docstatus NOT = 0 and Order Status NOT = "Closed" then allow to update the status to only "Closed" and on update the item status will be "Served" as well.

6\. Details: If any item Status NOT = "Served" then allow to update the status to only "Served"

7\. On print Section: Allow only "Print Receipt"

8\. In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item.

## Completed Scope Highlights (reported in source)

✓ Item quantity should be editable when the item status = waiting.

✓ Order status is not updating even when all the item status is ready to serve/served.

✓ Split order- edit pax to- Party size.

✓ When a draft order is created with a walk-in customer and later changed to a credit sales enabled customer, submitting the order with credit sales causes the item and order status to work incorrectly.

✓ Keep the party size fixed to 1 and disabled for foodpanda and pathao (Customer Type= Partnership)

✓ Showing the wrong print format for Front Order prints.

✓ Table is still showing as Occupied after submitting an order using Credit Sales.

✓ Remove this table part-

✓ In Edit Order-\> Show the issue type like this-

✓ In Edit Order-\> For foodpanda/pathao Select Customer fields are showing selectable instead of showing the linked customer by default.

*Note: 37 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 20. GitHub Issue \#53: Desktop \> 23-05-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Work Item        |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | None                      |
| **Checklist Status** | 13 checked / 0 unchecked                      | **Evidence refs**        | 4                         |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-05-23                                    | **Last Updated**         | 2026-06-24                |

## Professional Summary

GitHub issue \#53 is a mixed qa work item covering Split Order, Clock-IN/OUT. The source issue is currently closed and contains 13 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/53</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/53)

## Affected Modules / Areas

Split Order, Clock-IN/OUT

## Source-Derived Actual / Observed Behavior Indicators

• Party size is not updating after one slot payment.

• The Expected amount is not showing the updated amount.

## Source-Derived Expected / Required Behavior Indicators

• For variant items, in the cart, show item name instead of item code-

• Add three types of coffee – L/M/S. Change all item statuses to Ready to Serve from the front order. Then, in the split bill, drag only Coffee-L for payment and complete the payment.

• - The parent invoice should only be marked as paid and updated when there are no remaining items in the Unassigned Items section of the split bill.

• - New invoices should be created for each partial payment without closing the parent invoice.

• Allow to update Party Size and pass to Invoice also. Auto update the party size slot wise but user can also change it.

• After PIN enable, on save, the Discount field must be Disabled and the "SAVE" button replace to PIN with session ending.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ For variant items, in the cart, show item name instead of item code-

✓ Add three types of coffee – L/M/S. Change all item statuses to Ready to Serve from the front order. Then, in the split bill, drag only Coffee-L for payment and complete the payment.

✓ Party size is not updating after one slot payment.

✓ Allow to update Party Size and pass to Invoice also. Auto update the party size slot wise but user can also change it.

✓ After PIN enable, on save, the Discount field must be Disabled and the "SAVE" button replace to PIN with session ending.

✓ After Payment, the Print Modal should appear.

✓ Last Invoice must be update the Parent Invoice with last split payment. and also the Table should be available.

✓ After Last Slot is paid, then return to the Table page after Print Done.

✓ The Expected amount is not showing the updated amount.

✓ When Clock-IN/OUT is submitted for the first time for approval it should only show the 2nd message- Clock-IN/OUT submitted. Awaiting approval-

*Note: 3 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 21. GitHub Issue \#52: POS Web \> 21-05-2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Work Item        |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                      |
| **Checklist Status** | 80 checked / 53 unchecked                     | **Evidence refs**        | 6                         |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-05-21                                    | **Last Updated**         | 2026-09-16                |

## Professional Summary

GitHub issue \#52 is a mixed qa work item covering Existing Reports, New Report, New Report Query, Stock Transfer, Socket Notification. The source issue is currently closed and contains 80 checked/completed checklist item(s) and 53 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 53 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/52</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/52)

## Affected Modules / Areas

Existing Reports, New Report, New Report Query, Stock Transfer, Socket Notification, Reports (Module), Stock Requisition

## Source-Derived Expected / Required Behavior Indicators

• All the value must be fetched as per logged user's territory permission

• Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select.

• Add Print as PDF \[Should generate as per filter\] \> HEADER & FOOTER are same for all reports

• Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

• Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

• With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 53 unchecked source item(s).**

1\. Sales Overview

2\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

3\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

4\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

5\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

6\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

7\. Item Sales Summary

8\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

9\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

10\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

11\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

12\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

13\. Payment Overview

14\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

15\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

16\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

17\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

18\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

19\. Daily Cash Audit

20\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

21\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

22\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

23\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

24\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

25\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

26\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

27\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

28\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

29\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

30\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

31\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

32\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

33\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

34\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

35\. Use "Default Company" \> "company_logo" field as letter head "Header" \> Place on LEFT side & On RIGHT \> Place the Filtered "Outlet" name \[If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line

36\. Under the STRAIGHT line, on Center \> Place the Report Name \[Bold\]

37\. Under REPORT name, show filtered Date Range \[Date format LIKE 1st Jan 2026 - 28th Feb 2026\]

38\. With Above line \> Add text on LEFT and RIGHT side \> Prepared By, Authorized By

39\. Place at LEFT side "Powered by ArcPOS" and at RIGHT side \> Generated on \[Current Date, Current Time \> italic\]

40\. From Sales Invoice

41\. Doc Status = 1

42\. Order From = "customorderfrom"

43\. Service Mode = “customservicetype”

44\. Amount = Sum of “net_total”

45\. Group by "Order From + “Service Type + Territory”

46\. Total Sales = Sum of “net_total”

47\. Discount = "basediscountamount" \> (Sum of Discounted Invoice qty)

48\. SD = Table \> "Sales Taxes and Charges" \> "customissd = 1" \> tax_amount \> (Sum of with SD Invoice qty)

49\. VAT = Table \> "Sales Taxes and Charges" \> "customistax = 1" \> tax_amount

50\. Auto Round \> Sum of "rounding_adjustment" \> (Sum of Auto Round NOT = 0 Invoice qty)

51\. Additionally need percentage of each Payment method

52\. Group by + Territory

53\. Check: https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/46

## Completed Scope Highlights (reported in source)

✓ All the value must be fetched as per logged user's territory permission

✓ Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select.

✓ Add Print as PDF \[Should generate as per filter\] \> HEADER & FOOTER are same for all reports

✓ Header

✓ Footer

✓ All Item should be group by Territory also.

✓ Add a "Outlet" column after "Category"

✓ Add Print as PDF \[Should generate as per filter\]

✓ Add a "Outlet" column after "Method Name"

✓ Why it's showing same "Method Name" multiple time?

*Note: 70 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 22. GitHub Issue \#51: Desktop - 18-05-2026

| **GitHub State**     | CLOSED                                          | **Classification**       | Mixed QA Work Item          |
|----------------------|-------------------------------------------------|--------------------------|-----------------------------|
| **Assignee(s)**      | Unassigned                                      | **Labels**               | None                        |
| **Checklist Status** | 6 checked / 1 unchecked                         | **Evidence refs**        | 0                           |
| **QA Risk**          | Medium (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: Medium |
| **Created**          | 2026-05-18                                      | **Last Updated**         | 2026-06-03                  |

## Professional Summary

GitHub issue \#51 is a mixed qa work item covering 1. Global UI & Responsiveness, 2. Workflow: New Order (Pay First Mode), 3. Module: Outlet Opening & Closing Mechanics, 4. Module: Print Triggers & Formatting. The source issue is currently closed and contains 6 checked/completed checklist item(s) and 1 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 1 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/51</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/51)

## Affected Modules / Areas

1\. Global UI & Responsiveness, 2. Workflow: New Order (Pay First Mode), 3. Module: Outlet Opening & Closing Mechanics, 4. Module: Print Triggers & Formatting

## Source-Derived Actual / Observed Behavior Indicators

• \* Standard Staff Restriction (Draft Only): If a financial discrepancy exists and the active session user does not hold the Frappe roles "System Manager, ArcPOS Manager, or Restaurant Manager", the system will restrict actions to saving the entry as a Draft for administrative review. On waiting approval, user must not make another request.

## Source-Derived Expected / Required Behavior Indicators

• Clicking this button must securely save the active transactional state into the backend with a docstatus = 0 (Draft) configuration. I will check the next flows if its meets as I expecting!

• Smart Counter Defaulting: If a designated retail outlet operates with only a single counter registry, configure the UI to automatically populate that counter name as the default option.

• \* Zero-Variance Auto-Submission: If there is no difference (variance is 0) between physical cash and Expected counts, the Cashier Voucher entry must be automatically Submitted.

• \* Standard Staff Restriction (Draft Only): If a financial discrepancy exists and the active session user does not hold the Frappe roles "System Manager, ArcPOS Manager, or Restaurant Manager", the system will restrict actions to saving the entry as a Draft for administrative review. On waiting approval, user must not make another request.

• Option A (Automated Polling): If a Voucher remains in an Approval/Draft state, listen for state changes; upon a backend transition to Approved/Submitted, the operational modal must auto-close.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 1 unchecked source item(s).**

1\. Option A (Automated Polling): If a Voucher remains in an Approval/Draft state, listen for state changes; upon a backend transition to Approved/Submitted, the operational modal must auto-close.

## Completed Scope Highlights (reported in source)

✓ Cross-Device Responsiveness: Resolve layout and responsive styling issues on the Order Details page. Conduct a comprehensive UI audit across all other POS pages to ensure consistency across different screen dimensions.

✓ Draft Creation Control: Implement a "SAVE" button on the LEFT side of the panel.

✓ Clicking this button must securely save the active transactional state into the backend with a docstatus = 0 (Draft) configuration. I will check the next flows if its meets as I expecting!

✓ Smart Counter Defaulting: If a designated retail outlet operates with only a single counter registry, configure the UI to automatically populate that counter name as the default option.

✓ Option B (Manual Interrogation): Provide a dedicated "Re-sync" button or using existing Clock-IN/OUT button to dynamically call the latest document state flag. If the backend verification confirms the Voucher is now Approved/Submitted, programmatically close the modal.

✓ Print Pipeline Modifications: Standard print routine workflows require structural updates. (Logic specifications to be finalized and added here).

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 23. GitHub Issue \#50: POS - Desktop - 14-05-2026

| **GitHub State**     | OPEN                                          | **Classification**       | Mixed QA Work Item                    |
|----------------------|-----------------------------------------------|--------------------------|---------------------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | None                                  |
| **Checklist Status** | 10 checked / 1 unchecked                      | **Evidence refs**        | 6                                     |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | P1-P2 (recommended; verify with team) |
| **Created**          | 2026-05-14                                    | **Last Updated**         | 2026-05-18                            |

## Professional Summary

GitHub issue \#50 is a mixed qa work item covering New Order, Update Order, Order List and Details, Front Orders. The source issue is currently open and contains 10 checked/completed checklist item(s) and 1 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/50</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/50)

## Affected Modules / Areas

New Order, Update Order, Order List and Details, Front Orders

## Source-Derived Actual / Observed Behavior Indicators

• Showing this error while changing an order's status from Ready to Serve to Served from the order list-

• If Backend is unreachable then how the OFFLINE activity will be performed?

• Does not allowing to update "Number of Guest" by Keyboard Digit

• Table not fetching \> Shanta Forum

## Source-Derived Expected / Required Behavior Indicators

• Front Order- When "Ready All" or "Ready to Serve" is clicked, the success message should display "Item is now ready to serve" instead of current message.

• If "Pay First" \> then Order status+ Item Status should be "Waiting".

• Delete/Backspace button should change the qty to 0 and =0 should not allow to go next/save.

• If Order Type = Pay First and Order or Item Status = Served, then allow "Closed"

## Outstanding / Unchecked Items

1\. If Backend is unreachable then how the OFFLINE activity will be performed?

## Completed Scope Highlights (reported in source)

✓ Showing this error while changing an order's status from Ready to Serve to Served from the order list-

✓ Front Order- When "Ready All" or "Ready to Serve" is clicked, the success message should display "Item is now ready to serve" instead of current message.

✓ Showing no data in table switch-

✓ If "Pay First" \> then Order status+ Item Status should be "Waiting".

✓ Table Party size modal:

✓ Does not allowing to update "Number of Guest" by Keyboard Digit

✓ Delete/Backspace button should change the qty to 0 and =0 should not allow to go next/save.

✓ Table not fetching \> Shanta Forum

✓ If Order Type = Pay First and Order or Item Status = Served, then allow "Closed"

✓ If Single item status changed to "Ready to Serve" then change the Success Toast text to "Item now ready to serve".

## QA Impact & Retest Guidance

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 24. GitHub Issue \#49: POS- Desktop Issues- After 11th May

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed: Bug + Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | bug, enhancement          |
| **Checklist Status** | 17 checked / 0 unchecked                      | **Evidence refs**        | 6                         |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-05-12                                    | **Last Updated**         | 2026-06-03                |

## Professional Summary

GitHub issue \#49 is a mixed: bug + enhancement covering Credit Sales, After Lunch Task, Front Orders, Order Update, Print Correction. The source issue is currently closed and contains 17 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/49</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/49)

## Affected Modules / Areas

Credit Sales, After Lunch Task, Front Orders, Order Update, Print Correction

## Source-Derived Actual / Observed Behavior Indicators

• When one action button is clicked, other action buttons also shows as loading.

• In draft order edit, when the customer is updated, the system does not apply the new customer's default discount after the update.

• In draft order edit, when an item's issue type is changed from complimentary/gift/wastage to Regular, the item price remains as 0.00

## Source-Derived Expected / Required Behavior Indicators

• In draft order edit, when the customer is updated, the system does not apply the new customer's default discount after the update.

• Get data from sales invoice: Customer Email = "contactemail", Customer Phone = Rename to "Customer Mobile" = contactmobile and Customer Address = address_display. If No value then show (--)

• If the SD is not available, it should not be shown in the print.

• If a Table is occupied with a Submitted Order, then on click the Table, redirect to the Order Details page not to POS view.

• Show "Submit" \[will pass the invoice docstatus = 1 + "Is Credit Sales = 1"\] button instead of "Pay" from all the page, if the "Grand Total/Rounded Total = 0".

• Rename "Serve All" to "Ready All"

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ When one action button is clicked, other action buttons also shows as loading.

✓ In draft order edit, when the customer is updated, the system does not apply the new customer's default discount after the update.

✓ In draft order edit, when an item's issue type is changed from complimentary/gift/wastage to Regular, the item price remains as 0.00

✓ When only gift/complementary/wastage items are added-

✓ Get data from sales invoice: Customer Email = "contactemail", Customer Phone = Rename to "Customer Mobile" = contactmobile and Customer Address = address_display. If No value then show (--)

✓ If the SD is not available, it should not be shown in the print.

✓ If a Table is occupied with a Submitted Order, then on click the Table, redirect to the Order Details page not to POS view.

✓ Show "Submit" \[will pass the invoice docstatus = 1 + "Is Credit Sales = 1"\] button instead of "Pay" from all the page, if the "Grand Total/Rounded Total = 0".

✓ Do not pass any Order Status and Item Status \[except new added item\] on Edit/update

✓ If new Order, Order Status and Item Status will be same as now = Waiting

*Note: 7 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 25. GitHub Issue \#48: Order Split Functionality

| **GitHub State**     | CLOSED                                        | **Classification**       | Functional Requirement / Enhancement |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 0 checked / 7 unchecked                       | **Evidence refs**        | 2                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-05-10                                    | **Last Updated**         | 2026-07-01                           |

## Professional Summary

GitHub issue \#48 is a functional requirement / enhancement covering Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print. The source issue is currently closed and contains 0 checked/completed checklist item(s) and 7 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 7 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/48</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/48)

## Affected Modules / Areas

Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print

## Source-Derived Expected / Required Behavior Indicators

• Item-Wise Split Payment Workflow \[Only if the Main invoice docstatus = 0 and any item status = Ready to Serve/Served\]

• Phase 1: UI Trigger and Redirection

• Interface Redirection: Clicking this button redirects the user to a dedicated "Order Splitter" page.

• Taxes and Discounts: For every guest slot, the system must automatically recalculate SD, VAT, Rounded Adj, and Discounts \[Allow to set discount as per existing functionality\] based on the specific items and quantities in that slot.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 7 unchecked source item(s).**

1\. Item-Wise Split Payment Workflow \[Only if the Main invoice docstatus = 0 and any item status = Ready to Serve/Served\]

2\. Phase 1: UI Trigger and Redirection

3\. Phase 2: Drag-and-Drop Interface Logic

4\. Phase 3: Automated Calculations

5\. Phase 4: Transaction Execution (The "Pay" Action)

6\. Phase 5: Final Guest Optimization

7\. Phase 6: Individual Printing

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 26. GitHub Issue \#47: POS WEB MODIFICATIONS- After 5th May

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed: Bug + Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | arifjahan88, amirhamja4bd                     | **Labels**               | bug, enhancement          |
| **Checklist Status** | 39 checked / 2 unchecked                      | **Evidence refs**        | 20                        |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-05-06                                    | **Last Updated**         | 2026-07-01                |

## Professional Summary

GitHub issue \#47 is a mixed: bug + enhancement covering Navigation Bar, Orders- Fix the full functionality after completing POS order, Stock Requisition, Stock Requisition Details, POS \[Take the same code reference from Desktop App\]. The source issue is currently closed and contains 39 checked/completed checklist item(s) and 2 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 2 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/47</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/47)

## Affected Modules / Areas

Navigation Bar, Orders- Fix the full functionality after completing POS order, Stock Requisition, Stock Requisition Details, POS \[Take the same code reference from Desktop App\], Kitchen Orders

## Source-Derived Actual / Observed Behavior Indicators

• Order details- After payment table field is showing blank.

• The Order From column is also not showing table number after payment.

## Source-Derived Expected / Required Behavior Indicators

• Add an shortcut option with Menu list to move to another menu from except homepage. Show it like this-

• Should not show this when the page is loaded the first time-

• User can make the change of Default outlet only from the Homepage other wise disable the field.

• Should show data here according to this-

• Remove Guest Information from order details.

• Add a "Customer" filter (Type and Select) that is based on the user's territory permissions.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 2 unchecked source item(s).**

1\. \[SKIP FOR NOW\] Need to work on Not Started status- when a stock transfer created from Stock Requisition is cancelled. Also add in status filter.

2\. In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item.

## Completed Scope Highlights (reported in source)

✓ Fix the menu for mobile view.

✓ Add an shortcut option with Menu list to move to another menu from except homepage. Show it like this-

✓ Should not show this when the page is loaded the first time-

✓ User can make the change of Default outlet only from the Homepage other wise disable the field.

✓ Should show data here according to this-

✓ Remove Guest Information from order details.

✓ Add a "Customer" filter (Type and Select) that is based on the user's territory permissions.

✓ Order details- After payment table field is showing blank.

✓ The Order From column is also not showing table number after payment.

✓ Full calculation of SD/VAT/Auto round is pending.

*Note: 29 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 27. GitHub Issue \#46: Backend Issues - After 06-05-2026

| **GitHub State**     | OPEN                                          | **Classification**       | Mixed: Bug + Enhancement              |
|----------------------|-----------------------------------------------|--------------------------|---------------------------------------|
| **Assignee(s)**      | dev-Anamul                                    | **Labels**               | bug, enhancement                      |
| **Checklist Status** | 74 checked / 22 unchecked                     | **Evidence refs**        | 16                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | P1-P2 (recommended; verify with team) |
| **Created**          | 2026-05-06                                    | **Last Updated**         | 2026-09-24                            |

## Professional Summary

GitHub issue \#46 is a mixed: bug + enhancement covering Permission Issues, Web-POS, Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages, Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages, Frappe Customize. The source issue is currently open and contains 74 checked/completed checklist item(s) and 22 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/46</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/46)

## Affected Modules / Areas

Permission Issues, Web-POS, Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages, Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages, Frappe Customize, Correction of alert trigger of notification: \[Existing\], Split Bill, Stock Requisition, Stock Transfer

## Source-Derived Actual / Observed Behavior Indicators

• WC-Web POS-\> Payment for both credit sales and split payment is not working.

• Use an user who doesn't have these permissions- ArcPOS Manager/Restaurant Manager/System Manager

• Add an item with pin-\> after item status is changed from front order, on update order it shows this error-\>

• Clock-IN/OUT: New voucher entry on "Daily Cash Audit" \> On "Submit" \> notify-to "Territory" \[based on Territory default wise\] "Restaurant Cashier" and does not has any Manager Role

• - Clock-IN/OUT: New voucher entry on "Daily Cash Audit" \> On "Submit" \> notify-to "Territory" \[based on Territory default wise\] "Restaurant Cashier" and does not has any Manager Role (ArcPOS Manager/Restaurant Manager/System Manager)

• This Email setup is missing in the ArcPOS Settings

## Source-Derived Expected / Required Behavior Indicators

• Add an item with pin-\> after item status is changed from front order, on update order it shows this error-\>

• Show the variants in the sequence its shown in frappe as set the Item Attributes

• -- LIKE in an Template item's linked attribute's values are set in 1st row "Small", 2nd Row "Medium" and 3rd row "Large". So on your API, all the variant items should be in sequence as per variant value, else on front end \> there showing with sequence break

• Add territory for Sales Overview, Service Mode Analytics.

• In the Invoice \> If All Item status NOT = "Preparing/Ready To Serve/Served" and Void triggered then the invoice will be auto delete in a Cron Job

• But if any of item's status = "Preparing/Ready To Serve/Served" and Void triggered then the invoice should not delete

## Outstanding / Unchecked Items

1\. WC-Web POS-\> Payment for both credit sales and split payment is not working.

2\. https://wcpos.aninda.me/api/method/excelrestaurantpos.api.item.getitemdetails?item_code=Coffee

3\. Real time Email and Push Notification.

4\. Item Order Status = "Waiting" + Prepare AT = "Kitchen" then notify-to based on Territory default wise "Restaurant Chef" and "Restro Kitchen Staff"

5\. On click \> redirect to \> Specific "Kitchen Orders" page

6\. On click \> redirect to \> Specific order's details page

7\. Order: Order Status = "Open" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter"

8\. On click \> redirect to \> Specific order's details page

9\. Stock Requisition: If Purpose = "Material Transfer" \> On "Pending" \> notify-to "Target Outlet" \[based on Territory default wise\] "ArcPOS Requisition Approver"

10\. On click \> redirect to \> Specific Stock Requisition details page

11\. On click \> redirect to \> Specific Stock Requisition details page

12\. On click \> redirect to \> Specific Stock Transfer details page

13\. On click \> redirect to \> Specific wastage management details page

14\. On click \> redirect to \> Specific wastage management details page

15\. Clock-IN/OUT: New voucher entry on "Daily Cash Audit" \> On "Draft" \> notify-to "Territory" \[based on Territory default wise\] "Restaurant Manager"

16\. On click \> redirect to \> Specific Daily Cash Audit details page

17\. Clock-IN/OUT: New voucher entry on "Daily Cash Audit" \> On "Submit" \> notify-to "Territory" \[based on Territory default wise\] "Restaurant Cashier" and does not has any Manager Role

18\. I will add more stages here if I missed Below FYI \> In BanCan, we managed this ArcPOS settings for Push Notification + ArcPOS Notification Token

19\. Stock Requisition: If Purpose = "Material Transfer" \> On "Pending" \> notify-to "Source Outlet" \[based on Territory default wise\] "ArcPOS Requisition Approver"

20\. Using Print format for POS web prints (ArcPOS Settings) with Custom Page size.

21\. Earlier was notify-to "Target Outlet"but should be notify-to "Source Outlet"

22\. Just add one more condition that, if document's "Difference" value NOT = 0

## Completed Scope Highlights (reported in source)

✓ Invoice- ORD-26-00942

✓ Same issue when discount is applied with PIN-

✓ After approval, when creating a stock transfer and deleting an item, the deleted item still appears in the stock transfer.

✓ Add territory for Sales Overview, Service Mode Analytics.

✓ Front: The button will view if the Invoice docstatus = 0 and this will be manage by PIN

✓ In the Invoice \> If All Item status NOT = "Preparing/Ready To Serve/Served" and Void triggered then the invoice will be auto delete in a Cron Job

✓ But if any of item's status = "Preparing/Ready To Serve/Served" and Void triggered then the invoice should not delete

✓ If in a Invoice all item are "Prepare At" = "Front" or "Kitchen" then the order should only view in the specific Front or Kitchen list

✓ Only if all the item's status is "Preparing or Ready to Serve" then update the Order Status "Preparing or Ready to Serve"

✓ If the item's "Is BOM Item" is YES, only then the Work Order will execute (Re-Verify)

*Note: 64 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

## Follow-up Comments / Additional Scope

**Comment 1 - Emraz-MH (2026-06-02):** 9 checked / 0 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/46#issuecomment-4600698553)

• This Email setup is missing in the ArcPOS Settings

• All the Emails and Push/Socket Notifications must send as per default territory permission. Currently all specific users are getting the notifications.

• List page data and Details-update permission must be validate as per Outlet (Source and Target), not as per document's territory.

• TRIN document territory should be acceptors default territory

**Comment 2 - Emraz-MH (2026-06-11):** 4 checked / 2 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/46#issuecomment-4677418768)

• Stock Requisition: If Purpose = "Material Transfer" \> On "Pending" \> notify-to "Source Outlet" \[based on Territory default wise\] "ArcPOS Requisition Approver"

• Using Print format for POS web prints (ArcPOS Settings) with Custom Page size.

**Comment 3 - Emraz-MH (2026-06-14):** 11 checked / 2 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/46#issuecomment-4701521677)

• Earlier was notify-to "Target Outlet"but should be notify-to "Source Outlet"

• Just add one more condition that, if document's "Difference" value NOT = 0

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 28. GitHub Issue \#45: Meeting Topics 05-05-2026

| **GitHub State**     | CLOSED                                               | **Classification**       | Mixed: defect, requirement, and decision backlog |
|----------------------|------------------------------------------------------|--------------------------|--------------------------------------------------|
| **Assignee(s)**      | Unassigned                                           | **Labels**               | None                                             |
| **Checklist Status** | 0 checked / 9 unchecked                              | **Evidence refs**        | 0                                                |
| **QA Risk**          | Medium-High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High                        |
| **Created**          | 2026-05-06                                           | **Last Updated**         | 2026-07-01                                       |

## Professional Summary

GitHub issue \#45 is a mixed: defect, requirement, and decision backlog covering the areas described in the source issue. The source issue is currently closed and contains 0 checked/completed checklist item(s) and 9 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 9 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/45</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/45)

## Source-Derived Expected / Required Behavior Indicators

• SD % show like VAT; if not available, then hide

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 9 unchecked source item(s).**

1\. Table change impact is not happening

2\. New feature: Split selected items + qty to multiple order / move to other table temporarily

3\. Wastage / gift item amount on edit fetching actual rate

4\. SD % show like VAT; if not available, then hide

5\. Credit sales issue with customer change, on update

6\. Front order decision from them

7\. New feature: Material request for purchase

8\. Readiness for actual production environment and share credentials with them

9\. Test Desktop app on their POS machine

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 29. GitHub Issue \#42: POS- Desktop Issues- After 5th May

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed: Bug + Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | binshahed                                     | **Labels**               | bug, enhancement          |
| **Checklist Status** | 48 checked / 3 unchecked                      | **Evidence refs**        | 30                        |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-05-05                                    | **Last Updated**         | 2026-06-03                |

## Professional Summary

GitHub issue \#42 is a mixed: bug + enhancement covering POS, Orders, SD/VAT, Dark mode, Front Orders. The source issue is currently closed and contains 48 checked/completed checklist item(s) and 3 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 3 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/42</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/42)

## Affected Modules / Areas

POS, Orders, SD/VAT, Dark mode, Front Orders, PIN, Clock in/out

## Source-Derived Actual / Observed Behavior Indicators

• While editing a draft order, when a new mixed item is added, the system does not allow increasing the quantity of that item.

• In draft order edit when user tries to remove the last item it should show a proper error message- Cannot remove the last item. Plese void the order.

• -- The error message comes from Backend. Skipping now

• Selecting PIN is showing unknown error in offline mode.

• Showing this error when trying to make payment of a draft order created with credit sales- Not allowed to change Grand Total after submission from.

• Quick adding/removing items in the Draft order, works slowly also sometimes missed some items to add in the cart.

## Source-Derived Expected / Required Behavior Indicators

• DRAFT EDIT- Table change impact is not happening- If table has been changed to another Available Table, then the earlier table must be Available and next one should be Occupied with link the Order no on order update.

• User can make the change of Default outlet only from the Homepage other wise disable the field.

• Issue Type except REGULAR item should show as per select in the Cart/Print and should save as 0 rate in the invoice.

• How the Credit Sales button works? If the customer "Allowed Credit Sales" = 1, then the button should show and functional.

• In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item.

• While editing a draft order, when a new mixed item is added, the system does not allow increasing the quantity of that item.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 3 unchecked source item(s).**

1\. Order update and Data Sync- Please optimize the performance.

2\. SKIP OFFLINE work pending.

3\. When the user comes online from offline, the clock-in/clock-out modal flashes onto the screen for a second.

## Completed Scope Highlights (reported in source)

✓ Login page-

✓ In next update while login dont keep the username and password.

✓ DRAFT EDIT- Table change impact is not happening- If table has been changed to another Available Table, then the earlier table must be Available and next one should be Occupied with link the Order no on order update.

✓ User can make the change of Default outlet only from the Homepage other wise disable the field.

✓ Cash Open/Closing with Cash Drawer functionality check

✓ Issue Type except REGULAR item should show as per select in the Cart/Print and should save as 0 rate in the invoice.

✓ How the Credit Sales button works? If the customer "Allowed Credit Sales" = 1, then the button should show and functional.

✓ PIN- System Manager / ArcPOS Manager/ Restaurant Manager these role users won't have to enter PIN anywhere.

✓ In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item.

✓ While editing a draft order, when a new mixed item is added, the system does not allow increasing the quantity of that item.

*Note: 38 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 30. GitHub Issue \#40: Cash Opening/Closing Feature - WC

| **GitHub State**     | OPEN                                          | **Classification**       | Functional Requirement / Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                  |
| **Checklist Status** | 0 checked / 26 unchecked                      | **Evidence refs**        | 0                                     |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | P1-P2 (recommended; verify with team) |
| **Created**          | 2026-05-04                                    | **Last Updated**         | 2026-05-04                            |

## Professional Summary

GitHub issue \#40 is a functional requirement / enhancement covering The Functional Process (Logic Flow), Validations. The source issue is currently open and contains 0 checked/completed checklist item(s) and 26 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/40</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/40)

## Affected Modules / Areas

The Functional Process (Logic Flow), Validations

## Source-Derived Actual / Observed Behavior Indicators

• If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason.

## Source-Derived Expected / Required Behavior Indicators

• IF YES: The user is redirected to the general POS operation LIKE HOME Page.

• The user will press the button “Open Cash Drawer” and must count the physical cash in the drawer and enter it into the "Opening Amount". \> \[Just show the “Open Cash Drawer" button, no functionality for now\]

• If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason.

• If Diff = (+) = Then Cash Debit and Default Company \> Sales default income acc Credit

• If Diff = (-) = Then Cash Credit and Default Company \> “Default Deferred Expense Account” acc Debit

• The system should records all cash transactions during the shift in the GL Entry.

## Outstanding / Unchecked Items

1\. When a "Restaurant Cashier" logs into the POS, the system performs a background check:

2\. Search for a "Daily Cash Audit" entry for the "Current Date" and "Counter" where Submission Type == Clock In.

3\. IF NO: The "Clock In" modal pops up immediately. The general POS operation screen remains locked/hidden.

4\. IF YES: The user is redirected to the general POS operation LIKE HOME Page.

5\. The "Expected Opening Cash" = \[Cash account "Debit - Credit"\] of that counter

6\. The user will press the button “Open Cash Drawer” and must count the physical cash in the drawer and enter it into the "Opening Amount". \> \[Just show the “Open Cash Drawer" button, no functionality for now\]

7\. If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason.

8\. If the Logged user role = "Restaurant Cashier" then user can't submit the entry, pass the Draft to Submit (Approve) by Role user "Restaurant Manager"

9\. Once Approve by "Restaurant Manager" \> the cashier can start POS operation as the below conditions matched.

10\. Upon submission, the entry is saved, and the POS is unlocked for sales.

11\. If Diff = (+) = Then Cash Debit and Default Company \> Sales default income acc Credit

12\. If Diff = (-) = Then Cash Credit and Default Company \> “Default Deferred Expense Account” acc Debit

13\. Will Submit a Journal Entry automatically

14\. The system should records all cash transactions during the shift in the GL Entry.

15\. Before leaving, the user selects Clock Out.

16\. The system calculates the Expected Closing Cash using the formula in Backend:

17\. Cash account Debit - Credit + Cash Sales = Expected Closing Cash.

18\. The user performs a physical count as the same process of "Clock In".

19\. Once submitted, the user is permitted to log out.

20\. A cashier cannot open a new shift if a previous shift on the same counter was never "Clocked Out."

21\. Every "Reason" provided for a difference is flagged for Manager review in the backend.

22\. Use multi approval \> “Restaurant Manager” will Approve the Request from “Daily Cash Audit” list page.

23\. "Daily Cash Audit" module is only allowed for "Restaurant Manager" and can edit "Submitted Amount" and "Reason" in Draft.

24\. Send Notification to the “Restaurant Manager” on create DRAFT if found Diff.

25\. Cash Drawer Integration must be linked with each Counter.

26\. Without Clock In entry for "Current Date" and "Counter" should not allow to create any Cash Payment.

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 31. GitHub Issue \#32: BACKEND PENDING ISSUES- POS WEB AND DESKTOP- 29th April

| **GitHub State**     | CLOSED                                        | **Classification**       | Bug / Defect              |
|----------------------|-----------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | dev-Anamul                                    | **Labels**               | bug                       |
| **Checklist Status** | 5 checked / 1 unchecked                       | **Evidence refs**        | 2                         |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-04-29                                    | **Last Updated**         | 2026-09-24                |

## Professional Summary

GitHub issue \#32 is a bug / defect covering Kitchen Orders, Stock Requisition, Reports. The source issue is currently closed and contains 5 checked/completed checklist item(s) and 1 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 1 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/32</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/32)

## Affected Modules / Areas

Kitchen Orders, Stock Requisition, Reports

## Source-Derived Actual / Observed Behavior Indicators

• After order payment the Account Paid To is not working as expected.

• Kitchen orders are showing in the front order section, and front orders are appearing in the kitchen order section. The filtering functionality is not working as expected.

• Source Outlet and Target Outlet is showing blank when Stock Requisition is created from frappe.

## Source-Derived Expected / Required Behavior Indicators

• Add territory for Sales Overview, Service Mode Analytics.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 1 unchecked source item(s).**

1\. After approval, when creating a stock transfer and deleting an item, the deleted item still appears in the stock transfer.

## Completed Scope Highlights (reported in source)

✓ After order payment the Account Paid To is not working as expected.

✓ Kitchen orders are showing in the front order section, and front orders are appearing in the kitchen order section. The filtering functionality is not working as expected.

✓ Created By and Accepted By API pending.

✓ Source Outlet and Target Outlet is showing blank when Stock Requisition is created from frappe.

✓ Add territory for Sales Overview, Service Mode Analytics.

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 32. GitHub Issue \#30: Meeting Topics April 22, 2026

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed: defect, requirement, and decision backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                             |
| **Checklist Status** | 18 checked / 4 unchecked                      | **Evidence refs**        | 0                                                |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High                        |
| **Created**          | 2026-04-28                                    | **Last Updated**         | 2026-07-01                                       |

## Professional Summary

GitHub issue \#30 is a mixed: defect, requirement, and decision backlog covering the areas described in the source issue. The source issue is currently closed and contains 18 checked/completed checklist item(s) and 4 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 4 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/30</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/30)

## Source-Derived Expected / Required Behavior Indicators

• – Fixed, just need to rename the Cafe name from ArcPOS Settings.

• – We will remove the auto Delete functionality from Backend.

• Variant show as single item and show choice

• – Fixed, Need allow in BOM item & Publish to POS for variants

• Variant show with Display name

• – Fixed, Need to work on Desktop app

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 4 unchecked source item(s).**

1\. Order Void for prepared recipe invoice and keep track: permission for senior manager

2\. Coffee and drinks front e prepare, will not go to kitchen, split view for kitchen

3\. Ready to Serve order to POS notification

4\. ISD branch / Sell from ready stock process discuss, fixed items which may have recipe to prepare but will always be sold from ready stock from all outlets?i.e cheese cake slices

## Completed Scope Highlights (reported in source)

✓ Cafe name: The White Canary Café

✓ VAT & SD with Discount calculation will be provided by Jabed Bhai

✓ Variant show as single item and show choice

✓ Variant show with Display name

✓ All day captain America breakfast double item choice

✓ VAT & SD account different for outlets

✓ Complementary, Gift, Wastage

✓ Baking Prep and sell as single item? yes

✓ Credit sales differentiate flag for customer profile

✓ Discount 10/15/30/35, custom permission for senior manager

*Note: 8 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Follow-up Comments / Additional Scope

**Comment 1 - Emraz-MH (2026-04-29):** 3 checked / 0 unchecked checklist item(s). [<u>Open comment</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/30#issuecomment-4340808992)

• Outlet Counter wise Cash Account on Payment

• Counter Data in Sales invoice and Payment Entry

• Show the "Web Rate" for each item \> Web Item will be auto calculated and set to the Selling price.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 33. GitHub Issue \#18: POS WEB MODIFICATIONS- After 19th April

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | arifjahan88                                   | **Labels**               | None                                 |
| **Checklist Status** | 44 checked / 5 unchecked                      | **Evidence refs**        | 16                                   |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-04-19                                    | **Last Updated**         | 2026-05-06                           |

## Professional Summary

GitHub issue \#18 is a mixed qa defect / correction backlog covering Stock Requisition, Outlet Wise Permission- \[Emraz Bhai\], ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first, Kitchen Orders, Recipes. The source issue is currently closed and contains 44 checked/completed checklist item(s) and 5 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 5 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/18</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/18)

## Affected Modules / Areas

Stock Requisition, Outlet Wise Permission- \[Emraz Bhai\], ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first, Kitchen Orders, Recipes, Stock Transfer, Wastage Management

## Source-Derived Actual / Observed Behavior Indicators

• Kitchen orders- Items issued with PIN is not showing here.

• - After approving a stock requisition, if the user does not have permission for the specific Source Outlet, they should not be able to create a transfer from that outlet.

• Orders made with credit sales are showing an error when accepting them from kitchen orders

• Source outlet and target outlet filter not working

• The time in Stock Ledger is showing wrong time after a draft submission.

• Remarks is not updating when a draft entry is submitted.

## Source-Derived Expected / Required Behavior Indicators

• Remove Add Item button while creating transfer.

• In Required By date picker past dates should be disabled.

• Cancle button should not be shown when status is Completed

• Need to work on Not Started status- when a stock transfer created from Stock Requisition is cancelled. Also add in status filter.

• Need to work on outlet wise permission.

• - After approving a stock requisition, if the user does not have permission for the specific Source Outlet, they should not be able to create a transfer from that outlet.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 5 unchecked source item(s).**

1\. \[Screenshot/evidence attached in GitHub issue\]

2\. Kitchen orders- Items issued with PIN is not showing here.

3\. In Order details the items issued with PIN is also showing price.

4\. Need to work on Not Started status- when a stock transfer created from Stock Requisition is cancelled. Also add in status filter.

5\. System should not allow selecting the same outlet as both the source outlet and target outlet.

## Completed Scope Highlights (reported in source)

✓ Fix the status filter.

✓ Remove Add Item button while creating transfer.

✓ In Required By date picker past dates should be disabled.

✓ Cancle button should not be shown when status is Completed

✓ Fix the back button icon-

✓ Need to work on outlet wise permission.

✓ Orders- Restaurant Cashier,Restaurant Manager, ArcPOS Manager, System Manager, Restaurant Waiter

✓ Kitchen Orders- Restro Kitchen Staff, Restaurant Chef

✓ Recipes- ArcPOS Recipe User

✓ Stock Requisition-

*Note: 34 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 34. GitHub Issue \#14: Desktop Modifications- After 16th April

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 42 checked / 1 unchecked                      | **Evidence refs**        | 32                                   |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-04-16                                    | **Last Updated**         | 2026-05-06                           |

## Professional Summary

GitHub issue \#14 is a mixed qa defect / correction backlog covering POS, ORDERS. The source issue is currently closed and contains 42 checked/completed checklist item(s) and 1 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 1 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/14</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/14)

## Affected Modules / Areas

POS, ORDERS

## Source-Derived Actual / Observed Behavior Indicators

• When payment fails and the payment status remains unpaid, the order status incorrectly changes to closed instead of staying as draft.

• This error message should be shown when user tries to remove the only item left from an order- At least one item is required in the order.

• The Discount and VAT is not showing in the receipt.

• On sync error is showing in this format

• In order EDIT discount is resetting back to Zero.

• Sync button shows loading for all orders

## Source-Derived Expected / Required Behavior Indicators

• Add a confirmation modal when the user attempts to navigate to another page without saving the order-

• In Payment, Payment method dropdown data should be fetched from Mode of Payment.

• In Edit Order, adding a customer with a Default Discount Percentage still shows the discount as 0 instead of applying the configured default discount.

• Rename this filter to Outlet and All Outlets-

• This error message should be shown when user tries to remove the only item left from an order- At least one item is required in the order.

• When the print modal is dismissed (by clicking outside or auto-closing), the user is not redirected to the select table page as expected.

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 1 unchecked source item(s).**

1\. On sync error is showing in this format

## Completed Scope Highlights (reported in source)

✓ Add a confirmation modal when the user attempts to navigate to another page without saving the order-

✓ In Payment, Payment method dropdown data should be fetched from Mode of Payment.

✓ When payment fails and the payment status remains unpaid, the order status incorrectly changes to closed instead of staying as draft.

✓ In Edit Order, adding a customer with a Default Discount Percentage still shows the discount as 0 instead of applying the configured default discount.

✓ Rename this filter to Outlet and All Outlets-

✓ This error message should be shown when user tries to remove the only item left from an order- At least one item is required in the order.

✓ When the print modal is dismissed (by clicking outside or auto-closing), the user is not redirected to the select table page as expected.

✓ In table order edit, when the order status is updated from POS web, only the order status refreshes while the item status remains outdated until the page is reloaded again.

✓ While creating new order show only Pay button for Pay First.

✓ Add VAT and Discount in this

*Note: 32 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test online/offline transitions, pending sync recovery, conflict handling, and UI state restoration.

• Re-test print content, formatting, payment breakdown, printer/cash-drawer triggers, and behavior when printing is slow or unavailable.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 35. GitHub Issue \#12: Corrections \#2 \> POS Web

| **GitHub State**     | CLOSED                                               | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|------------------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | arifjahan88                                          | **Labels**               | None                                 |
| **Checklist Status** | 4 checked / 0 unchecked                              | **Evidence refs**        | 2                                    |
| **QA Risk**          | Medium-High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-04-15                                           | **Last Updated**         | 2026-05-06                           |

## Professional Summary

GitHub issue \#12 is a mixed qa defect / correction backlog covering the areas described in the source issue. The source issue is currently closed and contains 4 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/12</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/12)

## Source-Derived Actual / Observed Behavior Indicators

• Showing "Somthing Wrong" while trying to make the item status as "Ready to Serve"

## Source-Derived Expected / Required Behavior Indicators

• All the "Search" fields, must query on "Enter" trigger

• If the BOM \> Is Prep Item = 1 and "Allow to update Qty = 0" then should not show or work the "+/-" buttons.

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ All the "Search" fields, must query on "Enter" trigger

✓ Any kinds of update in the Sales Invoice, it's changing the Invoice Posting Date.

✓ If the BOM \> Is Prep Item = 1 and "Allow to update Qty = 0" then should not show or work the "+/-" buttons.

✓ Showing "Somthing Wrong" while trying to make the item status as "Ready to Serve"

## QA Impact & Retest Guidance

• Re-test the exact source-listed behaviors and confirm no regression in adjacent order, stock, permission, and navigation flows.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 36. GitHub Issue \#10: Corrections \#1 \> Desktop

| **GitHub State**     | CLOSED                                        | **Classification**       | Mixed QA Defect / Correction Backlog |
|----------------------|-----------------------------------------------|--------------------------|--------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                 |
| **Checklist Status** | 14 checked / 2 unchecked                      | **Evidence refs**        | 2                                    |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High            |
| **Created**          | 2026-04-15                                    | **Last Updated**         | 2026-05-06                           |

## Professional Summary

GitHub issue \#10 is a mixed qa defect / correction backlog covering the areas described in the source issue. The source issue is currently closed and contains 14 checked/completed checklist item(s) and 2 unchecked/pending item(s) across the issue body and comments. Because the issue is closed while 2 checklist item(s) remain unchecked, this report flags a closure/traceability inconsistency that should be reviewed before treating the scope as fully verified.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/10</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/10)

## Source-Derived Actual / Observed Behavior Indicators

• Order Status missing in the List page. Keep the same as BanCan POS Order List

• Item status functionality missing in the order edit/update. Keep the same as BanCan POS

• Cash Open/Closing with Cash Drawer functionality missing. Keep the same as BanCan POS, we will make correction after.

## Source-Derived Expected / Required Behavior Indicators

• If any user has no permission of "Territory" then show after login Toast "You have no territory permission, please contact your administrator"

• Show user's avatar/Image

• No need to show "Home" button. On click "Logo" will redirect to the Home page.

• Show Table Image if there are any image is linked otherwise show as default current icon.

• Rename "Tax" to "VAT"

• Remove "Company name" value and what is the Square portion marked in below image?

## Outstanding / Unchecked Items

**Closure discrepancy: this CLOSED issue still contains 2 unchecked source item(s).**

1\. Cash Open/Closing with Cash Drawer functionality missing. Keep the same as BanCan POS, we will make correction after.

2\. I will add hare other findings.................................

## Completed Scope Highlights (reported in source)

✓ If any user has no permission of "Territory" then show after login Toast "You have no territory permission, please contact your administrator"

✓ Check \> "POS and Orders" module only allowed for Frappe Role: ArcPOS Manager, Restaurant Cashier, Restaurant Manager and System Manager"

✓ Show user's avatar/Image

✓ Dark Mode Logo issue

✓ No need to show "Home" button. On click "Logo" will redirect to the Home page.

✓ Show Table Image if there are any image is linked otherwise show as default current icon.

✓ Order Status missing in the List page. Keep the same as BanCan POS Order List

✓ Item status functionality missing in the order edit/update. Keep the same as BanCan POS

✓ Home page view, can we keep the same view as the BanCan POS home page?

✓ Order list: Bold font for "Order No"

*Note: 4 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test monetary calculations, payment creation, due/paid state, and receipt/report totals for data integrity.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 37. GitHub Issue \#8: Features and Functionality - Internal

| **GitHub State**     | OPEN                                          | **Classification**       | Functional Requirement / Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                  |
| **Checklist Status** | 0 checked / 20 unchecked                      | **Evidence refs**        | 0                                     |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | P1-P2 (recommended; verify with team) |
| **Created**          | 2026-04-09                                    | **Last Updated**         | 2026-04-09                            |

## Professional Summary

GitHub issue \#8 is a functional requirement / enhancement covering Kitchen Order, Production, Stock Transfer, Wastage Management. The source issue is currently open and contains 0 checked/completed checklist item(s) and 20 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/8</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/8)

## Affected Modules / Areas

Kitchen Order, Production, Stock Transfer, Wastage Management

## Source-Derived Expected / Required Behavior Indicators

• Show only the invoices data if "Order Status = Accepted/Waiting/In kitchen/Preparing" + docstatus NOT = 2

• User Permission: If No permission for "Territory" then show all vouchers, If there are "Territory" permission exists then show only permitted "Territory"s vouchers & if there are "Territory" permission exists + "is_default = 1" then show only the default "Territory"s vouchers

• "Process Recipe" button should show if only "ArcPOS settings \> Allowed Production? = 1 + Role: ArcPOS Recipe User/Restaurant Manager/System Manager+ Item Maintain Stock = 1 + Is BOM Item = 1"

• Should show if only "ArcPOS settings \> Allowed Production? = 1 + Role: ArcPOS Recipe User/ArcPOS Recipe Approver/Restaurant Manager/System Manager/ArcPOS Manager"

• Should show if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager"

• For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "customlinkedoutlet" & if there are "Territory" permission exists + "isdefault = 1" then show only the default "Territory"s which are linked with Warehouse "customlinked_outlet". Note: Warehouse Type = Transit should not show or select.

## Outstanding / Unchecked Items

1\. Login user Frappe Role has : Restaurant Chef, Restro Kitchen Staff, System Manager, Restaurant Manager, ArcPOS Manager

2\. Show only the invoices data if "Order Status = Accepted/Waiting/In kitchen/Preparing" + docstatus NOT = 2

3\. Update on DateTime Desc.

4\. User Permission: If No permission for "Territory" then show all vouchers, If there are "Territory" permission exists then show only permitted "Territory"s vouchers & if there are "Territory" permission exists + "is_default = 1" then show only the default "Territory"s vouchers

5\. "Process Recipe" button should show if only "ArcPOS settings \> Allowed Production? = 1 + Role: ArcPOS Recipe User/Restaurant Manager/System Manager+ Item Maintain Stock = 1 + Is BOM Item = 1"

6\. Should show if only "ArcPOS settings \> Allowed Production? = 1 + Role: ArcPOS Recipe User/ArcPOS Recipe Approver/Restaurant Manager/System Manager/ArcPOS Manager"

7\. Should show if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager"

8\. For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "customlinkedoutlet" & if there are "Territory" permission exists + "isdefault = 1" then show only the default "Territory"s which are linked with Warehouse "customlinked_outlet". Note: Warehouse Type = Transit should not show or select.

9\. For Target Warehouse: Show all warehouse except the selected Warehouse and Warehouse Type = Transit

10\. New created Transfer can be Accept or Return

11\. Workflow Example: If Source Warehouse = Store & Target Warehouse = Good Stock then on submit the items will be send to the "Warehouse Type = Transit" warehouse and on "Accept" the following items will be transfer from "Warehouse Type = Transit" warehouse to "Target Warehouse = Good Stock"

12\. We need a list page of Stock Entry: Filter of voucher \> Stock Entry Type = Material Transfer + Voucher No Desc.

13\. To Create \> Frappe Has Role "ArcPOS Transfer Creator/Restaurant Manager/System Manager/ArcPOS Manager"

14\. After Create: Frappe Has Role "ArcPOS Transfer Creator/Restaurant Manager/System Manager/ArcPOS Manager" will get "Approve/Reject" Button \> On "Approve", the TROUT will be submitted & On "Reject" the voucher will be READ ONLY

15\. After "Approve" \> Status will be "In Transit" and the Frappe Has Role "ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" will get the button "Accept/Return" buttons

16\. On "Accept" \> An TRIN will create under the TROUT and On "Return" An BTRIN will create.

17\. If BTRIN \> Frappe Role: "ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" will get only "Accept" button

18\. Should show if only Role: ArcPOS Stock User/ArcPOS PCM Creator/ArcPOS PCM Approver/Restaurant Manager/System Manager/ArcPOS Manager"

19\. For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "customlinkedoutlet" & if there are "Territory" permission exists + "isdefault = 1" then show only the default "Territory"s which are linked with Warehouse "customlinked_outlet"

20\. We need a list page of Stock Entry: Filter of voucher \> Stock Entry Type = Material Issue + Voucher No Desc.

## QA Impact & Retest Guidance

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 38. GitHub Issue \#7: Functionality 1

| **GitHub State**     | OPEN                                          | **Classification**       | Functional Requirement / Enhancement  |
|----------------------|-----------------------------------------------|--------------------------|---------------------------------------|
| **Assignee(s)**      | Unassigned                                    | **Labels**               | None                                  |
| **Checklist Status** | 0 checked / 42 unchecked                      | **Evidence refs**        | 0                                     |
| **QA Risk**          | High (QA-inferred; verify with product owner) | **Recommended Priority** | P1-P2 (recommended; verify with team) |
| **Created**          | 2026-04-09                                    | **Last Updated**         | 2026-04-09                            |

## Professional Summary

GitHub issue \#7 is a functional requirement / enhancement covering the areas described in the source issue. The source issue is currently open and contains 0 checked/completed checklist item(s) and 42 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/7</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/7)

## Source-Derived Actual / Observed Behavior Indicators

• The "Source Outlet" value will be auto load for the set "Default Territory" and the "Target Outlet" will be Blank. User will search and select the "Target Outlet"

## Source-Derived Expected / Required Behavior Indicators

• Should show if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager"

• The "Source Outlet" value will be auto load for the set "Default Territory" and the "Target Outlet" will be Blank. User will search and select the "Target Outlet"

• Multiple Item should allow to add in the Item Table and Quantity must me minimum 1.

• Add to Transit = 1

• Default Source Warehouse = Source Outlet's Warehouse

• Default Target Warehouse = ArcPOS Settings \> Default In Transit Warehouse

## Outstanding / Unchecked Items

1\. - Allowed if

2\. Should show if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager"

3\. On new creation:

4\. The "Source Outlet" value will be auto load for the set "Default Territory" and the "Target Outlet" will be Blank. User will search and select the "Target Outlet"

5\. Multiple Item should allow to add in the Item Table and Quantity must me minimum 1.

6\. On Create/Draft button trigger \> Pass to frappe with

7\. Territory = Set Territory

8\. Naming Series = TROUT

9\. Stock Entry Type = Stock Transfer

10\. Add to Transit = 1

11\. Posting Date and Time = Creation Date

12\. Default Source Warehouse = Source Outlet's Warehouse

13\. Default Target Warehouse = ArcPOS Settings \> Default In Transit Warehouse

14\. Actual Target Warehouse = Target Outlet's Warehouse

15\. Items Table= Items

16\. Remarks = Remarks

17\. Docstatus = As per "Create=1/Draft=0"

18\. If Draft \> will covert the page in a Details page and show Edit and Create/Submit button. In the list page, Status will be "Draft"

19\. If Create \> will redirect to the List page and Status will be "In Transit"

20\. "In Transit" \> In the details page \> All will be Read only and show button "Accept", "Cancel" \[Cancel button will show all DocStatus = 1 and only allowed for System Manager"\] and "Return" \[Skip the Return Policy for now\]

21\. On "Accept" \> Pass to frappe with

22\. Territory = Set Territory

23\. Naming Series = TRIN

24\. Stock Entry Type = Stock Transfer

25\. Posting Date and Time = Creation Date

26\. Default Source Warehouse = The tagged TROUT's "Default Target Warehouse"

27\. Default Target Warehouse = The tagged TROUT's "Actual Target Warehouse"

28\. Items Table= Items

29\. Docstatus = 1

30\. On "Return" \> Pass to frappe with

31\. In the The tagged TROUT \> Update with "Is Returned? = 1"

32\. For the New Stock Entry:

33\. Territory = Set Territory

34\. Naming Series = BTRIN

35\. Stock Entry Type = Stock Transfer

36\. Posting Date and Time = Creation Date

37\. Default Source Warehouse = The tagged TROUT's "Default Target Warehouse"

38\. Default Target Warehouse = The tagged TROUT's "Default Source Warehouse"

39\. Items Table= Items

40\. Docstatus = 1

41\. Returned From = The tagged TROUT's ID/Voucher No

42\. Except Draft, all the other button trigger will redirect to the refreshed List page.

## QA Impact & Retest Guidance

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test positive and negative authorization paths for each specified role, PIN/session state, and outlet/territory permission.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# 39. GitHub Issue \#6: WC - Web - 09-04-2026

| **GitHub State**     | CLOSED                                               | **Classification**       | Mixed: Bug + Enhancement  |
|----------------------|------------------------------------------------------|--------------------------|---------------------------|
| **Assignee(s)**      | arifjahan88                                          | **Labels**               | bug, enhancement          |
| **Checklist Status** | 33 checked / 0 unchecked                             | **Evidence refs**        | 0                         |
| **QA Risk**          | Medium-High (QA-inferred; verify with product owner) | **Recommended Priority** | Regression Priority: High |
| **Created**          | 2026-04-09                                           | **Last Updated**         | 2026-05-06                |

## Professional Summary

GitHub issue \#6 is a mixed: bug + enhancement covering the areas described in the source issue. The source issue is currently closed and contains 33 checked/completed checklist item(s) and 0 unchecked/pending item(s) across the issue body and comments.

**Traceability:** [<u>https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/6</u>](https://github.com/Excel-Technologies-Ltd/white-canary-POS/issues/6)

## Source-Derived Actual / Observed Behavior Indicators

• Switch Territory missing

## Source-Derived Expected / Required Behavior Indicators

• Add Logo (As per ArcPOS Settiings"

• Remove " Forgot"

• Remove "Accept terms and Condition"

• Add "Title, Title 2 and Description" as same as BanCan. You can keep the same view.

• Rename "Username" to "Username or Email"

• Add Search and Filters:

## Outstanding / Unchecked Items

No unchecked checklist items were found in the issue body/comments.

## Completed Scope Highlights (reported in source)

✓ Name the browser tab as "ArcPOS"

✓ After Logout, correct the toast text to "Logout Successful"

✓ After Login, correct the toast text to "Login Successful"

✓ Switch Territory missing

✓ Add Logo (As per ArcPOS Settiings"

✓ Remove " Forgot"

✓ Remove "Accept terms and Condition"

✓ Add "Title, Title 2 and Description" as same as BanCan. You can keep the same view.

✓ Replace Sign In text to "Login"

✓ Rename "Username" to "Username or Email"

*Note: 23 additional checked item(s) exist in the source issue/comments and are covered by the checklist totals above.*

## QA Impact & Retest Guidance

• Re-test source/target outlet permissions, stock quantity validation, document status transitions, and stock-ledger effects.

• Re-test filters, outlet/territory scoping, date ranges, totals, export/PDF output, and print header/footer content.

• Re-test desktop/mobile layouts, dark mode, disabled-state visibility, modal alignment, and action-button states.

## Source Completeness / Limitations

Environment/build identifiers, exact reproduction prerequisites, and root cause are not consistently present in the exported GitHub source. Where absent, this report intentionally does not invent them. Screenshots/attachments referenced by the source remain available through the original GitHub issue links.

# Appendix A. Closed Issues with Unchecked Checklist Items

| **Issue** | **Title**                                               | **Unchecked Items** | **Action**                                                                       |
|-----------|---------------------------------------------------------|---------------------|----------------------------------------------------------------------------------|
| \#70      | Corrections \> 07-09-2026                               | 3                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#67      | Corrections \> 10-08-2026                               | 26                  | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#64      | Backend Issue \> 25-07-2026                             | 6                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#60      | POS WEB \> 14-06-2026                                   | 1                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#59      | Desktop \> 08-06-2026                                   | 2                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#52      | POS Web \> 21-05-2026                                   | 53                  | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#51      | Desktop - 18-05-2026                                    | 1                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#48      | Order Split Functionality                               | 7                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#47      | POS WEB MODIFICATIONS- After 5th May                    | 2                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#45      | Meeting Topics 05-05-2026                               | 9                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#42      | POS- Desktop Issues- After 5th May                      | 3                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#32      | BACKEND PENDING ISSUES- POS WEB AND DESKTOP- 29th April | 1                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#30      | Meeting Topics April 22, 2026                           | 4                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#18      | POS WEB MODIFICATIONS- After 19th April                 | 5                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#14      | Desktop Modifications- After 16th April                 | 1                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |
| \#10      | Corrections \#1 \> Desktop                              | 2                   | Review closure status; verify/resolve or explicitly mark deferred/ignored items. |

# Appendix B. Open GitHub Issues

• \#73 - Corrections \> 23-09-2026 (3 checked / 0 unchecked)

• \#61 - Epson TM-T81III Printer and QZ Tray Cash Drawer Setup Guide for Windows 11 (0 checked / 0 unchecked)

• \#57 - POS- WEB Ordering Process - 7th June (47 checked / 8 unchecked)

• \#50 - POS - Desktop - 14-05-2026 (10 checked / 1 unchecked)

• \#46 - Backend Issues - After 06-05-2026 (74 checked / 22 unchecked)

• \#40 - Cash Opening/Closing Feature - WC (0 checked / 26 unchecked)

• \#8 - Features and Functionality - Internal (0 checked / 20 unchecked)

• \#7 - Functionality 1 (0 checked / 42 unchecked)
