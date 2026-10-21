---
name: design-handoff
description: Use when asked to prepare a design handoff, write a spec for engineers, document states and behaviour, or check a build against the design.
---

# Design handoff and QA

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Design handoff spec for engineers

Write the handoff an engineer wishes they got. The picture shows one state; the spec covers all of them.

Design: [design from the person's request]
Stack: [stack from the person's request]

Method:
1. If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Use get_variable_defs to list the tokens in use (colour, type, spacing, radius) and flag any hard-coded values that should be tokens.
2. Write, for each frame or component: purpose in one line; anatomy and layout rules (what stretches, what is fixed, min and max widths, alignment); responsive behaviour at the breakpoints; every state (default, hover, focus, active, disabled, loading, error, empty, selected, long text, no data); and transitions with duration and easing.
3. Content rules: character limits, truncation and wrapping, localisation and right-to-left notes, real examples of the longest and shortest content.
4. Interaction and behaviour: what each control does, keyboard behaviour and order, validation timing, error placement, what is saved when.
5. Accessibility: roles and names for controls, focus management (modals, route changes), live announcements, target sizes, contrast results from check_contrast for each text and component pair, motion alternatives.
6. Analytics: events to fire at each moment (see prompt tracking_plan); call lint_tracking_plan on them.
7. Open questions and assumptions, labelled as such. Do not invent behaviour; ask.
8. Acceptance criteria as testable statements ("Pressing Escape closes the dialog and returns focus to the trigger").
Format as markdown with a heading per component, and keep each section skimmable. End with a list of the five things most likely to be built wrong.

## Design QA: build against the spec

Compare the build to the design and report what matters.

Design: [design from the person's request]
Build: [build from the person's request]
Tolerance: [tolerance from the person's request]

Method:
1. Get the design: If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Record frame sizes, type styles, colours and spacing from get_design_context and get_variable_defs.
2. Get the build: for a live URL call audit_page_accessibility and detect_design_slop; ask for screenshots at the same widths as the frames if you cannot view it.
3. Compare in this order, which is the order of impact: content and copy (missing, truncated, wrong), structure and hierarchy, states (hover, focus, error, empty, loading, disabled), colour and contrast (call check_contrast on build colours), typography (family, size, weight, line height), spacing and alignment, responsive behaviour, motion, accessibility (names, focus, keyboard).
4. Ignore differences inside the tolerance. Distinguish defects from deliberate engineering adaptations; ask when unsure.
5. Output a table: area, expected (value from design), actual (value from build), effect on the person, severity (blocker, major, minor, cosmetic), proposed fix, owner (design or engineering). Group blockers first. End with the three issues to fix before release and what you could not compare (states or widths not provided).

## Tools used

- check_contrast
- check_touch_targets
- lint_tracking_plan
- audit_page_accessibility
