# atp-plugins

A Claude Code plugin marketplace for the MCP servers built by [All the Possibles](https://allthepossibles.com). Every server is a remote Streamable HTTP endpoint, and the free tier needs no account or key.

## Install

Add the marketplace once:

```
/plugin marketplace add johnhowrey/atp-plugins
```

Then install the bundle, which wires up all five servers and both skills:

```
/plugin install all-the-possibles@atp-plugins
```

For designers working with AI (thirteen skills and the Designers server; start with the start-here skill):

```
/plugin install atp-designers@atp-plugins
```

Or install a single product:

```
/plugin install preflight@atp-plugins
/plugin install design-check@atp-plugins
/plugin install pulse@atp-plugins
/plugin install verdict@atp-plugins
/plugin install toolbox@atp-plugins
```

Run `/reload-plugins` after installing, then `/mcp` to confirm the servers are connected. From a shell, the same commands work as `claude plugin marketplace add johnhowrey/atp-plugins` and `claude plugin install preflight@atp-plugins`.

## Servers and tools

| Plugin | Product | Endpoint | Tools |
| --- | --- | --- | --- |
| `preflight` | Preflight | `https://preflight.allthepossibles.com/mcp` | scan_mcp_server, scan_content, scan_extension, check_output |
| `design-check` | Design Check | `https://designcheck.allthepossibles.com/mcp` | check_design, check_copy, check_code |
| `pulse` | Pulse | `https://pulse.allthepossibles.com/mcp` | check_vitals |
| `verdict` | Verdict | `https://verdict.allthepossibles.com/mcp` | critique_experience, generate_state_matrix, map_journey, audit_copy, find_assumptions, check_terminology |
| `toolbox` | Toolbox | `https://toolbox.allthepossibles.com/mcp` | check_tells, manifest_cost, lint_agent_md, mcp_install_snippets, check_ai_crawlers, check_headers, check_page_meta, json_to_schema, explain_cron, scrub_env, trace_redirects, check_sitemap, decode_jwt |

## Skills

The `preflight` plugin ships `scan-before-adding-mcp`. It tells Claude to scan any MCP endpoint with Preflight before suggesting you add it, and to report the verdict and the high severity findings.

The `toolbox` plugin ships `pre-publish-checks`. It runs `check_tells` on drafted copy, `check_headers` and `check_page_meta` on a URL you are about to ship, and `lint_agent_md` after edits to `CLAUDE.md`.

The `all-the-possibles` bundle includes both skills.

## Limits and keys

Preflight allows 10 scans a day per IP address on the free tier. A Pro key raises the limits and enables semantic prompt-injection detection. To use one, add a header to the server entry in your own settings: `"headers": {"Authorization": "Bearer pf_..."}`.

## Validate

```
claude plugin validate .
```

## License

MIT.
