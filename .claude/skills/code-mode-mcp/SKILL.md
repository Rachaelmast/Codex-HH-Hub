---
name: code-mode-mcp
description: Code Mode for MCP. Use when a task touches MCP servers with large data, polling, bulk actions, or candidate contact info (names, emails, phones). Best for job scans against the tracker, candidate-to-job matching across big lists, bulk outreach, and recurring reports. Skip for one-off questions or small tasks on one or two tools.
---

# Code Mode for MCP
Apply this whenever a task touches MCP servers, large data, polling, or candidate contact info.

MCP servers: Gmail, Google Drive, Google Docs, Google Sheets, Google Slides, Microsoft 365, Cloudflare (plus any others connected in the session).
Private fields: candidate names, emails, phone numbers.

01 TOOLS AS FILES
Generate ./servers/<server>/<tool>.ts for every tool in the connected MCP servers.
Each file: typed input, typed output, one callMCPTool() call.

02 LOAD ON DEMAND
Never load every definition. List ./servers, open only what the task needs.
Add search_tools(query, detail: name | description | full schema).

03 FILTER IN CODE
Filter, join, and count tool results inside the sandbox.
Log a count and at most 5 rows back to the model, never the raw dump.

04 LOOPS IN CODE
Write polling, retries, and branches as code that runs on its own.
No tool call + sleep round trips through the model.

05 PRIVATE BY DEFAULT
The client swaps private fields for [EMAIL_1], [PHONE_1], [NAME_1] tokens.
Real values go tool to tool. The model only ever sees the tokens.

06 SKILLS
Save working code to ./skills/<name>.ts with a SKILL.md next to it.
Run all generated code in a sandbox with time and memory limits.

## Best fits
Job scans against the tracker, candidate-to-job matching across big lists, bulk outreach, recurring reports, and anything touching candidate contact info.
Skip this mode for one-off questions or small tasks on one or two tools.
