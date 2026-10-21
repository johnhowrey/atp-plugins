---
name: ux-heuristics
description: Use when asked for a heuristic evaluation, usability review, UX audit or expert review of a flow, or to evaluate a design against Nielsen's ten heuristics. Walks one task and records findings with 0 to 4 severity.
---

# Nielsen heuristic evaluation

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Nielsen heuristic evaluation of a flow

Do a heuristic evaluation. It is a human-style judgement method: you walk a task and record problems. The tool gives signals; the findings are yours.

Flow: [flow from the person's request]
Task: [task from the person's request]
Person doing it: [audience from the person's request]

Method:
1. Read the file references/nielsen-heuristics.md for the heuristics, the walkthrough method and the severity scale.
2. Get the flow. If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. For a live URL, also call audit_page_accessibility and heuristic_worksheet with the url and task to collect signals.
3. Write the task as a list of steps a person takes. At each step note what they are trying to do, what they see, what they will do next.
4. For each problem write: step, what happens, heuristic number and name, effect on the person, severity 0 to 4 (rate after you have the full list, using frequency, difficulty to get past, and cost of failure), fix direction. Only record what would plausibly hurt a real person in this task. Do not log taste.
5. Run heuristic_worksheet with the flow's copy and the task to check you did not miss a heuristic that its signals point at; add findings only if you agree.
6. Output a table sorted by severity, then three sentences: the top three issues, one thing that works, and what a real evaluator would still need to test (states and devices you did not see). Say plainly that one evaluator finds roughly a third of problems and recommend two more independent passes.
If you have Pro, you can feed the findings to build_heuristic_report for a scored, exportable markdown report.

## Tools used

- heuristic_worksheet
- audit_page_accessibility
