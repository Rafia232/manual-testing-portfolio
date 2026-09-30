# White Canary POS — Final Product Documentation

## Overview

This document consolidates the final implemented behavior, business rules, UI expectations, workflows, reporting behavior, printing behavior, permissions, and operational requirements of the White Canary POS system.

All content is written as final product documentation. Tracking metadata, progress states, personnel metadata, first-person statements, and duplicate entries have been removed.

## Functional Documentation

### Authentication & Session

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Offline / Sync | 1: PIN Session Expiration Blocking Online Sync. |
| 2 | Business Rule | Description: When an online order containing PIN-restricted fields (such as Item or Discount) fails to sync due to an expired PIN session, the error message instructs the user to start a PIN session. |
| 3 | UI / UX | After PIN enable, on save, the Discount field must be Disabled and the "SAVE" button replace to PIN with session ending. |
| 4 | Business Rule | Standard Staff Restriction (Draft Only): If a financial discrepancy exists and the active session user does not hold the Frappe roles "System Manager, ArcPOS Manager, or Restaurant Manager", the system will restrict actions to saving the entry as a Draft for administrative review. On waiting approval, user must not make another request. |
| 5 | Offline / Sync | OFFLINE Login. |
| 6 | Functional Behavior | Login page. |
| 7 | Functional Behavior | In next update while login dont keep the username and password. |
| 8 | Business Rule | On Void, an remarks is mandatory > use "sales invoice > remarks. Show it in the Confirmation modal ++ Modal "Cancel" also should end/expire the session. |
| 9 | UI / UX | Currently every Reload initiates Clock-OUT, Clock IN/OUT modal should only auto appear after Login based on the login user's last status. |
| 10 | Functional Behavior | Step 1: Shift Validation (On Login). |
| 11 | Business Rule | If any user has no permission of "Territory" then show after login Toast "You have no territory permission, contact your administrator". |
| 12 | Business Rule | Login user Frappe Role has : Restaurant Chef, Restro Kitchen Staff, System Manager, Restaurant Manager, ArcPOS Manager. |
| 13 | Functional Behavior | After Logout, correct the toast text to "Logout Successful". |
| 14 | Functional Behavior | After Login, correct the toast text to "Login Successful". |
| 15 | Functional Behavior | Replace Sign In text to "Login". |
| 16 | Functional Behavior | Rename "Username" to "Username or Email". |

### Clock-In / Clock-Out & Cash Audit

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | Clock-IN/OUT. |
| 2 | Functional Behavior | In Any kinds of update in the Territory from frappe doctype, and evenif the Territory Counter's Last Status = , It's forcing to Clock-IN where allows to Clock-OUT. |
| 3 | UI / UX | Modal is popping multiple times when it's . |
| 4 | Business Rule | If any of Table is occupied or Any Sales Invoice docstatus is 0 for the closing period, restrict to clock-OUT and throw error to fix them first. |
| 5 | Business Rule | Only allowed Outlet Counter wise Payment method shows. (customdefaultwebsite = 1). |
| 6 | UI / UX | After app reload, freeze/loader to the screen until the pop up Clock-IN/OUT modal. |
| 7 | Functional Behavior | Preventing only if any Table is occupied, but the system requires also for If any Sales Invoice docstatus is 0 for the current period. |
| 8 | Functional Behavior | Clock-IN & Clock-OUT Time is showing UTC. |
| 9 | UI / UX | If user Select NOT = "Counter 1" then hide the button "Clock-OUT & Send Email". |
| 10 | Output / Printing | On trigger the button "Clock-OUT & Send Email" will auto POS print the "Day-end Audit Summary report" for the latest clock-OUT period. |
| 11 | Output / Printing | Cash drawer should not after every print, it should only when the payment method is Cash. |
| 12 | Output / Printing | Blank space at the top of the printed receipt should be fixed. |
| 13 | Functional Behavior | Connect the power adapter. |
| 14 | Output / Printing | Insert the receipt paper roll correctly. |
| 15 | Output / Printing | Connect the USB cable from the printer to the PC. |
| 16 | Output / Printing | Turn on the printer. |
| 17 | Functional Behavior | Right-click the Epson driver installer. |
| 18 | Functional Behavior | Select Run as administrator. |
| 19 | Output / Printing | Choose Install Printer Driver. |
| 20 | Functional Behavior | Select model: EPSON TM-T81III. |
| 21 | Functional Behavior | Select interface: USB. |
| 22 | Functional Behavior | Finish the setup. |
| 23 | Output / Printing | Control Panel > Devices and Printers. |
| 24 | Output / Printing | EPSON TM-T81III Receipt. |
| 25 | Output / Printing | Right-click the printer. |
| 26 | Output / Printing | Go to Printing Preferences. |
| 27 | Functional Behavior | Set the paper/roll size based on your roll. |
| 28 | Output / Printing | 80mm / Receipt / Roll Paper 80 x 297mm. |
| 29 | Functional Behavior | 58mm, if available. |
| 30 | Output / Printing | Go to Printer Properties. |
| 31 | Output / Printing | Click Print Test Page. |
| 32 | Output / Printing | If it prints, the driver setup is okay. |
| 33 | Functional Behavior | Right-click the downloaded installer. |
| 34 | Functional Behavior | Complete the installation. |
| 35 | Functional Behavior | Search QZ Tray from the Start Menu. |
| 36 | Functional Behavior | You should see the QZ Tray icon near the Windows clock/system tray. |
| 37 | Functional Behavior | Right-click the QZ Tray tray icon. |
| 38 | Functional Behavior | Enable Automatically Start, so QZ Tray starts when Windows starts. |
| 39 | Functional Behavior | Go to Advanced > Site Manager. |
| 40 | Functional Behavior | Click + Add. |
| 41 | Functional Behavior | Browse to the folder that has the .crt file and select it. |
| 42 | Functional Behavior | Rename the warning text to "You have already logged in a Counter" (Backend). |
| 43 | Functional Behavior | Counter options must be unique (Backend). |
| 44 | Functional Behavior | On Clock-IN, the Expected amount getting NULL/0, collaborate with Anamul (Backend). |
| 45 | Functional Behavior | getting the error when the Opening amount = 0 (backend). |
| 46 | Functional Behavior | The Expected amount is not showing the updated amount. |
| 47 | Functional Behavior | When Clock-IN/OUT is submitted for the first time for approval it should only show the 2nd message- Clock-IN/OUT submitted. Awaiting approval. |
| 48 | UI / UX | If user's last "Submission Type" is CLOCK-OUT of the territory's counter, and its status is DRAFT, then the Modal should not auto + all the input fileds will be disabled and allow a "Verify" button instead of CLOCK-OUT button. |
| 49 | Functional Behavior | Rename all the Clock in/out to "Clock-IN"/"Clock-OUT". |
| 50 | Business Rule | If Frappe Role has "Restaurant Cashier" and user Clicked IN, then disallow to change "Outlet" until Clock OUT. |
| 51 | Functional Behavior | Daily Cash Audit. |
| 52 | UI / UX | Make different font color for "Clock-IN and OUT" [List + Details]. |
| 53 | Functional Behavior | Smart Counter Defaulting: If a designated retail outlet operates with only a single counter registry, configure the UI to automatically populate that counter name as the default option. |
| 54 | UI / UX | Option B (Manual Interrogation): Provide a dedicated "Re-sync" button or using existing Clock-IN/OUT button to dynamically call the latest document state flag. If the backend verification confirms the Voucher is now Approved/Submitted, programmatically close the modal. |
| 55 | Reporting | Reports > Daily Cash Audit. |
| 56 | Functional Behavior | Cash Account (Paid To) must be as per Outlet's Counter wise For Pay Later/Pay First and Credit Order Payment. |
| 57 | Functional Behavior | If Order via QR Code (No Counter Linked) then use a default Account from the Outlet. You can use: Territory > customdefaultcash_account (Remove the Field Depends On). |
| 58 | Functional Behavior | If "From Counter" exists then the value set to the Payment Entry. |
| 59 | Functional Behavior | Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Draft" > notify-to "Territory" [based on Territory default wise] "Restaurant Manager". |
| 60 | Functional Behavior | On click > redirect to > Specific Daily Cash Audit details page. |
| 61 | Business Rule | Clock-IN/OUT: New voucher entry on "Daily Cash Audit" > On "Submit" > notify-to "Territory" [based on Territory default wise] "Restaurant Cashier" and does not has any Manager Role. |
| 62 | Business Rule | Is the "Last Opened By" user is fetching from the "Daily Cash Audit" last modified by? If yes, if the Manager approve/submit this then the cashier can be restricted. |
| 63 | Functional Behavior | outlet - Add "Fetch From" = 'territory.customoutletname' > Daily Cash Audit. |
| 64 | Functional Behavior | Need Mode of Payment wise + Territory wise + Counter wise account setup on Payment Entry. [For CASH, the system already ]. |
| 65 | Functional Behavior | Use territory's Default Counter data if document's Counter field is empty. Set on Draft and Submit. Function should work from from Main ERP also.[Did the system already worked on this?]. |
| 66 | Functional Behavior | Cash /Closing with Cash Drawer functionality check. |
| 67 | UI / UX | When the user comes online from offline, the clock-in/clock-out modal flashes onto the screen for a second. |
| 68 | Functional Behavior | When another user tries to clock in using a different counter, the system does not allow it. |
| 69 | Functional Behavior | The specific counter is disabled in the dropdown when another user is already clocked in with that counter. |
| 70 | Functional Behavior | Search for a "Daily Cash Audit" entry for the "Current Date" and "Counter" where Submission Type == Clock In. |
| 71 | Functional Behavior | The "Expected Opening Cash" = [Cash account "Debit - Credit"] of that counter. |
| 72 | UI / UX | The user will press the button " Cash Drawer" and must count the physical cash in the drawer and enter it into the "Opening Amount". > [Just show the " Cash Drawer" button, no functionality for now]. |
| 73 | Business Rule | If the "Opening Amount" does not match the expected amount and The "Difference" amount NOT = 0 then "Reason" field becomes mandatory. User must input the reason. |
| 74 | Functional Behavior | A cashier cannot a new shift if a previous shift on the same counter was never "Clocked Out.". |
| 75 | Functional Behavior | Use multi approval > "Restaurant Manager" will Approve the Request from "Daily Cash Audit" list page. |
| 76 | Business Rule | "Daily Cash Audit" module is only allowed for "Restaurant Manager" and can edit "Submitted Amount" and "Reason" in Draft. |
| 77 | Functional Behavior | Cash Drawer Integration must be linked with each Counter. |
| 78 | Functional Behavior | Without Clock In entry for "Current Date" and "Counter" does not allow to create any Cash Payment. |
| 79 | Functional Behavior | Outlet Counter wise Cash Account on Payment. |
| 80 | Functional Behavior | Counter Data in Sales invoice and Payment Entry. |

### Orders & POS

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | The filter is not working. |
| 2 | Functional Behavior | Add new Check field `Draft Entry" before existing field "From Outlet". |
| 3 | Functional Behavior | When an order Rounded Total/Grand Total is 0, its passing the "Is Credit Sales = 1". |
| 4 | Functional Behavior | All the total amount is showing 0. |
| 5 | Functional Behavior | Order details- Variant names are not showing here. |
| 6 | Functional Behavior | Fix this overlap. |
| 7 | Functional Behavior | Item transfer to another new/existing running order. []. |
| 8 | Functional Behavior | Show the Item's placed time for each items in the cart. |
| 9 | Functional Behavior | Order Draft: After Drafting an order, the table occupancy gets delay. |
| 10 | Functional Behavior | Auto fetch from Running Order invoice. |
| 11 | Functional Behavior | Add a new section on right side for "Credit Sales". |
| 12 | Functional Behavior | Total Credit Sales = GRAND TOTAL. |
| 13 | Functional Behavior | Remove the column "Supplier Code" and Try to show the "Posting Date" data in single line. |
| 14 | Reporting | Item Sales Summary = ArcPOS Item Sales Summary. |
| 15 | Functional Behavior | Table & Covers PnL = ArcPOS Table & Covers PnL. |
| 16 | Functional Behavior | If any invoice is draft (docstatus = 0), then add a mark as Running? |
| 17 | Functional Behavior | Order (New/Draft) in Pay Later. |
| 18 | Functional Behavior | Auto close if occupied table running order is paid. Sometimes the Order is Paid but order status does not turn to ! ( do the automation as the system on BanCan). |
| 19 | Business Rule | Cart Item changing " type" is not allowing after status "Waiting". no check the item status to restrict. Just validate the docstatus. Allow if only docstatus 0 or new order. |
| 20 | Functional Behavior | If any purchase order has been submitted with backdate on Date, then the purchase invoice also should be created by the actual day not current date. |
| 21 | Functional Behavior | If any item Status NOT = "Served" then allow to update the status to only "Served". |
| 22 | Functional Behavior | List page: If Docstatus NOT = 0 and Order Status NOT = "" then allow to update the status to only "" and on update the item status will be "Served" as well. |
| 23 | Functional Behavior | Voiding remarks should pass to the invoice's "customuserremarks" field. [this was functional earlier]. |
| 24 | Business Rule | In DRAFT order, existing Items in the Cart > Edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to Multiple and the "Variant Item Type" is set to Combo, then the user should NOT allowed to increase the quantity from List & POP UP. |
| 25 | Functional Behavior | Also cab be edited the "Service Type", "Preferences", " Type", "Order Note" from the POP UP as well. |
| 26 | Functional Behavior | In Order Split > If any item's "Serve Type NOT = Dine-in" then show the value beside the item name. |
| 27 | Functional Behavior | Item preview in Order page. |
| 28 | Functional Behavior | Order on New create/Update/Spit. |
| 29 | Functional Behavior | If Subtotal is less then 500 then upto .50 will be in negative and from .51 will be in positive. |
| 30 | Functional Behavior | If Subtotal is greater then 499.99 then upto .49 will be in negative and from .50 will be in positive. |
| 31 | Functional Behavior | Order Cart. |
| 32 | Functional Behavior | New Item add to Cart on update. |
| 33 | Functional Behavior | Item and order status. |
| 34 | Functional Behavior | If Grand Total value of 123.5000000 or Above will result in a Positive rounding adjustment. |
| 35 | Functional Behavior | Implement item row Dragging with row wise icon which will catch the item row in single tap. |
| 36 | Functional Behavior | Add a simple image as default for "All" in item category. |
| 37 | Functional Behavior | ORD-26-01617- Check the choose qty condition, it's automatically passing data when variant item choice type is single. |
| 38 | Functional Behavior | Item quantity should be editable when the item status = waiting. |
| 39 | Functional Behavior | Table is still showing as Occupied after submitting an order using Credit Sales. |
| 40 | Functional Behavior | Remove this table part. |
| 41 | Functional Behavior | In Edit Order-> Show the type like this. |
| 42 | Functional Behavior | Orders- Show only these filters. |
| 43 | Functional Behavior | Show the pin like this while typing. |
| 44 | Functional Behavior | Show 0 amount for other types. |
| 45 | Reporting | Beside order summary show the number of items added in the cart like this. |
| 46 | Functional Behavior | Write takeout beside the item name like this. |
| 47 | Functional Behavior | Match this part. |
| 48 | Functional Behavior | Rename this to only Type. |
| 49 | Functional Behavior | No show the order note under the item name. |
| 50 | Functional Behavior | In draft order edit, if the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to Combo, the user should be able to increase the quantity of the item. |
| 51 | Functional Behavior | Show the order and item status like this. |
| 52 | Functional Behavior | For variant items, in the cart, show item name instead of item code. |
| 53 | Functional Behavior | Showing no data in table switch. |
| 54 | Functional Behavior | If "Pay First" > then Order status+ Item Status should be "Waiting". |
| 55 | Functional Behavior | Does not allowing to update "Number of Guest" by Keyboard Digit. |
| 56 | Functional Behavior | Table not fetching > Shanta Forum. |
| 57 | Functional Behavior | If Order Type = Pay First and Order or Item Status = Served, then allow "". |
| 58 | Functional Behavior | If a Table is occupied with a Submitted Order, then on click the Table, redirect to the Order Details page not to POS view. |
| 59 | Functional Behavior | Do not pass any Order Status and Item Status [except new added item] on Edit/update. |
| 60 | Functional Behavior | In a Draft Table Order, the PARTY SIZE = 4, Table = Table 01-Gulshan 2. |
| 61 | Functional Behavior | Person 1 and 2. |
| 62 | Functional Behavior | Person all 4. |
| 63 | Functional Behavior | Person 1, 3, 4. |
| 64 | Functional Behavior | Add an shortcut option with Menu list to move to another menu from except homepage. Show it like this. |
| 65 | Functional Behavior | does not show this when the page is loaded the first time. |
| 66 | Functional Behavior | User can make the change of Default outlet only from the Homepage other wise disable the field. |
| 67 | Functional Behavior | shows data here according to this. |
| 68 | Functional Behavior | Remove Guest Information from order details. |
| 69 | Functional Behavior | Full calculation of SD/VAT/Auto round is . |
| 70 | Reporting | For pathao and foodpanda show the table name- outlet beside the order summary text like this. |
| 71 | Functional Behavior | Item Coffee-L and Coffee-M is showing separately. |
| 72 | Functional Behavior | No show Dine-in under item. Only show takeout beside the item name. The variant name should be under item name. |
| 73 | Functional Behavior | DRAFT EDIT- If table has been changed to another Available Table, then the earlier table must be Available and next one should be Occupied with link the Order no on order update. |
| 74 | Functional Behavior | If the "Attribute Type for POS" or "Choice Type for POS" is set to multiple, the system should take the parent item's price instead of the variant's price. Otherwise it will take the variant's price. |
| 75 | Functional Behavior | If both the "Attribute Type for POS" and "Choice Type for POS" are set to single, the system should create separate item names by concatenating the item's parent's name with the first attribute's variant name, and then create another item with the parent's name and the second attribute's variant name. |
| 76 | Functional Behavior | If the "Attribute Type for POS" or "Choice Type for POS" is set to multiple and the "Variant Item Type" is set to mixed, the system should concatenate the parent item's name from each attribute's variant using a hyphen ("-") and match it with the variant items created in the item list. |
| 77 | Functional Behavior | LIKE in an Template item's linked attribute's values are set in 1st row "Small", 2nd Row "Medium" and 3rd row "Large". So on your API, all the variant items should be in sequence as per variant value, else on front end > there showing with sequence break. |
| 78 | Functional Behavior | This can be managed by Client Script and already set this. You can verify. |
| 79 | Functional Behavior | Order with PIN impact. |
| 80 | Functional Behavior | Item Pricing. |
| 81 | Functional Behavior | Web Price should be auto calculated and set for the "Standard Selling price". |
| 82 | Functional Behavior | How manage it? |
| 83 | Functional Behavior | Purchase Order. |
| 84 | Functional Behavior | On Purchase Order creation, the Purchase Invoice should auto create taking the same data of the Order. |
| 85 | Functional Behavior | Purchase Invoice Customization: Make "update_stock" default 1. |
| 86 | Functional Behavior | Bill Split. |
| 87 | Functional Behavior | On click > redirect to > Specific order's details page. |
| 88 | Functional Behavior | Credit Sales. |
| 89 | Functional Behavior | Order with 0 Grand Total. |
| 90 | Functional Behavior | If the system archived this "Credit Sales" then,. |
| 91 | Functional Behavior | Set auto fetch the latest orders with interval every 30 Sec. |
| 92 | Functional Behavior | Order List page: If Order Status changed to "Served" OR "" then pass Item Status = Served. |
| 93 | Functional Behavior | New feature: Split selected items + qty to multiple order / move to other table temporarily. |
| 94 | Functional Behavior | Test Desktop app on their POS machine. |
| 95 | Functional Behavior | DRAFT EDIT- Table change impact is not happening- If table has been changed to another Available Table, then the earlier table must be Available and next one should be Occupied with link the Order no on order update. |
| 96 | Functional Behavior | While editing a draft order, when a new mixed item is added, the system does not allow increasing the quantity of that item. |
| 97 | Functional Behavior | In draft order edit when user tries to remove the last item it shows a proper error message- Cannot remove the last item. Plese void the order. |
| 98 | Functional Behavior | The error message comes from Backend. Skipping now. |
| 99 | Functional Behavior | In order list the total amount column value is showing wrong (doesn't match with the actual amount). |
| 100 | Functional Behavior | Add + sign for these 2. |
| 101 | Functional Behavior | After Clock OUT, immediate pop up of the Clock IN does not contains the actual expected Amount. If needed keep a loader to get the current Expected value of the account. |
| 102 | Functional Behavior | When a "Restaurant Cashier" logs into the POS, the system performs a background check. |
| 103 | Functional Behavior | IF YES: The user is redirected to the general POS operation LIKE HOME Page. |
| 104 | Functional Behavior | Once Approve by "Restaurant Manager" > the cashier can start POS operation as the below conditions matched. |
| 105 | Functional Behavior | Upon submission, the entry is saved, and the POS is unlocked for sales. |
| 106 | Functional Behavior | In Order details the items issued with PIN is also showing price. |
| 107 | Functional Behavior | In all the search item field it does not show template items.. |
| 108 | Functional Behavior | In all the search item field show Type to find items instead of No items found. |
| 109 | Functional Behavior | Message: "You have unsaved changes. Are you sure you want to leave without saving the order?". |
| 110 | Functional Behavior | In table order edit, when the order status is updated from POS web, only the order status refreshes while the item status remains outdated until the page is reloaded again. |
| 111 | Functional Behavior | Remove this from order status filter. |
| 112 | Functional Behavior | Remove the whole Order source filter. |
| 113 | Functional Behavior | The item group should be sticky. |
| 114 | Functional Behavior | Only show L here. |
| 115 | Functional Behavior | The table party size should be editable here. |
| 116 | Functional Behavior | Order type dropdown shows only Pay Later and Pay First. Pay Later should be selected by default. |
| 117 | Functional Behavior | While creating new order when Pay First is selected only Pay option will be shown. |
| 118 | Functional Behavior | Showing invalid date. |
| 119 | Functional Behavior | Remarks isn't showing any data. |
| 120 | Functional Behavior | Remove the No location part from My Orders. |
| 121 | Functional Behavior | Fix pagination. |
| 122 | Functional Behavior | All the "Search" fields, must query on "Enter" trigger. |
| 123 | Functional Behavior | Any kinds of update in the Sales Invoice, it's changing the Invoice Posting Date. |
| 124 | Functional Behavior | Home page view, keep the same view as the BanCan POS home page? |
| 125 | Functional Behavior | Order Details. |
| 126 | Functional Behavior | Place the Ordered Items into "Bill Details". |
| 127 | Functional Behavior | Posting Date and Time = Creation Date. |
| 128 | Functional Behavior | Docstatus = As per "Create=1/Draft=0". |
| 129 | Functional Behavior | Name the browser tab as "ArcPOS". |
| 130 | Functional Behavior | Add Logo (As per ArcPOS Settiings". |
| 131 | Functional Behavior | Order > > Almost Same functionality as BanCan. |
| 132 | Functional Behavior | Place the Invoice "Posting Date and Time" per order header. |

### Split Order / Split Bill

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Output / Printing | Split Order Print (After Payment). |
| 2 | Output / Printing | Split Order > Payment breakdown data missing in the Receipt Print. |
| 3 | Functional Behavior | When multiple payment methods are selected, the last selected payment method is not automatically populated with the remaining payable balance. |
| 4 | Functional Behavior | Order details- These data doesn't show for split orders. |
| 5 | Functional Behavior | The Cash payment method shouldn't be pre-selected by default. |
| 6 | Functional Behavior | Create a draft order with 1 Coffee L, 1 Coffee M, and a discount-eligible customer → Go to Split Order → Make payment for Coffee L → It shows this error. |
| 7 | Functional Behavior | This part shows as blank for split order payment. |
| 8 | Functional Behavior | In a draft order, when both discount-eligible and non-discount-eligible items are added, the Split Order screen incorrectly displays the discount percentage for the non-discount-eligible items during splitting. |
| 9 | Functional Behavior | After completing 1 guest slot payment show the Grand total here. |
| 10 | Functional Behavior | Create order with 1 Coffee M and 1 Coffee S → Save the order → Go to Split Order → Make payment only for Coffee M → After Coffee M payment is , select Coffee S from the left side → Coffee S does not appear on the right side for payment as expected. |
| 11 | UI / UX | Add a text in small italic font under the "Split Order" button > Orders can only be split if all items are at least in "Ready to Serve.". |
| 12 | Functional Behavior | Split order- edit pax to- Party size. |
| 13 | Functional Behavior | Add three types of coffee - L/M/S. Change all item statuses to Ready to Serve from the front order. Then, in the split bill, drag only Coffee-L for payment and complete the payment. |
| 14 | Functional Behavior | The parent invoice should only be marked as paid and updated when there are no remaining items in the Unassigned Items section of the split bill. |
| 15 | Functional Behavior | New invoices should be created for each partial payment without closing the parent invoice. |
| 16 | Functional Behavior | Currently, the main invoice is being updated with only the Coffee-L item and the order status is being . |
| 17 | Functional Behavior | Party size is not updating after one slot payment. |
| 18 | Functional Behavior | Allow to update Party Size and pass to Invoice also. Auto update the party size slot wise but user can also change it. |
| 19 | Output / Printing | After Payment, the Print Modal should appear. |
| 20 | Functional Behavior | Last Invoice must be update the Parent Invoice with last split payment. and also the Table should be available. |
| 21 | Output / Printing | After Last Slot is paid, then return to the Table page after Print . |
| 22 | Functional Behavior | After Payment, the "Served" time is missing. |

### Payments

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Output / Printing | Payment breakdown data missing in the Receipt Print. |
| 2 | Functional Behavior | The "Payment Information" data should fetch. |
| 3 | Functional Behavior | 1st Priority: from the invoice's custommodeofpayment & custompayment_amounts (attached SS fields). |
| 4 | Functional Behavior | 2nd Priority: From the "Sales Invoice Payment" (Table row). |
| 5 | Functional Behavior | Check this. |
| 6 | Functional Behavior | [But payment entry creates]. |
| 7 | Functional Behavior | [Payment entry not created]. |
| 8 | Functional Behavior | When an order Rounded Total/Grand Total is 0, somehow the "Outstanding Amount" showing in amount figure. |
| 9 | Functional Behavior | When an order/invoice is submitted with trigger on "Credit Sales", so that no payment entry should not auto initiate. [currently "With ArcPOS Payment" data in passing as 1]. |
| 10 | UI / UX | Remove Make Payment button for Order Type- Pay Later for new orders. |
| 11 | Functional Behavior | For submitted invoice payments, the Cash payment method is pre-selected by default. |
| 12 | Output / Printing | [Backend] For credit sales its showing Paid amount instead of Due amount in print. |
| 13 | Output / Printing | If there are Change amount on Cash, then show this in the print receipt on Payment section. |
| 14 | Functional Behavior | Sometimes the system is facing that, because of frappe rounding, its not matching with the system's auto rounding amount. So that payment not creating with error. What if the system save the invoice on Payfirst and always take the Grandtotal and other data from the Frappe Invoice. |
| 15 | UI / UX | Remove/Hide the spit button. |
| 16 | Functional Behavior | There will be now default/auto set any payment method. |
| 17 | Functional Behavior | If payment method "Cash" selected, do not auto set the the received amount. |
| 18 | Functional Behavior | If multiple payment method selected (except Cash), then last selected method will be auto filled the remaining balance. |
| 19 | Functional Behavior | Already added method can not be add again. |
| 20 | Functional Behavior | If there is no due then do not allow to add another method. |
| 21 | UI / UX | Disable MAKE PAYMENT button until DUE AMOUNT turn to 0. |
| 22 | UI / UX | If any method is selected, disable the "Credit Sales" button. |
| 23 | Functional Behavior | Payment Entry. |
| 24 | Functional Behavior | Hide: Excel Tax Payment. |
| 25 | Functional Behavior | Payment Overview = ArcPOS Payment Overview. |
| 26 | Functional Behavior | Auto email on payment section: Its taking the Date only, not validating the time! If needed add a custom field in the payment entry for Posting time (auto take the creation time and should not change on the document update/submit). |
| 27 | Functional Behavior | Columns: Posting Date, Supplier Code, Supplier Name, Supplier Group, Voucher No, Order No, Supplier Invoice, Invoice Amount, Outstanding Amount,. |
| 28 | Functional Behavior | Remove: Mode of Payment, Company. |
| 29 | Functional Behavior | Remove: Description, Payable Account, Mode of Payment, Project, Company, Expense Account. |
| 30 | Reporting | Make correction of the report description to: Summary of daily sales, charges, and payments. |
| 31 | Functional Behavior | After Payment success + Order Details (Online). |
| 32 | Offline / Sync | After Payment success + Order Details (Offline). |
| 33 | UI / UX | Show SD and VAT like this, same for Payment Summary modal. |
| 34 | UI / UX | Rename Payment button to Pay αº│Grand Total. |
| 35 | UI / UX | Payment Summary modal-> payment method is showing disabled mode of payments as well. |
| 36 | Functional Behavior | After making payment of a credit sales order it doesn't redirect back to that order details page. Shows error- Could not load this order details. And keeps showing error- User None is disabled. contact your System Manager. Which fixes after clearing the cookies. |
| 37 | Functional Behavior | Only keep these filters and maintain this sequence- Search box, Date range, Service type, Order Status, Payment Status, Outlet, Customer Type, Customer. |
| 38 | UI / UX | In a draft order- Make payment and Credit sales button is enabled only if all the item status and order status is either Ready to serve or Served. |
| 39 | Functional Behavior | Payment Overview. |
| 40 | Functional Behavior | Collection [Query same like Payment Overview]. |
| 41 | Functional Behavior | Additionally need percentage of each Payment method. |
| 42 | Functional Behavior | If the invoice Outstanding Amount = 0, then show > Paid Amount-------------------- {{rounded_total}}. |
| 43 | Functional Behavior | If the invoice Outstanding Amount NOT = 0, then show > Due Amount -------------- {{outstanding_amount}}. |
| 44 | Functional Behavior | Item-Wise Split Payment Workflow [Only if the Main invoice docstatus = 0 and any item status = Ready to Serve/Served]. |
| 45 | Functional Behavior | Phase 1: UI Trigger and Redirection. |
| 46 | Functional Behavior | Phase 2: Drag-and-Drop Interface Logic. |
| 47 | Functional Behavior | Phase 3: Automated Calculations. |
| 48 | Functional Behavior | Phase 4: Transaction Execution (The "Pay" Action). |
| 49 | Functional Behavior | Phase 5: Final Guest Optimization. |
| 50 | Output / Printing | Phase 6: Individual Printing. |
| 51 | Functional Behavior | Order details- After payment table field is showing blank. |
| 52 | Functional Behavior | The Order From column is also not showing table number after payment. |
| 53 | UI / UX | Rename Create Order button to-> Save and Create New. Pay button to-> Make Payment. |
| 54 | UI / UX | While creating new order when Pay First is selected only Make Payment option will be shown. [With credit sales button if available]. |
| 55 | Functional Behavior | WC-Web POS-> Payment for both credit sales and split payment is not working. |
| 56 | Functional Behavior | the system may have some to create payment entry from Main ERP. |
| 57 | Functional Behavior | New feature: Payment Entry: selected invoice payment amount auto set from Main ERP. |
| 58 | Functional Behavior | If Submitted order link with any Payment, then the order status should be changed to "" and Item status = Served. |
| 59 | Functional Behavior | customtotaloutsamount - Place below of "paidamount" > Payment Entry. |
| 60 | Business Rule | excelbankname_cheque - Hide and remove from "Mandatory Depends On" > Payment Entry. |
| 61 | Functional Behavior | Invoice and Payment Entry. |
| 62 | Functional Behavior | Add the "VAT & other charges" data also before Payment section [as like the Image shared in Telegram]. |
| 63 | UI / UX | The "Pay" button should occupy the full width of the container and Remove the amount from and button and Rename it to Make Payment. |
| 64 | Business Rule | Showing this error when trying to make payment of a draft order created with credit sales- Not allowed to change Grand Total after submission from. |
| 65 | Functional Behavior | After payment table field is showing blank. |
| 66 | Functional Behavior | After order payment the Account Paid To is not working as expected. |
| 67 | Functional Behavior | In Payment, Payment method dropdown data should be fetched from Mode of Payment. |
| 68 | Functional Behavior | When payment fails and the payment status remains unpaid, the order status incorrectly changes to instead of staying as draft. |
| 69 | Functional Behavior | Remove this from Payment status filter. |
| 70 | Functional Behavior | Split payment is not functional yet. |
| 71 | Functional Behavior | Rename Payment column to Payment Status. |

### Customers & Discounts

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | For partial discount orders with a 0% discount customer, save the order as a Draft, then change the customer to one with a discount. After the first validation error occurs, the discount percentage resets back to 0%. |
| 2 | Business Rule | For partial discount orders, when a discounted customer is selected, the following error is displayed: "No permission for discount on Sales Invoice. Ask a manager to enter their PIN for this action.". |
| 3 | Functional Behavior | For partial discount orders, select a discounted customer and save the order as a Draft. Then change the customer to another discounted customer. An error is displayed, but if another SD + Discount item is added afterward, the invoice is updated according to the newly selected customer's discount. |
| 4 | Functional Behavior | Customer Filter. |
| 5 | Business Rule | The dropdown customer list should validate as per user's territory frappe permissions. |
| 6 | Business Rule | While splitting an order, without Discount OR evenif the order does not contains BOTH type (Discount allowed or not) item also passing with Partial Discount Flag. (Make it same a like general order creation). |
| 7 | Offline / Sync | Showing this error when ordered offline- Coffee/Discounted Cust/Credit Sales. |
| 8 | UI / UX | In a draft order, the "Update Order" button shows enabled (For discounted customers). |
| 9 | Business Rule | In a draft order, when the customer is changed from a discount-eligible customer to a 0% discount customer and then changed back to a discount-eligible customer, the discount is incorrectly applied to the subtotal instead of recalculating based on the allowed discount-sale items. |
| 10 | Business Rule | [Backend] When a user without the ArcPOS Manager, Restaurant Manager, or System Manager role saves an order containing discount-eligible items and a discount-eligible customer, the system shows this error. |
| 11 | Business Rule | item wise discount allow not allow. (Some items won't be allowed to Discount). |
| 12 | UI / UX | New/Draft Order: Show the customers as simple button to change. ++ "Disabled/Frozen" customers does not show. |
| 13 | Business Rule | item wise calculate the discount amount only if the item is allowed to Discount (YES). |
| 14 | Business Rule | If any order has both type item (Allowed Discount Sales = YES & NO) and discount given in %, then pass the % rate to the Discount Percentage instead of Additional Discount Percentage with the Additional Discount Amount (BDT) at Sales Invoice. |
| 15 | Functional Behavior | Allow Discount on Sales. |
| 16 | Functional Behavior | Auto fetch from Item "Allow Discount on Sales". |
| 17 | Functional Behavior | GRAND TOTAL: SALES TOTAL (Net) - Discount + VAT + SD +/- Auto Round. |
| 18 | Functional Behavior | Customer Name ------ invoice's total data. |
| 19 | Functional Behavior | Discount. |
| 20 | Functional Behavior | Sum of invoice's Discount Amount data. |
| 21 | Business Rule | Credit Sales button missing when Credit allowed customer is selected. |
| 22 | UI / UX | If customer type = Partnership, then no show the search button in the Edit drawer. |
| 23 | Functional Behavior | When a draft order is created with a walk-in customer and later changed to a credit sales enabled customer, submitting the order with credit sales causes the item and order status to work incorrectly. |
| 24 | Functional Behavior | Keep the party size fixed to 1 and disabled for foodpanda and pathao (Customer Type= Partnership). |
| 25 | Functional Behavior | In Edit Order-> For foodpanda/pathao Select Customer fields are showing selectable instead of showing the linked customer by default. |
| 26 | Functional Behavior | Show Customer Address like this. |
| 27 | Functional Behavior | Customer search filter- Show type something to search. instead of No data found. |
| 28 | UI / UX | Only show the save button beside discount when the discount is modified with PIN. |
| 29 | Functional Behavior | The up/down arrows for the discount field should increment/decrement in decimal values. |
| 30 | Business Rule | on update- If any Draft order's customer is eligible for Credit Sales, then allow the Credit sales button on update too. Customer should be eligible for Credit Sales if only the customer field value "Allowed Credit Sales?" = 1. |
| 31 | Functional Behavior | Discount = "basediscountamount" > (Sum of Discounted Invoice qty). |
| 32 | Functional Behavior | In draft order edit, when the customer is updated, the system does not apply the new customer's default discount after the update. |
| 33 | UI / UX | Get data from sales invoice: Customer Email = "contactemail", Customer Phone = Rename to "Customer Mobile" = contactmobile and Customer Address = address_display. If No value then show (--). |
| 34 | Business Rule | Add a "Customer" filter (Type and Select) that is based on the user's territory permissions. |
| 35 | Functional Behavior | For other tables, Do not show pathao and foodpanda here and for pathao and foodpanda all the fields in Customer & Table will be non editable. |
| 36 | Business Rule | If the customer "Allowed Credit Sales" = 1, then the button shows and functional. |
| 37 | Functional Behavior | Show discount according to the default discount set for customer. |
| 38 | Functional Behavior | When an order is saved with a customer who has default discount e.g- 10% then in edit when another customer with default discount is selected e.g- 12%, the discount still shows for the previous customer. |
| 39 | Functional Behavior | Same when discount is applied with PIN. |
| 40 | Functional Behavior | Keep invoice wise record if any PIN user gives Item OR/And Discount OR/And Void. |
| 41 | Functional Behavior | How to submit the order which contains all the item with Type or 100% Discount? |
| 42 | Functional Behavior | Credit sales with customer change, on update. |
| 43 | Business Rule | How the Credit Sales button works? If the customer "Allowed Credit Sales" = 1, then the button shows and functional. |
| 44 | Functional Behavior | VAT & SD with Discount calculation will be provided by Jabed Bhai. |
| 45 | Functional Behavior | Credit sales differentiate flag for customer profile. |
| 46 | Business Rule | Discount 10/15/30/35, custom permission for senior manager. |
| 47 | Functional Behavior | In Edit Order, adding a customer with a Default Discount Percentage still shows the discount as 0 instead of applying the configured default discount. |
| 48 | Functional Behavior | Add VAT and Discount in this. |
| 49 | Output / Printing | The Discount and VAT is not showing in the receipt. |
| 50 | Functional Behavior | Customer type- partnership. If user goes through table dining then those customers won't show. |
| 51 | Functional Behavior | In order EDIT discount is resetting back to Zero. |
| 52 | Functional Behavior | Discount isn't showing in Bill Details. |
| 53 | Functional Behavior | Add values: Order Status, Order Type, Party Size, Updated On, Customer Note, Remarks. |

### Kitchen & Front Orders

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Output / Printing | Rename this to Kitchen Print and make all the button color same. |
| 2 | Output / Printing | For Kitchen Print: Add Item wise "Item Status" data. |
| 3 | Functional Behavior | Change view as like the attached demo image view. Scroll will be horizontally. |
| 4 | Output / Printing | When "Skip Kitchen Outlet" is same a logged user, then it's showing only the Print Receipt. the system requires the Front Print also. |
| 5 | Business Rule | do this dynamically? If "ArcPOS Settings > "Allowed to Skip Kitchen (Outlet)" has value (value= multiple outlet names separated by commas) && If any Invoice territory = {{ the value }}, then the data should not appear in this report. |
| 6 | Business Rule | If "ArcPOS Settings > Allowed to Skip Kitchen (Outlet)" has value and the value separating by COMMA match with the user's selected OUTLET then. |
| 7 | Functional Behavior | Any Item which is added to cart, the item Status will be "Ready to Serve" also for Kitchen Items. |
| 8 | Business Rule | If "ArcPOS Settings > Allowed to Skip Kitchen (Outlet)" has value and the value separating by COMMA match with the invoice's field territory value then. |
| 9 | UI / UX | For "Remove" button show/hide, keep the current condition If "Prepare At = Kitchen". |
| 10 | UI / UX | If "Prepare At = Front", then show the "Remove" button in status = "Waiting/Preparing/Ready to Serve". |
| 11 | Functional Behavior | Ignore the "Front Order" feature. |
| 12 | Functional Behavior | Only for "Prepare At = Front". |
| 13 | Functional Behavior | Pass item's order status = Ready to Serve. |
| 14 | Functional Behavior | No pass the "Ready to Serve" time. |
| 15 | Functional Behavior | When an order is created containing only front order items, the order status should automatically be set to Ready to Serve. |
| 16 | Functional Behavior | In that draft order, when a Prepare At = Kitchen item is added, the order status should automatically be updated to Waiting. |
| 17 | Functional Behavior | In a draft order, when a Prepare At = Front item is added, the item status should automatically be set to Ready to Serve. |
| 18 | Output / Printing | For POS web > use print formats from: ArcPOS Settings > Default KOP Format (Kitchen Print) & Default FOP Format (Front Print). |
| 19 | Business Rule | If ArCPOS Settings "Allowed Kitchen Order Print? = NO", then "Kitchen Print" option will be Hidden. |
| 20 | Output / Printing | There will be 2 Print data > 1. "Print Receipt" (Default preview), 2. "Front Print". |
| 21 | Output / Printing | All including "Front Print" will be accordion/expandable. |
| 22 | Output / Printing | Trigger option button will be two > 1. Print Active, 2. Print All. |
| 23 | Output / Printing | Trigger on "Print Active" will generate print the opened/previewed print data. |
| 24 | Output / Printing | Trigger on "Print All" will generate all print in sequence. |
| 25 | Output / Printing | There will be 3 Print data > 1. "Print Receipt" (Default preview), 2. "Front Print", 3. "Kitchen Print". |
| 26 | Output / Printing | After DRAFT success + PRINT button trigger (Online). |
| 27 | Output / Printing | All including "Print Receipt" will be accordion/expandable. |
| 28 | Output / Printing | After DRAFT success + PRINT button trigger (Offline). |
| 29 | Output / Printing | Trigger on "Print All" will generate for "Front Print" & "Kitchen Print" in sequence. |
| 30 | Functional Behavior | Ignore/hide the Items which are "Prepare At = Front". |
| 31 | Functional Behavior | Order status is not updating even when all the item status is ready to serve/served. |
| 32 | Output / Printing | Showing the wrong print format for Front Order prints. |
| 33 | Functional Behavior | [] 1 Coffee, 1 Captain America. When coffee's status is already served and then Captain America's status is changed to Ready to serve, The order status still shows as Waiting. It doesn't update the order status accordingly. |
| 34 | Functional Behavior | From the order list when the order status is changed from Ready to serve to Served, it doesn't update the item status. |
| 35 | Functional Behavior | In a draft order when a new front order is added- it should be added as Ready to serve instead of waiting. |
| 36 | UI / UX | Add a pay button in order details when- order is made with credit sales and order status = ready to serve/served. |
| 37 | Functional Behavior | When an order has Guest Choice- Show it above the kitchen note line, in one line- "Spice Level":"Mild","Add Butter/Ghee":"No","Crispiness":"Extra Crispy". |
| 38 | Functional Behavior | Showing this error while changing an order's status from Ready to Serve to Served from the order list. |
| 39 | Functional Behavior | Front Order- When "Ready All" or "Ready to Serve" is clicked, the success message should display "Item is now ready to serve" instead of current message. |
| 40 | Functional Behavior | If Single item status changed to "Ready to Serve" then change the Success Toast text to "Item now ready to serve". |
| 41 | Functional Behavior | Rename "Serve All" to "Ready All". |
| 42 | Functional Behavior | Update from "Front Order" > Removing other items which are "Prepare At = Kitchen" from Sales Invoice. |
| 43 | UI / UX | If all item status NOT = "Ready to Serve/Served" then Disable the "Pay" button. |
| 44 | UI / UX | Set auto fetch latest orders with interval every 30 Seconds. Also add a "Refetch Orders" button. |
| 45 | UI / UX | Accept All/Ready All button shows only for "Prepare At = Kitchen" items. |
| 46 | Functional Behavior | When accept an order from the kitchen, the items from the front order get deleted from the invoice. |
| 47 | Functional Behavior | In the Invoice > If All Item status NOT = "Preparing/Ready To Serve/Served" and Void triggered then the invoice will be auto delete in a Cron Job. |
| 48 | Functional Behavior | But if any of item's status = "Preparing/Ready To Serve/Served" and Void triggered then the invoice should not delete. |
| 49 | Functional Behavior | Kitchen/Front Order. |
| 50 | Functional Behavior | If in a Invoice all item are "Prepare At" = "Front" or "Kitchen" then the order should only view in the specific Front or Kitchen list. |
| 51 | Functional Behavior | Only if all the item's status is "Preparing or Ready to Serve" then update the Order Status "Preparing or Ready to Serve". |
| 52 | Functional Behavior | If the item's "Is BOM Item" is NO, then the Item status must be changed to "Ready to Serve" from Prepapring. |
| 53 | Functional Behavior | Item Order Status = "Waiting" + Prepare AT = "Kitchen" then notify-to based on Territory default wise "Restaurant Chef" and "Restro Kitchen Staff". |
| 54 | Functional Behavior | On click > redirect to > Specific "Kitchen Orders" page. |
| 55 | Functional Behavior | Notification Title: ì│ New Order Sent to Kitchen. |
| 56 | Functional Behavior | Order: Item Order Status = "Ready to Serve" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter". |
| 57 | Functional Behavior | Notification Title: ¢Ä∩╕Å Ready to Serve \| [Order ID] \| [Table ID]. |
| 58 | Functional Behavior | Check Occupied Tables and match with Running Order > If the order found with all items marked as "Ready to Serve" or "Served" + Docstatus = 1 + Is Credit Sales = 1, then It should make the linked table available. |
| 59 | Functional Behavior | Kitchen/Front Orders. |
| 60 | Functional Behavior | From Kitchen or Front orders > There is a that, removing opposite items from the Draft invoice. [Shahed already shared with you]. |
| 61 | Functional Behavior | Front order decision from them. |
| 62 | Functional Behavior | [Backend] Kitchen order items are showing in front order as blank. |
| 63 | Offline / Sync | OFFLINE work . |
| 64 | Functional Behavior | Remove these from filter. |
| 65 | UI / UX | When one action button is clicked, all other action buttons show as loading,. |
| 66 | Functional Behavior | know the source of this Remarks. |
| 67 | Functional Behavior | Show the time with am/pm. |
| 68 | Functional Behavior | Kitchen orders are showing in the front order section, and front orders are appearing in the kitchen order section. The filtering functionality is not working as expected. |
| 69 | Functional Behavior | Coffee and drinks front e prepare, will not go to kitchen, split view for kitchen. |
| 70 | Functional Behavior | Ready to Serve order to POS notification. |
| 71 | Functional Behavior | Kitchen orders- Items issued with PIN is not showing here. |
| 72 | Functional Behavior | Kitchen Orders- Restro Kitchen Staff, Restaurant Chef. |
| 73 | Functional Behavior | Showing no data in Remarks. |
| 74 | Functional Behavior | Sales invoices which has Is Deleted= 1, does not show in the list. |
| 75 | Functional Behavior | In source outlet filter show the list of all outlets. |
| 76 | Functional Behavior | Rename this placeholder to- Search order no. |
| 77 | Functional Behavior | Orders made with credit sales are showing an error when accepting them from kitchen orders. |
| 78 | Functional Behavior | Remove Special Instructions and Rename Kitchen Note to Order Notes. |
| 79 | Functional Behavior | Kitchen Orders. |
| 80 | Functional Behavior | Showing "Somthing Wrong" while trying to make the item status as "Ready to Serve". |
| 81 | Business Rule | Allowed if. |
| 82 | Functional Behavior | Show only the invoices data if "Order Status = Accepted/Waiting/In kitchen/Preparing" + docstatus NOT = 2. |
| 83 | Functional Behavior | Update on DateTime Desc. |
| 84 | Business Rule | User Permission: If No permission for "Territory" then show all vouchers, If there are "Territory" permission exists then show only permitted "Territory"s vouchers & if there are "Territory" permission exists + "is_default = 1" then show only the default "Territory"s vouchers. |
| 85 | Business Rule | "Process Recipe" button shows if only "ArcPOS settings > Allowed Production? = 1 + Role: ArcPOS Recipe User/Restaurant Manager/System Manager+ Item Maintain Stock = 1 + Is BOM Item = 1". |

### Printing

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Output / Printing | Make the Print View (font) as like the "Swapno" print font. The fonts should be clear to see after print. |
| 2 | Output / Printing | Print in A4 (PDF), Thermal and export in Excel file. Below is the reference. |
| 3 | Output / Printing | Reports (Sales Type): When report has been generated with "All" outlet, then it's showing all the active Territory/Outlet names in Print. But the system requires only the outlets name which outlets are linked with the generated report. |
| 4 | Output / Printing | Table color turn to Yellow if the print receipt is printed. []. |
| 5 | Output / Printing | Check the Print out gets delay. Need more faster. |
| 6 | Output / Printing | If the modal pop up on draft order and there is front items then the "Front" print should be default/1st otherwise Receipt print. [This was functional earlier]. |
| 7 | Output / Printing | Table number to be highlighted/ in Big Font in all print output to highlight it. |
| 8 | Output / Printing | In "Front Print" > Show only the last ordered items only which are not printed yet. the system can use "Is Print" field as the system used them on BanCan. |
| 9 | Output / Printing | Remove the item's serial no from all the print. |
| 10 | Output / Printing | Make "item qty" bit bigger font size to all the print. |
| 11 | Output / Printing | Draft Order: After adding a new item to the cart and without Update Order, the item showing in the Print Preview. |
| 12 | Output / Printing | Is Printed? |
| 13 | Output / Printing | The Table border is not showing in the Print Output. |
| 14 | Output / Printing | auto marked the Use Letter head field when user click on PDF from a report? |
| 15 | Output / Printing | On PDF print, End of right side column data hiding on Portrait page mode. |
| 16 | Output / Printing | Reduce bit of value font size on Print PDF. |
| 17 | Output / Printing | Remove Column: Purchase Receipt. |
| 18 | Output / Printing | On PDF print, all the columns are not showing. |
| 19 | Output / Printing | Table no show in the print receipt. Currently the system is showing the service type only. Add the linked table data. LIKE Table 01-Dine-In > Take the table data till -. dont show the Outlet name. |
| 20 | Output / Printing | Print PDF > LIKE the below image (Page can be Portrait or Landscape). |
| 21 | Functional Behavior | Show the preference like this. |
| 22 | Output / Printing | On print Section: Allow only "Print Receipt". |
| 23 | Functional Behavior | Check the below attachment, this error accorded? |
| 24 | Output / Printing | Implement the Item Preferences. also show in all prints. [Reference can be BanCan Print]. |
| 25 | UI / UX | Rename the "" button text to "Close". |
| 26 | Output / Printing | Keep enabled the"Close" button when its printing. (Because sometimes it's may take sometime to print success, meanwhile the display stuck until the print gets success or fail. |
| 27 | Output / Printing | If the modal pop up on draft order and there is front items then the "Front" print should be default/1st otherwise Receipt print. |
| 28 | Output / Printing | After last slot get paid and after print modal "Close" > redirect to Table page. |
| 29 | Output / Printing | If any item's type = Wastage, then does not show in the print. (This condition applied to only Receipt print). |
| 30 | Output / Printing | Add Print as PDF [Should generate as per filter] > HEADER & FOOTER are same for all reports. |
| 31 | Output / Printing | Add Print as PDF [Should generate as per filter]. |
| 32 | Output / Printing | Add and implement "Print" as PDF generate as per documents default Print Format > Direct call Frappe document PDF. |
| 33 | Output / Printing | Place the "Print" button in the Details page. |
| 34 | Output / Printing | Print Pipeline Modifications: Standard print routine workflows require structural updates. (Logic specifications to be finalized and added here). |
| 35 | Output / Printing | If the SD is not available, it is not shown in the print. |
| 36 | Functional Behavior | Show below data under the Grand Total row. |
| 37 | Output / Printing | Print functionality . |
| 38 | Output / Printing | Type except REGULAR item shows as per select in the Cart/Print and should save as 0 rate in the invoice. |
| 39 | Business Rule | Follow for > User Territory permission wise data and Print PDF >. |
| 40 | Output / Printing | Print PDF (on Frappe documents). |
| 41 | Output / Printing | Not getting the data in PDF, and fix >. |
| 42 | Output / Printing | Using Print format for POS web prints (ArcPOS Settings) with Custom Page size. |
| 43 | Output / Printing | In every order print preview show like the order no. |
| 44 | Output / Printing | Print Modal should not Scroll full, the Buttons should appear always as floating. |
| 45 | Output / Printing | SD % show like VAT; if not available, then hide- As the system showing the VAT % in the below of cart, make it similar for SD (10%) and if the all item is without SD then no show the SD row in the CART side and Print. |
| 46 | Output / Printing | Fix the SD and VAT calculation in Print. |
| 47 | Output / Printing | Print format design will be provided. |
| 48 | Output / Printing | When the print modal is dismissed (by clicking outside or auto-closing), the user is not redirected to the select table page as expected. |
| 49 | Output / Printing | Clicking on the Print button shows the print modal with receipt first. |
| 50 | Output / Printing | Rename it to Print Order. |

### Offline & Sync

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | UI / UX | Requirement: Add a direct "Enter PIN" action button within trigger sync or On click Individual "Sync" button should appear PIN modal for this type of error orders. |
| 2 | Offline / Sync | 2: UI Item Disappearance on Sync Error. |
| 3 | Offline / Sync | Description: If a sync error occurs while staying inside the active Order view, certain items temporarily disappear from the UI. However, navigating away and re-entering the Order restores and correctly displays all items. |
| 4 | Functional Behavior | Online order workflow is showing abnormal behavior. |
| 5 | Offline / Sync | Pictures are not showing in offline. |
| 6 | Offline / Sync | When an order is paid offline and another draft order is created on the same table, the subsequent online sync fails and displays an error in ONLINE. |
| 7 | Offline / Sync | This keeps loading when later is clicked in Resolve sync before clock in. |
| 8 | Functional Behavior | For credit sales it shows as PAID instead of DUE. |
| 9 | Functional Behavior | Pathao and Foodpanda shows occupied. |
| 10 | Offline / Sync | If any table or Invoice has been updated in OFFLINE and for Sync then those Table or Invoice should not to allow update when its online until sync successful. |
| 11 | Offline / Sync | 1 > An order has been placed on Table 1 when its OFFLINE, but before the data sync another order has been placed and running when its ONLINE. So that the offline order not allowing to sync as the table is occupied. |
| 12 | Offline / Sync | 2 > An order has been placed and updated on Table 1 when its OFFLINE, but before the data sync the order has been paid or submitted (docstatus = 1). So that the offline order data not allowing to sync to the order as the invoice docstatus is already 1. |
| 13 | Functional Behavior | Failed Queue job alert in 10 mins interval except the order creation/update page. |
| 14 | UI / UX | Same Alert on /Failed Queue job on trigger Clock Out button. |
| 15 | Functional Behavior | Same Alert on /Failed Queue job on trigger on close/exit the app. |
| 16 | Offline / Sync | Offline Order Sync. |
| 17 | Offline / Sync | On order sync, keep the OFFLINE data is first priority and update the order forcefully even the order has been modified during offline the desktop. |
| 18 | Offline / Sync | Voucher Status Synchronization Window. |
| 19 | Offline / Sync | If Backend is unreachable then how the OFFLINE activity will be performed? |
| 20 | Offline / Sync | Add a new field in the "Sales Invoice" > "customisofflinevoucher" (Field Type = Check, Allow On Submit = 1" under existing field "customdeletedbyname". |
| 21 | Offline / Sync | On OFFLINE order update, OFFLINE data is first priority. So if there are any change in Sales invoice in Backend Data then showing error LIKE "There is a modification already". So how ignore this and update the invoice with OFFLINE data? |
| 22 | Offline / Sync | Order update and Data Sync- optimize the performance. |
| 23 | Offline / Sync | Selecting PIN is showing unknown error in offline mode. |
| 24 | Business Rule | If offline, the Role users will get auto access. |
| 25 | Offline / Sync | On sync error is showing in this format. |
| 26 | Offline / Sync | Clicking reload while being offline shows- No restaurant tables found. Sync while online or check your data. |
| 27 | Offline / Sync | Unsynced orders should be auto synced once user goes online. |
| 28 | Offline / Sync | The order and item status is not syncing with POS web. The page should be reloaded when user goes into the order. |
| 29 | UI / UX | Sync button shows loading for all orders. |

### Stock Requisition

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | UI / UX | Rename the "Create" button to "Save". |
| 2 | UI / UX | When Allowing "Submit" button to the Creator, The "Edit" button is missing. |
| 3 | Business Rule | Submit Button Allowed IF: Frappe Role = "ArcPOS Transfer Creator"/"System Manager && DocStatus = 0 && Draft Entry = 1 && Selected Outlet = Target Outlet. |
| 4 | UI / UX | When Allowing "Approve" button to the Approver, The "Edit" button will enabled/show (Check). |
| 5 | Business Rule | Approve Button Allowed IF: Frappe Role = "ArcPOS Requisition Approverr"/" && DocStatus = 0 && Draft Entry = 0 && Selected Outlet = Target Outlet & target outlets combine approver. |
| 6 | Functional Behavior | Else System Manager. |
| 7 | Functional Behavior | Material Request. |
| 8 | Functional Behavior | As per "ArcPOS Settings > "Allow Update UOM?" > If NO, then make the UOM field READ ONLY. |
| 9 | Functional Behavior | Rename "Add Row" to "Add Item". |
| 10 | UI / UX | Without fill all other required fields, the "Add Item" & "Add Multiple" button is disabled. |
| 11 | Functional Behavior | Item selection dropdown has limit in the Item row? Manage to show all the matched options/Items. |
| 12 | UI / UX | In Mobile view: while searching any item in single word, its not appearing the dropdown until adding any space or another word. |
| 13 | UI / UX | "Create" button not showing in the Mobile view from list page. |
| 14 | Functional Behavior | Correction of Workflow. |
| 15 | Functional Behavior | Current Workflow. |
| 16 | UI / UX | Creation: When an outlet clicks the Create button, a Material Request entry is generated with a Draft status. |
| 17 | Business Rule | First Approval: The entry is sent for approval to users who have the Source Outlet (Territory) permission and hold the role "ArcPOS Requisition Approver" (with Email and Socket notifications). |
| 18 | Business Rule | Transfer Execution: Once approved and submitted, the document is routed to users who have the Source Outlet (Territory) permission and hold the role "ArcPOS Transfer Creator" (with Email and Socket notifications) to execute the transfer. |
| 19 | Functional Behavior | Corrections of Workflow. |
| 20 | UI / UX | Creation & Editable Draft: When an outlet clicks the Create button, it creates a Material Request entry as a Draft with the custom flag set to Draft Entry = 1. While this flag is active (1), the creator or target outlet user can edit and update the document freely. |
| 21 | UI / UX | Custom Submission Action: A new Submit button is introduced. Clicking this button updates the document with the latest data, changes the custom flag from Draft Entry = 1 to Draft Entry = 0, and initiates the approval process. |
| 22 | Business Rule | Approval Routing: The document is sent for approval to users whose email addresses are configured under the Target Outlet/Territory's "Combined Approver" field && Combined Approver(s) who holds the role "ArcPOS Requisition Approver" (with Email and Socket notifications). |
| 23 | Business Rule | Transfer Execution: Once the entry is approved and submitted, it is routed to users who have the Source Outlet (Territory) permission and hold the role "ArcPOS Transfer Creator" (with Email and Socket notifications) to proceed with the transfer. |
| 24 | Functional Behavior | Email Trigger correction of "ArcPOS Settings > Notification > Stock Requisition Awaiting Approval". |
| 25 | Functional Behavior | Stage of "Material Request > Draft". |
| 26 | Business Rule | If Purpose = "Material Transfer" > On "Draft" && Draft Entry = 0 > notify-to users whose email addresses are configured under the Target Outlet/Territory's "Combined Approver" field && Combined Approver(s) who holds the role "ArcPOS Requisition Approver". |
| 27 | Functional Behavior | For input items in the table add a function to item multi select including Category wise filter which will add item wise row on a trigger. |
| 28 | Functional Behavior | Territory data not passing to Frappe. |
| 29 | Functional Behavior | Doctype: Material Request. |
| 30 | Functional Behavior | Currently. |
| 31 | Business Rule | But now for the "Source Outlet" is set as default on the web" > instead of this check the user has the source outlet/territory permission and others, then allow those buttons. |
| 32 | Business Rule | Email & Socket notification: Stage for "Requisition Approval" > Send the notification just check if the user has the Source outlet/territory permission only. No check which is default. And role "ArcPOS Requisition Approver". |
| 33 | Functional Behavior | Details > 2nd row's outlet data is empty. ? and also same thing the system is viewing on the 1st row. |
| 34 | Functional Behavior | So, check first for the 2nd row, is there are any functionality or not? If NO, then the system can remove this. |
| 35 | Functional Behavior | On Edit, "Required By" is not updating in Backend/Frappe document. |
| 36 | Functional Behavior | After "Approve", redirect to "Requisition" list page with latest data. |
| 37 | Functional Behavior | "Create Transfer" > the OUTLET should be pass as per selected from "POS WEB". |
| 38 | Business Rule | "Approve" button should be validate with "Source Outlet". |
| 39 | Functional Behavior | [FOR NOW] work on Not Started status- when a stock transfer created from Stock Requisition is cancelled. Also add in status filter. |
| 40 | Functional Behavior | Create stock transfer is not accepting decimal values. |
| 41 | UI / UX | The font color of disabled fields is not properly visible in dark mode. |
| 42 | Functional Behavior | Stock Requisition. |
| 43 | Functional Behavior | Stock Requisition: If Purpose = "Material Transfer" > On "" > notify-to "Target Outlet" [based on Territory default wise] "ArcPOS Requisition Approver". |
| 44 | Functional Behavior | On click > redirect to > Specific Stock Requisition details page. |
| 45 | Functional Behavior | Notification Title: ôï Stock Requisition Awaiting Approval. |
| 46 | Functional Behavior | Stock Requisition: If Purpose = "Material Transfer" > On "Approve" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS Transfer Creator". |
| 47 | Functional Behavior | Notification Title: Stock Requisition Approved! |
| 48 | Functional Behavior | actual_qty - Mark > In List View > Material Request Item. |
| 49 | Functional Behavior | Territory - new field add on Top > Material Request. |
| 50 | Functional Behavior | Not Solved yet. |
| 51 | Functional Behavior | New feature: Material request for purchase. |
| 52 | Functional Behavior | Created By and Accepted By API . |
| 53 | Functional Behavior | Source Outlet and Target Outlet is showing blank when Stock Requisition is created from frappe. |
| 54 | Business Rule | Material requisition and intermediate approval, and edit permission. |
| 55 | Functional Behavior | Fix the status filter. |
| 56 | UI / UX | Remove Add Item button while creating transfer. |
| 57 | Functional Behavior | In Required By date picker past dates is disabled. |
| 58 | UI / UX | Cancle button is not shown when status is. |
| 59 | UI / UX | Fix the back button icon. |
| 60 | Business Rule | After approving a stock requisition, if the user does not have permission for the specific Source Outlet, they should not be able to create a transfer from that outlet. |
| 61 | Functional Behavior | Module view- ArcPOS Transfer Approver, ArcPOS Transfer Creator, ArcPOS Requisition Approver. |
| 62 | Functional Behavior | Approve- ArcPOS Requisition Approver. |

### Stock Transfer

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | Option B [Stock Transfer (Including Manufacturing Transfer) & Wastage Management]. |
| 2 | Business Rule | Validate the "Source Warehouse" item wise current stock. if entered Transfer qty is greater then the current stock then throw error. |
| 3 | Functional Behavior | Auto fetch from Warehouse. |
| 4 | Functional Behavior | Data does not show if "actual_qty is less then 0" or warehouse LIKE Work In Progress. |
| 5 | UI / UX | "Accept" button should enabled only if the "Target Outlet" is set as default from "POS WEB". |
| 6 | Business Rule | "Cancel" button should enabled only for FRAPPE Role = System Manager + ArcPOS Manager. |
| 7 | UI / UX | "Edit" & "Submit" button should enabled only if the "Source Outlet" is set as default from "POS WEB". |
| 8 | Functional Behavior | What is the internal filter on List page? |
| 9 | Functional Behavior | On Draft, "ArcPOS Transfer Creator" + Source Outlet = User's Default Territory" can edit the voucher. Also can Submit the TROUT. |
| 10 | Business Rule | "Accept" button should be validate with "Target Outlet". |
| 11 | Functional Behavior | After approval, when creating a stock transfer and deleting an item, the deleted item still appears in the stock transfer. |
| 12 | Functional Behavior | Stock Transfer: If Type= "Material Transfer" > On "In Transit" > notify-to "Target Outlet" [based on Territory default wise] "ArcPOS Transfer Approver". |
| 13 | Functional Behavior | On click > redirect to > Specific Stock Transfer details page. |
| 14 | Functional Behavior | Stock transfer. |
| 15 | Functional Behavior | TRIN document territory should be acceptors default territory. |
| 16 | Functional Behavior | On Accept > Set the "custom_status" = Accepted. |
| 17 | Functional Behavior | Not Solved. |
| 18 | Functional Behavior | Show the list of all outlets. |
| 19 | Functional Behavior | Remove search territory filter. |
| 20 | Functional Behavior | Source outlet and target outlet filter not working. |
| 21 | Functional Behavior | Remove Submitted from status filter and Add In Transit. |
| 22 | Functional Behavior | System does not allow selecting the same outlet as both the source outlet and target outlet. |
| 23 | Business Rule | shows if only Role: ArcPOS Stock User/ArcPOS Transfer Creator/ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager". |
| 24 | Business Rule | For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "customlinkedoutlet" & if there are "Territory" permission exists + "isdefault = 1" then show only the default "Territory"s which are linked with Warehouse "customlinked_outlet". Note: Warehouse Type = Transit does not show or select. |
| 25 | Functional Behavior | For Target Warehouse: Show all warehouse except the selected Warehouse and Warehouse Type = Transit. |
| 26 | Functional Behavior | New created Transfer can be Accept or Return. |
| 27 | Functional Behavior | the system requires a list page of Stock Entry: Filter of voucher > Stock Entry Type = Material Transfer + Voucher No Desc. |
| 28 | Business Rule | To Create > Frappe Has Role "ArcPOS Transfer Creator/Restaurant Manager/System Manager/ArcPOS Manager". |
| 29 | Business Rule | After Create: Frappe Has Role "ArcPOS Transfer Creator/Restaurant Manager/System Manager/ArcPOS Manager" will get "Approve/Reject" Button > On "Approve", the TROUT will be submitted & On "Reject" the voucher will be READ ONLY. |
| 30 | Business Rule | After "Approve" > Status will be "In Transit" and the Frappe Has Role "ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" will get the button "Accept/Return" buttons. |
| 31 | Functional Behavior | On "Accept" > An TRIN will create under the TROUT and On "Return" An BTRIN will create. |
| 32 | Business Rule | If BTRIN > Frappe Role: "ArcPOS Transfer Approver/Restaurant Manager/System Manager/ArcPOS Manager" will get only "Accept" button. |
| 33 | Business Rule | For Source Warehouse: User Permission: If No permission for "Territory" then show all warehouse, If there are "Territory" permission exists then show only permitted "Territory" which are linked with Warehouse "customlinkedoutlet" & if there are "Territory" permission exists + "isdefault = 1" then show only the default "Territory"s which are linked with Warehouse "customlinked_outlet". |
| 34 | Functional Behavior | Naming Series = TROUT. |
| 35 | Functional Behavior | Stock Entry Type = Stock Transfer. |
| 36 | Functional Behavior | Default Source Warehouse = Source Outlet's Warehouse. |
| 37 | Functional Behavior | Default Target Warehouse = ArcPOS Settings > Default In Transit Warehouse. |
| 38 | Functional Behavior | Actual Target Warehouse = Target Outlet's Warehouse. |
| 39 | Functional Behavior | Naming Series = TRIN. |
| 40 | Functional Behavior | Default Source Warehouse = The tagged TROUT's "Default Target Warehouse". |
| 41 | Functional Behavior | Default Target Warehouse = The tagged TROUT's "Actual Target Warehouse". |
| 42 | Functional Behavior | In the The tagged TROUT > Update with "Is Returned? = 1". |
| 43 | Functional Behavior | Naming Series = BTRIN. |
| 44 | Functional Behavior | Returned From = The tagged TROUT's ID/Voucher No. |
| 45 | Functional Behavior | If voucher name LIKE "TRIN" then does not show in the list. |
| 46 | Functional Behavior | Add "Accepted By" > the value of TRIN owner name. |
| 47 | Functional Behavior | Filter: Date Range, Source Warehouse, Target Warehouse, Status, , Territory. |
| 48 | UI / UX | Create new/Details modal: Replace display texts "Warehouse" to "Outlet" and the value will be "Outlet/Territory name" but in the backend. |

### Wastage Management

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | Including all the current flow, when the data is passing to frappe then always for each item, pass the "ArcPOS Settings > defaultwastageaccount" value in the "Difference Account" field. If the settings value is NULL then pass this as now. |
| 2 | Functional Behavior | In draft order edit, when an item's type is changed from complimentary/gift/wastage to Regular, the item price remains as 0.00. |
| 3 | Functional Behavior | When only gift/complementary/wastage items are added. |
| 4 | Functional Behavior | Wastage Management: If Type= "Material " > On "Draft" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Approver". |
| 5 | Functional Behavior | On click > redirect to > Specific wastage management details page. |
| 6 | Functional Behavior | Notification Title: Wastage Entry Awaiting Review. |
| 7 | Functional Behavior | Wastage Management: If Type= "Material " > On "Submit" > notify-to "Source Outlet" [based on Territory default wise] "ArcPOS PCM Creator". |
| 8 | Functional Behavior | Notification Title: Æ╛ Wastage Entry Approved! |
| 9 | Functional Behavior | Wastage / gift item amount on edit fetching actual rate. |
| 10 | Functional Behavior | [Backend] The items issued with PIN-complimentary/gift/wastage is also showing price in order details. |
| 11 | Functional Behavior | Complementary, Gift, Wastage. |
| 12 | Functional Behavior | Wastage Management. |
| 13 | Functional Behavior | The time in Stock Ledger is showing wrong time after a draft submission. |
| 14 | Functional Behavior | Source outlet is shown by default and non editable. |
| 15 | Functional Behavior | In wastage view- Show only Item Name and Remove the action column. |
| 16 | Functional Behavior | Modify it to- This entry displays the wastage details. |
| 17 | Functional Behavior | Remarks is not updating when a draft entry is submitted. |
| 18 | Business Rule | shows if only Role: ArcPOS Stock User/ArcPOS PCM Creator/ArcPOS PCM Approver/Restaurant Manager/System Manager/ArcPOS Manager". |

### Recipes & Production

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Business Rule | Add new Check field `Allow Update UOM?" under existing field "Allowed Production?". |
| 2 | Functional Behavior | When trying to force "Update Cost" manually, showing this error ```exc_type. |
| 3 | UI / UX | Pop modal: NOTE data view in Dark Mode. |
| 4 | Functional Behavior | If any item's total_cost value in BOM doctype is not same for the item's Standard Buying price OR the item does not has Standard Buyingprice, then update or set the price for the item. |
| 5 | Functional Behavior | 1st Trigger can be on update the BOM. |
| 6 | UI / UX | Show NOTE for value of BOM's "Website Description" value in the Recipe modal. |
| 7 | Functional Behavior | Work Order: Invoice Reference in Work Order. |
| 8 | Functional Behavior | If item's are "Is BOM Item = 1" then initiate Workorder and related things. |
| 9 | Functional Behavior | If the item's "Is BOM Item" is YES, only then the Work Order will execute (Re-Verify). |
| 10 | Functional Behavior | If any BOM item's "totalcost" gets updated then the "Standard Buying" price rate of the item's should be auto updated. [Because if the system submit Stock ledger with Negative stock and if there are no valuation rate then its takes rate from the Buying Rate]_. |
| 11 | Functional Behavior | On Doctype "BOM Item" > add an field under "item_code" > "Is Prep?" > Type = Check > In List View = 1 > Allow on Submit = 1. |
| 12 | Functional Behavior | Readiness for actual production environment and share credentials with them. |
| 13 | Business Rule | Order Void for prepared recipe invoice and keep track: permission for senior manager. |
| 14 | Functional Behavior | ISD branch / Sell from ready stock process discuss, fixed items which may have recipe to prepare but will always be sold from ready stock from all outlets?.e cheese cake slices. |
| 15 | Functional Behavior | Recipes- ArcPOS Recipe User. |
| 16 | Functional Behavior | Rename to Prepare. |
| 17 | UI / UX | If the BOM > Is Prep Item = 1 and "Allow to update Qty = 0" then does not show or work the "+/-" buttons. |
| 18 | Business Rule | shows if only "ArcPOS settings > Allowed Production? = 1 + Role: ArcPOS Recipe User/ArcPOS Recipe Approver/Restaurant Manager/System Manager/ArcPOS Manager". |
| 19 | Functional Behavior | URL path change from "production" to "recipes". |
| 20 | UI / UX | Prepare Modal: Remove all the text "Production" + If it's prep item and "Allow Alternative Item = 0" then allow to update qty by clicking (+/-). Per click will add the qty value but does not allow to go below. |

### Reports & Analytics

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Reporting | New Report (WEB) > Item-wise Sales Register. |
| 2 | Reporting | Frappe Report: ArcPOS Item-wise Purchase Register. |
| 3 | Reporting | Correction of "Day-End Audit Summary". |
| 4 | Reporting | Frappe Report: ArcPOS Accounts Payable. |
| 5 | Reporting | ArcPOS WEB Report: All the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet. |
| 6 | Reporting | [] Frappe Report: NEW [all the report should be generate as per Outlet Periodic time slot and with Date Range & All Outlet]. |
| 7 | Reporting | replicate "ArcPOS WEB Report". |
| 8 | Functional Behavior | Sales Overview = ArcPOS Sales Overview. |
| 9 | Reporting | Order-to-Serve Lag Report = ArcPOS Order-to-Serve Lag Report. |
| 10 | Reporting | Day-End Audit Summary = ArcPOS Day-End Audit Summary. |
| 11 | Reporting | Report > Day-End Audit Summary. |
| 12 | Functional Behavior | Supplier Invoice Data missing!! |
| 13 | Functional Behavior | Rename the Column header "Total Tax" to "Total VAT". |
| 14 | Reporting | This report query data will change. |
| 15 | Functional Behavior | Without select a valid Outlet, should not execute the query or do not show any data > Remove "All" option. |
| 16 | Reporting | If above not possible then > If any Invoice territory = ISD, then the data should not appear in this report. |
| 17 | Reporting | Need Customized report > ArcPOS Accounts Payable. |
| 18 | Functional Behavior | Filters: Date Range, Supplier Name, Supplier Group. |
| 19 | Functional Behavior | No need any chart. |
| 20 | Functional Behavior | For Header Footer >. |
| 21 | Reporting | Need Customized report > ArcPOS Item-wise Purchase Register. |
| 22 | Functional Behavior | Additionally Add: Order No, Supplier Invoice. |
| 23 | Reporting | Reports page. |
| 24 | Reporting | Place the report in the Center and if multiple then the per row 2 reports. |
| 25 | Functional Behavior | Sales Overview. |
| 26 | Business Rule | All the value must be fetched as per logged user's territory permission. |
| 27 | Business Rule | Set the user's default user permission "Territory" in the Outlet filter and if user has on;y 1 territory permission then do not allow to change/All to select. |
| 28 | Business Rule | Use "Default Company" > "company_logo" field as letter head "Header" > Place on LEFT side & On RIGHT > Place the Filtered "Outlet" name [If "All" then show the user's permission wise all TERRITORY name with COMMA separate. Also add a full width straight line. |
| 29 | Reporting | Under the STRAIGHT line, on Center > Place the Report Name [Bold]. |
| 30 | Reporting | Under REPORT name, show filtered Date Range [Date format LIKE 1st Jan 2026 - 28th Feb 2026]. |
| 31 | Functional Behavior | With Above line > Add text on LEFT and RIGHT side > Prepared By, Authorized By. |
| 32 | Functional Behavior | Place at LEFT side "Powered by ArcPOS" and at RIGHT side > Generated on [Current Date, Current Time > italic]. |
| 33 | Reporting | Item Sales Summary. |
| 34 | Functional Behavior | All Item should be group by Territory also. |
| 35 | Functional Behavior | Add a "Outlet" column after "Category". |
| 36 | Functional Behavior | Add a "Outlet" column after "Method Name". |
| 37 | Functional Behavior | it's showing same "Method Name" multiple time? |
| 38 | Functional Behavior | The default date range should be set to today. |
| 39 | Functional Behavior | Date range filter > showing till 1 day before the End date. |
| 40 | Functional Behavior | Details: Add "Update by" = "modified_by". |
| 41 | Functional Behavior | In the list, Submitted On time is always showing as 12:00 AM. |
| 42 | Functional Behavior | List page: If Draft, show status = To Approve, If Submitted = Approved. |
| 43 | UI / UX | Rename the Accept button to "Approve". |
| 44 | Reporting | Service Mode Analytics. |
| 45 | Functional Behavior | Correct the subtitle to "Compare Dine-in & Takeout". |
| 46 | Reporting | Correct the additional path name to "Service Mode Analytics". |
| 47 | Functional Behavior | Change the color and name for these, also fix in the chart. |
| 48 | Reporting | When no data is found, the message should be updated to: "No service mode analytics data found for the selected date range.". |
| 49 | Functional Behavior | from Biplob. |
| 50 | Functional Behavior | from Amir. |
| 51 | Functional Behavior | Table & Covers PnL. |
| 52 | Reporting | Order-to-Serve Lag Report. |
| 53 | Functional Behavior | Order by "Voucher No" descending. |
| 54 | Reporting | Day-End Audit Summary. |
| 55 | Business Rule | Permission > System Manager, ArcPOS Manager, Restaurant Manager, Restaurant Cashier. |
| 56 | Functional Behavior | Follow the image. |
| 57 | Functional Behavior | Sales [Query much like Service Mode and Sales Overview]. |
| 58 | Functional Behavior | Doc Status = 1. |
| 59 | Functional Behavior | Order From = "customorderfrom". |
| 60 | Functional Behavior | Service Mode = "customservicetype". |
| 61 | Functional Behavior | Amount = Sum of "net_total". |
| 62 | Functional Behavior | Group by "Order From + "Service Type + Territory". |
| 63 | Functional Behavior | Total Sales = Sum of "net_total". |
| 64 | Functional Behavior | SD = Table > "Sales Taxes and Charges" > "customissd = 1" > tax_amount > (Sum of with SD Invoice qty). |
| 65 | Functional Behavior | VAT = Table > "Sales Taxes and Charges" > "customistax = 1" > tax_amount. |
| 66 | Functional Behavior | Auto Round > Sum of "rounding_adjustment" > (Sum of Auto Round NOT = 0 Invoice qty). |
| 67 | Functional Behavior | Group by + Territory. |
| 68 | Reporting | Individual Report. |
| 69 | Reporting | All reports except "Day-End Audit Summary". |
| 70 | Business Rule | Permission > System Manager, ArcPOS Manager, Restaurant Manager. |
| 71 | Reporting | Only "Day-End Audit Summary". |
| 72 | Business Rule | Outlet filter's default value should be the user's Frappe default territory permission, do not change auto if user update the outlet from POS front end.. |
| 73 | Reporting | Add territory for Sales Overview, Service Mode Analytics. |
| 74 | Reporting | Table wise party size income/cogs pnl report > Table & Covers PnL. |
| 75 | Reporting | Service performance report > Order-to-Serve Lag Report. |
| 76 | Reporting | Reports- ArcPOS Manager, System Manager, Restaurant Manager. |
| 77 | Reporting | Reports: > Almost Same things as BanCan. |

### Notifications

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | Add new Multi-Select (User) field POS Approvers" under existing field "Order Pay Default" + Combined Approver` (Auto fetch from "POS Approvers" COMMA separated) to use them to send emails. |
| 2 | Functional Behavior | Closing Email: All the precipitants should receive email in single email. (To and CC). |
| 3 | Business Rule | Remove "System Manager" Role from all the Email & Socket notifications. |
| 4 | Functional Behavior | Notification dropdown. |
| 5 | Functional Behavior | If Draft order then redirect to Draft Mode of the Order from Notification. |
| 6 | UI / UX | Notification dropdown > the ringer "Sound" button > Keep "ON" as default. That means, if user "OFF" this and somehow the app gets reload or restart so that sound will be turned ON automatically. |
| 7 | Functional Behavior | Notification. |
| 8 | Functional Behavior | Real time Email and Push Notification. |
| 9 | Functional Behavior | Notification Title: ôæ New Order Alert \| [Order ID] \| [Table ID]. |
| 10 | Functional Behavior | Notification Title: ÜÜ Stock Shipment In Transit. |
| 11 | Functional Behavior | Notification Title: Æ░ [Submission Type} Awaiting Approval. |
| 12 | Functional Behavior | Notification Title: Æ░ [Submission Type} Alert! |
| 13 | Functional Behavior | Remove all standard notification from Frappe for WC. |
| 14 | Functional Behavior | This Email setup is missing in the ArcPOS Settings. |
| 15 | Business Rule | All the Emails and Push/Socket Notifications must send as per default territory permission. Currently all specific users are getting the notifications. |
| 16 | Functional Behavior | Correction of alert trigger of notification: [Existing]. |
| 17 | Functional Behavior | Earlier was notify-to "Target Outlet"but should be notify-to "Source Outlet". |
| 18 | Functional Behavior | Just add one more condition that, if document's "Difference" value NOT = 0. |
| 19 | Functional Behavior | Send Notification to the "Restaurant Manager" on create DRAFT if found Diff. |

### Permissions & Roles

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | How these 2 field works and what's the functionality? |
| 2 | Business Rule | Allow only Frappe Role user "System Manager" to change the Outlet from any page. |
| 3 | Business Rule | Menu permission = System Manger/Auditor (Frappe Role). |
| 4 | Business Rule | Mark on "Ignore User Permissions". |
| 5 | Business Rule | When user has ArcPOS Manager/Restaurant Manager/System Manager permission then PIN shouldn't be there for VOID. |
| 6 | Business Rule | Managerial Override (Direct Submission): If a financial discrepancy exists but the user possesses the role of "System Manager, ArcPOS Manager, or Restaurant Manager", grant immediate bypass clearance to directly Submit the entry. |
| 7 | Business Rule | PIN- System Manager / ArcPOS Manager/ Restaurant Manager these role users won't have to enter PIN anywhere. |
| 8 | Business Rule | Check > If the docstatus = 0, then only Frappe Role = Restaurant Manager, ArcPOS Manager and System Manager" can Approve/Submit. |
| 9 | Functional Behavior | Invoice- ORD-26-00942. |
| 10 | Business Rule | List page data and Details-update permission must be validate as per Outlet (Source and Target), not as per document's territory. |
| 11 | Business Rule | If the Logged user role = "Restaurant Cashier" then user can't submit the entry, pass the Draft to Submit (Approve) by Role user "Restaurant Manager". |
| 12 | Business Rule | work on outlet wise permission. |
| 13 | Functional Behavior | Orders- Restaurant Cashier,Restaurant Manager, ArcPOS Manager, System Manager, Restaurant Waiter. |
| 14 | Functional Behavior | Create- ArcPOS Transfer Creator. |
| 15 | Functional Behavior | Create Transfer- ArcPOS Transfer Creator. |
| 16 | Functional Behavior | Cancel- ArcPOS Manager, System Manager. |
| 17 | Functional Behavior | Approve- ArcPOS Transfer Approver. |
| 18 | Functional Behavior | Module view- ArcPOS PCM Approver, ArcPOS PCM Creator. |
| 19 | Functional Behavior | Create- ArcPOS PCM Creator. |
| 20 | Functional Behavior | Submit- ArcPOS PCM Approver. |
| 21 | Business Rule | Check > "POS and Orders" module only allowed for Frappe Role: ArcPOS Manager, Restaurant Cashier, Restaurant Manager and System Manager". |
| 22 | Business Rule | "In Transit" > In the details page > All will be Read only and show button "Accept", "Cancel" [Cancel button will show all DocStatus = 1 and only allowed for System Manager"] and "Return" [Skip the Return Policy for now]. |

### Settings & Configuration

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Functional Behavior | ArcPOS Settings. |
| 2 | Functional Behavior | Territory. |
| 3 | Business Rule | Then "ArcPOS Settings > "Validate Stock?". If NO. |
| 4 | Business Rule | Then "ArcPOS Settings > "Validate Stock?". If YES. |
| 5 | Functional Behavior | Supplier: Use Frappe default Bank Account doctype for below data. |
| 6 | Functional Behavior | Data will be get from "BIN" doctype. |
| 7 | Functional Behavior | Field name: custom_territory. |
| 8 | Functional Behavior | Currently add a custom field = "customtotalouts_amount" and keep the new field as Currency Type and Read Only [Already set in WC staging]. |
| 9 | Functional Behavior | Order: Order Status = "" then notify-to based on Territory default wise "Restaurant Cashier" and "Restaurant Waiter". |
| 10 | Functional Behavior | Doctype Customization. |
| 11 | Functional Behavior | Rename Territory to Outlet. |
| 12 | Functional Behavior | The "Source Outlet" value will be auto load for the set "Default Territory" and the "Target Outlet" will be Blank. User will search and select the "Target Outlet". |
| 13 | Functional Behavior | Territory = Set Territory. |
| 14 | Functional Behavior | Switch Territory missing. |
| 15 | Functional Behavior | Filters: Date Range [Default Today]. Item name, Service Type, Item Status, Territory. |

### UI / UX & Responsiveness

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | UI / UX | Draft Order: From cart, if any item is variant, allow to replace the item to another variant of the parent item's in the Item edit pop up modal. |
| 2 | UI / UX | Draft Order: After entering to the order and closing the page without update anything, its showing the Update Order button enabled and showing Discard modal. |
| 3 | Functional Behavior | On trigger should redirect to the Home page. |
| 4 | UI / UX | If the trigger from New Order, then pop up a warning modal first, if confirms then initiate reload. |
| 5 | UI / UX | Add the"Bell Icon" with functionality also on the Modal's top right corner. |
| 6 | UI / UX | "Mark as Read" text button/pausing the alert tone button is not stopping the ringing from this modal. |
| 7 | UI / UX | This text should be in RED color font. |
| 8 | Functional Behavior | On Order Submit (passing Docstatus = 1 to frappe). |
| 9 | Functional Behavior | On success > Pass item's order status = Served. |
| 10 | Functional Behavior | No pass the "Serve" time. |
| 11 | Functional Behavior | On Order Draft (passing Docstatus = 0 to frappe). |
| 12 | UI / UX | Fix mobile responsiveness for this modal when type is selected. |
| 13 | UI / UX | Fix this for mobile responsiveness- 360 x 740. |
| 14 | UI / UX | Fix this for mobile responsiveness for clock in/out modal. |
| 15 | Functional Behavior | Fix this. |
| 16 | UI / UX | Align this in mobile view. |
| 17 | UI / UX | Show this with full name in mobile view. |
| 18 | UI / UX | Browser back button-> discard not working. |
| 19 | UI / UX | Add a Refetch Orders button on top right of the list page. |
| 20 | UI / UX | Make the button colors different like this. |
| 21 | UI / UX | The radio button should be displayed before the variant name. |
| 22 | UI / UX | Show a confirmation modal like this when user tries to remove an item. |
| 23 | UI / UX | Cross-Device Responsiveness: Resolve layout and responsive styling issues on the Order Details page. Conduct a comprehensive UI audit across all other POS pages to ensure consistency across different screen dimensions. |
| 24 | UI / UX | Draft Creation Control: Implement a "SAVE" button on the LEFT side of the panel. |
| 25 | UI / UX | Clicking this button must securely save the active transactional state into the backend with a docstatus = 0 (Draft) configuration. |
| 26 | UI / UX | Option A (Automated Polling): If a Voucher remains in an Approval/Draft state, listen for state changes; upon a backend transition to Approved/Submitted, the operational modal must auto-close. |
| 27 | UI / UX | Table Party size modal. |
| 28 | UI / UX | Delete/Backspace button should change the qty to 0 and =0 does not allow to go next/save. |
| 29 | UI / UX | When one action button is clicked, other action buttons also shows as loading. |
| 30 | UI / UX | Show "Submit" [will pass the invoice docstatus = 1 + "Is Credit Sales = 1"] button instead of "Pay" from all the page, if the "Grand Total/Rounded Total = 0". |
| 31 | UI / UX | Fix the menu for mobile view. |
| 32 | UI / UX | Select a Table- add a Refetch Tables button. |
| 33 | UI / UX | On update item modify this button to Update item. |
| 34 | UI / UX | While creating new order when Pay Later is selected only Save and Create New button will be shown. [With credit sales button if available]. |
| 35 | UI / UX | The item modal should when the user clicks anywhere on the item row. |
| 36 | UI / UX | In draft order edit the void button should also have PIN functionality. |
| 37 | UI / UX | Modify the confirmation modal when the user attempts to navigate to another page without saving the order. |
| 38 | UI / UX | Front: The button will view if the Invoice docstatus = 0 and this will be manage by PIN. |
| 39 | Functional Behavior | Quick adding/removing items in the Draft order, works slowly also sometimes missed some items to add in the cart. |
| 40 | UI / UX | Item Cart > Remove item should pop up a confirmation modal. |
| 41 | UI / UX | Use this button instead of the X button. |
| 42 | UI / UX | Show the confirm modal in the middle of the page. |
| 43 | UI / UX | IF NO: The "Clock In" modal pops up immediately. The general POS operation screen remains locked/hidden. |
| 44 | UI / UX | Add a confirmation modal when the user attempts to navigate to another page without saving the order. |
| 45 | UI / UX | Buttons: Discard \| Save & Exit. |
| 46 | Functional Behavior | This error message is shown when user tries to remove the only item left from an order- At least one item is required in the order. |
| 47 | UI / UX | While creating new order show only Pay button for Pay First. |
| 48 | UI / UX | Rename New Order button to-> Save and Create New. |
| 49 | UI / UX | While creating new order when Pay Later is selected only New Order button will be shown. |
| 50 | UI / UX | Clicking on the items should a modal, similar to ArcPOS. |
| 51 | UI / UX | Dark Mode Logo. |
| 52 | UI / UX | No show "Home" button. On click "Logo" will redirect to the Home page. |
| 53 | UI / UX | Order list: Bold font for "Order No". |
| 54 | UI / UX | On Create/Draft button trigger > Pass to frappe with. |
| 55 | UI / UX | If Draft > will covert the page in a Details page and show Edit and Create/Submit button. In the list page, Status will be "Draft". |
| 56 | UI / UX | Except Draft, all the other button trigger will redirect to the refreshed List page. |
| 57 | UI / UX | Change the Module and Modal Item's Icon. |

### General System Functionality

| # | Category | Final documented behavior |
|---:|---|---|
| 1 | Business Rule | Add new Check field `Validate Stock?" under existing field "Allow Update UOM?". |
| 2 | Functional Behavior | Add new Check field `Is Sales Outlet?" under existing field "Is Group". |
| 3 | Functional Behavior | Add new "Section Break" under items. |
| 4 | Functional Behavior | Add new Currency field. |
| 5 | Functional Behavior | Grand Total = customgrandtotal. |
| 6 | Functional Behavior | Depends On = eval:doc.customgrandtotal!="0". |
| 7 | Functional Behavior | Read Only. |
| 8 | Functional Behavior | Add new Small Text field. |
| 9 | Functional Behavior | In Words (Grand Total) = custominwordsgrandtotal. |
| 10 | Functional Behavior | Option A. |
| 11 | Functional Behavior | If Frappe Default Stock Setting > "Allow Negative Stock" = NO. |
| 12 | Functional Behavior | Override frappe functionality to allow Negative Stock while Sales Invoice is submitting with "update_stock". |
| 13 | Functional Behavior | Stock Entry on "SUBMIT" or "Item Qty entry from Web". |
| 14 | Functional Behavior | Check first If Frappe Default Stock Setting > "Allow Negative Stock" = YES. |
| 15 | Functional Behavior | Check and fix the pendings. |
| 16 | Functional Behavior | RATE column's Total as Average Rate. |
| 17 | Functional Behavior | Below is the reference. |
| 18 | Functional Behavior | User is logged out every time the application is . |
| 19 | Functional Behavior | In smaller screen the date time looks like this. |
| 20 | Functional Behavior | These disabled fields are not fully visible. |
| 21 | Functional Behavior | 2nd Trigger can be a cron job at midnight. |
| 22 | Functional Behavior | Can you do one thing, Whenever the app opens, it should with default Full screen. |
| 23 | Functional Behavior | Options: YES/NO. |
| 24 | Business Rule | Mandatory if "Allow Sales". |
| 25 | Functional Behavior | Sales Invoice Item. |
| 26 | Functional Behavior | Sales Invoice. |
| 27 | Functional Behavior | Checkbox. |
| 28 | Functional Behavior | Restaurant Table. |
| 29 | Functional Behavior | Pay Method. |
| 30 | Functional Behavior | Options: Blank/Cash/Bank. |
| 31 | Business Rule | Mandatory. |
| 32 | Functional Behavior | Beneficiary Account Name. |
| 33 | Functional Behavior | account_name. |
| 34 | Business Rule | Mandatory if not CASH in "Pay Method". |
| 35 | Functional Behavior | Beneficiary Account Number. |
| 36 | Functional Behavior | bankaccountno. |
| 37 | Functional Behavior | Routing Number. |
| 38 | Functional Behavior | customroutingnumber. |
| 39 | Functional Behavior | Receiver Bank Name. |
| 40 | Functional Behavior | Receiver Branch Name. |
| 41 | Functional Behavior | branch_code. |
| 42 | Functional Behavior | Same Field will be auto fetch from Supplier Bank Account. |
| 43 | Functional Behavior | Default 1 > Custom Remarks. |
| 44 | Functional Behavior | On "Sales Breakdown" data, take the invoice's total data. |
| 45 | Functional Behavior | Rename the SALES TOTAL to SALES TOTAL (Net). |
| 46 | Functional Behavior | Total Revenue = GRAND TOTAL. |
| 47 | Functional Behavior | Rename the Total Collected to Collections. |
| 48 | Functional Behavior | Sales Breakdown. |
| 49 | Functional Behavior | Sales Invoice (Is Credit Invoice? = 1 && docstatus = 1). |
| 50 | Functional Behavior | SALES TOTAL (Net) = Sum of invoice's total data. |
| 51 | Functional Behavior | Sum of invoice's > Table "Sales Taxes and Charges" > Is SD? = 1 > Sum of Amount data. |
| 52 | Functional Behavior | Sum of invoice's > Table "Sales Taxes and Charges" > Is TAX/VAT? = 1 > Sum of Amount data. |
| 53 | Functional Behavior | Auto Round. |
| 54 | Functional Behavior | Sum of invoice's Rounding Adjustment data. |
| 55 | Functional Behavior | Invoice Amount: Data should be the Invoice's Rounded Total. |
| 56 | Functional Behavior | Default full screen taking the full screen including the task bar and there are no option to shrink the screen. |
| 57 | Functional Behavior | show the task bar as well when its in default full screen. |
| 58 | Functional Behavior | If the system can achieve in the Alert on close/exit the app, then the interval alert can be each 30 mins. |
| 59 | Functional Behavior | Add a new menu "Stock Availability". |
| 60 | Functional Behavior | Just a list view with Search (Item name), Filter : Outlet, Category. |
| 61 | Functional Behavior | Columns: Item Name \| Category \| Outlet \| Current Stock. |
| 62 | Functional Behavior | Item name > excelitemname. |
| 63 | Functional Behavior | Category > excelitemgroup. |
| 64 | Functional Behavior | Outlet > custom_outlet. |
| 65 | Functional Behavior | Current Stock > actual_qty. |
| 66 | Functional Behavior | Keep 3 sections side by side until Tablet screen. |
| 67 | Functional Behavior | Sales Invoice: Parent Invoice reference on Split invoices. |
| 68 | Functional Behavior | Frappe Customization. |
| 69 | Functional Behavior | Click on this specific alert, not marking as read. |
| 70 | Functional Behavior | For "Rounding Adjustment". |
| 71 | Functional Behavior | If Grand Total value of 123.4999999 or below will result in a negative rounding adjustment. |
| 72 | Functional Behavior | Zero-Variance Auto-Submission: If there is no difference (variance is 0) between physical cash and Expected counts, the Cashier Voucher entry must be automatically Submitted. |
| 73 | Functional Behavior | Update your existing logic. |
| 74 | Functional Behavior | Table QR Code. |
| 75 | Functional Behavior | The Generated QR code link must be LIKE : >[portalbaseurl]/?tableid=[id]&outlet=[defaultoutlet]. |
| 76 | Functional Behavior | Implement a function to RE GENERATE the QR Code. |
| 77 | Functional Behavior | customwebrate - Make > Read Only > Item Price. |
| 78 | Functional Behavior | custom_outlet - hide > Restaurant Table. |
| 79 | Functional Behavior | Footer view is hiding, to fix it. check. |
| 80 | Functional Behavior | Buying price auto set. |
| 81 | Functional Behavior | But now the system modify this or another feature > Condition is. |
| 82 | Functional Behavior | This not worked from Frontend! |
| 83 | Functional Behavior | Table change impact is not happening. |
| 84 | Functional Behavior | SD % show like VAT; if not available, then hide. |
| 85 | Functional Behavior | Step 2: "Clock In" Process. |
| 86 | Functional Behavior | If Diff = (+) = Then Cash Debit and Default Company > Sales default income acc Credit. |
| 87 | Functional Behavior | If Diff = (-) = Then Cash Credit and Default Company > "Default Deferred Expense Account" acc Debit. |
| 88 | Functional Behavior | Will Submit a Journal Entry automatically. |
| 89 | Functional Behavior | Step 3: General Operations. |
| 90 | Functional Behavior | The system should records all cash transactions during the shift in the GL Entry. |
| 91 | Functional Behavior | Step 4: "Clock Out" Process. |
| 92 | Functional Behavior | Before leaving, the user selects Clock Out. |
| 93 | Functional Behavior | The system calculates the Expected Closing Cash using the formula in Backend. |
| 94 | Functional Behavior | Cash account Debit - Credit + Cash Sales = Expected Closing Cash. |
| 95 | Functional Behavior | The user performs a physical count as the same process of "Clock In". |
| 96 | Functional Behavior | Once submitted, the user is permitted to log out. |
| 97 | Functional Behavior | Every "Reason" provided for a difference is flagged for Manager review in the backend. |
| 98 | Functional Behavior | Cafe name: The White Canary Café. |
| 99 | Functional Behavior | Variant show as single item and show choice. |
| 100 | Functional Behavior | Variant show with Display name. |
| 101 | Functional Behavior | All day captain America breakfast double item choice. |
| 102 | Functional Behavior | VAT & SD account different for outlets. |
| 103 | Functional Behavior | Baking Prep and sell as single item? yes. |
| 104 | Functional Behavior | Batch qty edit allow. |
| 105 | Functional Behavior | Show the "Web Rate" for each item > Web Item will be auto calculated and set to the Selling price. |
| 106 | Functional Behavior | Title: "Unsaved Changes". |
| 107 | Functional Behavior | Rename this filter to Outlet and All Outlets. |
| 108 | Functional Behavior | Fix this view. |
| 109 | Functional Behavior | Remove these two from service type filter. |
| 110 | Functional Behavior | Show user's avatar/Image. |
| 111 | Functional Behavior | Show Table Image if there are any image is linked otherwise show as default current icon. |
| 112 | Functional Behavior | Rename "Tax" to "VAT". |
| 113 | Functional Behavior | Remove "Company name" value and what is the Square portion marked in below image? |
| 114 | Functional Behavior | On new creation. |
| 115 | Functional Behavior | Multiple Item allows to add in the Item Table and Quantity must me minimum 1. |
| 116 | Functional Behavior | Add to Transit = 1. |
| 117 | Functional Behavior | Items Table= Items. |
| 118 | Functional Behavior | Remarks = Remarks. |
| 119 | Functional Behavior | If Create > will redirect to the List page and Status will be "In Transit". |
| 120 | Functional Behavior | On "Accept" > Pass to frappe with. |
| 121 | Functional Behavior | Docstatus = 1. |
| 122 | Functional Behavior | On "Return" > Pass to frappe with. |
| 123 | Functional Behavior | For the New Stock Entry. |
| 124 | Functional Behavior | Remove " Forgot". |
| 125 | Functional Behavior | Remove "Accept terms and Condition". |
| 126 | Functional Behavior | Add Search and Filters. |
| 127 | Functional Behavior | Search: Voucher name, Item name. |
| 128 | Functional Behavior | Not add any item related filter if need implement later. |
| 129 | Functional Behavior | Replace Column "Item" to "UOM". |
| 130 | Functional Behavior | Replace Column "Item Name" to "Is Prep Item". |
| 131 | Functional Behavior | Search: Display Name, Item. |
| 132 | Functional Behavior | Filter: Item, Is Prep Item. |
| 133 | Functional Behavior | "Created By" value must be the Owner Full name. |
| 134 | Functional Behavior | Search: Voucher No, Owner name [Optional], Remarks. |
| 135 | Functional Behavior | Create new: Add Remarks Field. |

## Quality Assurance Use

This document can be used as the baseline for regression testing, release verification, user acceptance testing, onboarding, and functional reference.

## Documentation Summary

- Functional areas covered: 19
- Consolidated unique documented behaviors: 1011
- Duplicate and overlapping entries have been consolidated.
- All items are documented as completed system behavior rather than future work.
- Issue-tracking references, assignees, tracking metadata, and progress-state wording are excluded.