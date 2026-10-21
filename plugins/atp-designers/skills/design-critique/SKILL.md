---
name: design-critique
description: Use when asked to critique, review, give feedback on or evaluate a design, mockup, screen or Figma frame, or to compare two design options. Frames the critique by stage and gives observations with impact instead of taste.
---

# Design critique

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Design critique for the stage the work is in

Run a design critique as a senior design lead would: specific, kind to the maker, hard on the work, and aware of the stage.

Design: [design from the person's request]
Stage: [stage from the person's request]
Goal and audience: [goal from the person's request]
Feedback wanted: [focus from the person's request]

Method:
1. Read the stage rubric: the file references/critique-rubric.md. Note what feedback to refuse at this stage and say so once, briefly, if you park any.
2. Look at the design. If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file.
3. Call plan_critique with the description and stage if the person wants a session plan for a team; otherwise skip it.
4. State what is working first, with reasons, so it survives the redesign. Name two or three specific strengths, not "nice layout".
5. Write findings as observation, impact, optional direction. Each names the part of the design (frame and element), says what you see, says what it does for the person using it or for the goal, and offers a direction to try, not an instruction. Where a check is objective, run the tool and cite it: check_contrast for colour pairs, review_ui_copy for strings, detect_design_slop for a live page.
6. Run lint_design_feedback on your own findings and rewrite any it flags as vague, opinion or solution-without-problem.
7. Finish with: the three changes most likely to improve the work, ordered; two questions the designer should answer before the next stage; what you could not judge from what you were given (states not shown, real content, devices).
Never say "make it pop", "clean" or "modern". Do not give taste as fact. Keep it under 700 words unless asked for more.

## Compare two designs honestly

Compare two designs against a goal and choose one. Do not flatter. A comparison that finds both fine has not looked hard enough.

Option A: [option a from the person's request]
Option B: [option b from the person's request]
Goal: [goal from the person's request]

Rules: you must name a winner for this goal, or say plainly that evidence is missing and what would settle it. You must find at least two real problems in each option, and one thing each does better than the other. No praise without a reason.
1. Get both designs. If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. For two live URLs call detect_design_slop and audit_page_accessibility with compareUrl to get an evidence-based delta.
2. Score each on the goal's criteria (say what they are, usually: clarity of the main action, hierarchy, trust, accessibility, fit with the brand, effort to build). For objective criteria use the tools: check_contrast on key pairs, review_ui_copy on strings, check_touch_targets on controls.
3. Write: a table of criteria with a winner and a one-line reason for each; the overall pick and the single biggest reason; the problems in each option; what would change your mind; one change to the winner that borrows the best idea from the loser.
4. State what you could not see (states, devices, real content) and how that could flip the result.

## Tools used

- plan_critique
- lint_design_feedback
- check_contrast
- review_ui_copy
- detect_design_slop
