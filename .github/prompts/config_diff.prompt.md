# Config Diff Prompt

Compare the configuration between two legal entities in F&O using the dynamics365 MCP server.

For each configuration area (Vendor Groups, Customer Groups, Payment Terms, 
Tax Groups, Main Accounts), query both legal entities and compare results.

Output an Excel file to Output/[EntityA]_vs_[EntityB]_Config_Diff.xlsx with:
- A Summary sheet showing total items, both, entity A only, entity B only, gap count, alignment %
- One sheet per configuration area
- Columns: Code/ID | Description | [EntityA] ✓ | [EntityB] ✓ | Status | Action
- Color coding: green rows for both, yellow for gaps, checkmarks ✓ for present, — for missing
- Frozen headers on each sheet
- Action column flagging gaps with "Consider adding to [Entity]"