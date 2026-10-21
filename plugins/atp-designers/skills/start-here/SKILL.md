---
name: start-here
description: Use when someone asks what these design skills or the Designers server can do, says they are new or confused, or asks for help with design but does not say which kind. Asks what they have and routes them to the right skill, prompt or tool.
---

# Start here: find the right design skill

Connect the Designers server once and every skill here can do exact checks (colour contrast maths, page accessibility audits, slop signals, lint for feedback, research questions and tracking plans). The skills still work without it, by reasoning, but the numbers will not be machine-verified.

To connect: the address is https://designers.allthepossibles.com/mcp. In Claude Code run: claude mcp add --transport http designers https://designers.allthepossibles.com/mcp . For Claude Desktop, claude.ai, Cursor, VS Code, Codex and ChatGPT see https://designers.allthepossibles.com/docs/install . If something does not work, call the doctor tool or read https://designers.allthepossibles.com/docs/troubleshooting .

Plain-language terms for newcomers: an MCP server is an add-on that gives the assistant extra abilities and is connected with one web address; a tool is one ability (check this colour pair); a prompt is a saved set of expert instructions; a skill is a folder of expert instructions the assistant loads by itself when a request matches.

## Getting started: what can this server do for me?

The person is new to the Designers MCP server. Explain it in plain language and help them start. Do not assume they know what MCP, a tool or a prompt is.

What they have: [have from the person's request]

1. In three short sentences say what this server is: a set of checks and expert instructions that let you (the AI assistant) review design work properly. It does the exact things models are bad at (colour contrast maths, reading a live page for accessibility problems, spotting generic AI-made design and writing) and gives you the method that a senior design lead would use for critiques, heuristic reviews, research and handoff.
2. Call whoami to show their tier and how many calls they have left today, in one line.
3. Suggest exactly three first tasks that fit what they have. Pick from:
   - Figma link: an accessibility review of the frame (prompt accessibility_review), a critique for the stage the work is in (prompt critique), a heuristic evaluation of a flow (prompt heuristic_evaluation).
   - Live URL: accessibility check (audit_page_accessibility), design slop check (detect_design_slop), heuristic review (prompt heuristic_evaluation).
   - Copy or UI strings: microcopy review (review_ui_copy, prompt microcopy_review).
   - Research idea or draft questions: prompt research_plan, then lint_research_questions on the guide.
   - Event list or analytics plan: lint_tracking_plan, or prompt tracking_plan for a new product.
   - Nothing yet: ask what they are designing and at what stage, then use plan_critique to plan a review.
4. For each task, give the one-line request they can paste next, with their own details filled in where you know them.
5. Mention in one sentence that some deeper prompts, site-wide crawls and scored reports need Pro ($5 a month, 7-day trial) and which free task covers the same ground at smaller scale. Do not push it.
Keep the whole reply under 250 words. End by asking which of the three they want to start with.

## Tools used

- getting_started
- whoami
- doctor
