# White Canary POS — Requirements, Defects & QA Review

> A reader-friendly product and QA specification covering defects, functional requirements, enhancements, operational setup, and verification items.

## 1. Document Purpose

This document consolidates the supplied White Canary POS work items into a single product/SQA reference. It intentionally separates **defects** from **requirements** so readers can understand whether an item describes incorrect current behavior or a requested/expected capability.

### How to read this document

- **Defect** — current behavior is incorrect, missing, inconsistent, failing, or producing an error.
- **Requirement** — expected behavior, business rule, workflow, UI change, permission rule, or new capability to be implemented.
- **Verification / Decision** — an item that requires confirmation, investigation, or a product/technical decision before implementation.
- **Documentation / Setup** — operational or environment configuration guidance rather than a product defect.
- **Pending** — not marked complete in the supplied source.
- **Implemented / Reported Complete** — marked complete in the supplied source; this report does not independently retest it.
- **Deferred** — explicitly marked to skip/ignore for now.

## 2. Overall Scope Summary

- **Work packages reviewed:** 37
- **Tracked checklist items:** 1018
- **Defects identified:** 463
- **Requirements identified:** 549
- **Verification / decision items:** 6
- **Documentation / setup items:** 0
- **Pending items:** 240
- **Deferred items:** 6
- **Implemented / reported complete items:** 772

## 3. Detailed Bugs, Requirements & Verification Scope

Each section below represents a coherent batch of product work. **Pending and deferred items are shown first** because they need attention. Completed items are retained in collapsible sections for regression and historical reference.

## 3.1 Corrections & Requirements — 23-09-2026

**Main functional focus:** Stock & Inventory  
**Content mix:** 1 defect(s), 2 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 3 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within stock & inventory.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### Business rules / contextual notes

- **Submit Button Allowed IF:** Frappe Role = "ArcPOS Transfer Creator"/"System Manager && DocStatus = 0 && Draft Entry = 1 && Selected Outlet = Target Outlet *(POS WEB > Stock Requisition)*
- **Approve Button Allowed IF:** Frappe Role = "ArcPOS Requisition Approverr"/" && DocStatus = 0 && Draft Entry = 0 && Selected Outlet = Target Outlet & target outlets combine approver *(POS WEB > Stock Requisition)*
- _I will add here new if found............._ *(POS WEB > Stock Requisition)*

### QA verification focus

- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (3 items)</strong></summary>

- **Requirement** — Rename the "Create" button to "Save" *(POS WEB > Stock Requisition)*
- **Defect** — When Allowing "Submit" button to the Creator, The "Edit" button is missing. *(POS WEB > Stock Requisition)*
- **Requirement** — When Allowing "Approve" button to the Approver, The "Edit" button will enabled/show (Check) *(POS WEB > Stock Requisition)*

</details>

## 3.2 Corrections & Requirements — 20/09/2026

**Main functional focus:** Backend / Frappe ERP  
**Content mix:** 3 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 3 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within backend / frappe erp.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.

<details>
<summary><strong>Implemented / reported complete scope (3 items)</strong></summary>

- **Defect** — For partial discount orders with a 0% discount customer, save the order as a Draft, then change the customer to one with a discount. After the first validation error occurs, the discount percentage resets back to 0%. *(Frontend)*
- **Defect** — For partial discount orders, when a discounted customer is selected, the following error is displayed: “No permission for discount on Sales Invoice. Ask a manager to enter their PIN for this action.” *(Frontend > Backend)*
- **Defect** — For partial discount orders, select a discounted customer and save the order as a Draft. Then change the customer to another discounted customer. An error is displayed, but if another SD + Discount item is added afterward, the invoice is updated according to the newly selected customer's discount. *(Frontend > Backend)*

</details>

## 3.3 Desktop Corrections & Requirements — 10-09-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 4 defect(s), 3 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 7 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify offline/online reconciliation and synchronization.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (7 items)</strong></summary>

- **Requirement** — Make the Print View (font) as like the "Swapno" print font. The fonts should be clear to see after print. *(Print View)*
- **Defect** — Payment breakdown data missing in the Receipt Print. *(Print View > Other corrections (17-08-2026))*
- **Requirement** — In Any kinds of update in the Territory from frappe doctype, and evenif the Territory Counter's `Last Status` = Open, It's forcing to Clock-IN where should allow to Clock-OUT. *(Print View > Other corrections (17-08-2026))*
- **Defect** — **Description:** When an online order containing PIN-restricted fields (such as Item Issue or Discount) fails to sync due to an expired PIN session, the error message instructs the user to start a PIN session. *(Print View > Other corrections (17-08-2026) > OFFLINE Order (New/Draft))*
- **Defect** — **Requirement:** Add a direct "Enter PIN" action button within trigger sync or On click Individual "Sync" button should appear PIN modal for this type of error orders. *(Print View > Other corrections (17-08-2026) > OFFLINE Order (New/Draft))*
- **Defect** — **Description:** If a sync error occurs while staying inside the active Order view, certain items temporarily disappear from the UI. However, navigating away and re-entering the Order restores and correctly displays all items. *(Print View > Other corrections (17-08-2026) > OFFLINE Order (New/Draft))*
- **Requirement** — The "Payment Information" data should fetch *(Print View > Other corrections (17-08-2026) > Order Details)*

</details>

## 3.4 Corrections & Requirements — 07-09-2026

**Main functional focus:** Stock & Inventory  
**Content mix:** 8 defect(s), 19 requirement(s), 1 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 25 implemented/reported complete, 3 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements, verification/decision points within stock & inventory.

### Pending / Deferred items

- **Requirement · Pending** — Option A *(Backend: > Frappe ERP > Validate Stock)*
- **Requirement · Pending** — If Frappe Default Stock Setting > "Allow Negative Stock" = NO *(Backend: > Frappe ERP > Validate Stock > Option A)*
- **Defect · Pending** — Review the related behavior and complete the referenced correction described elsewhere in the supplied source. *(Backend: > Frappe ERP > Stock Requisition)*

### Business rules / contextual notes

- Purpose *(Backend: > Frappe ERP)*
- Then "ArcPOS Settings > "Validate Stock?". If NO *(Backend: > Frappe ERP > Validate Stock)*
- Check first If Frappe Default Stock Setting > "Allow Negative Stock" = YES *(Backend: > Frappe ERP > Validate Stock)*
- Then "ArcPOS Settings > "Validate Stock?". If YES *(Backend: > Frappe ERP > Validate Stock)*
- Validate the "Source Warehouse" item wise current stock. if entered Transfer qty is greater then the current stock then throw error. *(Backend: > Frappe ERP > Validate Stock)*
- **Current Workflow** *(Material Request (Purpose = Material Transfer) > Workflow correction)*
- **Corrections of Workflow** *(Material Request (Purpose = Material Transfer) > Workflow correction)*
- **Email Trigger correction of "ArcPOS Settings > Notification > Stock Requisition Awaiting Approval"** *(Material Request (Purpose = Material Transfer) > Workflow correction > Frappe ERP (Customization) > Email and Socket Notification)*

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify responsive layout, dark mode and action-state behavior.
- Verify notifications, recipient selection and redirection.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (25 items)</strong></summary>

- **Requirement** — Add new Check field `Allow Update UOM?" under existing field "Allowed Production?" *(Backend: > Frappe ERP)*
- **Requirement** — Add new Check field `Validate Stock?" under existing field "Allow Update UOM?" *(Backend: > Frappe ERP)*
- **Requirement** — Add new Check field `Is Sales Outlet?" under existing field "Is Group". *(Backend: > Frappe ERP)*
- **Requirement** — Add new Multi-Select (User) field `POS Approvers" under existing field "Order Pay Default" + `Combined Approver` (Auto fetch from "POS Approvers" COMMA separated) to use them to send emails. *(Backend: > Frappe ERP)*
- **Requirement** — Add new "Section Break" under `items` *(Backend: > Frappe ERP)*
- **Requirement** — Add new Currency field *(Backend: > Frappe ERP)*
- **Requirement** — Add new Small Text field *(Backend: > Frappe ERP)*
- **Requirement** — Option B [Stock Transfer _(Including Manufacturing Transfer)_ & Wastage Management] *(Backend: > Frappe ERP > Validate Stock)*
- **Requirement** — Stock Entry on "SUBMIT" or "Item Qty entry from Web" *(Backend: > Frappe ERP > Validate Stock > Option B [Stock Transfer _(Including Manufacturing Transfer)_ & Wastage Management])*
- **Defect** — Review the related behavior and complete the referenced correction described elsewhere in the supplied source. *(Backend: > Frappe ERP > Payment Error)*
- **Defect** — When trying to force "Update Cost" manually, showing this error ```exc_type *(Backend: > Frappe ERP > BOM > Update Cost button)*
- **Defect** — Review the related behavior and complete the referenced correction described elsewhere in the supplied source. *(Backend: > Frappe ERP > Other corrections)*
- **Verification / Decision** — How these 2 field works and what's the functionality? *(Backend: > Frappe ERP > ArcPOS Settings > Permissions)*
- **Requirement** — As per "ArcPOS Settings > "Allow Update UOM?" > If NO, then make the UOM field READ ONLY. *(Backend: > Frappe ERP > Stock Requisition + Stock Transfer & Wastage Management)*
- **Requirement** — Rename "Add Row" to "Add Item" *(Backend: > Frappe ERP > Stock Requisition + Stock Transfer & Wastage Management)*
- **Requirement** — Without fill all other required fields, the "Add Item" & "Add Multiple" button should be disabled. *(Backend: > Frappe ERP > Stock Requisition + Stock Transfer & Wastage Management)*
- **Requirement** — Item selection dropdown has limit in the Item row? Manage to show all the matched options/Items. *(Backend: > Frappe ERP > Stock Requisition + Stock Transfer & Wastage Management)*
- **Defect** — In Mobile view: while searching any item in single word, its not appearing the dropdown until adding any space or another word. *(Backend: > Frappe ERP > Stock Requisition + Stock Transfer & Wastage Management > Item selection dropdown has limit in the Item row? Manage to show all the matched options/Items.)*
- **Defect** — "Create" button not showing in the Mobile view from list page. *(Backend: > Frappe ERP > Stock Requisition + Stock Transfer & Wastage Management)*
- **Requirement** — Allow only Frappe Role user "System Manager" to change the Outlet from any page. *(Backend: > Frappe ERP > Outlet change)*
- **Requirement** — The dropdown customer list should validate as per user's territory frappe permissions. *(Backend: > Frappe ERP > Order List page)*
- **Defect** — The filter is not working. *(Backend: > Frappe ERP > Order List page)*
- **Defect** — Pop modal: NOTE data view issue in Dark Mode *(Backend: > Frappe ERP > Recipe)*
- **Requirement** — Add new Check field `Draft Entry" before existing field "From Outlet". *(Material Request (Purpose = Material Transfer) > Workflow correction > Frappe ERP (Customization))*
- **Requirement** — If Purpose = "Material Transfer" > On "Draft" && `Draft Entry = 0` > notify-to users whose email addresses are configured under the Target Outlet/Territory's "Combined Approver" field && `Combined Approver(s)` who holds the role "ArcPOS Requisition Approver" *(Material Request (Purpose = Material Transfer) > Workflow correction > Frappe ERP (Customization) > Email and Socket Notification)*

</details>

## 3.5 Corrections & Requirements — 30-08-2026

**Main functional focus:** Reporting & Analytics  
**Content mix:** 2 defect(s), 11 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 13 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within reporting & analytics.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify notifications, recipient selection and redirection.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (13 items)</strong></summary>

- **Requirement** — New Report (WEB) > Item-wise Sales Register *(Backend:)*
- **Requirement** — Print in A4 (PDF), Thermal and export in Excel file. Below is the reference *(Backend: > New Report (WEB) > Item-wise Sales Register)*
- **Defect** — Split Order > Payment breakdown data missing in the Receipt Print. *(Backend:)*
- **Requirement** — Closing Email: All the precipitants should receive email in single email. (To and CC) *(Backend:)*
- **Requirement** — When an order Rounded Total/Grand Total is 0, somehow the "Outstanding Amount" showing in amount figure. *(Backend:)*
- **Requirement** — Reports (Sales Type): When report has been generated with "All" outlet, then it's showing all the active Territory/Outlet names in Print. But we need only the outlets name which outlets are linked with the generated report. *(Backend:)*
- **Requirement** — Frappe Report: `ArcPOS Item-wise Purchase Register` *(Backend:)*
- **Requirement** — Need to RATE column's Total as Average Rate *(Backend: > Frappe Report: `ArcPOS Item-wise Purchase Register`)*
- **Requirement** — When an order/invoice is submitted with trigger on "Credit Sales", so that no payment entry should not auto initiate. [currently "With ArcPOS Payment" data in passing as 1] *(Backend: > Desktop:)*
- **Defect** — While splitting an order, without Discount OR evenif the order does not contains BOTH type (Discount allowed or not) item also passing with Partial Discount Flag. (Make it same a like general order creation) *(Backend: > Desktop:)*
- **Requirement** — When an order Rounded Total/Grand Total is 0, its passing the "Is Credit Sales = 1" *(Backend: > Desktop:)*
- **Requirement** — New Report (WEB) > `Item-wise Sales Register` *(Backend: > Desktop: > WEB:)*
- **Requirement** — Below is the reference *(Backend: > Desktop: > WEB: > New Report (WEB) > `Item-wise Sales Register`)*

</details>

## 3.6 Desktop Corrections & Requirements — 18-08-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 18 defect(s), 9 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 27 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (27 items)</strong></summary>

- **Defect** — User is logged out every time the application is closed.
- **Requirement** — In smaller screen the date time looks like this
- **Defect** — These disabled fields are not fully visible
- **Defect** — Online order workflow is showing abnormal behavior *(OFFLINE)*
- **Defect** — Pictures are not showing in offline *(OFFLINE)*
- **Defect** — Showing this error when ordered offline- Coffee/Discounted Cust/Credit Sales *(OFFLINE)*
- **Defect** — When an order is paid offline and another draft order is created on the same table, the subsequent online sync fails and displays an error in ONLINE *(OFFLINE)*
- **Defect** — This keeps loading when later is clicked in Resolve pending sync before clock in *(OFFLINE)*
- **Requirement** — For credit sales it shows as PAID instead of DUE *(OFFLINE)*
- **Requirement** — Pathao and Foodpanda shows occupied *(OFFLINE)*
- **Requirement** — Modal is popping multiple times when it's open. *(OFFLINE > Clock-IN/OUT)*
- **Defect** — All the total amount is showing 0 *(OFFLINE > Clock-IN/OUT > POS)*
- **Requirement** — Remove Make Payment button for Order Type- Pay Later for new orders. *(OFFLINE > Clock-IN/OUT > POS)*
- **Defect** — Order details- Variant names are not showing here *(OFFLINE > Clock-IN/OUT > POS)*
- **Requirement** — In a draft order, the "Update Order" button shows enabled (For discounted customers) *(OFFLINE > Clock-IN/OUT > POS)*
- **Defect** — In a draft order, when the customer is changed from a discount-eligible customer to a 0% discount customer and then changed back to a discount-eligible customer, the discount is incorrectly applied to the subtotal instead of recalculating based on the allowed discount-sale items. *(OFFLINE > Clock-IN/OUT > POS)*
- **Requirement** — Rename this to Kitchen Print and make all the button color same *(OFFLINE > Clock-IN/OUT > POS)*
- **Defect** — Fix this overlap *(OFFLINE > Clock-IN/OUT > POS)*
- **Requirement** — For submitted invoice payments, the Cash payment method is pre-selected by default. *(OFFLINE > Clock-IN/OUT > POS)*
- **Requirement** — For credit sales its showing Paid amount instead of Due amount in print. *(OFFLINE > Clock-IN/OUT > POS)*
- **Defect** — When a user without the ArcPOS Manager, Restaurant Manager, or System Manager role saves an order containing discount-eligible items and a discount-eligible customer, the system shows this error *(OFFLINE > Clock-IN/OUT > POS)*
- **Defect** — When multiple payment methods are selected, the last selected payment method is not automatically populated with the remaining payable balance *(OFFLINE > Clock-IN/OUT > Split Order)*
- **Defect** — Order details- These data doesn't show for split orders *(OFFLINE > Clock-IN/OUT > Split Order)*
- **Defect** — The Cash payment method shouldn't be pre-selected by default. *(OFFLINE > Clock-IN/OUT > Split Order)*
- **Defect** — Create a draft order with 1 Coffee L, 1 Coffee M, and a discount-eligible customer → Go to Split Order → Make payment for Coffee L → It shows this error *(OFFLINE > Clock-IN/OUT > Split Order)*
- **Defect** — This part shows as blank for split order payment *(OFFLINE > Clock-IN/OUT > Split Order)*
- **Defect** — In a draft order, when both discount-eligible and non-discount-eligible items are added, the Split Order screen incorrectly displays the discount percentage for the non-discount-eligible items during splitting. *(OFFLINE > Clock-IN/OUT > Split Order)*

</details>

## 3.7 Corrections & Requirements — 10-08-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 14 defect(s), 91 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 79 implemented/reported complete, 24 pending, 2 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

- **Defect · Pending** — 1st Trigger can be on update the BOM *(Backend > Buying Price auto update: > If any item's `total_cost` value in BOM doctype is not same for the item's `Standard Buying` price OR the item does not has `Standard Buying`price, then update or set the price for the item.)*
- **Requirement · Deferred** — Item transfer to another new/existing running order. *(Backend > Buying Price auto update: > Draft Order update:)*
- **Requirement · Deferred** — Table color turn to Yellow if the print receipt is printed. *(Backend > Buying Price auto update: > Table View:)*
- **Defect · Pending** — Order Draft: After Drafting an order, the table occupancy gets delay. *(Backend > Buying Price auto update: > Order in Draft or Submitted:)*
- **Requirement · Pending** — Total Credit Sales = GRAND TOTAL *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement · Pending** — Sales Breakdown *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement · Pending** — Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1) *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales" > Sales Breakdown)*
- **Requirement · Pending** — Customer Name ------ invoice's `total` data *(Frappe Customization: > Backend: > Sales Breakdown > Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1))*
- **Requirement · Pending** — `SALES TOTAL (Net)` = Sum of invoice's `total` data *(Frappe Customization: > Backend: > Sales Breakdown > Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1))*
- **Requirement · Pending** — Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1) *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales" > Discount)*
- **Requirement · Pending** — Sum of invoice's `Discount Amount` data *(Frappe Customization: > Backend: > Discount > Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1))*
- **Requirement · Pending** — Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1) *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales" > SD)*
- **Requirement · Pending** — Sum of invoice's > Table "Sales Taxes and Charges" > `Is SD? = 1` > Sum of `Amount` data *(Frappe Customization: > Backend: > SD > Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1))*
- **Requirement · Pending** — Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1) *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales" > VAT)*
- **Requirement · Pending** — Sum of invoice's > Table "Sales Taxes and Charges" > `Is TAX/VAT? = 1` > Sum of `Amount` data *(Frappe Customization: > Backend: > VAT > Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1))*
- **Requirement · Pending** — Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1) *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales" > Auto Round)*
- **Requirement · Pending** — Sum of invoice's `Rounding Adjustment` data *(Frappe Customization: > Backend: > Auto Round > Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1))*
- **Requirement · Pending** — GRAND TOTAL = `SALES TOTAL (Net)` - `Discount` + `VAT` + `SD` +/- `Auto Round` *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement · Pending** — Need to replicate "ArcPOS WEB Report" *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet.)*
- **Requirement · Pending** — Sales Overview = `ArcPOS Sales Overview` *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. > Need to replicate "ArcPOS WEB Report":)*
- **Requirement · Pending** — Item Sales Summary = `ArcPOS Item Sales Summary` *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. > Need to replicate "ArcPOS WEB Report":)*
- **Requirement · Pending** — Payment Overview = `ArcPOS Payment Overview` *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. > Need to replicate "ArcPOS WEB Report":)*
- **Requirement · Pending** — Table & Covers PnL = `ArcPOS Table & Covers PnL` *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. > Need to replicate "ArcPOS WEB Report":)*
- **Requirement · Pending** — Order-to-Serve Lag Report = `ArcPOS Order-to-Serve Lag Report` *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. > Need to replicate "ArcPOS WEB Report":)*
- **Requirement · Pending** — Day-End Audit Summary = `ArcPOS Day-End Audit Summary` *(Frappe Customization: > Backend: > ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. > Need to replicate "ArcPOS WEB Report":)*
- **Defect · Pending** — Same Alert on Pending/Failed Queue job on trigger on close/exit the app *(Frappe Customization: > Backend: > Default > Failed Queue job alert in 10 mins interval except the order creation/update page)*

### Business rules / contextual notes

- _EXAMPLE: If in a order 2 item (each rate is 50 BDT > Total 100 BDT), and 1 of them if Disallowed then if 10% discount then Discount amount will be 5 taka NOT 10 Taka._ *(Backend > Buying Price auto update: > New or Draft Order update:)*
- _EXAMPLE: If in a order has 2 items [One of item rate is 20 BDT (Discount = NO)] & [Another One of item rate is 80 BDT (Discount = YES)] > Total 100 BDT), then if 10% discount then Discount amount will be 8 taka NOT 10 Taka. *(Backend > Buying Price auto update: > Order on NEW and Draft)*
- Mandatory if "Allow Sales" *(Frappe Customization:)*
- Mandatory if not CASH in "Pay Method" *(Frappe Customization:)*
- Mandatory if not CASH in "Pay Method" *(Frappe Customization:)*
- Mandatory if not CASH in "Pay Method" *(Frappe Customization:)*
- Mandatory if not CASH in "Pay Method" *(Frappe Customization:)*
- Mandatory if not CASH in "Pay Method" *(Frappe Customization:)*
- Correction of "Day-End Audit Summary" *(Frappe Customization: > Backend:)*
- _If we can achieve in the Alert on close/exit the app, then the interval alert can be each 30 mins._ *(Frappe Customization: > Backend: > Default)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.

<details>
<summary><strong>Implemented / reported complete scope (79 items)</strong></summary>

- **Defect** — If any item's `total_cost` value in BOM doctype is not same for the item's `Standard Buying` price OR the item does not has `Standard Buying`price, then update or set the price for the item. *(Backend > Buying Price auto update:)*
- **Defect** — 2nd Trigger can be a cron job at midnight *(Backend > Buying Price auto update: > If any item's `total_cost` value in BOM doctype is not same for the item's `Standard Buying` price OR the item does not has `Standard Buying`price, then update or set the price for the item.)*
- **Requirement** — item wise discount allow not allow. (Some items won't be allowed to Discount) *(Backend > Buying Price auto update: > New or Draft Order update:)*
- **Defect** — If any of Table is occupied or Any Sales Invoice docstatus is 0 for the closing period, restrict to clock-OUT and throw error to fix them first. *(Backend > Buying Price auto update: > Final Clock-OUT:)*
- **Requirement** — Can you do one thing, Whenever the app opens, it should open with default Full screen. *(Backend > Buying Price auto update: > App Opening:)*
- **Defect** — Check why the Print out gets delay. Need more faster. *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — If there are Change amount on Cash, then show this in the print receipt on Payment section. *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — Make the Print Modal UI something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — If the modal pop up on draft order and there is front items then the "Front" print should be default/1st otherwise Receipt print. _[This was functional earlier]_ *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — Table number to be highlighted/ in Big Font in all print output to highlight it. *(Backend > Buying Price auto update: > Print:)*
- **Defect** — In "Front Print" > Show only the last ordered items only which are not printed yet. _We can use "Is Print" field as we used them on BanCan._ *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — Remove the item's serial no from all the print. *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — Make "item qty" bit bigger font size to all the print. *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — For Kitchen Print: Add Item wise "Item Status" data *(Backend > Buying Price auto update: > Print:)*
- **Requirement** — Show the Item's placed time for each items in the cart. *(Backend > Buying Price auto update: > Order in Draft or Submitted:)*
- **Requirement** — New/Draft Order: Show the customers as simple button to change. ++ "Disabled/Frozen" customers should not show. *(Backend > Buying Price auto update: > Order in Draft or Submitted:)*
- **Requirement** — Draft Order: From cart, if any item is variant, need to allow to replace the item to another variant of the parent item's in the Item edit pop up modal. *(Backend > Buying Price auto update: > Order in Draft or Submitted:)*
- **Requirement** — Draft Order: After adding a new item to the cart and without Update Order, the item showing in the Print Preview. *(Backend > Buying Price auto update: > Order in Draft or Submitted:)*
- **Defect** — Sometimes we are facing that, because of frappe rounding, its not matching with our auto rounding amount. So that payment not creating with error. _What if we save the invoice on Payfirst and always take the Grandtotal and other data from the Frappe Invoice._ *(Backend > Buying Price auto update: > Order Payment:)*
- **Requirement** — Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_ *(Backend > Buying Price auto update: > Order Payment:)*
- **Requirement** — Only allowed Outlet Counter wise Payment method should show. (custom_default_website = 1) *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — Remove/Hide the spit button *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — There will be now default/auto set any payment method. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — If payment method "Cash" selected, do not auto set the the received amount. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — If multiple payment method selected (except Cash), then last selected method will be auto filled the remaining balance. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — Already added method can not be add again. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — If there is no due then do not allow to add another method. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — Disable MAKE PAYMENT button until DUE AMOUNT turn to 0. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — If any method is selected, disable the "Credit Sales" button. *(Backend > Buying Price auto update: > Order Payment: > Make the Modal view something like the attached reference: **NOTE: THIS IS JUST A DEMO UI** _[Once the UI is developed, please knock me to make some related changes]_)*
- **Requirement** — item wise calculate the discount amount only if the item is allowed to Discount (YES) *(Backend > Buying Price auto update: > Order on NEW and Draft)*
- **Requirement** — If any order has both type item (Allowed Discount Sales = YES & NO) and discount given in %, then pass the % rate to the `Discount Percentage` instead of `Additional Discount Percentage` with the `Additional Discount Amount (BDT)` at Sales Invoice. *(Backend > Buying Price auto update: > Order on NEW and Draft > item wise calculate the discount amount only if the item is allowed to Discount (YES))*
- **Requirement** — If any table or Invoice has been updated in OFFLINE and pending for Sync then those Table or Invoice should not to allow update when its online until sync successful. *(Backend > Buying Price auto update: > OFFLINE data sync:)*
- **Requirement** — Change view as like the attached demo image view. Scroll will be horizontally. *(Backend > Buying Price auto update: > Kitchen orders:)*
- **Requirement** — For input items in the table need to add a function to item multi select including Category wise filter which will add item wise row on a trigger. *(Backend > Buying Price auto update: > Stock Requisition & Transfer:)*
- **Requirement** — Item *(Frappe Customization:)*
- **Requirement** — Sales Invoice Item *(Frappe Customization:)*
- **Requirement** — Sales Invoice *(Frappe Customization:)*
- **Requirement** — Restaurant Table *(Frappe Customization:)*
- **Requirement** — BIN *(Frappe Customization:)*
- **Requirement** — Supplier: **Use Frappe default Bank Account doctype for below data** *(Frappe Customization:)*
- **Requirement** — Payment Entry *(Frappe Customization:)*
- **Requirement** — Same Field will be auto fetch from Supplier Bank Account *(Frappe Customization: > Payment Entry)*
- **Requirement** — Hide: Excel Tax Payment *(Frappe Customization: > Payment Entry)*
- **Requirement** — Default 1 > Custom Remarks *(Frappe Customization: > Payment Entry)*
- **Requirement** — On "Sales Breakdown" data, take the invoice's `total` data *(Frappe Customization: > Backend:)*
- **Requirement** — Rename the `SALES TOTAL` to `SALES TOTAL (Net)` *(Frappe Customization: > Backend:)*
- **Requirement** — GRAND TOTAL: `SALES TOTAL (Net)` - `Discount` + `VAT` + `SD` +/- `Auto Round` *(Frappe Customization: > Backend:)*
- **Requirement** — Total Revenue = GRAND TOTAL *(Frappe Customization: > Backend:)*
- **Requirement** — Rename the `Total Collected` to `Collections` *(Frappe Customization: > Backend:)*
- **Requirement** — Add a new section on right side for "Credit Sales" *(Frappe Customization: > Backend:)*
- **Requirement** — Discount *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement** — SD *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement** — VAT *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement** — Auto Round *(Frappe Customization: > Backend: > Add a new section on right side for "Credit Sales")*
- **Requirement** — Invoice Amount: Data should be the Invoice's `Rounded Total` *(Frappe Customization: > Backend:)*
- **Requirement** — Remove the column "Supplier Code" and Try to show the "Posting Date" data in single line. *(Frappe Customization: > Backend: > Invoice Amount: Data should be the Invoice's `Rounded Total`)*
- **Defect** — The Table border is not showing in the Print Output. *(Frappe Customization: > Backend: > Invoice Amount: Data should be the Invoice's `Rounded Total`)*
- **Defect** — On PDF : The Table border is not showing in the Print Output. *(Frappe Customization: > Backend:)*
- **Requirement** — ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. *(Frappe Customization: > Backend:)*
- **Requirement** — After app reload, freeze/loader to the screen until the pop up Clock-IN/OUT modal *(Frappe Customization: > Backend: > Clock-IN/OUT Modal)*
- **Requirement** — If any invoice is draft (docstatus = 0), then add a mark as `Running`? *(Frappe Customization: > Backend: > Order List)*
- **Requirement** — Default full screen taking the full screen including the task bar and there are no option to shrink the screen. *(Frappe Customization: > Backend: > Default)*
- **Defect** — Failed Queue job alert in 10 mins interval except the order creation/update page *(Frappe Customization: > Backend: > Default)*
- **Defect** — Same Alert on Pending/Failed Queue job on trigger Clock Out button *(Frappe Customization: > Backend: > Default > Failed Queue job alert in 10 mins interval except the order creation/update page)*
- **Requirement** — Territory data not passing to Frappe. *(Frappe Customization: > Backend: > Stock Requisition)*
- **Requirement** — Show NOTE for value of BOM's "Website Description" value in the Recipe modal *(Frappe Customization: > Backend: > Recipe)*
- **Requirement** — Add a new menu "Stock Availability" *(Frappe Customization: > Backend: > New Menu)*
- **Requirement** — Menu permission = System Manger/Auditor (Frappe Role) *(Frappe Customization: > Backend: > New Menu > Add a new menu "Stock Availability")*
- **Requirement** — Data will be get from "BIN" doctype *(Frappe Customization: > Backend: > New Menu > Add a new menu "Stock Availability")*
- **Requirement** — Just a list view with Search (Item name), Filter : Outlet, Category *(Frappe Customization: > Backend: > New Menu > Add a new menu "Stock Availability")*
- **Requirement** — Columns: Item Name | Category | Outlet | Current Stock *(Frappe Customization: > Backend: > New Menu > Add a new menu "Stock Availability")*
- **Requirement** — Data should not show if "actual_qty is less then 0" or warehouse LIKE `Work In Progress` *(Frappe Customization: > Backend: > New Menu > Add a new menu "Stock Availability")*
- **Requirement** — Preventing only if any Table is occupied, but we need also for If any Sales Invoice docstatus is 0 for the current period. *(Corrections > 18-08-2026 > Backend: > Final Clock-OUT:)*
- **Requirement** — Clock-IN & Clock-OUT Time is showing UTC *(Corrections > 18-08-2026 > Backend: > Desktop)*
- **Requirement** — Keep 3 sections side by side until Tablet screen *(Corrections > 18-08-2026 > Backend: > Desktop)*
- **Defect** — Credit Sales button missing when Credit allowed customer is selected *(Corrections > 18-08-2026 > Backend: > Desktop)*
- **Requirement** — If customer type = Partnership, then no need to show the search button in the Edit drawer. *(Corrections > 18-08-2026 > Backend: > Desktop)*
- **Requirement** — Draft Order: After entering to the order and closing the page without update anything, its showing the Update Order button enabled and showing Discard modal. *(Corrections > 18-08-2026 > Backend: > Desktop)*
- **Requirement** — Clock-IN & Clock-OUT Time is showing UTC *(Corrections > 18-08-2026 > Backend: > Web)*

</details>

## 3.8 Corrections & Requirements — 04-08-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 6 defect(s), 15 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 21 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.
- Verify notifications, recipient selection and redirection.

<details>
<summary><strong>Implemented / reported complete scope (21 items)</strong></summary>

- **Defect** — Auto close if occupied table running order is paid. Sometimes the Order is Paid but order status does not turn to CLOSED! _(Need to do the automation as we done on BanCan)_ *(Backend)*
- **Defect** — Auto email issue on payment section: Its taking the Date only, not validating the time! If needed add a custom field in the payment entry for Posting time (auto take the creation time and should not change on the document update/submit) *(Backend)*
- **Requirement** — Sales Invoice: Parent Invoice reference on Split invoices *(Backend)*
- **Requirement** — Work Order: Invoice Reference in Work Order. *(Backend)*
- **Requirement** — Frappe Customization *(Backend)*
- **Requirement** — Is there any way to auto marked the `Use Letter head` field when user click on PDF from a report? *(Backend)*
- **Defect** — Supplier Invoice Data missing!! *(Backend > ArcPOS Accounts Payable:)*
- **Requirement** — On PDF print, End of right side column data hiding on Portrait page mode *(Backend > ArcPOS Accounts Payable:)*
- **Requirement** — Reduce bit of value font size on Print PDF *(Backend > ArcPOS Accounts Payable:)*
- **Defect** — Supplier Invoice Data missing!! *(Backend > ArcPOS Accounts Payable: > ArcPOS Item-wise purchase register)*
- **Requirement** — Remove Column: Purchase Receipt *(Backend > ArcPOS Accounts Payable: > ArcPOS Item-wise purchase register)*
- **Requirement** — Rename the Column header "Total Tax" to "Total VAT" *(Backend > ArcPOS Accounts Payable: > ArcPOS Item-wise purchase register)*
- **Defect** — On PDF print, all the columns are not showing. *(Backend > ArcPOS Accounts Payable: > ArcPOS Item-wise purchase register)*
- **Requirement** — Reduce bit of value font size on Print PDF *(Backend > ArcPOS Accounts Payable: > ArcPOS Item-wise purchase register)*
- **Requirement** — Table no show in the print receipt. Currently we are showing the service type only. Add the linked table data. LIKE Table 01-Dine-In > Take the table data till -. dont show the Outlet name. *(Backend > ArcPOS Accounts Payable: > Print:)*
- **Requirement** — When "Skip Kitchen Outlet" is same a logged user, then it's showing only the Print Receipt. we need the Front Print also. *(Backend > ArcPOS Accounts Payable: > Print:)*
- **Defect** — Cart Item changing "Issue type" is not allowing after status "Waiting". no need to check the item status to restrict. Just validate the docstatus. Allow if only docstatus 0 or new order. *(Backend > ArcPOS Accounts Payable: > Order in Draft)*
- **Requirement** — This report query data will change *(Backend > ArcPOS Accounts Payable: > Report: Day-end Audit Summary)*
- **Requirement** — Without select a valid Outlet, should not execute the query or do not show any data > Remove "All" option *(Backend > ArcPOS Accounts Payable: > Report: Day-end Audit Summary)*
- **Requirement** — If user Select NOT = "Counter 1" then hide the button "Clock-OUT & Send Email" *(Backend > ArcPOS Accounts Payable: > Clock-OUT Modal)*
- **Requirement** — On trigger the button "Clock-OUT & Send Email" will auto POS print the "`Day-end Audit Summary` report" for the latest clock-OUT period *(Backend > ArcPOS Accounts Payable: > Clock-OUT Modal)*

</details>

## 3.9 POS Web — Corrections & Requirements 29-07-2026

**Main functional focus:** Stock & Inventory  
**Content mix:** 0 defect(s), 2 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 2 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers functional or UI requirements within stock & inventory.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### Business rules / contextual notes

- Currently we have a validation that, If the logged user has Role "ArcPOS Requisition Approver" OR "System Manager" && "Source Outlet" is set as default on the web, then user can get the `Edit` and `Approve` button permission. *(Stock Requisition)*

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (2 items)</strong></summary>

- **Requirement** — But now for the "Source Outlet" is set as default on the web" > instead of this check the user has the source outlet/territory permission and others, then allow those buttons. *(Stock Requisition)*
- **Requirement** — Including all the current flow, when the data is passing to frappe then always for each item, pass the "ArcPOS Settings > `default_wastage_account`" value in the "Difference Account" field. If the settings value is NULL then pass this as now. *(Stock Requisition > Wastage Management)*

</details>

## 3.10 Backend Issue — 25-07-2026

**Main functional focus:** Reporting & Analytics  
**Content mix:** 19 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 13 implemented/reported complete, 6 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within reporting & analytics.

### Pending / Deferred items

- **Defect · Pending** — If above not possible then > If any Invoice `territory` = ISD, then the data should not appear in this report. *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Can we do this dynamically? If "ArcPOS Settings > "Allowed to Skip Kitchen (Outlet)" has value (value= multiple outlet names separated by commas) && If any Invoice `territory` = {{ the value }}, then the data should not appear in this report.)*
- **Defect · Pending** — For Header Footer > we will use frappe "Letter Head" *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Accounts Payable (Report) [Ignore Now] > Print PDF > LIKE the below image (Page can be Portrait or Landscape))*
- **Defect · Pending** — Remove: Mode of Payment, Company *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now] > Filters: Same as existing report)*
- **Defect · Pending** — Additionally Add: Order No, Supplier Invoice *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now] > Columns: Same as existing report)*
- **Defect · Pending** — Remove: Description, Payable Account, Mode of Payment, Project, Company, Expense Account *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now] > Columns: Same as existing report)*
- **Defect · Pending** — For Header Footer > we will use frappe "Letter Head" *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now] > Print PDF > LIKE the below image (Page can be Portrait or Landscape))*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify notifications, recipient selection and redirection.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (13 items)</strong></summary>

- **Defect** — Email & Socket notification: Stage for "Requisition Approval" > Send the notification just check if the user has the Source outlet/territory permission only. No need to check which is default. And role "ArcPOS Requisition Approver"
- **Defect** — Remove "System Manager" Role from all the Email & Socket notifications.
- **Defect** — If any purchase order has been submitted with backdate on `Date`, then the purchase invoice also should be created by the actual day not current date. *(Auto Purchase Invoice)*
- **Defect** — Can we do this dynamically? If "ArcPOS Settings > "Allowed to Skip Kitchen (Outlet)" has value (value= multiple outlet names separated by commas) && If any Invoice `territory` = {{ the value }}, then the data should not appear in this report. *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report)*
- **Defect** — Need Customized report > `ArcPOS Accounts Payable` *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Accounts Payable (Report) [Ignore Now])*
- **Defect** — Filters: Date Range, Supplier Name, Supplier Group *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Accounts Payable (Report) [Ignore Now])*
- **Defect** — Columns: Posting Date, Supplier Code, Supplier Name, Supplier Group, Voucher No, Order No, Supplier Invoice, Invoice Amount, Outstanding Amount, *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Accounts Payable (Report) [Ignore Now])*
- **Defect** — No need any chart *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Accounts Payable (Report) [Ignore Now])*
- **Defect** — Print PDF > LIKE the below image (Page can be Portrait or Landscape) *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Accounts Payable (Report) [Ignore Now])*
- **Defect** — Need Customized report > `ArcPOS Item-wise Purchase Register` *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now])*
- **Defect** — Filters: Same as existing report *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now])*
- **Defect** — Columns: Same as existing report *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now])*
- **Defect** — Print PDF > LIKE the below image (Page can be Portrait or Landscape) *(Auto Purchase Invoice > POS Report: Order-to-Serve Lag Report > Frappe Report: Item-wise Purchase Register (Report) [Ignore Now])*

</details>

## 3.11 Desktop Pending Corrections & Requirements — 15-07-2026

**Main functional focus:** Printing  
**Content mix:** 3 defect(s), 13 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 16 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within printing.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### Business rules / contextual notes

- If "ArcPOS Settings > Allowed to Skip Kitchen (Outlet)" has value and the value separating by COMMA match with the user's selected OUTLET then *(Order Receipt Print > Split > POS Order page)*
- If "ArcPOS Settings > Allowed to Skip Kitchen (Outlet)" has value and the value separating by COMMA match with the invoice's field `territory` value then *(Order Receipt Print > Split > Order List and Details page)*
- NOTE: I checked a Printer is set as default. But Can we check from the App that is there any connected Printer or not? *(Order Receipt Print > Split > POS Print Issue)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (16 items)</strong></summary>

- **Requirement** — Show the **preference** like this *(Order Receipt Print)*
- **Requirement** — After completing 1 guest slot payment show the Grand total here *(Order Receipt Print > Split)*
- **Requirement** — On trigger should redirect to the Home page *(Order Receipt Print > Split > Reload Button)*
- **Requirement** — If the trigger from New Order, then pop up a warning modal first, if confirms then initiate reload. *(Order Receipt Print > Split > Reload Button)*
- **Requirement** — Any Item which is added to cart, the item Status will be "Ready to Serve" also for Kitchen Items. *(Order Receipt Print > Split > POS Order page)*
- **Requirement** — If any item Status NOT = "Served" then allow to update the status to only "Served" *(Order Receipt Print > Split > POS Order page)*
- **Requirement** — On print Section: Allow only "Print Receipt" *(Order Receipt Print > Split > POS Order page)*
- **Requirement** — List page: If Docstatus NOT = 0 and Order Status NOT = "Closed" then allow to update the status to only "Closed" and on update the item status will be "Served" as well. *(Order Receipt Print > Split > Order List and Details page)*
- **Requirement** — Details: If any item Status NOT = "Served" then allow to update the status to only "Served" *(Order Receipt Print > Split > Order List and Details page)*
- **Requirement** — On print Section: Allow only "Print Receipt" *(Order Receipt Print > Split > Order List and Details page)*
- **Defect** — Check the below attachment, why this error accorded? *(Order Receipt Print > Split > POS Print Issue)*
- **Requirement** — Voiding remarks should pass to the invoice's "custom_user_remarks" field. **[this was functional earlier]** *(Void Order)*
- **Requirement** — In DRAFT order, existing Items in the Cart > Edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to `Multiple` and the "Variant Item Type" is set to `Combo`, then the user should NOT allowed to increase the quantity from List & POP UP. *(Void Order > POS Order > **[this was functional earlier]**)*
- **Defect** — In NEW or DRAFT order, including existing Items in the Cart > if the "Attribute Type for POS" or "Choice Type for POS" is set to `Multiple` and the "Variant Item Type" is NOT set to `Combo`, then the user should allowed to increase the quantity from List & POP UP as well. *(Void Order > POS Order > **[this was functional earlier]**)*
- **Defect** — Also cab be edited the "Service Type", "Preferences", "Issue Type", "Order Note" from the POP UP as well. *(Void Order > POS Order > **[this was functional earlier]** > In NEW or DRAFT order, including existing Items in the Cart > if the "Attribute Type for POS" or "Choice Type for POS" is set to `Multiple` and the "Variant Item Type" is NOT set to `Combo`, then the user should allowed to increase the quantity from List & POP UP as well.)*
- **Requirement** — In Order Split > If any item's "Serve Type NOT = Dine-in" then show the value beside the item name. *(Void Order > POS Order > **[this was functional earlier]**)*

</details>

## 3.12 Desktop Application Defects & Requirements — 01/07/2026

**Main functional focus:** Printing  
**Content mix:** 3 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 3 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within printing.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify printing content, format, routing and cash-drawer behavior.

<details>
<summary><strong>Implemented / reported complete scope (3 items)</strong></summary>

- **Defect** — Cash drawer should not open after every print, it should open only when the payment method is **Cash**. *(Cash Drawer/Print)*
- **Defect** — Blank space at the top of the printed receipt should be fixed. *(Cash Drawer/Print)*
- **Defect** — Create order with 1 Coffee M and 1 Coffee S → Save the order → Go to Split Order → Make payment only for Coffee M → After Coffee M payment is completed, select Coffee S from the left side → Coffee S does not appear on the right side for payment as expected. *(Cash Drawer/Print > Split Bill)*

</details>

## 3.13 Epson TM-T81III Printer and QZ Tray Cash Drawer Setup Guide for Windows 11

**Main functional focus:** Printing  
**Content mix:** 0 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 0 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers  within printing.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### Business rules / contextual notes

- If the printer is not detected by USB, also download **TMUSB Device Driver for Windows 10 or later OS** from the same Epson page. *(Epson TM-T81III Printer Setup for Windows 11 > 2. Optional USB Driver)*
- **58mm**, if available. *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- 4. If it prints, the driver setup is okay. *(Epson TM-T81III Printer Setup for Windows 11 > 7. Print Test Page)*

### Operational / documentation content

- Go to the official Epson TM-T81III download page and select **Windows 11 64-bit**. *(Epson TM-T81III Printer Setup for Windows 11 > 1. Download Epson Driver)*
- Download **EPSON Advanced Printer Driver 6 for TM-T81III**. *(Epson TM-T81III Printer Setup for Windows 11 > 1. Download Epson Driver)*
- Epson’s download center currently lists **Advanced Printer Driver 6 v6.12** for TM-T81III on Windows 11 x64. *(Epson TM-T81III Printer Setup for Windows 11 > 1. Download Epson Driver)*
- If the printer is not detected by USB, also download **TMUSB Device Driver for Windows 10 or later OS** from the same Epson page. *(Epson TM-T81III Printer Setup for Windows 11 > 2. Optional USB Driver)*
- Epson lists this USB driver separately for Windows 11 x64. *(Epson TM-T81III Printer Setup for Windows 11 > 2. Optional USB Driver)*
- 1. Connect the power adapter. *(Epson TM-T81III Printer Setup for Windows 11 > 3. Connect Printer Hardware)*
- 2. Insert the receipt paper roll correctly. *(Epson TM-T81III Printer Setup for Windows 11 > 3. Connect Printer Hardware)*
- 3. Connect the USB cable from the printer to the PC. *(Epson TM-T81III Printer Setup for Windows 11 > 3. Connect Printer Hardware)*
- 4. Turn on the printer. *(Epson TM-T81III Printer Setup for Windows 11 > 3. Connect Printer Hardware)*
- 1. Right-click the Epson driver installer. *(Epson TM-T81III Printer Setup for Windows 11 > 4. Install Driver)*
- 2. Select **Run as administrator**. *(Epson TM-T81III Printer Setup for Windows 11 > 4. Install Driver)*
- 3. Choose **Install Printer Driver**. *(Epson TM-T81III Printer Setup for Windows 11 > 4. Install Driver)*
- 4. Select model: **EPSON TM-T81III**. *(Epson TM-T81III Printer Setup for Windows 11 > 4. Install Driver)*
- 5. Select interface: **USB**. *(Epson TM-T81III Printer Setup for Windows 11 > 4. Install Driver)*
- **Control Panel > Devices and Printers** *(Epson TM-T81III Printer Setup for Windows 11 > 5. Check Printer in Windows)*
- Confirm the printer appears, usually like *(Epson TM-T81III Printer Setup for Windows 11 > 5. Check Printer in Windows)*
- **EPSON TM-T81III Receipt** *(Epson TM-T81III Printer Setup for Windows 11 > 5. Check Printer in Windows)*
- 1. Right-click the printer. *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- 2. Go to **Printing Preferences**. *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- 3. Set the paper/roll size based on your roll *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- For **80mm roll**, select *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- **80mm / Receipt / Roll Paper 80 x 297mm** *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- For **58mm roll**, select *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- **58mm**, if available. *(Epson TM-T81III Printer Setup for Windows 11 > 6. Set Paper Size)*
- 1. Right-click the printer. *(Epson TM-T81III Printer Setup for Windows 11 > 7. Print Test Page)*
- 2. Go to **Printer Properties**. *(Epson TM-T81III Printer Setup for Windows 11 > 7. Print Test Page)*
- 3. Click **Print Test Page**. *(Epson TM-T81III Printer Setup for Windows 11 > 7. Print Test Page)*
- 4. If it prints, the driver setup is okay. *(Epson TM-T81III Printer Setup for Windows 11 > 7. Print Test Page)*
- Official download page *(Cash Drawer Setup > 1. Download QZ Tray)*
- Choose the **Windows** installer from that page. *(Cash Drawer Setup > 1. Download QZ Tray)*
- QZ Tray’s official download page lists Windows, macOS, and Linux versions. *(Cash Drawer Setup > 1. Download QZ Tray)*
- 1. Right-click the downloaded installer. *(Cash Drawer Setup > 2. Install QZ Tray)*
- 2. Select **Run as administrator**. *(Cash Drawer Setup > 2. Install QZ Tray)*
- 3. Complete the installation. *(Cash Drawer Setup > 2. Install QZ Tray)*
- 1. Search **QZ Tray** from the Start Menu. *(Cash Drawer Setup > 3. Open QZ Tray)*
- 3. You should see the QZ Tray icon near the Windows clock/system tray. *(Cash Drawer Setup > 3. Open QZ Tray)*
- 1. Right-click the QZ Tray tray icon. *(Cash Drawer Setup > 4. Enable Auto Start)*
- 2. Enable **Automatically Start**, so QZ Tray starts when Windows starts. *(Cash Drawer Setup > 4. Enable Auto Start)*
- 1. Right-click the QZ Tray icon. *(Cash Drawer Setup > 5. Add/Trust Certificate for Testing)*
- 2. Go to **Advanced > Site Manager**. *(Cash Drawer Setup > 5. Add/Trust Certificate for Testing)*
- 4. Browse to the folder that has the **.crt** file and select it. *(Cash Drawer Setup > 5. Add/Trust Certificate for Testing)*
- [Download/Certificate](https://drive.google.com/file/d/1nktzCmDaEbceI7VLWofkIuh16SsmBS7z/view?usp=sharing) *(Cash Drawer Setup > 5. Add/Trust Certificate for Testing)*

## 3.14 POS WEB — 14-06-2026

**Main functional focus:** Stock & Inventory  
**Content mix:** 1 defect(s), 6 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 6 implemented/reported complete, 1 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within stock & inventory.

### Pending / Deferred items

- **Requirement · Pending** — "Create Transfer" > the OUTLET should be pass as per selected from "POS WEB" *(Stock Transfer > Stock Requisition)*

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (6 items)</strong></summary>

- **Requirement** — "Accept" button should enabled only if the "Target Outlet" is set as default from "POS WEB" *(Stock Transfer)*
- **Requirement** — "Cancel" button should enabled only for FRAPPE Role = System Manager + ArcPOS Manager *(Stock Transfer)*
- **Requirement** — "Edit" & "Submit" button should enabled only if the "Source Outlet" is set as default from "POS WEB" *(Stock Transfer)*
- **Requirement** — So, check first for the 2nd row, is there are any functionality or not? If NO, then we can remove this *(Stock Transfer > Stock Requisition)*
- **Defect** — On Edit, "Required By" is not updating in Backend/Frappe document. *(Stock Transfer > Stock Requisition)*
- **Requirement** — After "Approve", redirect to "Requisition" list page with latest data. *(Stock Transfer > Stock Requisition)*

</details>

## 3.15 Desktop — 08-06-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 5 defect(s), 27 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 30 implemented/reported complete, 2 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

- **Requirement · Pending** — If Subtotal is less then 500 then upto .50 will be in negative and from .51 will be in positive *(For "Rounding Adjustment")*
- **Requirement · Pending** — If Subtotal is greater then 499.99 then upto .49 will be in negative and from .50 will be in positive *(For "Rounding Adjustment")*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.

<details>
<summary><strong>Implemented / reported complete scope (30 items)</strong></summary>

- **Requirement** — Implement the Item Preferences. also show in all prints. [Reference can be BanCan Print]
- **Requirement** — Rename the warning text to "You have already logged in a Counter" (Backend)
- **Requirement** — Counter options must be unique (Backend)
- **Requirement** — On Clock-IN, the Expected amount getting NULL/0, please collaborate with Anamul (Backend)
- **Defect** — Why I am getting the error when the Opening amount = 0 (backend)
- **Requirement** — Add the"Bell Icon" with functionality also on the Modal's top right corner.
- **Defect** — "Mark as Read" text button/pausing the alert tone button is not stopping the ringing from this modal *(Add the"Bell Icon" with functionality also on the Modal's top right corner.)*
- **Requirement** — This text should be in RED color font
- **Requirement** — Place the report in the Center and if multiple then the per row 2 reports.
- **Requirement** — Make correction of the report description to: `Summary of daily sales, charges, and payments.`
- **Requirement** — Click on this specific alert, not marking as read
- **Requirement** — On order sync, keep the OFFLINE data is first priority and update the order forcefully even the order has been modified during offline the desktop
- **Requirement** — For "Rounding Adjustment"
- **Requirement** — Order Cart
- **Requirement** — For "Remove" button show/hide, keep the current condition If "Prepare At = Kitchen" *(Order Cart)*
- **Requirement** — If "Prepare At = Front", then show the "Remove" button in status = "Waiting/Preparing/Ready to Serve" *(Order Cart)*
- **Requirement** — New Item add to Cart on update
- **Defect** — Item and order status issue *(New Item add to Cart on update)*
- **Requirement** — If Grand Total value of **123.4999999 or below** will result in a **negative rounding adjustment** *(For "Rounding Adjustment")*
- **Requirement** — If Grand Total value of **123.5000000 or Above** will result in a **Positive rounding adjustment** *(For "Rounding Adjustment")*
- **Requirement** — If Draft order then redirect to Draft Mode of the Order from Notification *(For "Rounding Adjustment" > Alert redirection)*
- **Requirement** — Notification dropdown > the ringer "Sound" button > Keep "ON" as default. That means, if user "OFF" this and somehow the app gets reload or restart so that sound will be turned ON automatically. *(For "Rounding Adjustment" > Alert redirection)*
- **Requirement** — Rename the "Done" button text to "Close" *(For "Rounding Adjustment" > Alert redirection > Print Modal)*
- **Defect** — Keep enabled the"Close" button when its printing. (Because sometimes it's may take sometime to print success, meanwhile the display stuck until the print gets success or fail. *(For "Rounding Adjustment" > Alert redirection > Print Modal)*
- **Requirement** — If the modal pop up on draft order and there is front items then the "Front" print should be default/1st otherwise Receipt print. *(For "Rounding Adjustment" > Alert redirection > Print Modal)*
- **Requirement** — Implement item row Dragging with row wise icon which will catch the item row in single tap. *(For "Rounding Adjustment" > Alert redirection > Order Splitting)*
- **Requirement** — After last slot get paid and after print modal "Close" > redirect to Table page *(For "Rounding Adjustment" > Alert redirection > Order Splitting)*
- **Defect** — If any item's issue type = Wastage, then should not show in the print. **(This condition applied to only Receipt print)** *(For "Rounding Adjustment" > Alert redirection > Receipt print)*
- **Requirement** — Add a text in small italic font under the "Split Order" button > `Orders can only be split if all items are at least in "Ready to Serve."` *(For "Rounding Adjustment" > Alert redirection > Order edit drawer)*
- **Requirement** — Add a simple image as default for "All" in item category. *(For "Rounding Adjustment" > Alert redirection > New/Draft Order)*

</details>

## 3.16 Requirement of 04-06-2026

**Main functional focus:** Reporting & Analytics  
**Content mix:** 0 defect(s), 35 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 35 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers functional or UI requirements within reporting & analytics.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### Business rules / contextual notes

- If ArCPOS Settings "Allowed Kitchen Order Print? = NO", then "Kitchen Print" option will be Hidden. *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (35 items)</strong></summary>

- **Requirement** — Only for "Prepare At = Front" *(Need to do:)*
- **Requirement** — If item's are "Is BOM Item = 1" then initiate Workorder and related things *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — On success > Pass item's order status = Served *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — No need to pass the "Serve" time *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — Only for "Prepare At = Front" *(Need to do:)*
- **Requirement** — Pass item's order status = Ready to Serve *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — No need to pass the "Ready to Serve" time *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — When an order is created containing only front order items, the order status should automatically be set to **Ready to Serve**. *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — In that draft order, when a Prepare At = Kitchen item is added, the order status should automatically be updated to **Waiting**. *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — In a draft order, when a Prepare At = Front item is added, the item status should automatically be set to **Ready to Serve**. *(Need to do: > Only for "Prepare At = Front")*
- **Requirement** — After Payment success + Order Details (Online) *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_)*
- **Requirement** — There will be 2 Print data > 1. "Print Receipt" (Default preview), 2. "Front Print" *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Online))*
- **Requirement** — All including "Front Print" will be accordion/expandable *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Online) > There will be 2 Print data > 1. "Print Receipt" (Default preview), 2. "Front Print")*
- **Requirement** — Trigger option button will be two > 1. Print Active, 2. Print All *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Online))*
- **Requirement** — Trigger on "Print Active" will generate print the opened/previewed print data *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Online) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — Trigger on "Print All" will generate all print in sequence *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Online) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — After Payment success + Order Details (Offline) *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_)*
- **Requirement** — There will be 3 Print data > 1. "Print Receipt" (Default preview), 2. "Front Print", 3. "Kitchen Print" *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Offline))*
- **Requirement** — All including "Front Print" & "Kitchen Print" will be accordion/expandable *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Offline) > There will be 3 Print data > 1. "Print Receipt" (Default preview), 2. "Front Print", 3. "Kitchen Print")*
- **Requirement** — Trigger option button will be two > 1. Print Active, 2. Print All *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Offline))*
- **Requirement** — Trigger on "Print Active" will generate print the opened/previewed print data *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Offline) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — Trigger on "Print All" will generate all print in sequence *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After Payment success + Order Details (Offline) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — After DRAFT success + PRINT button trigger (Online) *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_)*
- **Requirement** — There will be 2 Print data > 1. "Print Receipt", 2. "Front Print" (Default preview) *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Online))*
- **Requirement** — All including "Print Receipt" will be accordion/expandable *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Online) > There will be 2 Print data > 1. "Print Receipt", 2. "Front Print" (Default preview))*
- **Requirement** — Trigger option button will be two > 1. Print Active, 2. Print All *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Online))*
- **Requirement** — Trigger on "Print Active" will generate print the opened/previewed print data *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Online) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — Trigger on "Print All" will generate all print in sequence *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Online) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — After DRAFT success + PRINT button trigger (Offline) *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_)*
- **Requirement** — There will be 3 Print data > 1. "Print Receipt", 2. "Front Print", 3. "Kitchen Print" (Default preview) *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Offline))*
- **Requirement** — All including "Front Print" & "Print Receipt" will be accordion/expandable *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Offline) > There will be 3 Print data > 1. "Print Receipt", 2. "Front Print", 3. "Kitchen Print" (Default preview))*
- **Requirement** — Trigger option button will be two > 1. Print Active, 2. Print All *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Offline))*
- **Requirement** — Trigger on "Print Active" will generate print the opened/previewed print data *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Offline) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — Trigger on "Print All" will generate for "Front Print" & "Kitchen Print" in sequence *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > After DRAFT success + PRINT button trigger (Offline) > Trigger option button will be two > 1. Print Active, 2. Print All)*
- **Requirement** — Ignore/hide the Items which are "Prepare At = Front" *(Need to do: > Print Modal options: _[Front Print = (Prepare At = Front) items, Kitchen Print = (Prepare At = Kitchen) items]_ > Report > Order-to-Serve Lag Report)*

</details>

## 3.17 POS- WEB Ordering Process - 7th June

**Main functional focus:** Printing  
**Content mix:** 55 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 46 implemented/reported complete, 8 pending, 1 deferred

**Summary:** This work package covers reported product defects/corrections within printing.

### Pending / Deferred items

- **Defect · Pending** — ORD-26-01617- Check the choose qty condition, it's automatically passing data when variant item choice type is single. *(NEW ISSUES |)*
- **Defect · Pending** — Any Item which is added to cart, the item Status will be "Ready to Serve" also for Kitchen Items. *(NEW ISSUES | > POS Order page)*
- **Defect · Pending** — If any item Status NOT = "Served" then allow to update the status to only "Served" *(NEW ISSUES | > POS Order page)*
- **Defect · Pending** — On print Section: Allow only "Print Receipt" *(NEW ISSUES | > POS Order page)*
- **Defect · Pending** — List page: If Docstatus NOT = 0 and Order Status NOT = "Closed" then allow to update the status to only "Closed" and on update the item status will be "Served" as well. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect · Pending** — Details: If any item Status NOT = "Served" then allow to update the status to only "Served" *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect · Pending** — On print Section: Allow only "Print Receipt" *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect · Deferred** — 1 Coffee, 1 Captain America. When coffee's status is already served and then Captain America's status is changed to Ready to serve, The order status still shows as Waiting. It doesn't update the order status accordingly. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect · Pending** — In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item. *(NEW ISSUES | > POS Order page > OLD ISSUES)*

### Business rules / contextual notes

- If "ArcPOS Settings > Allowed to Skip Kitchen (Outlet)" has value and the value separating by COMMA match with the user's selected OUTLET then *(NEW ISSUES | > POS Order page)*
- If "ArcPOS Settings > Allowed to Skip Kitchen (Outlet)" has value and the value separating by COMMA match with the invoice's field `territory` value then *(NEW ISSUES | > POS Order page > Order List and Details page)*
- Then below that- Kitchen Note. Rename the kitchen note to only **NOTE** *(NEW ISSUES | > POS Order page > KITCHEN ORDERS)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (46 items)</strong></summary>

- **Defect** — Item quantity should be editable when the item status = waiting. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Order status is not updating even when all the item status is ready to serve/served. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Split order- edit pax to- Party size. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — When a draft order is created with a walk-in customer and later changed to a credit sales enabled customer, submitting the order with credit sales causes the item and order status to work incorrectly. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Keep the party size fixed to 1 and disabled for foodpanda and pathao (Customer Type= Partnership) *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Showing the wrong print format for **Front Order** prints. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Table is still showing as Occupied after submitting an order using Credit Sales. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Remove this table part *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — In Edit Order-> Show the issue type like this *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — In Edit Order-> For foodpanda/pathao Select Customer fields are showing selectable instead of showing the linked customer by default. *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — **Orders**- Show only these filters *(NEW ISSUES | > POS Order page > Order List and Details page)*
- **Defect** — Fix mobile responsiveness for this modal when issue type is selected *(NEW ISSUES | > POS Order page > Order List and Details page > Mobile Responsiveness)*
- **Defect** — Fix this for mobile responsiveness- 360 x 740 *(NEW ISSUES | > POS Order page > Order List and Details page > Mobile Responsiveness)*
- **Defect** — Fix this for mobile responsiveness for clock in/out modal. *(NEW ISSUES | > POS Order page > Order List and Details page > Mobile Responsiveness)*
- **Defect** — Fix this *(NEW ISSUES | > POS Order page > Order List and Details page > Mobile Responsiveness)*
- **Defect** — Align this in mobile view *(NEW ISSUES | > POS Order page > Order List and Details page > Mobile Responsiveness)*
- **Defect** — Show this with full name in mobile view *(NEW ISSUES | > POS Order page > Order List and Details page > Mobile Responsiveness)*
- **Defect** — Show the pin like this while typing *(NEW ISSUES | > POS Order page > NEW ISSUES ||)*
- **Defect** — Show 0 amount for other issue types. *(NEW ISSUES | > POS Order page > NEW ISSUES ||)*
- **Defect** — Browser back button-> discard not working. *(NEW ISSUES | > POS Order page > NEW ISSUES ||)*
- **Defect** — Show SD and VAT like this, same for Payment Summary modal *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — Show Customer Address like this *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — Rename Payment button to **Pay ৳Grand Total** *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — **Payment Summary modal**-> payment method is showing disabled mode of payments as well. *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — After making payment of a credit sales order it doesn't redirect back to that order details page. Shows error- Could not load this order details. And keeps showing error- User None is disabled. Please contact your System Manager. Which fixes after clearing the cookies. *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — Add a Refetch Orders button on top right of the list page. *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — Only keep these filters and maintain this sequence- Search box, Date range, Service type, Order Status, Payment Status, Outlet, Customer Type, Customer. *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — Customer search filter- Show **Please type something to search.** instead of No data found. *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — From the order list when the order status is changed from Ready to serve to Served, it doesn't update the item status. *(NEW ISSUES | > POS Order page > Order)*
- **Defect** — In a draft order when a new front order is added- it should be added as Ready to serve instead of waiting. *(NEW ISSUES | > POS Order page > POS)*
- **Defect** — When user has ArcPOS Manager/Restaurant Manager/System Manager permission then PIN shouldn't be there for **VOID**. *(NEW ISSUES | > POS Order page > POS)*
- **Defect** — In a draft order- **Make payment** and **Credit sales** button should be enabled only if all the item status and order status is either Ready to serve or Served. *(NEW ISSUES | > POS Order page > POS)*
- **Defect** — Beside order summary show the number of items added in the cart like this *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Write takeout beside the item name like this *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Only show the save button beside discount when the discount is modified with PIN. *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Match this part *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Rename this to only Issue Type *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — No need to show the order note under the item name. *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — The up/down arrows for the discount field should increment/decrement in decimal values *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Make the button colors different like this *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — The radio button should be displayed before the variant name *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Show a confirmation modal like this when user tries to remove an item *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — on update- If any Draft order's customer is eligible for Credit Sales, then allow the Credit sales button on update too. Customer should be eligible for Credit Sales if only the customer field value "Allowed Credit Sales?" = 1. *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Show the order and item status like this *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — Add a pay button in order details when- order is made with credit sales and order status = ready to serve/served *(NEW ISSUES | > POS Order page > OLD ISSUES)*
- **Defect** — When an order has Guest Choice- Show it above the kitchen note line, in one line- "Spice Level":"Mild","Add Butter/Ghee":"No","Crispiness":"Extra Crispy" *(NEW ISSUES | > POS Order page > KITCHEN ORDERS)*

</details>

## 3.18 Desktop — 23-05-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 2 defect(s), 11 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 13 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (13 items)</strong></summary>

- **Requirement** — For variant items, in the cart, show item name instead of item code
- **Requirement** — Add three types of coffee – L/M/S. Change all item statuses to Ready to Serve from the front order. Then, in the split bill, drag only Coffee-L for payment and complete the payment. *(Split Order:)*
- **Defect** — Party size is not updating after one slot payment. *(Split Order:)*
- **Requirement** — Allow to update Party Size and pass to Invoice also. Auto update the party size slot wise but user can also change it. *(Split Order:)*
- **Requirement** — After PIN enable, on save, the Discount field must be Disabled and the "SAVE" button replace to PIN with session ending. *(Split Order:)*
- **Requirement** — After Payment, the Print Modal should appear. *(Split Order:)*
- **Requirement** — Last Invoice must be update the Parent Invoice with last split payment. and also the Table should be available. *(Split Order:)*
- **Requirement** — After Last Slot is paid, then return to the Table page after Print Done. *(Split Order:)*
- **Defect** — The Expected amount is not showing the updated amount. *(Split Order: > Clock-IN/OUT)*
- **Requirement** — When Clock-IN/OUT is submitted for the first time for approval it should only show the 2nd message- Clock-IN/OUT submitted. Awaiting approval *(Split Order: > Clock-IN/OUT)*
- **Requirement** — If user's last "Submission Type" is CLOCK-OUT of the territory's counter, and its status is DRAFT, then the Modal should not auto closed + all the input fileds will be disabled and allow a "Verify" button instead of CLOCK-OUT button. *(Split Order: > Clock-IN/OUT)*
- **Requirement** — Rename all the Clock in/out to "Clock-IN"/"Clock-OUT" *(Split Order: > Clock-IN/OUT)*
- **Requirement** — If Frappe Role has "Restaurant Cashier" and user Clicked IN, then disallow to change "Outlet" until Clock OUT. *(Split Order: > Clock-IN/OUT)*

</details>

## 3.19 POS Web — 21-05-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 3 defect(s), 128 requirement(s), 2 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 80 implemented/reported complete, 53 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements, verification/decision points within cash control / clock-in-out.

### Pending / Deferred items

- **Requirement · Pending** — Sales Overview *(Existing Reports:)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_ > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_ > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_ > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_ > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_ > Footer)*
- **Requirement · Pending** — Item Sales Summary *(Existing Reports:)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Payment Overview *(Existing Reports:)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Daily Cash Audit *(Existing Reports:)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line *(Existing Reports: > New Report: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under the STRAIGHT line, on Center > Place the Report Name [Bold] *(Existing Reports: > New Report: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026] *(Existing Reports: > New Report: > Add Print as PDF [Should generate as per filter] > Header)*
- **Requirement · Pending** — With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By *(Existing Reports: > New Report: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic] *(Existing Reports: > New Report: > Add Print as PDF [Should generate as per filter] > Footer)*
- **Requirement · Pending** — From Sales Invoice *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview])*
- **Requirement · Pending** — Doc Status = 1 *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Order From = "custom_order_from" *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Service Mode = “custom_service_type” *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Amount = Sum of “net_total” *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Group by "Order From + “Service Type + Territory” *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Total Sales = Sum of “net_total” *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Discount = "base_discount_amount" > (Sum of Discounted Invoice qty) *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — SD = Table > "Sales Taxes and Charges" > "custom_is_sd = 1" > tax_amount > (Sum of with SD Invoice qty) *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — VAT = Table > "Sales Taxes and Charges" > "custom_is_tax = 1" > tax_amount *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Auto Round > Sum of "rounding_adjustment" > (Sum of Auto Round NOT = 0 Invoice qty) *(Existing Reports: > New Report: > New Report Query: > Sales [Query much like Service Mode and Sales Overview] > From Sales Invoice)*
- **Requirement · Pending** — Additionally need percentage of each Payment method *(Existing Reports: > New Report: > New Report Query: > Collection [Query same like Payment Overview])*
- **Requirement · Pending** — _Group by + Territory_ *(Existing Reports: > New Report: > New Report Query: > Collection [Query same like Payment Overview])*
- **Defect · Pending** — Check *(Existing Reports: > New Report: > Socket Notification:)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (80 items)</strong></summary>

- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Sales Overview)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Sales Overview)*
- **Requirement** — Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_ *(Existing Reports: > Sales Overview)*
- **Requirement** — Header *(Existing Reports: > Sales Overview > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_)*
- **Requirement** — Footer *(Existing Reports: > Sales Overview > Add Print as PDF [Should generate as per filter] > _**HEADER & FOOTER are same for all reports**_)*
- **Requirement** — All Item should be group by Territory also. *(Existing Reports: > Item Sales Summary)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Item Sales Summary)*
- **Requirement** — Add a "Outlet" column after "Category" *(Existing Reports: > Item Sales Summary)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Item Sales Summary)*
- **Requirement** — Add Print as PDF [Should generate as per filter] *(Existing Reports: > Item Sales Summary)*
- **Requirement** — Header *(Existing Reports: > Item Sales Summary > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Footer *(Existing Reports: > Item Sales Summary > Add Print as PDF [Should generate as per filter])*
- **Requirement** — All Item should be group by Territory also. *(Existing Reports: > Payment Overview)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Payment Overview)*
- **Requirement** — Add a "Outlet" column after "Method Name" *(Existing Reports: > Payment Overview)*
- **Verification / Decision** — Why it's showing same "Method Name" multiple time? *(Existing Reports: > Payment Overview)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Payment Overview)*
- **Requirement** — Add Print as PDF [Should generate as per filter] *(Existing Reports: > Payment Overview)*
- **Requirement** — Header *(Existing Reports: > Payment Overview > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Footer *(Existing Reports: > Payment Overview > Add Print as PDF [Should generate as per filter])*
- **Requirement** — The default date range should be set to today. *(Existing Reports: > Daily Cash Audit)*
- **Defect** — Date range filter issue > showing till 1 day before the End date. *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — Details: Add "Update by" = "modified_by" *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — In the list, Submitted On time is always showing as 12:00 AM *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — Make different font color for "Clock-IN and OUT" [List + Details] *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — List page: If Draft, show status = To Approve, If Submitted = Approved *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — Rename the Accept button to "Approve" *(Existing Reports: > Daily Cash Audit)*
- **Requirement** — Service Mode Analytics *(Existing Reports:)*
- **Requirement** — Correct the subtitle to "Compare Dine-in & Takeout" *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Correct the additional path name to "Service Mode Analytics" *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Change the color and name for these, also fix in the chart *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — When no data is found, the message should be updated to: "No service mode analytics data found for the selected date range." *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Do the same as BanCan > Add "Order From" value + Card wise "Order Qty" & Add "Total Orders" beside the "Total Revenue" *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Completed from Biplob *(Existing Reports: > Service Mode Analytics > Do the same as BanCan > Add "Order From" value + Card wise "Order Qty" & Add "Total Orders" beside the "Total Revenue")*
- **Requirement** — Completed from Amir *(Existing Reports: > Service Mode Analytics > Do the same as BanCan > Add "Order From" value + Card wise "Order Qty" & Add "Total Orders" beside the "Total Revenue")*
- **Defect** — Date range filter issue > showing till 1 day before the End date. *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Add Print as PDF [Should generate as per filter] *(Existing Reports: > Service Mode Analytics)*
- **Requirement** — Header *(Existing Reports: > Service Mode Analytics > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Footer *(Existing Reports: > Service Mode Analytics > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Table & Covers PnL *(Existing Reports:)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Table & Covers PnL)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Table & Covers PnL)*
- **Requirement** — Add Print as PDF [Should generate as per filter] *(Existing Reports: > Table & Covers PnL)*
- **Requirement** — Header *(Existing Reports: > Table & Covers PnL > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Footer *(Existing Reports: > Table & Covers PnL > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Order-to-Serve Lag Report *(Existing Reports:)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > Order-to-Serve Lag Report)*
- **Requirement** — Order by "Voucher No" descending. *(Existing Reports: > Order-to-Serve Lag Report)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > Order-to-Serve Lag Report)*
- **Requirement** — Add Print as PDF [Should generate as per filter] *(Existing Reports: > Order-to-Serve Lag Report)*
- **Requirement** — Header *(Existing Reports: > Order-to-Serve Lag Report > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Footer *(Existing Reports: > Order-to-Serve Lag Report > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Day-End Audit Summary *(Existing Reports: > New Report:)*
- **Requirement** — Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier *(Existing Reports: > New Report: > Day-End Audit Summary)*
- **Requirement** — All the value must be fetched as per logged user's territory permission *(Existing Reports: > New Report: > Day-End Audit Summary)*
- **Requirement** — Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. *(Existing Reports: > New Report: > Day-End Audit Summary)*
- **Requirement** — Add Print as PDF [Should generate as per filter] *(Existing Reports: > New Report: > Day-End Audit Summary)*
- **Requirement** — Header *(Existing Reports: > New Report: > Day-End Audit Summary > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Footer *(Existing Reports: > New Report: > Day-End Audit Summary > Add Print as PDF [Should generate as per filter])*
- **Requirement** — Follow the image *(Existing Reports: > New Report: > Day-End Audit Summary)*
- **Requirement** — Sales [Query much like Service Mode and Sales Overview] *(Existing Reports: > New Report: > New Report Query:)*
- **Requirement** — Collection [Query same like Payment Overview] *(Existing Reports: > New Report: > New Report Query:)*
- **Verification / Decision** — What is the internal filter on List page? *(Existing Reports: > New Report: > Stock Transfer:)*
- **Requirement** — On Draft, "ArcPOS Transfer Creator" + Source Outlet = User's Default Territory" can edit the voucher. Also can Submit the TROUT. *(Existing Reports: > New Report: > Stock Transfer:)*
- **Requirement** — Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier *(Existing Reports: > New Report: > Reports (Module):)*
- **Requirement** — All reports except "Day-End Audit Summary" *(Existing Reports: > New Report: > Reports (Module): > Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier)*
- **Requirement** — Permission > System Manager, ArcPOS Manager, Restaurant Manager *(Existing Reports: > New Report: > Reports (Module): > Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier > All reports except "Day-End Audit Summary")*
- **Requirement** — Only "Day-End Audit Summary" *(Existing Reports: > New Report: > Reports (Module): > Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier)*
- **Requirement** — Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier *(Existing Reports: > New Report: > Reports (Module): > Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier > Only "Day-End Audit Summary")*
- **Requirement** — Outlet filter's default value should be the user's Frappe default territory permission, do not change auto if user update the outlet from POS front end.. *(Existing Reports: > New Report: > Reports (Module):)*
- **Requirement** — Add and implement "Print" as PDF generate as per documents default Print Format > Direct call Frappe document PDF. *(Existing Reports: > New Report: > Stock Requisition:)*
- **Requirement** — Place the "Print" button in the Details page *(Existing Reports: > New Report: > Stock Requisition: > Add and implement "Print" as PDF generate as per documents default Print Format > Direct call Frappe document PDF.)*
- **Requirement** — "Approve" button should be validate with "Source Outlet" *(Existing Reports: > New Report: > Stock Requisition:)*
- **Requirement** — Add and implement "Print" as PDF generate as per documents default Print Format > Direct call Frappe document PDF. *(Existing Reports: > New Report: > Stock Transfer:)*
- **Requirement** — Place the "Print" button in the Details page *(Existing Reports: > New Report: > Stock Transfer: > Add and implement "Print" as PDF generate as per documents default Print Format > Direct call Frappe document PDF.)*
- **Requirement** — "Accept" button should be validate with "Target Outlet" *(Existing Reports: > New Report: > Stock Transfer:)*

</details>

## 3.20 Desktop — 18-05-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 1 defect(s), 6 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 6 implemented/reported complete, 1 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

- **Requirement · Pending** — **Option A (Automated Polling):** If a Voucher remains in an Approval/Draft state, listen for state changes; upon a backend transition to Approved/Submitted, the operational modal must auto-close. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 3. Module: Outlet Opening & Closing Mechanics > **Smart Counter Defaulting:** If a designated retail outlet operates with only a single counter registry, configure the UI to automatically populate that counter name as the default option.)*

### Business rules / contextual notes

- * **Zero-Variance Auto-Submission:** If there is no difference (variance is 0) between physical cash and Expected counts, the Cashier Voucher entry must be automatically Submitted. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 3. Module: Outlet Opening & Closing Mechanics)*
- * **Standard Staff Restriction (Draft Only):** If a financial discrepancy exists and the active session user does not hold the Frappe roles "System Manager, ArcPOS Manager, or Restaurant Manager", the system will restrict actions to saving the entry as a Draft for administrative review. On waiting approval, user must not make another request. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 3. Module: Outlet Opening & Closing Mechanics)*
- * **Managerial Override (Direct Submission):** If a financial discrepancy exists but the user possesses the role of "System Manager, ArcPOS Manager, or Restaurant Manager", grant immediate bypass clearance to directly Submit the entry. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 3. Module: Outlet Opening & Closing Mechanics)*

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (6 items)</strong></summary>

- **Defect** — **Cross-Device Responsiveness:** Resolve layout and responsive styling issues on the Order Details page. Conduct a comprehensive UI audit across all other POS pages to ensure consistency across different screen dimensions. *(1. Global UI & Responsiveness)*
- **Requirement** — **Draft Creation Control:** Implement a "SAVE" button on the LEFT side of the panel. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode))*
- **Requirement** — Clicking this button must securely save the active transactional state into the backend with a docstatus = 0 (Draft) configuration. _I will check the next flows if its meets as I expecting!_ *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > **Draft Creation Control:** Implement a "SAVE" button on the LEFT side of the panel.)*
- **Requirement** — **Smart Counter Defaulting:** If a designated retail outlet operates with only a single counter registry, configure the UI to automatically populate that counter name as the default option. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 3. Module: Outlet Opening & Closing Mechanics)*
- **Requirement** — **Option B (Manual Interrogation):** Provide a dedicated "Re-sync" button or using existing Clock-IN/OUT button to dynamically call the latest document state flag. If the backend verification confirms the Voucher is now Approved/Submitted, programmatically close the modal. *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 3. Module: Outlet Opening & Closing Mechanics > **Smart Counter Defaulting:** If a designated retail outlet operates with only a single counter registry, configure the UI to automatically populate that counter name as the default option.)*
- **Requirement** — **Print Pipeline Modifications:** _Standard print routine workflows require structural updates. (Logic specifications to be finalized and added here)._ *(1. Global UI & Responsiveness > 2. Workflow: New Order (Pay First Mode) > 4. Module: Print Triggers & Formatting)*

</details>

## 3.21 POS - Desktop — 14-05-2026

**Main functional focus:** Offline & Synchronization  
**Content mix:** 4 defect(s), 7 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 10 implemented/reported complete, 1 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within offline & synchronization.

### Pending / Deferred items

- **Defect · Pending** — If Backend is unreachable then how the OFFLINE activity will be performed?

### QA verification focus

- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (10 items)</strong></summary>

- **Defect** — Showing this error while changing an order's status from **Ready to Serve** to **Served** from the order list
- **Requirement** — **Front Order**- When "Ready All" or "Ready to Serve" is clicked, the success message should display "Item is now ready to serve" instead of current message.
- **Requirement** — Showing no data in table switch
- **Requirement** — If "Pay First" > then Order status+ Item Status should be "Waiting". *(New Order:)*
- **Requirement** — Table Party size modal *(New Order:)*
- **Defect** — Does not allowing to update "Number of Guest" by Keyboard Digit *(New Order: > Table Party size modal:)*
- **Requirement** — Delete/Backspace button should change the qty to 0 and =0 should not allow to go next/save. *(New Order: > Table Party size modal:)*
- **Defect** — Table not fetching > Shanta Forum *(New Order: > Update Order:)*
- **Requirement** — If Order Type = Pay First and Order or Item Status = Served, then allow "Closed" *(New Order: > Update Order: > Order List and Details:)*
- **Requirement** — If Single item status changed to "Ready to Serve" then change the Success Toast text to "Item now ready to serve". *(New Order: > Update Order: > Front Orders:)*

</details>

## 3.22 POS- Desktop Defects & Requirements — After 11th May

**Main functional focus:** Stock & Inventory  
**Content mix:** 17 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 17 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within stock & inventory.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.
- Verify notifications, recipient selection and redirection.

<details>
<summary><strong>Implemented / reported complete scope (17 items)</strong></summary>

- **Defect** — When one action button is clicked, other action buttons also shows as loading.
- **Defect** — In draft order edit, when the customer is updated, the system does not apply the new customer's default discount after the update.
- **Defect** — In draft order edit, when an item's issue type is changed from complimentary/gift/wastage to Regular, the item price remains as 0.00
- **Defect** — When only gift/complementary/wastage items are added
- **Defect** — Get data from sales invoice: Customer Email = "contact_email", Customer Phone = Rename to "Customer Mobile" = contact_mobile and Customer Address = address_display. If No value then show (--)
- **Defect** — If the SD is not available, it should not be shown in the print.
- **Defect** — If a Table is occupied with a Submitted Order, then on click the Table, redirect to the Order Details page not to POS view.
- **Defect** — Show "Submit" [will pass the invoice docstatus = 1 + "Is Credit Sales = 1"] button instead of "Pay" from all the page, if the "Grand Total/Rounded Total = 0".
- **Defect** — Do not pass any Order Status and Item Status [except new added item] on Edit/update *(Credit Sales)*
- **Defect** — If new Order, Order Status and Item Status will be same as now = Waiting *(Credit Sales)*
- **Defect** — Related behavior requires review; the supplied source referenced it without restating the details. *(Credit Sales > After Lunch Task:)*
- **Defect** — Rename "Serve All" to "Ready All" *(Credit Sales > After Lunch Task: > Front Orders)*
- **Defect** — Update from "Front Order" > Removing other items which are "Prepare At = Kitchen" from Sales Invoice *(Credit Sales > After Lunch Task: > Front Orders)*
- **Defect** — If all item status NOT = "Ready to Serve/Served" then Disable the "Pay" button *(Credit Sales > After Lunch Task: > Order Update)*
- **Defect** — Show below data under the Grand Total row *(Credit Sales > After Lunch Task: > Print Correction)*
- **Defect** — If the invoice Outstanding Amount = 0, then show > Paid Amount-------------------- {{rounded_total}} *(Credit Sales > After Lunch Task: > Print Correction > Show below data under the Grand Total row)*
- **Defect** — If the invoice Outstanding Amount NOT = 0, then show > Due Amount -------------- {{outstanding_amount}} *(Credit Sales > After Lunch Task: > Print Correction > Show below data under the Grand Total row)*

</details>

## 3.23 Order Split Functionality

**Main functional focus:** Printing  
**Content mix:** 0 defect(s), 7 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 0 implemented/reported complete, 7 pending, 0 deferred

**Summary:** This work package covers functional or UI requirements within printing.

### Pending / Deferred items

- **Requirement · Pending** — Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**] *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print)*
- **Requirement · Pending** — Phase 1: UI Trigger and Redirection *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print > Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**])*
- **Requirement · Pending** — Phase 2: Drag-and-Drop Interface Logic *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print > Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**])*
- **Requirement · Pending** — Phase 3: Automated Calculations *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print > Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**])*
- **Requirement · Pending** — Phase 4: Transaction Execution (The "Pay" Action) *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print > Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**])*
- **Requirement · Pending** — Phase 5: Final Guest Optimization *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print > Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**])*
- **Requirement · Pending** — Phase 6: Individual Printing *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print > Item-Wise Split Payment Workflow [Only if the **Main invoice docstatus = 0 and any item status = Ready to Serve/Served**])*

### Business rules / contextual notes

- Example: Assuming
- Split Bill Trigger: After the "Pay" button, a new "Split Order" option will be available. *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print)*
- Quantity Sync: When items are moved to the right and update the Qty, the left-side quantity increase/decreases in real-time. If a left-side item’s quantity reaches 0, that row is automatically hidden and marked for "deletion" in the backend. *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print)*
- Original Invoice Update: Upon a successful payment, the original (left-side) invoice is updated by subtracting the paid items/quantities. Items with a quantity of 0 are permanently deleted from the original document. *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print)*
- Last Guest Logic: The system will not create a new invoice for the final guest. Instead, it will update the remaining original invoice and process the final payment against it. *(Now, All 4 want's to split the Bill and also make payment individually with individual Bill Print)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.

## 3.24 POS WEB Changes & Requirements — After 5th May

**Main functional focus:** Stock & Inventory  
**Content mix:** 38 defect(s), 3 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 39 implemented/reported complete, 1 pending, 1 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within stock & inventory.

### Pending / Deferred items

- **Defect · Deferred** — Need to work on Not Started status- when a stock transfer created from Stock Requisition is cancelled. Also add in status filter. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > Stock Requisition)*
- **Defect · Pending** — In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (39 items)</strong></summary>

- **Defect** — Fix the menu for mobile view.
- **Requirement** — Add an shortcut option with Menu list to move to another menu from except homepage. Show it like this *(Navigation Bar)*
- **Requirement** — Should not show this when the page is loaded the first time *(Navigation Bar)*
- **Requirement** — User can make the change of Default outlet only from the Homepage other wise disable the field. *(Navigation Bar)*
- **Defect** — Should show data here according to this *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — Remove Guest Information from order details. *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — Add a "Customer" filter (Type and Select) that is based on the user's territory permissions. *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — Order details- After payment table field is showing blank. *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — The Order From column is also not showing table number after payment. *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — Full calculation of SD/VAT/Auto round is pending. *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — Print functionality pending. *(Navigation Bar > Orders- Fix the full functionality after completing POS order)*
- **Defect** — Create stock transfer is not accepting decimal values *(Navigation Bar > Orders- Fix the full functionality after completing POS order > Stock Requisition Details)*
- **Defect** — The font color of disabled fields is not properly visible in dark mode. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > Stock Requisition Details)*
- **Defect** — Select a Table- add a **Refetch Tables** button *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — On update item modify this button to Update item *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — For other tables, Do not show pathao and foodpanda here and for pathao and foodpanda all the fields in Customer & Table will be non editable *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — For pathao and foodpanda show the table name- outlet beside the order summary text like this *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Item **Coffee-L and Coffee-M** is showing separately *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Rename Create Order button to-> Save and Create New. Pay button to-> Make Payment. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — No need to show Dine-in under item. Only show takeout beside the item name. The variant name should be under item name. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — While creating new order when Pay Later is selected only Save and Create New button will be shown. [With credit sales button if available] *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — While creating new order when Pay First is selected only Make Payment option will be shown. [With credit sales button if available] *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — DRAFT EDIT- If table has been changed to another Available Table, then the earlier table must be Available and next one should be Occupied with link the Order no on order update. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Issue Type except REGULAR item should show as per select in the Cart/Print and should save as 0 rate in the invoice. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — If the customer "Allowed Credit Sales" = 1, then the button should show and functional. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — If any Draft order's customer is eligible for Credit Sales, then allow the Credit sales button on update too. Customer should be eligible for Credit Sales if only the customer field value "Allowed Credit Sales?" = 1. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — PIN- System Manager / ArcPOS Manager/ Restaurant Manager these role users won't have to enter PIN anywhere. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — If the "Attribute Type for POS" or "Choice Type for POS" is set to multiple, the system should take the parent item's price instead of the variant's price. Otherwise it will take the variant's price. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — If both the "Attribute Type for POS" and "Choice Type for POS" are set to single, the system should create separate item names by concatenating the item's parent's name with the first attribute's variant name, and then create another item with the parent's name and the second attribute's variant name. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — If the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to mixed, the system should concatenate the parent item's name from each attribute's variant using a hyphen ("-") and match it with the variant items created in the item list. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — The item modal should open when the user clicks anywhere on the item row. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Show discount according to the default discount set for customer. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — When an order is saved with a customer who has default discount e.g- 10% then in edit when another customer with default discount is selected e.g- 12%, the discount still shows for the previous customer. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — In draft order edit the void button should also have PIN functionality. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Modify the confirmation modal when the user attempts to navigate to another page without saving the order *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Check > If the docstatus = 0, then only Frappe Role = Restaurant Manager, ArcPOS Manager and System Manager" can Approve/Submit. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > POS _[Take the same code reference from Desktop App]_)*
- **Defect** — Set auto fetch latest orders with interval every 30 Seconds. Also add a "Refetch Orders" button *(Navigation Bar > Orders- Fix the full functionality after completing POS order > Kitchen Orders)*
- **Defect** — Accept All/Ready All button should show only for "Prepare At = Kitchen" items. *(Navigation Bar > Orders- Fix the full functionality after completing POS order > Kitchen Orders)*
- **Defect** — When I accept an order from the kitchen, the items from the front order get deleted from the invoice *(Navigation Bar > Orders- Fix the full functionality after completing POS order > Kitchen Orders)*

</details>

## 3.25 Backend Defects & Requirements — After 06-05-2026

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 95 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 72 implemented/reported complete, 22 pending, 1 deferred

**Summary:** This work package covers reported product defects/corrections within cash control / clock-in-out.

### Pending / Deferred items

- **Defect · Pending** — **WC-Web POS**-> Payment for both credit sales and split payment is not working.
- **Defect · Pending** — https://wcpos.aninda.me/api/method/excel_restaurant_pos.api.item.get_item_details?item_code=Coffee *(Permission Issues > Web-POS)*
- **Defect · Pending** — Real time Email and Push Notification. *(Permission Issues > Web-POS)*
- **Defect · Pending** — Item Order Status = "Waiting" + Prepare AT = "Kitchen" then notify-to based on Territory default wise "Restaurant Chef" and "Restro Kitchen Staff" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect · Pending** — On click > redirect to > Specific "Kitchen Orders" page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Item Order Status = "Waiting" + Prepare AT = "Kitchen" then notify-to based on Territory default wise "Restaurant Chef" and "Restro Kitchen Staff")*
- **Defect · Pending** — On click > redirect to > Specific order's details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Order: Item Order Status = "Ready to Serve" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter")*
- **Defect · Pending** — Order: Order Status = "Open" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect · Pending** — On click > redirect to > Specific order's details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Order: Order Status = "Open" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter")*
- **Defect · Pending** — Stock Requisition: If Purpose = "Material Transfer" > On "Pending" > notify-to "Target Outlet" [based on Territory default wise] "ArcPOS Requisition Approver" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect · Pending** — On click > redirect to > Specific Stock Requisition details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Stock Requisition: If Purpose = "Material Transfer" > On "Pending" > notify-to "Target Outlet" [based on Territory default wise] "ArcPOS Requisition Approver")*
- **Defect · Pending** — On click > redirect to > Specific Stock Requisition details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Stock Requisition: If Purpose = "Material Transfer" > On "Approve" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS Transfer Creator")*
- **Defect · Pending** — On click > redirect to > Specific Stock Transfer details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Stock Transfer: If Type= "Material Transfer" > On "In Transit" > notify-to "Target Outlet" [based on Territory default wise] "ArcPOS Transfer Approver")*
- **Defect · Pending** — On click > redirect to > Specific wastage management details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Wastage Management: If Type= "Material Issue" > On "Draft" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Approver")*
- **Defect · Pending** — On click > redirect to > Specific wastage management details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Wastage Management: If Type= "Material Issue" > On "Submit" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Creator")*
- **Defect · Pending** — Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect · Pending** — On click > redirect to > Specific Daily Cash Audit details page *(Permission Issues > Web-POS > Real time Email and Push Notification. > Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager")*
- **Defect · Pending** — Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Submit" > notify-to "Territory" [based on Territory default wise] "Restaurant Cashier" and does not has any Manager Role *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect · Pending** — _I will add more stages here if I missed_ Below FYI > In BanCan, we managed this ArcPOS settings for **Push Notification** + ArcPOS Notification Token *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect · Pending** — Stock Requisition: If Purpose = "Material Transfer" > On "Pending" > notify-to **"Source Outlet"** [based on Territory default wise] "ArcPOS Requisition Approver" *(Correction of alert trigger of notification: [Existing])*
- **Defect · Deferred** — `IGNORE NOW` On OFFLINE order update, OFFLINE data is first priority. So if there are any change in Sales invoice in Backend Data then showing error LIKE "There is a modification already". So how can we ignore this and update the invoice with OFFLINE data?
- **Defect · Pending** — Using Print format for POS web prints (ArcPOS Settings) with Custom Page size.
- **Defect · Pending** — Earlier was `notify-to "Target Outlet"`but should be `notify-to "Source Outlet"` *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Correction of alert trigger of notification: [Existing] > Stock Requisition: If Purpose = "Material Transfer" > On "Pending" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS Requisition Approver")*
- **Defect · Pending** — Just add one more condition that, if document's "Difference" value NOT = 0 *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Correction of alert trigger of notification: [Existing] > Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager")*

### Business rules / contextual notes

- We may have some ToDo to create payment entry from Main ERP. I will let you know. Here is Logic *(Permission Issues > Web-POS)*
- Currently we have a feature that, if we create any new item, then a "Standard Buying" price setting automatically with 1 BDT rate.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.

<details>
<summary><strong>Implemented / reported complete scope (72 items)</strong></summary>

- **Defect** — Invoice- ORD-26-00942 *(Permission Issues)*
- **Defect** — Same issue when discount is applied with PIN *(Permission Issues)*
- **Defect** — After approval, when creating a stock transfer and deleting an item, the deleted item still appears in the stock transfer. *(Permission Issues > Web-POS)*
- **Defect** — Add territory for Sales Overview, Service Mode Analytics. *(Permission Issues > Web-POS)*
- **Defect** — Front: The button will view if the Invoice docstatus = 0 and this will be manage by PIN *(Permission Issues > Web-POS)*
- **Defect** — In the Invoice > If All Item status NOT = "Preparing/Ready To Serve/Served" and Void triggered then the invoice will be auto delete in a Cron Job *(Permission Issues > Web-POS)*
- **Defect** — But if any of item's status = "Preparing/Ready To Serve/Served" and Void triggered then the invoice should not delete *(Permission Issues > Web-POS)*
- **Defect** — If in a Invoice all item are "Prepare At" = "Front" or "Kitchen" then the order should only view in the specific Front or Kitchen list *(Permission Issues > Web-POS)*
- **Defect** — Only if all the item's status is "Preparing or Ready to Serve" then update the Order Status "Preparing or Ready to Serve" *(Permission Issues > Web-POS)*
- **Defect** — If the item's "Is BOM Item" is YES, only then the Work Order will execute (Re-Verify) *(Permission Issues > Web-POS)*
- **Defect** — If the item's "Is BOM Item" is NO, then the Item status must be changed to "Ready to Serve" from Prepapring *(Permission Issues > Web-POS)*
- **Defect** — Cash Account (Paid To) must be as per Outlet's Counter wise For Pay Later/Pay First and Credit Order Payment *(Permission Issues > Web-POS)*
- **Defect** — If Order via QR Code (No Counter Linked) then use a default Account from the Outlet. You can use: Territory > custom_default_cash_account (Remove the Field Depends On) *(Permission Issues > Web-POS)*
- **Defect** — If "From Counter" exists then the value set to the Payment Entry *(Permission Issues > Web-POS)*
- **Defect** — New feature: Payment Entry: selected invoice payment amount auto set from Main ERP *(Permission Issues > Web-POS)*
- **Defect** — This can be managed by Client Script and already set this. You can verify. *(Permission Issues > Web-POS > New feature: Payment Entry: selected invoice payment amount auto set from Main ERP)*
- **Defect** — Currently need to add a custom field = "custom_total_outs_amount" and keep the new field as Currency Type and Read Only [Already set in WC staging] *(Permission Issues > Web-POS > New feature: Payment Entry: selected invoice payment amount auto set from Main ERP)*
- **Defect** — Keep invoice wise record if any PIN user gives Item Issue OR/And Discount OR/And Void *(Permission Issues > Web-POS)*
- **Defect** — Web Price should be auto calculated and set for the "Standard Selling price". *(Permission Issues > Web-POS)*
- **Defect** — How can we manage it? My Opinion > Can we use Login PIN to use alternative Credentials for ONLINE and OFFLINE? *(Permission Issues > Web-POS)*
- **Defect** — On Purchase Order creation, the Purchase Invoice should auto create taking the same data of the Order. *(Permission Issues > Web-POS)*
- **Defect** — Purchase Invoice Customization: Make "update_stock" default 1. *(Permission Issues > Web-POS)*
- **Defect** — Review the related behavior and complete the referenced correction described elsewhere in the supplied source. *(Permission Issues > Web-POS)*
- **Defect** — Order: Item Order Status = "Ready to Serve" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect** — Stock Requisition: If Purpose = "Material Transfer" > On "Approve" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS Transfer Creator" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect** — Stock Transfer: If Type= "Material Transfer" > On "In Transit" > notify-to "Target Outlet" [based on Territory default wise] "ArcPOS Transfer Approver" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect** — Wastage Management: If Type= "Material Issue" > On "Draft" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Approver" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect** — Wastage Management: If Type= "Material Issue" > On "Submit" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Creator" *(Permission Issues > Web-POS > Real time Email and Push Notification.)*
- **Defect** — Update your existing logic *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Check Occupied Tables and match with Running Order > If the order found with all items marked as "Ready to Serve" or "Served" + Docstatus = 1 + Is Credit Sales = 1, then It should make the linked table available. *(Permission Issues > Web-POS > More will add here.... > Update your existing logic:)*
- **Defect** — If Submitted order link with any Payment, then the order status should be changed to "Closed" and Item status = Served *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — How to submit the order which contains all the item with ISSUE Type or 100% Discount? *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — If we archived this "**Credit Sales**" then, we will show "Submit" _[will pass the invoice docstatus = 1]_ button instead of "Pay" if the "Grand Total/Rounded Total = 0" with Flag "Is Credit Sales = 1", so that, with the cron Job condition, this will automatically update the Table Availability also. *(Permission Issues > Web-POS > More will add here.... > How to submit the order which contains all the item with ISSUE Type or 100% Discount?)*
- **Defect** — Is the "Last Opened By" user is fetching from the "Daily Cash Audit" last modified by? If yes, if the Manager approve/submit this then the cashier can be restricted. *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — From Kitchen or Front orders > There is a issue that, removing opposite items from the Draft invoice. [Shahed already shared with you] *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Set auto fetch the latest orders with interval every 30 Sec. *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — The Generated QR code link must be LIKE : https://_ArcPOS_ >_[portal_base_url]_/?table_id=_[id]_&outlet=_[default_outlet]_ *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Implement a function to RE GENERATE the QR Code *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — custom_web_rate - Make > Read Only > **Item Price** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — custom_total_outs_amount - Place below of "paid_amount" > **Payment Entry** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — excel_bank_name_cheque - Hide and remove from "Mandatory Depends On" > **Payment Entry** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — actual_qty - Mark > In List View > **Material Request Item** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Territory - new field add on Top > **Material Request** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — custom_outlet - hide > **Restaurant Table** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — outlet - Add "Fetch From" = 'territory.custom_outlet_name' > **Daily Cash Audit** *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Remove all standard notification from Frappe for WC *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Need Mode of **Payment wise + Territory wise + Counter wise** account setup on Payment Entry. [For CASH, we already done] *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Follow for > User Territory permission wise data and Print PDF *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — Footer view is hiding, please check to fix it. check: https://wcpos.aninda.me/api/method/frappe.utils.print_format.download_pdf?doctype=Material%20Request&name=MAT-MR-2026-00066&format=ArcPOS%20Material%20Request&no_letterhead=1&letterhead=No%20Letterhead&settings=%7B%7D&_lang=en *(Permission Issues > Web-POS > More will add here....)*
- **Defect** — This Email setup is missing in the ArcPOS Settings
- **Defect** — All the Emails and Push/Socket Notifications must send as per default territory permission. Currently all specific users are getting the notifications.
- **Defect** — List page data and Details-update permission must be validate as per Outlet (Source and Target), not as per document's territory.
- **Defect** — TRIN document territory should be acceptors default territory
- **Defect** — But now we need to modify this or another feature > **Condition is**
- **Defect** — If any BOM item's "total_cost" gets updated then the "Standard Buying" price rate of the item's should be auto updated. _[Because if we submit Stock ledger with Negative stock and if there are no valuation rate then its takes rate from the Buying Rate]_ *(But now we need to modify this or another feature > **Condition is**)*
- **Defect** — Use territory's Default Counter data if document's Counter field is empty. Set on Draft and Submit. Function should work from from Main ERP also.**[Did we already worked on this?]**
- **Defect** — Not getting the data in PDF, please check and fix > https://wcpos.aninda.me/app/print-format/Day-End%20Audit%20Summary
- **Defect** — Add the "VAT & other charges" data also before Payment section [as like the Image shared in Telegram]
- **Defect** — Order List page: If Order Status changed to "Served" OR "Closed" then pass Item Status = Served
- **Defect** — Add a new field in the "Sales Invoice" > "custom_is_offline_voucher" (Field Type = Check, Allow On Submit = 1" under existing field "custom_deleted_by_name"
- **Defect** — Correction of alert trigger of notification: [Existing]
- **Defect** — Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages:)*
- **Defect** — Wastage Management: If Type= "Material Issue" > On "Draft" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Approver" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages:)*
- **Defect** — Wastage Management: If Type= "Material Issue" > On "Submit" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Creator" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages:)*
- **Defect** — Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages:)*
- **Defect** — Wastage Management: If Type= "Material Issue" > On "Draft" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Approver" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages:)*
- **Defect** — On Doctype "BOM Item" > add an field under "item_code" > "Is Prep?" > Type = Check > In List View = 1 > Allow on Submit = 1 *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Frappe Customize:)*
- **Defect** — Stock Requisition: If Purpose = "Material Transfer" > On "Pending" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS Requisition Approver" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Correction of alert trigger of notification: [Existing])*
- **Defect** — Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager" *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Correction of alert trigger of notification: [Existing])*
- **Defect** — After Payment, the "Served" time is missing *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Split Bill)*
- **Defect** — Not Solved yet *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Stock Requisition)*
- **Defect** — Not Solved *(Email Notifications must send as per default territory permission. Currently all specific users are getting the notifications. For below stages: > Same email is receiving twice LIKE "Clock-IN/Out" Approval. For below stages: > Stock Transfer)*

</details>

## 3.26 Product Decisions & Requirements 05-05-2026

**Main functional focus:** Stock & Inventory  
**Content mix:** 2 defect(s), 6 requirement(s), 1 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 0 implemented/reported complete, 9 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements, verification/decision points within stock & inventory.

### Pending / Deferred items

- **Defect · Pending** — Table change impact is not happening
- **Requirement · Pending** — New feature: Split selected items + qty to multiple order / move to other table temporarily
- **Requirement · Pending** — Wastage / gift item amount on edit fetching actual rate
- **Requirement · Pending** — SD % show like VAT; if not available, then hide
- **Defect · Pending** — Credit sales issue with customer change, on update
- **Requirement · Pending** — Front order decision from them
- **Requirement · Pending** — New feature: Material request for purchase
- **Requirement · Pending** — Readiness for actual production environment and share credentials with them
- **Verification / Decision · Pending** — Test Desktop app on their POS machine

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify stock movement quantities, source/target outlet and workflow state.

## 3.27 POS- Desktop Defects & Requirements — After 5th May

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 49 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 46 implemented/reported complete, 3 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within cash control / clock-in-out.

### Pending / Deferred items

- **Defect · Pending** — Order update and Data Sync- Please optimize the performance.
- **Defect · Pending** — **SKIP** OFFLINE work pending. *(POS > Orders > Front Orders)*
- **Defect · Pending** — When the user comes online from offline, the clock-in/clock-out modal flashes onto the screen for a second. *(POS > Orders > Clock in/out)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.

<details>
<summary><strong>Implemented / reported complete scope (46 items)</strong></summary>

- **Defect** — Login page
- **Defect** — In next update while login dont keep the username and password.
- **Defect** — **DRAFT EDIT**- Table change impact is not happening- If table has been changed to another Available Table, then the earlier table must be Available and next one should be Occupied with link the Order no on order update.
- **Defect** — User can make the change of Default outlet only from the Homepage other wise disable the field.
- **Defect** — Cash Open/Closing with Cash Drawer functionality check
- **Defect** — Issue Type except REGULAR item should show as per select in the Cart/Print and should save as 0 rate in the invoice. *(POS)*
- **Defect** — How the Credit Sales button works? If the customer "Allowed Credit Sales" = 1, then the button should show and functional. *(POS)*
- **Defect** — **PIN**- **System Manager / ArcPOS Manager/ Restaurant Manager** these role users won't have to enter PIN anywhere. *(POS)*
- **Defect** — In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to **Combo**, the user should be able to increase the quantity of the item. *(POS)*
- **Defect** — While editing a draft order, when a new mixed item is added, the system does not allow increasing the quantity of that item. *(POS)*
- **Defect** — Credit sales issue with customer change, on update- If any Draft order's customer is eligible for Credit Sales, then allow the Credit sales button on update too. Customer should be eligible for Credit Sales if only the customer field value "Allowed Credit Sales?" = 1. *(POS)*
- **Defect** — The item modal should open when the user clicks anywhere on the item row *(POS)*
- **Defect** — When an order is saved with a customer who has default discount e.g- 10% then in edit when another customer with default discount is selected e.g- 12%, the discount still shows for the previous customer. *(POS)*
- **Defect** — In draft order edit the void button should also have PIN functionality. *(POS)*
- **Defect** — In draft order edit when user tries to remove the last item it should show a proper error message- **Cannot remove the last item. Plese void the order.** *(POS)*
- **Defect** — The error message comes from Backend. Skipping now *(POS > In draft order edit when user tries to remove the last item it should show a proper error message- **Cannot remove the last item. Plese void the order.**)*
- **Defect** — The "Pay" button should occupy the full width of the container and Remove the amount from and button and Rename it to **Make Payment** *(POS)*
- **Defect** — Selecting PIN is showing unknown error in offline mode. *(POS)*
- **Defect** — If offline, the Role users will get auto access. *(POS > Selecting PIN is showing unknown error in offline mode.)*
- **Defect** — Showing this error when trying to make payment of a draft order created with credit sales- Not allowed to change Grand Total after submission from. *(POS)*
- **Defect** — In every order print preview show like #00610 the order no. *(POS)*
- **Defect** — On Void, an remarks is mandatory > use "sales invoice > remarks. Show it in the Confirmation modal ++ Modal "Cancel" also should end/expire the session. *(POS)*
- **Defect** — Print Modal should not Scroll full, the Buttons should appear always as floating. *(POS)*
- **Defect** — Quick adding/removing items in the Draft order, works slowly also sometimes missed some items to add in the cart. *(POS)*
- **Defect** — Item Cart > Remove item should pop up a confirmation modal. *(POS)*
- **Defect** — In order list the total amount column value is showing wrong (doesn't match with the actual amount) *(POS > Orders)*
- **Defect** — The items issued with PIN-complimentary/gift/wastage is also showing price in order details. *(POS > Orders)*
- **Defect** — Add a "Customer" filter (Type and Select) that is based on the user's territory permissions. *(POS > Orders)*
- **Defect** — Make the order details design similar to this. Keep the fields same as before. *(POS > Orders)*
- **Defect** — Add + sign for these 2 *(POS > Orders)*
- **Defect** — After payment table field is showing blank. *(POS > Orders)*
- **Defect** — The Order From column is also not showing table number after payment. *(POS > Orders)*
- **Defect** — SD % show like VAT; if not available, then hide- As we showing the VAT % in the below of cart, make it similar for SD (10%) and if the all item is without SD then no need to show the SD row in the CART side and Print. *(POS > Orders > SD/VAT)*
- **Defect** — Fix the SD and VAT calculation in **Print**. *(POS > Orders > SD/VAT)*
- **Defect** — Kitchen order items are showing in front order as blank *(POS > Orders > Front Orders)*
- **Defect** — Remove these from filter *(POS > Orders > Front Orders)*
- **Defect** — When one action button is clicked, all other action buttons show as loading, *(POS > Orders > Front Orders)*
- **Defect** — Need to know the source of this **Remarks** *(POS > Orders > Front Orders)*
- **Defect** — Show the time with am/pm. *(POS > Orders > Front Orders)*
- **Defect** — Use this button instead of the X button *(POS > Orders > PIN)*
- **Defect** — Currently every Reload initiates Clock-OUT, Clock IN/OUT modal should only auto appear after Login based on the login user's last status. *(POS > Orders > Clock in/out)*
- **Defect** — After Clock OUT, immediate pop up of the Clock IN does not contains the actual expected Amount. If needed keep a loader to get the current Expected value of the account. *(POS > Orders > Clock in/out)*
- **Defect** — When another user tries to clock in using a different counter, the system does not allow it. *(POS > Orders > Clock in/out)*
- **Defect** — The specific counter should be disabled in the dropdown when another user is already clocked in with that counter *(POS > Orders > Clock in/out)*
- **Defect** — Show the confirm modal in the middle of the page *(POS > Orders > Clock in/out)*
- **Defect** — Fix this *(POS > Orders > Clock in/out)*

</details>

## 3.28 Cash Opening/Closing Feature - WC

**Main functional focus:** Cash Control / Clock-IN-OUT  
**Content mix:** 5 defect(s), 21 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 0 implemented/reported complete, 26 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within cash control / clock-in-out.

### Pending / Deferred items

- **Requirement · Pending** — When a "Restaurant Cashier" logs into the POS, the system performs a background check *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — Search for a "Daily Cash Audit" entry for the "Current Date" and "Counter" where Submission Type == Clock In. *(The Functional Process (Logic Flow) > When a "Restaurant Cashier" logs into the POS, the system performs a background check:)*
- **Defect · Pending** — IF NO: The "Clock In" modal pops up immediately. The general POS operation screen remains locked/hidden. *(The Functional Process (Logic Flow) > When a "Restaurant Cashier" logs into the POS, the system performs a background check: > Search for a "Daily Cash Audit" entry for the "Current Date" and "Counter" where Submission Type == Clock In.)*
- **Requirement · Pending** — IF YES: The user is redirected to the general POS operation LIKE HOME Page. *(The Functional Process (Logic Flow) > When a "Restaurant Cashier" logs into the POS, the system performs a background check: > Search for a "Daily Cash Audit" entry for the "Current Date" and "Counter" where Submission Type == Clock In.)*
- **Requirement · Pending** — The "Expected Opening Cash" = [Cash account "Debit - Credit"] of that counter *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — The user will press the button “Open Cash Drawer” and must count the physical cash in the drawer and enter it into the "Opening Amount". > [Just show the “Open Cash Drawer" button, no functionality for now] *(The Functional Process (Logic Flow))*
- **Defect · Pending** — If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason. *(The Functional Process (Logic Flow))*
- **Defect · Pending** — If the Logged user role = "Restaurant Cashier" then user can't submit the entry, pass the Draft to Submit (Approve) by Role user "Restaurant Manager" *(The Functional Process (Logic Flow) > If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason.)*
- **Defect · Pending** — Once Approve by "Restaurant Manager" > the cashier can start POS operation as the below conditions matched. *(The Functional Process (Logic Flow) > If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason.)*
- **Requirement · Pending** — Upon submission, the entry is saved, and the POS is unlocked for sales. *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — If Diff = (+) = Then Cash Debit and Default Company > Sales default income acc Credit *(The Functional Process (Logic Flow) > Upon submission, the entry is saved, and the POS is unlocked for sales.)*
- **Requirement · Pending** — If Diff = (-) = Then Cash Credit and Default Company > “Default Deferred Expense Account” acc Debit *(The Functional Process (Logic Flow) > Upon submission, the entry is saved, and the POS is unlocked for sales.)*
- **Requirement · Pending** — Will Submit a Journal Entry automatically *(The Functional Process (Logic Flow) > Upon submission, the entry is saved, and the POS is unlocked for sales.)*
- **Requirement · Pending** — The system should records all cash transactions during the shift in the GL Entry. *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — Before leaving, the user selects Clock Out. *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — The system calculates the Expected Closing Cash using the formula in Backend *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — Cash account Debit - Credit + Cash Sales = Expected Closing Cash. *(The Functional Process (Logic Flow) > The system calculates the Expected Closing Cash using the formula in Backend:)*
- **Requirement · Pending** — The user performs a physical count as the same process of "Clock In". *(The Functional Process (Logic Flow))*
- **Requirement · Pending** — Once submitted, the user is permitted to log out. *(The Functional Process (Logic Flow))*
- **Defect · Pending** — A cashier cannot open a new shift if a previous shift on the same counter was never "Clocked Out." *(The Functional Process (Logic Flow) > Validations)*
- **Requirement · Pending** — Every "Reason" provided for a difference is flagged for Manager review in the backend. *(The Functional Process (Logic Flow) > Validations)*
- **Requirement · Pending** — Use multi approval > “Restaurant Manager” will Approve the Request from “Daily Cash Audit” list page. *(The Functional Process (Logic Flow) > Validations)*
- **Requirement · Pending** — "Daily Cash Audit" module is only allowed for "Restaurant Manager" and can edit "Submitted Amount" and "Reason" in Draft. *(The Functional Process (Logic Flow) > Validations)*
- **Requirement · Pending** — Send Notification to the “Restaurant Manager” on create DRAFT if found Diff. *(The Functional Process (Logic Flow) > Validations)*
- **Requirement · Pending** — Cash Drawer Integration must be linked with each Counter. *(The Functional Process (Logic Flow) > Validations)*
- **Requirement · Pending** — Without Clock In entry for "Current Date" and "Counter" should not allow to create any Cash Payment. *(The Functional Process (Logic Flow) > Validations)*

### Business rules / contextual notes

- Note: For Clock Out > If the last entry from the Counter is "Clock In" and "Clock Out" entry not found against the Clock In, then find the "Clock In" date and match with ArcPOS Settings > If "Manage Outlet = Single" > "Default Outlet's" Day wise "Start to End Time" Duration. If the the Duration is crossed then On Browser Reload or After Login should pop up the "Clock Out" Modal. *(The Functional Process (Logic Flow) > Validations)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.
- Verify notifications, recipient selection and redirection.

## 3.29 BACKEND PENDING Defects & Requirements- POS WEB AND DESKTOP- 29th April

**Main functional focus:** Stock & Inventory  
**Content mix:** 6 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 5 implemented/reported complete, 1 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within stock & inventory.

### Pending / Deferred items

- **Defect · Pending** — After approval, when creating a stock transfer and deleting an item, the deleted item still appears in the stock transfer. *(Kitchen Orders > Stock Requisition)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (5 items)</strong></summary>

- **Defect** — After order payment the Account Paid To is not working as expected.
- **Defect** — Kitchen orders are showing in the front order section, and front orders are appearing in the kitchen order section. The filtering functionality is not working as expected. *(Kitchen Orders)*
- **Defect** — Created By and Accepted By API pending. *(Kitchen Orders > Stock Requisition)*
- **Defect** — Source Outlet and Target Outlet is showing blank when Stock Requisition is created from frappe. *(Kitchen Orders > Stock Requisition)*
- **Defect** — Add territory for Sales Overview, Service Mode Analytics. *(Kitchen Orders > Stock Requisition > Reports)*

</details>

## 3.30 Product Decisions & Requirements April 22, 2026

**Main functional focus:** Stock & Inventory  
**Content mix:** 0 defect(s), 22 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 18 implemented/reported complete, 4 pending, 0 deferred

**Summary:** This work package covers functional or UI requirements within stock & inventory.

### Pending / Deferred items

- **Requirement · Pending** — Order Void for prepared recipe invoice and keep track: permission for senior manager
- **Requirement · Pending** — Coffee and drinks front e prepare, will not go to kitchen, split view for kitchen
- **Requirement · Pending** — Ready to Serve order to POS notification
- **Requirement · Pending** — ISD branch / Sell from ready stock process discuss, fixed items which may have recipe to prepare but will always be sold from ready stock from all outlets?i.e cheese cake slices

### Business rules / contextual notes

- – We will remove the auto Delete functionality from Backend.
- – We will create variant items as multi. And need to implement in the POS
- We have to unmark "Is BOM Item" and it will treat as normal item. And also we will manage the Recipe and Kitchen/Front Orders menu by Role.
- – All set just need make corrections.

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify notifications, recipient selection and redirection.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (18 items)</strong></summary>

- **Requirement** — Cafe name: The White Canary Café
- **Requirement** — VAT & SD with Discount calculation will be provided by Jabed Bhai
- **Requirement** — Variant show as single item and show choice
- **Requirement** — Variant show with Display name
- **Requirement** — All day captain America breakfast double item choice
- **Requirement** — VAT & SD account different for outlets
- **Requirement** — Complementary, Gift, Wastage
- **Requirement** — Baking Prep and sell as single item? yes
- **Requirement** — Credit sales differentiate flag for customer profile
- **Requirement** — Discount 10/15/30/35, custom permission for senior manager
- **Requirement** — Batch qty edit allow
- **Requirement** — Material requisition and intermediate approval, and edit permission
- **Requirement** — Table wise party size income/cogs pnl report > Table & Covers PnL
- **Requirement** — Service performance report > Order-to-Serve Lag Report
- **Requirement** — Print format design will be provided
- **Requirement** — Outlet Counter wise Cash Account on Payment
- **Requirement** — Counter Data in Sales invoice and Payment Entry
- **Requirement** — Show the "Web Rate" for each item > Web Item will be auto calculated and set to the Selling price.

</details>

## 3.31 POS WEB Changes & Requirements — After 19th April

**Main functional focus:** Stock & Inventory  
**Content mix:** 48 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 44 implemented/reported complete, 4 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within stock & inventory.

### Pending / Deferred items

- **Defect · Pending** — **Kitchen orders**- Items issued with PIN is not showing here. *(New issues)*
- **Defect · Pending** — In Order details the items issued with PIN is also showing price. *(New issues)*
- **Defect · Pending** — Need to work on Not Started status- when a stock transfer created from Stock Requisition is cancelled. Also add in status filter. *(New issues > Stock Requisition)*
- **Defect · Pending** — System should not allow selecting the same outlet as both the source outlet and target outlet. *(New issues > Stock Requisition > Stock Transfer)*

### Business rules / contextual notes

- After approving a stock requisition, if the user does not have permission for the specific Source Outlet, they should not be able to create a transfer from that outlet. *(New issues > Stock Requisition > Outlet Wise Permission- **[Emraz Bhai]**)*

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify responsive layout, dark mode and action-state behavior.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (44 items)</strong></summary>

- **Defect** — Fix the **status** filter. *(New issues > Stock Requisition)*
- **Defect** — Remove Add Item button while creating transfer. *(New issues > Stock Requisition)*
- **Defect** — In Required By date picker past dates should be disabled. *(New issues > Stock Requisition)*
- **Defect** — Cancle button should not be shown when status is **Completed** *(New issues > Stock Requisition)*
- **Defect** — Fix the back button icon *(New issues > Stock Requisition)*
- **Defect** — Need to work on outlet wise permission. *(New issues > Stock Requisition > Outlet Wise Permission- **[Emraz Bhai]**)*
- **Defect** — **Orders**- Restaurant Cashier,Restaurant Manager, ArcPOS Manager, System Manager, Restaurant Waiter *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — **Kitchen Orders-** Restro Kitchen Staff, Restaurant Chef *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — **Recipes**- ArcPOS Recipe User *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — **Stock Requisition** *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — **Module view**- ArcPOS Transfer Approver, ArcPOS Transfer Creator, ArcPOS Requisition Approver *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Requisition**-)*
- **Defect** — **Create**- ArcPOS Transfer Creator *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Requisition**-)*
- **Defect** — **Approve**- ArcPOS Requisition Approver *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Requisition**-)*
- **Defect** — **Create Transfer**- ArcPOS Transfer Creator *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Requisition**-)*
- **Defect** — **Cancel**- ArcPOS Manager, System Manager *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Requisition**-)*
- **Defect** — **Stock Transfer** *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — **Module view**- ArcPOS Transfer Approver, ArcPOS Transfer Creator *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Transfer**-)*
- **Defect** — **Create**- ArcPOS Transfer Creator *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Transfer**-)*
- **Defect** — **Approve**- ArcPOS Transfer Approver *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Transfer**-)*
- **Defect** — **Cancel**- ArcPOS Manager, System Manager *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Stock Transfer**-)*
- **Defect** — **Wastage Management** *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — **Module view**- ArcPOS PCM Approver, ArcPOS PCM Creator *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Wastage Management**)*
- **Defect** — **Create**- ArcPOS PCM Creator *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Wastage Management**)*
- **Defect** — **Submit**- ArcPOS PCM Approver *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Wastage Management**)*
- **Defect** — **Cancel**- ArcPOS Manager, System Manager *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first > **Wastage Management**)*
- **Defect** — **Reports**- ArcPOS Manager, System Manager, Restaurant Manager *(New issues > Stock Requisition > ROLE PERMISSION- Tick Accounts Manager/Sales Manager/Stock Manager first)*
- **Defect** — In all the search item field it should not show template items.. *(New issues > Stock Requisition > Overall)*
- **Defect** — In all the search item field show Type to find items instead of No items found *(New issues > Stock Requisition > Overall)*
- **Defect** — Rename Territory to Outlet *(New issues > Stock Requisition > Overall)*
- **Defect** — Showing no data in Remarks. *(New issues > Stock Requisition > Kitchen Orders)*
- **Defect** — Sales invoices which has Is Deleted= 1, should not show in the list. *(New issues > Stock Requisition > Kitchen Orders)*
- **Defect** — In source outlet filter show the list of all outlets. *(New issues > Stock Requisition > Kitchen Orders)*
- **Defect** — Rename this placeholder to- Search order no. *(New issues > Stock Requisition > Kitchen Orders)*
- **Defect** — Orders made with credit sales are showing an error when accepting them from kitchen orders *(New issues > Stock Requisition > Kitchen Orders)*
- **Defect** — Rename to Prepare. *(New issues > Stock Requisition > Recipes)*
- **Defect** — Show the list of all outlets *(New issues > Stock Requisition > Stock Transfer)*
- **Defect** — Remove search territory filter. *(New issues > Stock Requisition > Stock Transfer)*
- **Defect** — Source outlet and target outlet filter not working *(New issues > Stock Requisition > Stock Transfer)*
- **Defect** — Remove **Submitted** from status filter and Add **In Transit**. *(New issues > Stock Requisition > Stock Transfer)*
- **Defect** — The time in Stock Ledger is showing wrong time after a draft submission. *(New issues > Stock Requisition > Wastage Management)*
- **Defect** — Source outlet should be shown by default and non editable. *(New issues > Stock Requisition > Wastage Management)*
- **Defect** — In wastage view- Show only Item Name and Remove the action column. *(New issues > Stock Requisition > Wastage Management)*
- **Defect** — Modify it to- This entry displays the wastage details. *(New issues > Stock Requisition > Wastage Management)*
- **Defect** — Remarks is not updating when a draft entry is submitted. *(New issues > Stock Requisition > Wastage Management)*

</details>

## 3.32 Desktop Changes & Requirements — After 16th April

**Main functional focus:** Printing  
**Content mix:** 43 defect(s), 0 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 42 implemented/reported complete, 1 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections within printing.

### Pending / Deferred items

- **Defect · Pending** — On sync error is showing in this format *(New Issues > Overall > POS)*

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify offline/online reconciliation and synchronization.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (42 items)</strong></summary>

- **Defect** — Add a confirmation modal when the user attempts to navigate to another page without saving the order *(New Issues)*
- **Defect** — In Payment, **Payment method** dropdown data should be fetched from **Mode of Payment**. *(New Issues)*
- **Defect** — When payment fails and the payment status remains **unpaid**, the order status incorrectly changes to **closed** instead of staying as **draft**. *(New Issues)*
- **Defect** — In Edit Order, adding a customer with a Default Discount Percentage still shows the discount as 0 instead of applying the configured default discount. *(New Issues)*
- **Defect** — Rename this filter to Outlet and All Outlets *(New Issues)*
- **Defect** — This error message should be shown when user tries to remove the only item left from an order- **At least one item is required in the order.** *(New Issues)*
- **Defect** — When the print modal is dismissed (by clicking outside or auto-closing), the user is not redirected to the select table page as expected. *(New Issues)*
- **Defect** — In table order edit, when the order status is updated from POS web, only the order status refreshes while the item status remains outdated until the page is reloaded again. *(New Issues)*
- **Defect** — While creating new order show only Pay button for Pay First. *(New Issues)*
- **Defect** — Add VAT and Discount in this *(New Issues)*
- **Defect** — Fix this view *(New Issues)*
- **Defect** — Show the confirm modal in the middle of the page *(New Issues)*
- **Defect** — Remove these two from service type filter *(New Issues)*
- **Defect** — Remove this from order status filter *(New Issues)*
- **Defect** — Remove the whole Order source filter. *(New Issues)*
- **Defect** — Remove this from Payment status filter *(New Issues)*
- **Defect** — Rename Territory to Outlet *(New Issues > Overall)*
- **Defect** — Clicking on the Print button should show the print modal with receipt first. *(New Issues > Overall)*
- **Defect** — The Discount and VAT is not showing in the receipt. *(New Issues > Overall)*
- **Defect** — Customer type- partnership. If user goes through table dining then those customers won't show. *(New Issues > Overall > POS)*
- **Defect** — Rename **New Order** button to-> **Save and Create New**. *(New Issues > Overall > POS)*
- **Defect** — The item group should be sticky *(New Issues > Overall > POS)*
- **Defect** — Only show L here *(New Issues > Overall > POS)*
- **Defect** — The table party size should be editable here *(New Issues > Overall > POS)*
- **Defect** — Order type dropdown should show only Pay Later and Pay First. Pay Later should be selected by default. *(New Issues > Overall > POS)*
- **Defect** — While creating new order when Pay Later is selected only New Order button will be shown. *(New Issues > Overall > POS)*
- **Defect** — While creating new order when Pay First is selected only Pay option will be shown. *(New Issues > Overall > POS)*
- **Defect** — Clicking on the items should open a modal, similar to ArcPOS. *(New Issues > Overall > POS)*
- **Defect** — Rename it to **Print Order** *(New Issues > Overall > POS)*
- **Defect** — Remove Special Instructions and Rename Kitchen Note to Order Notes. *(New Issues > Overall > POS)*
- **Defect** — Clicking reload while being offline shows- No restaurant tables found. Sync while online or check your data. *(New Issues > Overall > POS)*
- **Defect** — Unsynced orders should be auto synced once user goes online *(New Issues > Overall > POS)*
- **Defect** — In order EDIT discount is resetting back to Zero. *(New Issues > Overall > ORDERS)*
- **Defect** — The order and item status is not syncing with POS web. The page should be reloaded when user goes into the order. *(New Issues > Overall > ORDERS)*
- **Defect** — Showing invalid date *(New Issues > Overall > ORDERS)*
- **Defect** — Sync button shows loading for all orders *(New Issues > Overall > ORDERS)*
- **Defect** — Remarks isn't showing any data. *(New Issues > Overall > ORDERS)*
- **Defect** — Remove the **No location** part from My Orders. *(New Issues > Overall > ORDERS)*
- **Defect** — Split payment is not functional yet. *(New Issues > Overall > ORDERS)*
- **Defect** — Rename Payment column to Payment Status. *(New Issues > Overall > ORDERS)*
- **Defect** — Discount isn't showing in Bill Details. *(New Issues > Overall > ORDERS)*
- **Defect** — Fix pagination. *(New Issues > Overall > ORDERS)*

</details>

## 3.33 Corrections & Requirements #2 — POS Web

**Main functional focus:** Backend / Frappe ERP  
**Content mix:** 1 defect(s), 3 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 4 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within backend / frappe erp.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### QA verification focus

- Verify draft/submitted order status and item status transitions.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (4 items)</strong></summary>

- **Requirement** — All the "Search" fields, must query on "Enter" trigger
- **Requirement** — Any kinds of update in the Sales Invoice, it's changing the Invoice Posting Date.
- **Requirement** — If the BOM > Is Prep Item = 1 and "Allow to update Qty = 0" then should not show or work the "+/-" buttons.
- **Defect** — Showing "Somthing Wrong" while trying to make the item status as "Ready to Serve"

</details>

## 3.34 Corrections & Requirements #1 — Desktop

**Main functional focus:** Backend / Frappe ERP  
**Content mix:** 4 defect(s), 10 requirement(s), 2 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 14 implemented/reported complete, 2 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements, verification/decision points within backend / frappe erp.

### Pending / Deferred items

- **Defect · Pending** — Cash Open/Closing with Cash Drawer functionality missing. Keep the same as BanCan POS, we will make correction after.
- **Requirement · Pending** — I will add hare other findings.................................

### QA verification focus

- Verify order totals, discounts, vat/sd, rounding, and payment amounts.
- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify printing content, format, routing and cash-drawer behavior.
- Verify responsive layout, dark mode and action-state behavior.

<details>
<summary><strong>Implemented / reported complete scope (14 items)</strong></summary>

- **Requirement** — If any user has no permission of "Territory" then show after login Toast "You have no territory permission, please contact your administrator"
- **Verification / Decision** — Check > "POS and Orders" module only allowed for Frappe Role: ArcPOS Manager, Restaurant Cashier, Restaurant Manager and System Manager"
- **Requirement** — Show user's avatar/Image
- **Defect** — Dark Mode Logo issue
- **Requirement** — No need to show "Home" button. On click "Logo" will redirect to the Home page.
- **Requirement** — Show Table Image if there are any image is linked otherwise show as default current icon.
- **Defect** — Order Status missing in the List page. Keep the same as BanCan POS Order List
- **Defect** — Item status functionality missing in the order edit/update. Keep the same as BanCan POS
- **Requirement** — Home page view, can we keep the same view as the BanCan POS home page?
- **Requirement** — Order list: Bold font for "Order No"
- **Requirement** — Rename "Tax" to "VAT"
- **Requirement** — Place the Ordered Items into "Bill Details"
- **Verification / Decision** — Remove "Company name" value and what is the Square portion marked in below image?
- **Requirement** — Add values: Order Status, Order Type, Party Size, Updated On, Customer Note, Remarks

</details>

## 3.35 Features and Functionality - Internal

**Main functional focus:** Stock & Inventory  
**Content mix:** 1 defect(s), 19 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 0 implemented/reported complete, 20 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within stock & inventory.

### Pending / Deferred items

- **Requirement · Pending** — Login user Frappe Role has : Restaurant Chef, Restro Kitchen Staff, System Manager, Restaurant Manager, ArcPOS Manager *(Kitchen Order:)*
- **Requirement · Pending** — Show only the invoices data if "Order Status = Accepted/Waiting/In kitchen/Preparing" + docstatus NOT = 2 *(Kitchen Order:)*
- **Requirement · Pending** — Update on DateTime Desc. *(Kitchen Order:)*
- **Requirement · Pending** — User Permission: If No permission for "Territory" then show all vouchers, If there are "Territory" permission exists then show only permitted "Territory"s vouchers & if there are "Territory" permission exists + "is_default = 1" then show only the default "Territory"s vouchers *(Kitchen Order:)*
- **Requirement · Pending** — "Process Recipe" button should show if only "ArcPOS settings > Allowed Production? = 1 + Role: ArcPOS Recipe User/Restaurant Manager/System Manager+ Item Maintain Stock = 1 + Is BOM Item = 1" *(Kitchen Order:)*
- **Requirement · Pending** — Should show if only "ArcPOS settings > Allowed Production? = 1 + Role: ArcPOS Recipe User/ArcPOS Recipe Approver/Restaurant Manager/System Manager/ArcPOS Manager" *(Kitchen Order: > Production:)*
- **Requirement · Pending** — Should show if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "custom_linked_outlet" & if there are "Territory" permission exists + "is_default = 1" then show only the default "Territory"s which are linked with Warehouse "custom_linked_outlet". Note: Warehouse Type = Transit should not show or select. *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — For Target Warehouse: Show all warehouse except the selected Warehouse and Warehouse Type = Transit *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — New created Transfer can be Accept or Return *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — Workflow Example: If Source Warehouse = Store & Target Warehouse = Good Stock then on submit the items will be send to the "Warehouse Type = Transit" warehouse and on "Accept" the following items will be transfer from "Warehouse Type = Transit" warehouse to "Target Warehouse = Good Stock" *(Kitchen Order: > Production: > Stock Transfer: > New created Transfer can be Accept or Return)*
- **Requirement · Pending** — We need a list page of Stock Entry: Filter of voucher > Stock Entry Type = Material Transfer + Voucher No Desc. *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — To Create > Frappe Has Role "ArcPOS Transfer Creator/Restaurant Manager/System Manager/ArcPOS Manager" *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — After Create: Frappe Has Role "ArcPOS Transfer Creator/Restaurant Manager/System Manager/ArcPOS Manager" will get "Approve/Reject" Button > On "Approve", the TROUT will be submitted & On "Reject" the voucher will be READ ONLY *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — After "Approve" > Status will be "In Transit" and the Frappe Has Role "ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" will get the button "Accept/Return" buttons *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — On "Accept" > An TRIN will create under the TROUT and On "Return" An BTRIN will create. *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — If BTRIN > Frappe Role: "ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" will get only "Accept" button *(Kitchen Order: > Production: > Stock Transfer:)*
- **Requirement · Pending** — Should show if only Role: ArcPOS Stock User/ArcPOS PCM Creator/ArcPOS PCM Approver/Restaurant Manager/System Manager/ArcPOS Manager" *(Kitchen Order: > Production: > Wastage Management:)*
- **Requirement · Pending** — For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "custom_linked_outlet" & if there are "Territory" permission exists + "is_default = 1" then show only the default "Territory"s which are linked with Warehouse "custom_linked_outlet" *(Kitchen Order: > Production: > Wastage Management:)*
- **Defect · Pending** — We need a list page of Stock Entry: Filter of voucher > Stock Entry Type = Material Issue + Voucher No Desc. *(Kitchen Order: > Production: > Wastage Management:)*

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify responsive layout, dark mode and action-state behavior.
- Verify report filters, outlet permissions, totals and date/time boundaries.

## 3.36 Functionality 1

**Main functional focus:** Stock & Inventory  
**Content mix:** 1 defect(s), 41 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 0 implemented/reported complete, 41 pending, 1 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within stock & inventory.

### Pending / Deferred items

- **Requirement · Pending** — Allowed if
- **Requirement · Pending** — Should show if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" *(- Allowed if)*
- **Requirement · Pending** — **On new creation:** *(- Allowed if)*
- **Defect · Pending** — The "Source Outlet" value will be auto load for the set "Default Territory" and the "Target Outlet" will be Blank. User will search and select the "Target Outlet" *(- Allowed if > **On new creation:**)*
- **Requirement · Pending** — Multiple Item should allow to add in the Item Table and Quantity must me minimum 1. *(- Allowed if > **On new creation:**)*
- **Requirement · Pending** — On Create/Draft button trigger > Pass to frappe with *(- Allowed if > **On new creation:**)*
- **Requirement · Pending** — Territory = Set Territory *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Naming Series = TROUT *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Stock Entry Type = Stock Transfer *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Add to Transit = 1 *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Posting Date and Time = Creation Date *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Default Source Warehouse = Source Outlet's Warehouse *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Default Target Warehouse = ArcPOS Settings > Default In Transit Warehouse *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Actual Target Warehouse = Target Outlet's Warehouse *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Items Table= Items *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Remarks = Remarks *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — Docstatus = As per "Create=1/Draft=0" *(**On new creation:** > On Create/Draft button trigger > Pass to frappe with)*
- **Requirement · Pending** — If Draft > will covert the page in a Details page and show Edit and Create/Submit button. In the list page, Status will be "Draft" *(- Allowed if > **On new creation:**)*
- **Requirement · Pending** — If Create > will redirect to the List page and Status will be "In Transit" *(- Allowed if > **On new creation:**)*
- **Requirement · Deferred** — "In Transit" > In the details page > All will be Read only and show button "Accept", "Cancel" [Cancel button will show all DocStatus = 1 and only allowed for System Manager"] and "Return" [Skip the Return Policy for now] *(**On new creation:** > If Create > will redirect to the List page and Status will be "In Transit")*
- **Requirement · Pending** — On "Accept" > Pass to frappe with *(- Allowed if > **On new creation:**)*
- **Requirement · Pending** — Territory = Set Territory *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Naming Series = TRIN *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Stock Entry Type = Stock Transfer *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Posting Date and Time = Creation Date *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Default Source Warehouse = The tagged TROUT's "Default Target Warehouse" *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Default Target Warehouse = The tagged TROUT's "Actual Target Warehouse" *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Items Table= Items *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — Docstatus = 1 *(**On new creation:** > On "Accept" > Pass to frappe with)*
- **Requirement · Pending** — On "Return" > Pass to frappe with *(- Allowed if > **On new creation:**)*
- **Requirement · Pending** — In the The tagged TROUT > Update with "Is Returned? = 1" *(**On new creation:** > On "Return" > Pass to frappe with)*
- **Requirement · Pending** — For the New Stock Entry *(**On new creation:** > On "Return" > Pass to frappe with)*
- **Requirement · Pending** — Territory = Set Territory *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Naming Series = BTRIN *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Stock Entry Type = Stock Transfer *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Posting Date and Time = Creation Date *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Default Source Warehouse = The tagged TROUT's "Default Target Warehouse" *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Default Target Warehouse = The tagged TROUT's "Default Source Warehouse" *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Items Table= Items *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Docstatus = 1 *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Returned From = The tagged TROUT's ID/Voucher No *(On "Return" > Pass to frappe with > For the New Stock Entry:)*
- **Requirement · Pending** — Except Draft, all the other button trigger will redirect to the refreshed List page.

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify responsive layout, dark mode and action-state behavior.

## 3.37 WC - Web — 09-04-2026

**Main functional focus:** Backend / Frappe ERP  
**Content mix:** 1 defect(s), 32 requirement(s), 0 verification/decision item(s), 0 documentation/setup item(s)  
**Progress:** 33 implemented/reported complete, 0 pending, 0 deferred

**Summary:** This work package covers reported product defects/corrections, functional or UI requirements within backend / frappe erp.

### Pending / Deferred items

No pending or deferred checklist items were identified in this work package.

### Business rules / contextual notes

- **Not add any item related filter if need implement later**

### QA verification focus

- Verify role, pin, outlet/territory and document-state permissions.
- Verify draft/submitted order status and item status transitions.
- Verify stock movement quantities, source/target outlet and workflow state.
- Verify responsive layout, dark mode and action-state behavior.
- Verify notifications, recipient selection and redirection.
- Verify report filters, outlet permissions, totals and date/time boundaries.

<details>
<summary><strong>Implemented / reported complete scope (33 items)</strong></summary>

- **Requirement** — Name the browser tab as "ArcPOS"
- **Requirement** — After Logout, correct the toast text to "Logout Successful"
- **Requirement** — After Login, correct the toast text to "Login Successful"
- **Defect** — Switch Territory missing
- **Requirement** — Add Logo (As per ArcPOS Settiings"
- **Requirement** — Remove " Forgot"
- **Requirement** — Remove "Accept terms and Condition"
- **Requirement** — Add "Title, Title 2 and Description" as same as BanCan. You can keep the same view.
- **Requirement** — Replace Sign In text to "Login"
- **Requirement** — Rename "Username" to "Username or Email"
- **Requirement** — Add Search and Filters
- **Requirement** — Search: Voucher name, **Item name** *(Add Search and Filters:)*
- **Requirement** — Filters: Date Range [Default Today]. **Item name**, Service Type, **Item Status**, Territory *(Add Search and Filters:)*
- **Requirement** — Place the Invoice "Posting Date and Time" per order header
- **Requirement** — URL path change from "production" to "recipes"
- **Requirement** — Change the Module and Modal Item's Icon
- **Requirement** — Replace Column "Item" to "UOM"
- **Requirement** — Replace Column "Item Name" to "Is Prep Item"
- **Requirement** — Search: Display Name, Item
- **Requirement** — Filter: Item, Is Prep Item
- **Requirement** — Prepare Modal: Remove all the text "Production" + If it's prep item and "Allow Alternative Item = 0" then allow to update qty by clicking (+/-). Per click will add the qty value but should not allow to go below.
- **Requirement** — "Created By" value must be the Owner Full name
- **Requirement** — If voucher name LIKE "TRIN" then should not show in the list.
- **Requirement** — Add "Accepted By" > the value of TRIN owner name.
- **Requirement** — Search: Voucher No, Owner name [Optional], Remarks
- **Requirement** — Filter: Date Range, Source Warehouse, Target Warehouse, Status, , Territory
- **Requirement** — Create new/Details modal: Replace display texts "Warehouse" to "Outlet" and the value will be "Outlet/Territory name" but in the backend we will pass the Default warehouse.
- **Requirement** — Create new: Add Remarks Field
- **Requirement** — "Created By" value must be the Owner Full name
- **Requirement** — Search: Voucher No, Owner name [Optional], Remarks
- **Requirement** — Filter: Date Range, Source Warehouse, Status, Territory
- **Requirement** — Create new/Details modal: Replace display texts "Warehouse" to "Outlet" and the value will be "Outlet/Territory name" but in the backend we will pass the Default warehouse.
- **Requirement** — Create new: Add Remarks Field

</details>

## 4. QA Usage Guidance

For active development and regression testing, prioritize the **Pending** defect and requirement items in each section. Items marked implemented/reported complete should be used as regression coverage rather than assumed to be verified.

Where a source item states only the desired behavior and does not provide an exact reproduction path, test data, environment, or build number, this document preserves that limitation rather than inventing unsupported details.

For formal defect execution, QA can convert any pending **Defect** item into an executable test record with: preconditions, test data, numbered reproduction steps, actual result, expected result, severity, priority, environment, evidence, and retest result.
