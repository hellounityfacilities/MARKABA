# MARKABA — Showroom · Rental · Finance

A bilingual (English / العربية) dealer management system for car showrooms that sell new and used cars **and** run a rental fleet, with a full double-entry accounting core underneath. This first deliverable is a single-file working prototype — the same approach as the Mizan and Daftar demos — so it can be shared by link and clicked through end to end before the production build.

Open `index.html` in any modern browser. No install, no server, no build step. Data is saved in that browser (localStorage for records, IndexedDB for document files). Use *Backup → Copy backup with documents* to move everything to another computer.

---

## What's inside

| Area | What it does |
|---|---|
| **Dashboard** | Role-aware KPIs, 6-month revenue by stream (vehicle sales / rental / workshop & parts / finance), returns due and pickups, and a "needs attention" list: Istimara & insurance expiry, service due, overdue rentals, deposits ready to release, cheques due, overdue installments, reorder alerts, aged stock. |
| **Deals** | Quote → booking deposit → delivery & invoice. Add-ons (tint, warranty, accessories issued from stock), trade-ins, bank finance (QNB, Dukhan…), in-house installments, minimum-price control with manager approval, salesperson commission on gross profit. |
| **Leads & test drives** | Pipeline board (New → Contacted → Test drive → Negotiation → Won/Lost), convert a lead straight into a deal, test-drive log with licence numbers. |
| **Installment plans** | Flat-rate schedules, collection by cash, card, transfer or **post-dated cheque**; a returned cheque re-opens the installment automatically. |
| **Trade-ins & consignment** | Trade-ins enter used stock at actual cash value (over-allowance booked separately). Consignment cars stay off the balance sheet; on sale the owner payout becomes a payable and only the margin is income. |
| **Vehicle stock** | New / used / consignment / fleet with VIN, Qatar plate, odometer, branch, days in stock, landed-cost build-up (freight, customs, reconditioning), floor-plan purchases, move to fleet and de-fleet at net book value. |
| **Rental** | Fleet board with a 3-week availability timeline, reservations, agreements with daily / weekly / monthly plans, CDW, extras, free-km allowance, fuel in eighths, damage, late days, interim billing for monthly corporate hires, security deposits held for the fines window, blacklist and licence-expiry checks. |
| **Traffic fines** | Enter a Metrash fine by plate and date — the system finds who had the car and recharges it with a handling fee; unrented dates become a company cost. Pay fines to the authority in a batch. |
| **Workshop** | Job cards for customer, warranty, fleet maintenance and pre-sale reconditioning. Customer jobs invoice; warranty jobs claim on the manufacturer; fleet jobs cost to maintenance; reconditioning capitalises into the car. |
| **Parts & accessories** | Weighted-average stock, goods received (GRN), counter sales, stock counts, reorder levels, movement history. |
| **Finance** | Receivables with allocation, payables, bank & cash book, bank reconciliation, PDC register, expenses, manual journals with reversal, bilingual chart of accounts, fixed assets & depreciation (fleet + furniture), payroll with commission payout and 21-day gratuity accrual (WPS), period lock and year-end close. |
| **Reports** | Trial balance, P&L, balance sheet, general ledger, tax summary, AR/AP aging, installments due, deal profitability, sales by salesperson, stock valuation & aging, fleet utilisation & profitability, workshop summary, expiry register. Every report copies as CSV. |
| **Supporting documents** | Attach invoices, receipts, contracts and photos to any journal — from the journal page (drag-and-drop or choose) or while posting a manual journal, expense, receipt, payment, transfer, vehicle purchase, vehicle cost or parts receipt. Vehicles and contacts have their own document folders (Istimara, QID, licence, CR). Phone photos are scaled down automatically; PDFs and images preview in place. The journal list shows a paperclip count and filters for journals with or without documents. Only an administrator or accountant can remove a document, never in a locked period, and every attach/remove is in the audit log. |
| **Printed documents** | A4 bilingual (English + Arabic on the same page) tax invoice, quotation, receipt voucher, payment voucher, journal voucher and rental agreement with terms & conditions. Your logo, tax number, address, bank details and rental terms come from Settings; every amount is written in words in both languages. Print or save as PDF from the hosted app. |
| **Import & opening balances** | Bring in customers, suppliers, vehicles (sales stock and fleet), parts and an opening trial balance from Excel (.xlsx) or CSV, or paste rows straight from Excel. Every row is checked first (duplicate VINs and codes, bad dates, missing parties) and shown before anything is saved. Opening stock and balances post one journal against *3900 Opening balance equity*; opening receivables and payables become open invoices and bills so aging and allocation work from day one. |
| **Approvals & revisions** | Manual journals are saved as drafts, submitted, then approved and posted by a second person (maker-checker) — or rejected with a reason and sent back. Documents attached to a draft move to the posted journal. Quotes and bookings can be revised (price, discount, add-ons, trade-in, finance) with a revision history; a booked deal keeps its car and customer. |
| **Global search** | Press `/` or Ctrl+K anywhere. Finds cars by VIN, plate (with or without the space) or stock number; contacts by name (English or Arabic), phone, QID or licence; and deals, agreements, invoices, receipts, payments, journals, job cards, parts and cheques by number. Arrow keys and Enter to open. |
| **Vehicle condition check** | At check-out and check-in: tap the car diagram to mark scratches, dents, cracks and missing parts (with notes), attach photos, and capture the customer's signature on screen. At check-in, damage already noted at check-out shows in amber and new damage in red; the new damage is written into the check-in invoice automatically. Both diagrams and signatures print on the rental agreement. |
| **Customer reminders** | A queue worked out from the books: installments due or overdue, rental returns due or overdue, overdue invoices (grouped per customer), cheques about to be deposited, hirer licences expiring, first service due, and quotation follow-ups. Each message is ready in English or Arabic (per customer, editable templates in Settings); open it in WhatsApp or copy it for SMS, then mark it sent — the message is logged on the customer's record. Automatic sending needs an SMS gateway or the WhatsApp Business API in the production build. |
| **Approvals inbox** | One place for everything that needs a second person: discounts over the per-company limit (default 3%) or below the car's minimum price, deposit refunds on cancelled bookings, leave requests and manual journals. A sales executive's over-limit deal can't be booked or delivered until a manager approves it; nobody can approve their own request, and every decision is kept with name and reason. |
| **Purchase orders & shipments** | Order cars from the distributor in USD, JPY or EUR at an exchange rate, mark the shipment sailed (bill of lading, vessel, ETA), add freight, customs, clearing and insurance as the bills come in (held in *1320 Vehicles in transit*), then receive the cars with their VINs. Landed costs are shared across the cars by value, so each car's cost is exact before it reaches the showroom. |
| **Floor-plan financing** | Every car bought on the bank's floor plan is a loan with its own days and interest. Monthly accrual posts the interest; settling a sold car pays principal plus interest in one entry. Cars sold but not settled, or past the curtailment date, show on the dashboard. |
| **Workshop appointments** | Week calendar by bay with clash checking. When the customer arrives, one click opens the job card; no-shows are recorded. Customers booked for tomorrow appear in the reminder queue. |
| **Leave & WPS** | Leave requests (annual, sick, unpaid, emergency) with manager approval, annual balances per Qatar Labour Law (21 days, 28 after five years; Fridays not counted). Approved unpaid leave is deducted in payroll. Each payroll run downloads a WPS salary information file (SIF) with QID, bank and IBAN per employee. |
| **Branch P&L and budgets** | Profit & loss by branch (showroom, workshop, rental desk, head office) straight from the ledger. Monthly budgets per account — typed in or filled from this year's actuals — and a budget vs actual report with variances. |
| **Guided demo tour** | *Demo tour* in the top bar walks a client through 16 highlights in English or Arabic, moving between screens and spotlighting each feature. Arrow keys or Next/Back; works on a phone too. |
| **Administration** | Multi-company (each with its own books and numbering), branches, users & roles, settings, audit log, backup & restore. |

### Roles
Administrator · Showroom manager · Sales executive · Rental agent · Service advisor · Accountant. Each sees only their areas; switch user from the top bar in the demo.

---

## How the money moves (posting rules)

| Event | Journal |
|---|---|
| Buy a car for sale | Dr Vehicle stock (1300 new / 1310 used) — Cr Supplier (2100), Bank, or Floor-plan loan (2600) |
| Landed cost | Dr Vehicle stock — Cr Bank / Supplier (capitalised into that car) |
| Booking deposit | Dr Bank — Cr Customer deposits (2200) |
| **Deliver a deal** | Dr Customer (1100) total · Cr Vehicle sales (4100/4110) · Dr Discounts (4150) · Cr Add-on revenue (4510/4500) · Cr Output tax (2400) · Dr Cost of vehicles sold (5100/5110) — Cr Stock · Trade-in: Dr Used stock at ACV, Dr over-allowance (4150), Cr Customer · Deposits: Dr 2200 — Cr 1100 · Bank finance: Dr Finance company (1110) — Cr 1100 · In-house: Dr Installments (1120) — Cr 1100 · Commission: Dr 6110 — Cr 2310 |
| Consignment sale | Dr Customer — Cr Consignor payable (2110) owner payout · Cr Consignment commission (4200) margin |
| Installment collected | Dr Bank or PDC on hand (1160) — Cr Installments (1120) principal · Cr Finance income (4400) interest |
| PDC cleared / returned | Dr Bank — Cr 1160 / full reversal of the receipt, invoice or installment re-opened |
| Rental deposit | Dr Bank — Cr Rental deposits (2210) |
| Rental invoice | Dr Customer — Cr Rental revenue (4300) · Cr Extra charges (4310: km, fuel, damage) · Cr Output tax |
| Traffic fine | Hirer found: Dr Customer — Cr Fines payable (2250) + Cr Fee income (4320) · none: Dr Fines expense (6240) — Cr 2250 |
| Workshop close | Customer: Dr 1100 — Cr Labour (4500), Parts (4510); Dr COGS parts (5200) — Cr Parts stock (1330) · Warranty: Dr Warranty claims (1130) · Fleet: Dr Fleet maintenance (5300) — Cr 1330, Cr labour absorbed · Recon: Dr the car's stock |
| Depreciation | Dr Fleet depreciation (5310) — Cr Accumulated (1510); F&E 6250 / 1610 |
| Payroll | Dr Salaries (6100), Dr Commission payable (2310) — Cr Salaries payable (2300); Dr Gratuity (6120) — Cr Provision (2320) · unpaid leave reduces salaries |
| Import landed cost | Dr Vehicles in transit (1320) — Cr Supplier / Bank |
| Shipment received | Dr Vehicle stock (1300) each car at price × rate + share of landed cost — Cr Supplier (2100) goods · Cr 1320 landed costs |
| Floor-plan interest | Month end: Dr Floor-plan interest (6280) — Cr Accrued expenses (2500) · Settlement: Dr Floor-plan loan (2600), Dr 2500, Dr 6280 (days since accrual) — Cr Bank |

### Controls enforced on every posting
1. At least two lines · 2. One-sided, positive lines · 3. Debits = credits to the fils · 4. Active, known accounts · 5. Control accounts carry a party of the right type · 6. Nothing posts on or before the lock date · 7. Journals are append-only — corrections by reversal.

Business rules on top: manual journals need a second person to approve (configurable), discounts over the limit and prices below the minimum need a manager, deposit refunds by non-managers need approval, blacklisted customers and expired licences can't rent, a car on rent can't be rented twice, odometers never go backwards, cheques can't clear before their date, depreciation and payroll run once per month.

---

## Demo data
Two companies are seeded through the real services (so every number is backed by balanced journals), with dates relative to today so the demo never looks stale:

- **Al Dana Motors W.L.L.** — three branches (Salwa Road showroom, Industrial Area workshop, Airport rental desk), ~70 vehicles, 56 deals including trade-in, bank-finance, in-house-installment and consignment sales, an 8-car rental fleet with five months of hires, fines, workshop history, payroll and depreciation.
- **Pearl Drive Rentals W.L.L.** — a small rental-only company, to show multi-company.

**Presenting to a client:** press **▶ Demo tour** in the top bar — it signs in as the administrator of Al Dana Motors and walks through the highlights. The seed also includes a pending discount approval, a pending refund, pending leave requests, three import purchase orders (received, on the water, on order), a floor-plan car sold but not yet settled, this week's workshop appointments and a budget for the year.

**Ten-minute tour by hand:** open *Deals → New deal*, add a trade-in and bank finance, take a deposit, deliver it, then open the journal it posted · *Fleet board → Check out* a car, then *Check in* with extra km and less fuel · *Traffic fines → Record fine* on a date the car was rented · *Post-dated cheques → Returned* on a held cheque and watch the installment re-open · *Reports → Balance sheet* (always balanced) · switch to **العربية** and to another user role from the top bar.

---

## Tests
```
node test/ledger.test.js      # 132 accounting assertions: every control account ties to its sub-ledger, controls reject bad postings, full sale and rental cycles
node test/ui-smoke.js         # every screen and form in English and Arabic, no console errors
node test/ui-flows.js         # fills and submits the main forms in a real browser, books still balance, data survives reload
node test/ui-roles.js         # every role × every company × every visible screen; no horizontal overflow at phone width
node test/ui-docs.js          # attach, compress, preview, filter, remove and back up supporting documents
node test/ui-batch2.js        # printed documents, logo, quote revision, journal approval and CSV import through the screens
node test/ui-downloads.js     # template, report CSV and print button in the hosted app
node test/ui-batch3.js        # search, condition check with signature and photo, reminders through the screens
node test/ui-batch4.js        # approvals, refunds, floor plan, purchase order to receipt, appointments, leave & WPS, branch P&L, budgets, demo tour (EN, AR, phone)
```
(The browser tests use Playwright.) Source lives in `src/`; `node build.js` produces `dist/index.html`.

---

## Toward production
This prototype proves the workflows and the accounting. For go-live with real customers, the same path as Mizan: Node/Express + PostgreSQL + React, with the ledger invariants enforced in the database, server-side sessions and RBAC, multi-user concurrency, document numbering per branch, and optional integrations (bank feeds, SMS reminders for installments and returns). Qatar has no VAT today; the tax rate is a per-company setting ready for when it applies, or for a showroom elsewhere in the GCC.
