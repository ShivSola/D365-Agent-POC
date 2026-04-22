# D365 Configuration Agent — POC

AI-powered Dynamics 365 Finance & Operations implementation and configuration tool using GitHub Copilot + MCP connected to a live F&O environment.

## Inspired By

- [ScottMGaines/D365-Configuration-Agent](https://github.com/ScottMGaines/D365-Configuration-Agent) — agent framework for F&O implementation planning
- [Ted Ohlsson — Finding Configuration Diffs in D365 F&O with AI](https://medium.com/@ted.ohlsson/finding-configuration-diffs-in-dynamics-36-f-o-with-ai-7502a107b7b1) — config diff approach between environments and legal entities

---

## 1. First-Time Setup After Install

### Step 1: Configure the Dynamics 365 MCP server URL

Copy `.vscode/mcp.sample.json` to `.vscode/mcp.json` and update the URL to point to your F&O environment:

```json
{
  "servers": {
    "microsoftdocs/mcp": {
      "type": "http",
      "url": "https://learn.microsoft.com/api/mcp"
    },
    "dynamics365": {
      "type": "http",
      "url": "https://YOUR-ENVIRONMENT.sandbox.operations.dynamics.com/mcp",
      "authorization": {
        "type": "vscode",
        "providerId": "microsoft",
        "scopes": ["https://YOUR-ENVIRONMENT.sandbox.operations.dynamics.com/.default"]
      }
    }
  },
  "inputs": []
}
```

> `.vscode/mcp.json` is gitignored — never commit your real environment URL.

### Step 2: Enable MCP support in Dynamics 365

In your F&O environment, search for `MCP` in Feature Management and enable the Copilot/Chat MCP feature flag. Then go to **System Administration → Allowed MCP Clients** and add your VS Code client ID.

### Step 3: Verify connection

In GitHub Copilot agent chat, type:
> *"List the available MCP tools"*

You should see the dynamics365 server listed with 21 tools discovered.

---

## 2. Working Folders

| Folder | Purpose |
|--------|---------|
| `Transcripts/` | Discovery input files — meeting transcripts, notes, requirements |
| `Processes/` | Generated process implementation markdown workbooks |
| `Output/` | Generated deliverables — dashboards, logs, summaries, diff reports |
| `Sample/` | Reference examples only — do not add your work here |
| `.github/agents/` | Agent instruction files — Project Manager, Solution Architect, Solution Consultant |
| `.github/prompts/` | Prompt files — Process Markdown, Config Diff |
| `Microsoft BPC/` | Microsoft Business Process Catalog — reference for all F&O processes |

---

## 3. Main Workflow

### Workflow A: Implementation Planning (Scott's approach)

#### Step 1: Generate the process workbook

Add a transcript or requirements document to `Transcripts/` then ask the agent:
> *"Run the Process Markdown prompt using the transcript file Transcripts/[filename]"*

Output target: `Processes/Implement_<Process>.template.md`

#### Step 2: Review and adjust the workbook

Open the generated file in `Processes/` and confirm or adjust any business and configuration decisions before implementation starts. Fill in any `TBC` placeholders.

#### Step 3: Switch to Project Manager agent

Once the workbook is ready, ask the agent:
> *"Switch to the Project Manager agent and execute the process workbook Processes/[filename]"*

The Project Manager orchestrates execution by delegating to:
- **Solution Architect** — validates workbook completeness and design assumptions
- **Solution Consultant** — executes configuration tasks against the live F&O environment

Output: an HTML dashboard in `Output/` tracking all implementation tasks with status.

---

### Workflow B: Configuration Diff (Ted's approach)

Compare configuration between two legal entities or two environments to identify gaps.

Ask the agent:
> *"Compare the configuration of legal entity USMF vs DEMF in my F&O environment. Check Vendor Groups, Customer Groups, Payment Terms, Main Accounts and Tax Groups. Output to Output/[EntityA]_vs_[EntityB]_Config_Diff.xlsx"*

Output: an Excel diff report showing what exists in one entity but not the other, with gap flagging and alignment percentage per config area.

---

## 4. What Was Done in This POC

| # | Activity | Output |
|---|----------|--------|
| 1 | Connected GitHub Copilot to F&O sandbox via MCP | 21 tools discovered, 25 legal entities retrieved |
| 2 | Ran Record-to-Report process end-to-end | `Output/Record_To_Report_Implementation_Dashboard.html` |
| 3 | Generated 16-task implementation plan | `Output/Record_To_Report_02-configuration-plan.md` |
| 4 | Validated live F&O — confirmed USMF and DEMF exist | PI-01 completed, USSE and GBMF flagged as missing |
| 5 | Ran config diff between USMF and DEMF legal entities | `Output/USMF_vs_DEMF_Config_Diff.xlsx` |

---

## 5. Practical Notes

- The Project Manager agent generates and updates an HTML dashboard throughout execution to track progress.
- Always verify legal entity context before any configuration activity.
- Use `Output/` as the active destination for all generated deliverables.
- Data import execution remains manual — agents prepare configuration and data-load readiness but do not execute bulk data loads.
- Tokens expire after ~1 hour when using Bearer token auth — refresh with `az account get-access-token` if needed.
- Always test in sandbox before pointing agents at a live production environment.