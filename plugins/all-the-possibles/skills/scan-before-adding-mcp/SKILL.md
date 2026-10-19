---
name: scan-before-adding-mcp
description: Run Preflight on any MCP server endpoint before suggesting the user add it to their configuration. Use whenever you are about to recommend, install or configure a remote MCP server.
---

# Scan before adding an MCP server

Before you suggest that the user add an MCP server, scan its endpoint with Preflight. This applies to any remote server URL, whether the user supplied it or you found it yourself.

## Steps

1. Call the `scan_mcp_server` tool from the Preflight server with the endpoint as `url`. Pass the Streamable HTTP endpoint, which usually ends in `/mcp`.
2. Read the `verdict` in the result. It is one of `clear`, `caution` or `high-risk`.
3. Report the verdict first, in one sentence.
4. List every finding with severity `high` (and `critical`, if present). Give each one's title, the tool it names, and what the detail says in your own words.
5. Mention medium findings only as a count, unless the user asks for them. An unauthenticated transport is common and is not a reason to refuse by itself.

## What to recommend

If the verdict is `clear`, say so and go ahead with the install instructions. If it is `caution`, show the findings and let the user decide. If it is `high-risk`, do not give install instructions until the user has read the high findings and confirmed they want to proceed.

If the scan fails because the server is unreachable or the free tier limit of 10 scans a day was reached, say that plainly and tell the user the server was not checked. Do not describe an unscanned server as safe.
