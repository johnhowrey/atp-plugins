---
name: pre-publish-checks
description: Run Toolbox checks before work ships. Use when the user drafts public copy, is about to publish a URL, or when you edit CLAUDE.md or other agent instruction files.
---

# Pre-publish checks

Run these Toolbox checks at the moment work is about to leave the user's machine. Run the ones that apply and skip the rest.

## Drafted copy

When you have written or revised copy that will be published (a README, a post, a landing page, a reply), pass the text to `check_tells`. Fix the flagged phrases and run it again until it returns clean, then show the user the final text.

## A URL about to ship

When the user is about to deploy or announce a URL, call `check_headers` and `check_page_meta` on it. Summarise missing security headers, caching problems, absent titles or descriptions, and broken social card tags. Put the findings that block launch first.

## Agent instruction files

After you edit `CLAUDE.md`, `AGENTS.md` or a similar file, pass its full contents to `lint_agent_md`. Apply the fixes that do not change the author's intent, and ask about the rest.

## Reporting

Keep the report short: what you ran, what failed, what you fixed. If a tool is unreachable, say that the check did not run rather than implying the work passed.
