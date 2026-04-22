# Record-to-Report Implementation Discovery Workbook

## Title and Preamble

This workbook captures the Record-to-Report (R2R) discovery decisions from the provided transcript and prepares the implementation plan for Dynamics 365 Finance configuration.

It is intended for consultants and automation agents to use as the authoritative source for setup, data migration, validation, and build execution.

---

## Process Context

This workbook covers the Record-to-Report process for a global finance deployment with two legal entities:
- USMF — United States (master legal entity)
- DEMF — Germany

**Scope Adjustment:** USSE and GBMF do not exist in the target environment and have been removed from scope. Implementation will proceed with USMF and DEMF only.

The focus is on a shared global chart of accounts, financial dimensions, fiscal calendar management, and period control for month-end and audit adjustments.

---

## Configuration Summary

Key implementation decisions derived from the transcript:

- Legal entity scope: USMF, DEMF (USSE and GBMF removed — do not exist in target environment)
- Master legal entity: USMF
- Global chart of accounts: **Shared** 6-digit structure used across all legal entities
- Main account structure: 6-digit (e.g., 110101, 110110, 120100) — **adjusted from original 7-digit design**
- Legal entities (USMF, DEMF) use the existing **Shared** chart of accounts
- Account types: BalanceSheet, Total, and other standard types supported
- Financial dimensions:
  - Department
  - Cost Center
  - Business Unit
  - Project (internal capital tracking only)
- Dimension rules:
  - Department and Cost Center mandatory for all P&L accounts
  - Optional for balance sheet accounts
  - Business Unit optional for all accounts
  - Project optional and restricted to specific journal types
- Fiscal calendar: Calendar year, January–December
- Accounting periods: 12 normal periods plus period 13 for audit adjustments
- Period reopen control: reopen only by Finance Manager role

Areas not yet confirmed or outside transcript coverage remain marked as `TBC`.

---

## Data Import Plan

Data entities and master data to prepare for the Record-to-Report build:

- Legal entities (companies) and address information
- Chart of accounts (main account master data)
- Financial dimensions and dimension values:
  - Department
  - Cost Center
  - Business Unit
  - Project
- Fiscal calendar and ledger calendar
- Periods and year-end adjustment period
- Security roles for period reopen control

Data import should use the standard D365 Finance entities for General ledger, Ledger chart of accounts, and Financial dimensions.

---

## How to Use This Workbook

1. Review the transcript evidence summary and confirm decisions with the business.
2. Use the configuration summary to validate scope before starting setup.
3. Populate any `TBC` answers with confirmed design decisions.
4. **Validation Mode**: Inspect existing D365 Finance configuration for R2R readiness (read-only; no modifications).
5. Use the validation scenarios to confirm the R2R process behavior against existing setup.
6. Track any remaining open items in the Open Items and Clarifications section.

---

## Company Profile and Scope

- Company name: Fabrikam Industrial Services (fictional)
- Primary process: Record-to-Report
- Legal entities in scope: USMF, DEMF
- Master legal entity: USMF
- Implementation coverage: Global chart of accounts, financial dimensions, fiscal calendar, period control, and security for period reopen

Scope markers:
- `In scope`: Ledger foundation, chart of accounts, dimensions, period management, legal entity alignment
- `Out of scope / TBC`: Tax setup, fixed assets, electronic reporting, statutory reporting requirements, intercompany posting rules, multiple charts of accounts

---

## Detailed Configuration Guidance and Discovery Questions

### 1. Legal Entities

- ✅ Verified: USMF and DEMF exist in the target environment.
- ✅ Verified: USMF is designated as the master legal entity.
- Confirm currency and statutory settings by legal entity if required.
- Note: USSE and GBMF were in the original scope but do not exist in the environment and have been removed.

Discovery questions:
1. Do USMF and DEMF use the same currency or local currencies?
2. Does USMF need to be configured as the primary financial reporting legal entity for consolidation?

### 2. Chart of Accounts

- ✅ Verified: Existing 6-digit main account structure is in use (e.g., 110101, 110110, 120100).
- ✅ Verified: "Shared" chart of accounts is available for use across legal entities.
- ✅ Decision: Adopt existing 6-digit structure; design from transcript adjusted from 7-digit to match environment standard.
- Confirm whether any natural account segments or analytics segments are required beyond the current structure.
- Note: Original design specified 7-digit accounts (1000000–1999999 ranges), but environment uses 6-digit structure. Use "Shared" chart for USMF and DEMF.

Discovery questions:
1. Should USMF and DEMF share the existing "Shared" chart of accounts, or use separate charts?
2. Will any account combination rules be needed to prevent invalid account/dimension combinations?

### 3. Financial Dimensions

- Create the following financial dimensions:
  - Department
  - Cost Center
  - Business Unit
  - Project
- Configure dimension rules:
  - Department and Cost Center mandatory for P&L accounts
  - Optional for balance sheet accounts
  - Business Unit optional everywhere
  - Project optional, only for specific journal types

Discovery questions:
1. Which specific journal types are in scope for Project dimension usage?
2. Are Department and Cost Center mandatory on all journals that post to P&L, including accrual and depreciation journals?

### 4. Fiscal Calendar and Period Management

- Configure a calendar fiscal year from January to December.
- Create 12 normal accounting periods and period 13 for audit adjustments.
- Configure period control and closing rules.
- Assign Finance Manager role the permission to reopen closed periods.

Discovery questions:
1. What is the naming convention for accounting periods and fiscal years?
2. Should period 13 be restricted to audit adjustments only, or can it also be used for other year-end corrections?

### 5. Security and Controls

- Define or verify the `Finance Manager` role.
- Restrict period reopen permissions to this role.
- Confirm whether any other roles require special access for period close approval or journal posting.

Discovery questions:
1. Which users or roles must be assigned the ability to reopen closed periods?
2. Are there any separate workflow approvals required for year-end adjustment journals?

### 6. Additional R2R Considerations

The transcript does not provide explicit decisions for the following areas. Keep these as `TBC` until confirmed.

- Tax configuration and statutory reporting by legal entity
- Fixed asset posting and capitalization rules
- Intercompany accounting and elimination dimensions
- Consolidation requirements and reporting entity mappings
- Budgeting or forecast integration

---

## Validation Scenarios

1. Verify legal entities USMF, USSE, DEMF, GBMF exist and are active.
2. Confirm the global chart of accounts is configured with 7-digit main accounts and the six ranges.
3. Create a sample P&L transaction and confirm Department and Cost Center are required.
4. Create a sample balance sheet transaction and confirm Department and Cost Center are optional.
5. Create a sample journal using Project dimension and confirm it is allowed only on the approved journal type(s).
6. Close a period and verify only a Finance Manager role user can reopen it.
7. Confirm period 13 exists and can be used for audit adjustment postings.

---

## Risks and Dependencies

- Missing legal entity currency and statutory setup may delay legal reporting configuration.
- If chart of accounts range definitions change later, reconfiguration may require mapping and conversion effort.
- Lack of explicit tax and fixed asset decisions may leave the workbook incomplete for full R2R deployment.
- Period reopen control is dependent on security role definitions in the target environment.

---

## Open Items and Clarifications

1. ✅ **RESOLVED**: Legal entity scope adjusted to USMF and DEMF (existing entities); USSE and GBMF removed.
2. Confirm legal entity currencies and local statutory requirements for USMF and DEMF.
3. Confirm the journal types that may use the Project dimension.
4. Confirm whether any additional main account ranges are required beyond the six ranges listed.
5. Confirm whether period 13 is solely for audit adjustments or also year-end closing entries.
6. Confirm whether consolidation or intercompany accounting is required for USMF and DEMF.

---

## Agent Handoff Payload

```yaml
record_to_report:
  legal_entities:
    - USMF
    - DEMF
  master_legal_entity: USMF
  chart_of_accounts:
    structure: "Shared 6-digit (adapted from original 7-digit design)"
    chart_name: "Shared"
    example_accounts:
      - "110101: Cash Advance Returns"
      - "110110: Bank Account - USD"
      - "120100: Bonds"
  financial_dimensions:
    - Department
    - Cost Center
    - Business Unit
    - Project
  dimension_rules:
    department_cost_center: "Mandatory for P&L accounts, optional for balance sheet accounts"
    business_unit: "Optional"
    project: "Optional, specific journal types only"
  fiscal_calendar:
    year_type: "Calendar fiscal year"
    periods: "12 periods + period 13"
  period_reopen_role: "Finance Manager"
```

---

## Reference Documentation

- Microsoft Business Process Catalog — Record-to-Report process overview
- Microsoft Learn — Dynamics 365 Finance general ledger setup
- Microsoft Learn — Financial dimensions setup
- Microsoft Learn — Ledger periods and fiscal calendars

---

## Transcript Evidence Summary

- Files reviewed:
  - `Sample/Transcripts/Record _To_Report/Record_To_Report_Transcript.md`
- Process areas covered:
  - Legal entity scope (verified and adjusted)
  - Global chart of accounts design
  - Financial dimensions
  - Fiscal calendar and period management
  - Period reopen controls
- Confidence level: High
  - Legal entities verified in target environment
  - Core R2R ledger foundation decisions explicit
  - Scope adjusted to match environment readiness
- Status: 
  - PI-01 (Legal Entity Verification) — ✅ Complete
  - PI-02 (Chart of Accounts Validation) — ✅ Complete
    - **Design Alignment**: Original transcript specified 7-digit accounts (1000000–1999999 ranges). Environment uses 6-digit structure. Adopted existing 6-digit approach using the **Shared** chart of accounts for USMF and DEMF. Decision reduces implementation complexity.
