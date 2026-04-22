# Record_To_Report Configuration Plan

## Process Context
- Process: Record_To_Report
- Implementation file: Processes/Implement_Record_To_Report.template.md
- Skill file: .github/skills/record-to-report/SKILL.md
- Target legal entities: USMF, USSE, DEMF, GBMF
- Current status: Baseline plan created for orchestration and handoff

## Objective
Create an implementation-ready execution plan for Record-to-Report in Dynamics 365 Finance while preserving the Project Manager orchestration role. This plan is the work queue for Solution Architect and Solution Consultant agents.

## Implementation Phases

### Phase 1: Requirements Validation
1. Review `Processes/Implement_Record_To_Report.template.md` and confirm the workbook is execution-ready.
2. Validate that all `TBC` items and open questions are identifiable and documented.
3. Confirm whether any additional design decisions are required before configuration.
4. Record readiness status and clarification needs in `Output/Record_To_Report_Implementation_log.md`.

### Phase 2: Process Implementation
1. Verify legal entities exist and confirm USMF as the master legal entity.
2. Configure the shared global chart of accounts (`FAB-GL`) with the six main account ranges.
3. Create financial dimensions: Department, Cost Center, Business Unit, and Project.
4. Apply dimension rules:
   - Department and Cost Center mandatory for P&L accounts
   - Optional for balance sheet accounts
   - Business Unit optional for all accounts
   - Project optional, restricted to approved journal types
5. Configure fiscal calendar and accounting periods:
   - Calendar year (January–December)
   - Periods P01–P12 plus P13 for audit adjustments
   - Period close controls and year-end locking rules
6. Configure security controls:
   - Finance Manager role definition or verification
   - Period reopen permissions restricted to Finance Manager
7. Execute validation scenarios:
   - Legal entity existence and master entity verification
   - P&L transaction with required Department and Cost Center
   - Balance sheet transaction with optional dimensions
   - Project usage on approved journal types
   - Close period and reopen permission validation

### Phase 3: Data Load Readiness
1. Validate readiness for the Main Accounts data load (`MainAccountEntity`).
2. Validate readiness for Financial Dimension Values (`FinancialDimensionValues`).
3. Validate readiness for Exchange Rates load and exchange rate provider setup.
4. Validate readiness for Bank Accounts data load.
5. Validate readiness for Budget Account Entries data load.
6. Validate readiness for Intercompany mapping load (`LedgerInterCompanyAccounts`).
7. Validate readiness for Opening Balance Journal load.

### Phase 4: Finalization
1. Consolidate implementation progress into `Output/Record_To_Report_Implementation_Summary.md`.
2. Ensure dashboard and log reflect current execution state.
3. Document follow-up actions and handoff requirements.

## Dependency Sequence
1. Phase 1 must complete and confirm the workbook is ready.
2. Phase 2 may begin once the Solution Architect returns `GO` for at least one implementation task.
3. Phase 2 tasks are eligible for parallel dispatch up to 5 concurrent Solution Consultant instances.
4. Phase 3 readiness validations may proceed in parallel after the foundational ledger, dimensions, and calendar tasks are confirmed.
5. Phase 4 occurs after all implementation and readiness tasks are either implemented, blocked, or deferred with documented rationale.

## Task Dispatch Rules
- Maximum 5 concurrent Solution Consultant tasks.
- Run the Solution Architect parallel execution dependency check before assigning any new task.
- Do not reassign a task that is already `Currently Being Implemented` unless it has been silent for 15+ minutes.
- Prioritize error retry items first if they become unblocked.

## Known Clarification Questions
- Are all four legal entities already created in the target environment?
- Do the entities use the same or different local currencies?
- Which specific journal types are in scope for Project dimension usage?
- Is period 13 restricted to audit adjustments only?
- Does consolidation/intercompany accounting need to be configured in this phase?
- Are there additional main account ranges needed beyond the six listed?

## Output Deliverables
- `Output/Record_To_Report_Implementation_Dashboard.html`
- `Output/Record_To_Report_02-configuration-plan.md`
- `Output/Record_To_Report_Implementation_log.md`
- `Output/Record_To_Report_Implementation_Summary.md`

## Next Steps
1. Invoke the Solution Architect to validate workbook readiness for `RV-01` and `RV-02`.
2. Once the workbook is ready, begin dispatching Phase 2 tasks through the dashboard.
3. Track all child-agent progress in `Output/Record_To_Report_Implementation_Dashboard.html`.
4. Update the summary and log iteratively as tasks move to `Implemented`, `Error`, or `Currently Being Implemented`.
