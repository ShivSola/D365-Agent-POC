# USMF vs DEMF Configuration Comparison

This document compares the configuration between legal entities USMF and DEMF in the F&O environment for the following areas: Vendor Groups, Customer Groups, Payment Terms, Main Accounts, and Tax Groups.

For each area, the table shows:
- **Identifier**: The unique code/ID for the item
- **Name**: The description/name
- **USMF**: Whether it exists in USMF (Yes/No)
- **DEMF**: Whether it exists in DEMF (Yes/No)
- **Status**: Both (exists in both), USMF only, DEMF only

Note: Existence is determined by the presence of the Identifier. Minor differences in descriptions are noted but do not affect the status.

## Vendor Groups

| Identifier | Name | USMF | DEMF | Status |
|------------|------|------|------|--------|
| 10 | Parts vendors | Yes | Yes | Both |
| 20 | Services vendors | Yes | Yes | Both |
| 30 | Tax Authorities / Tax authorities | Yes | Yes | Both |
| 40 | Other vendors | Yes | Yes | Both |
| 50 | Intercompany vendors | Yes | Yes | Both |
| ONE | One-time vendors | Yes | No | USMF only |

## Customer Groups

| Identifier | Name | USMF | DEMF | Status |
|------------|------|------|------|--------|
| 10 | Wholesales customers | Yes | Yes | Both |
| 20 | Major customers | Yes | Yes | Both |
| 30 | Retail customers | Yes | Yes | Both |
| 40 | Internet customers | Yes | Yes | Both |
| 80 | Other customers | Yes | Yes | Both |
| 90 | Intercompany customers / Incompany customers | Yes | Yes | Both |
| 100 | Intercompany retail customers | Yes | No | USMF only |

## Payment Terms

| Identifier | Name | USMF | DEMF | Status |
|------------|------|------|------|--------|
| Net10 | Net 10 days | Yes | Yes | Both |
| Net15 | Net 15 days | Yes | Yes | Both |
| Net30 | Net 30 days | Yes | Yes | Both |
| Net45 | Net 45 days | Yes | Yes | Both |
| Cash | Cash | Yes | Yes | Both |
| COD | Cash on delivery | Yes | Yes | Both |
| Month+15 | Month end + 15 days | Yes | Yes | Both |
| Sch_6M | Declining payment schedule over 6 months / declining payment schedule over 6 months | Yes | Yes | Both |
| Sch_5M | Equal payment schedule over 5 months | Yes | Yes | Both |
| Net1 | Net 1 day | Yes | Yes | Both |

## Main Accounts

Both USMF and DEMF use the same shared Chart of Accounts ("Shared"), so all Main Accounts exist in both legal entities.

| Identifier | Name | USMF | DEMF | Status |
|------------|------|------|------|--------|
| 110110 | Bank Account - USD | Yes | Yes | Both |
| 110115 | Bank Account - CAD | Yes | Yes | Both |
| 110120 | Bank Account - CNY | Yes | Yes | Both |
| 110130 | Bank Account - EUR | Yes | Yes | Both |
| 110140 | Bank Account - DKK | Yes | Yes | Both |
| 110150 | Bank Account - GBP | Yes | Yes | Both |
| 110160 | Bank Account - Payroll | Yes | Yes | Both |
| 110180 | Petty Cash | Yes | Yes | Both |
| 112000 | Safe drop | Yes | Yes | Both |
| 112010 | Bank drop | Yes | Yes | Both |
| 112100 | Deposits - Cash | Yes | Yes | Both |
| 112110 | Deposits - Check | Yes | Yes | Both |
| 112120 | Deposits - Credit card | Yes | Yes | Both |
| 112130 | Deposits - Voucher | Yes | Yes | Both |
| 112140 | Deposits - Gift card | Yes | Yes | Both |
| 112150 | Deposits - Currency | Yes | Yes | Both |
| 112160 | Deposits - Loyalty | Yes | Yes | Both |
| 119999 | TOTAL CASH & CASH EQUIVALENTS | Yes | Yes | Both |
| 120100 | Bonds | Yes | Yes | Both |
| 120200 | Other Marketable Securities | Yes | Yes | Both |
| 120300 | Bill of Exchange (BOE) | Yes | Yes | Both |
| 120400 | BOE Remitted for Collection | Yes | Yes | Both |
| 120500 | BOE Remitted for Discount | Yes | Yes | Both |
| 120600 | Protested BOE | Yes | Yes | Both |
| 129999 | TOTAL SECURITIES | Yes | Yes | Both |
| 130100 | Accounts Receivable - Domestic | Yes | Yes | Both |
| 130110 | Accounts Receivable - Foreign | Yes | Yes | Both |
| 133300 | Intercompany Receivable - USMF/DEMF | Yes | Yes | Both |
| 130300 | Accounts Receivable - Not Invoiced | Yes | Yes | Both |
| 133350 | Intercompany Receivable - Delivered Sales Not Invoiced | Yes | Yes | Both |
| 130400 | Credit Card Receivable | Yes | Yes | Both |
| 130500 | Interest Receivable | Yes | Yes | Both |
| 130600 | Notes Receivable | Yes | Yes | Both |
| 130700 | Other Receivables | Yes | Yes | Both |
| 130725 | Bridging | Yes | Yes | Both |
| 130750 | Use Tax Receivable | Yes | Yes | Both |
| 130800 | VAT Tax Receivable | Yes | Yes | Both |
| 130999 | TOTAL ACCOUNTS RECEIVABLE | Yes | Yes | Both |
| 132100 | Prepaid Insurance | Yes | Yes | Both |
| 132110 | Prepaid Commissions | Yes | Yes | Both |
| 132190 | Prepaid Other Expenses | Yes | Yes | Both |
| 132999 | TOTAL OTHER CURRENT ASSETS | Yes | Yes | Both |
| 133100 | Intercompany Receivable - USSI/GBSI | Yes | Yes | Both |
| 133200 | Intercompany Receivable - USRT/FRRT | Yes | Yes | Both |
| 133399 | TOTAL INTERCOMPANY RECEIVABLES | Yes | Yes | Both |
| 140100 | Raw Materials Inventory | Yes | Yes | Both |
| 140200 | Finished Goods Inventory | Yes | Yes | Both |
| 149999 | TOTAL PHYSICAL INVENTORY | Yes | Yes | Both |
| 150100 | Production WIP-Clearing | Yes | Yes | Both |
| 150150 | Production WIP-Materials | Yes | Yes | Both |
| 150200 | Production WIP-Labor | Yes | Yes | Both |
| 150250 | Production WIP-Overhead | Yes | Yes | Both |
| 150300 | Production WIP-Subcontracting | Yes | Yes | Both |
| 150999 | TOTAL PRODUCTION WIP | Yes | Yes | Both |
| 159999 | TOTAL PRODUCTION INVENTORY | Yes | Yes | Both |
| 160100 | WIP - Labor | Yes | Yes | Both |
| 160200 | WIP - Products | Yes | Yes | Both |
| 160300 | WIP - Expense | Yes | Yes | Both |
| 160400 | WIP - Accrued Loss | Yes | Yes | Both |
| 160500 | WIP - Other | Yes | Yes | Both |
| 160600 | WIP - Invoiced On Account | Yes | Yes | Both |
| 160999 | TOTAL PROJECT WIP COST VALUE | Yes | Yes | Both |
| 161100 | WIP - Production | Yes | Yes | Both |
| 161200 | WIP - Profit | Yes | Yes | Both |
| 161300 | WIP - Sales Value | Yes | Yes | Both |
| 161399 | TOTAL PROJECT WIP SALES VALUE | Yes | Yes | Both |
| 161999 | PROJECT GROSS WIP | Yes | Yes | Both |
| 162100 | WIP - Invoiced - On Account | Yes | Yes | Both |
| 169999 | PROJECT NET WIP | Yes | Yes | Both |
| 170150 | Goodwill | Yes | Yes | Both |
| 170250 | Development | Yes | Yes | Both |
| 179999 | TOTAL INTANGIBLE ASSETS | Yes | Yes | Both |
| 180100 | Tangible Fixed Assets | Yes | Yes | Both |
| 180140 | Intangible Fixed Assets | Yes | Yes | Both |
| 180199 | TOTAL FIXED ASSETS | Yes | Yes | Both |
| 180200 | Accumulated Depreciation - Tangible Fixed Assets | Yes | Yes | Both |
| 180240 | Amortization - Intangible Fixed Assets | Yes | Yes | Both |
| 180280 | Deferred Tax Assets, Long-term | Yes | Yes | Both |
| 180290 | Revaluation Adjustment | Yes | Yes | Both |
| 180292 | Write Down/Up Fixed Assets | Yes | Yes | Both |
| 180295 | Other Assets | Yes | Yes | Both |
| 180299 | TOTAL ACCUMULATED DEPRECIATION | Yes | Yes | Both |
| 189999 | TOTAL FIXED ASSETS AND DEPRECIATION | Yes | Yes | Both |
| 199999 | TOTAL ASSETS | Yes | Yes | Both |
| 200100 | Accounts Payable - Domestic | Yes | Yes | Both |
| 200110 | Accounts Payable - Other | Yes | Yes | Both |
| 200115 | Accounts Payable - Employees | Yes | Yes | Both |
| 231300 | Intercompany Payable - USMF/DEMF | Yes | Yes | Both |
| 200125 | Accounts Payable - Offset Invoice Pending Approval | Yes | Yes | Both |
| 200130 | Invoice Pending Approval | Yes | Yes | Both |
| 200140 | Accrued Purchases - Received Not Invoiced | Yes | Yes | Both |
| 200150 | Promisorry Notes | Yes | Yes | Both |
| 200160 | Remitted Promissory Notes | Yes | Yes | Both |
| 200170 | Bill of Exchange Liability | Yes | Yes | Both |
| 200190 | Accrued Purchases | Yes | Yes | Both |
| 200999 | TOTAL ACCOUNTS PAYABLE | Yes | Yes | Both |
| 201100 | Salaries and Wages Payable | Yes | Yes | Both |
| 201110 | Commissions Payable | Yes | Yes | Both |
| 201120 | Payroll Benefits Payable | Yes | Yes | Both |
| 201130 | Payroll Deductions Payable | Yes | Yes | Both |
| 201140 | Employee Benefits Payable | Yes | Yes | Both |
| 201150 | State Worker's Compentation Payable | Yes | Yes | Both |
| 201160 | Federal Witholding Tax | Yes | Yes | Both |
| 201170 | State Witholding Tax | Yes | Yes | Both |
| 201180 | FICA Tax Payable | Yes | Yes | Both |
| 201190 | FUTA Tax Payable | Yes | Yes | Both |
| 201200 | SUTA Payable | Yes | Yes | Both |
| 201999 | TOTAL PAYROLL LIABILITIES | Yes | Yes | Both |
| 202100 | California State Tax Payable | Yes | Yes | Both |
| 202110 | Colorado State Tax Payable | Yes | Yes | Both |
| 202120 | Tennesse State Tax Payable | Yes | Yes | Both |
| 202130 | Nevada State Tax Payable | Yes | Yes | Both |
| 202140 | New Jersey State Tax Payable | Yes | Yes | Both |
| 202150 | Michigan State Tax Payable | Yes | Yes | Both |
| 202160 | DC State Tax Payable | Yes | Yes | Both |
| 202170 | Florida State Tax Payable | Yes | Yes | Both |
| 202180 | Georgia State Tax Payable | Yes | Yes | Both |
| 202190 | Iowa State Tax Payable | Yes | Yes | Both |
| 202200 | Idaho State Tax Payable | Yes | Yes | Both |
| 202210 | Illinois State Tax Payable | Yes | Yes | Both |
| 202220 | Massachusetts State Tax Payable | Yes | Yes | Both |
| 202230 | Maryland State Tax Payable | Yes | Yes | Both |
| 202240 | Minnesota State Tax Payable | Yes | Yes | Both |
| 202250 | North Dakota State Tax Payable | Yes | Yes | Both |
| 202260 | New York State Tax Payable | Yes | Yes | Both |
| 202270 | Ohio State Tax Payable | Yes | Yes | Both |
| 202280 | Oregon State Tax Payable | Yes | Yes | Both |
| 202290 | Pennsylvania State Tax Payable | Yes | Yes | Both |
| 202300 | Texas State Tax Payable | Yes | Yes | Both |
| 202310 | Washington State Tax Payable | Yes | Yes | Both |
| 202500 | Chicago City Tax Payable | Yes | Yes | Both |
| 202510 | Fargo City Tax Payable | Yes | Yes | Both |
| 202520 | Los Angeles City Tax Payable | Yes | Yes | Both |
| 202700 | Cook County Tax Payable | Yes | Yes | Both |
| 202710 | Orange County Tax Payable | Yes | Yes | Both |
| 202900 | Sales Tax Clearing | Yes | Yes | Both |
| 202999 | TOTAL SALES TAX PAYABLE | Yes | Yes | Both |
| 211600 | Dividends Payable | Yes | Yes | Both |
| 211650 | Freight Payable | Yes | Yes | Both |
| 212100 | Short Term Interest Payable | Yes | Yes | Both |
| 212150 | Prepayment of Service Subscription Fee | Yes | Yes | Both |
| 212160 | Customer Deposits | Yes | Yes | Both |
| 221240 | Income Taxes Payable | Yes | Yes | Both |
| 221250 | Property Taxes Payable | Yes | Yes | Both |
| 221850 | Other Taxes Payable | Yes | Yes | Both |
| 222100 | Use Tax Payable | Yes | Yes | Both |
| 222170 | Reserve for Deferred Profit on Assets | Yes | Yes | Both |
| 222190 | Other Current Liabilities | Yes | Yes | Both |
| 222200 | VAT Tax Payable | Yes | Yes | Both |
| 222999 | TOTAL OTHER CURRENT LIABILITIES | Yes | Yes | Both |
| 231350 | Intercompany Payable - USSI/GBSI | Yes | Yes | Both |
| 231355 | Intercompany Payable - USRT/FRRT | Yes | Yes | Both |
| 231399 | TOTAL INTERCOMPANY PAYABLES | Yes | Yes | Both |
| 249999 | TOTAL SHORT TERM LIABILITIES | Yes | Yes | Both |
| 250100 | Longterm Bank Loans | Yes | Yes | Both |
| 250200 | Notes Payable | Yes | Yes | Both |
| 250300 | Mortgage Payable | Yes | Yes | Both |
| 250400 | Longterm Interest Payable | Yes | Yes | Both |
| 250500 | Deferred Income Tax | Yes | Yes | Both |
| 250600 | Deferred Revenue | Yes | Yes | Both |
| 259999 | TOTAL LONG TERM LIABILITIES | Yes | Yes | Both |
| 299999 | TOTAL LIABILITIES | Yes | Yes | Both |
| 300110 | Capital Stock | Yes | Yes | Both |
| 300120 | Paid-in Capital | Yes | Yes | Both |
| 300130 | Dividends Paid | Yes | Yes | Both |
| 300140 | Capital Stock - Foreign | Yes | Yes | Both |
| 300150 | Unrealized Currency Gain/Loss | Yes | Yes | Both |
| 300160 | Retained Earnings | Yes | Yes | Both |
| 300170 | Accumulated Other Comprehensive Income | Yes | Yes | Both |
| 300999 | TOTAL EQUITY | Yes | Yes | Both |
| 399999 | TOTAL LIABILITIES & EQUITY | Yes | Yes | Both |
| 401100 | Product Sales | Yes | Yes | Both |
| 401200 | Service Revenues | Yes | Yes | Both |
| 401400 | Accrued Sales (Shipped Not Invoiced) | Yes | Yes | Both |
| 402200 | Intercompany Accrued Sales (Packing Slip) | Yes | Yes | Both |
| 401999 | TOTAL EXTERNAL SALES | Yes | Yes | Both |
| 402100 | Sales Adjustment Internal | Yes | Yes | Both |
| 402999 | TOTAL SALES INTERNAL | Yes | Yes | Both |
| 403150 | Miscellaneous Charges | Yes | Yes | Both |
| 403160 | Customer Invoice Discounts | Yes | Yes | Both |
| 403200 | Discount | Yes | Yes | Both |
| 403210 | Quantity Discount | Yes | Yes | Both |
| 403220 | Mix and Match Discount | Yes | Yes | Both |
| 403300 | Customer Cash Discounts Taken | Yes | Yes | Both |
| 403400 | Commissions (Vendor Related) | Yes | Yes | Both |
| 403500 | Freight - Outbound | Yes | Yes | Both |
| 403600 | Sale of Intellectual Property | Yes | Yes | Both |
| 403700 | Sale of Discontinued Operations | Yes | Yes | Both |
| 403800 | Income from Discontinued Operations | Yes | Yes | Both |
| 403999 | TOTAL OTHER INCOME | Yes | Yes | Both |
| 409999 | TOTAL SALES | Yes | Yes | Both |
| 411100 | Revenue - Labor | Yes | Yes | Both |
| 411200 | Revenue - Products | Yes | Yes | Both |
| 411300 | Revenue - Expenses | Yes | Yes | Both |
| 411400 | Revenue - Fees | Yes | Yes | Both |
| 411500 | Revenue - On Account | Yes | Yes | Both |
| 402300 | Intercompany Sales - USMF/DEMF | Yes | Yes | Both |
| 411999 | TOTAL PROJECT INVOICED REVENUE | Yes | Yes | Both |
| 420050 | Accrued Revenue - Production | Yes | Yes | Both |

## Tax Groups

| Identifier | Name | USMF | DEMF | Status |
|------------|------|------|------|--------|
| 5Pct | 5Pct Tax | Yes | No | USMF only |
| CA | California | Yes | No | USMF only |
| CALA | California Los Angeles | Yes | No | USMF only |
| CALA-USE | California Los Angeles Use Tax | Yes | No | USMF only |
| CO | Colorado | Yes | No | USMF only |
| DC | Washington DC | Yes | No | USMF only |
| FL | Florida | Yes | No | USMF only |
| FLORCNTY | Florida Orange County | Yes | No | USMF only |
| GA | Georgia | Yes | No | USMF only |
| IA | Iowa | Yes | No | USMF only |
| ID | Idaho | Yes | No | USMF only |
| IL | Illinois | Yes | No | USMF only |
| ILCHCITY | Illinois Chicago City, Cooke County | Yes | No | USMF only |
| MA | Massachusetts | Yes | No | USMF only |
| MD | Maryland | Yes | No | USMF only |
| MI | Michigan | Yes | No | USMF only |
| MN | Minnesota | Yes | No | USMF only |
| NDFAR | Fargo North Dakota | Yes | No | USMF only |
| NDGOV | North Dakota Government | Yes | No | USMF only |
| NDRSL | North Dakota Resale | Yes | No | USMF only |
| NDSCHL | North Dakota School | Yes | No | USMF only |
| NJ | New Jersey | Yes | No | USMF only |
| No-Tax | No Tax Codes | Yes | No | USMF only |
| NV | Nevada | Yes | No | USMF only |
| NY | New York | Yes | No | USMF only |
| AP-DOM | Accounts payable Domestic | No | Yes | DEMF only |
| AP-EU | Accounts payable EU | No | Yes | DEMF only |
| AP-THIRD | Accounts payable Third country | No | Yes | DEMF only |
| AR-DOM | Accounts receivable Domestic | No | Yes | DEMF only |
| AR-EU | Accounts receivable EU | No | Yes | DEMF only |
| AR-THIRD | Accounts receivable Third country | No | Yes | DEMF only |