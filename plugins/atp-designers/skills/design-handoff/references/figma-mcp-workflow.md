# Working with a Figma link: the Figma MCP plus these tools

When the person gives you a Figma link, read the design before you judge it. The Figma MCP server gives you the file; this server gives you the checks models do badly.

## Step 1: read the design
1. Parse the link: figma.com/design/:fileKey/... with node-id=1-2 means nodeId "1:2" (replace hyphen with colon).
2. get_metadata for the structure: frames, names, sizes. Use it to find the frames for the flow, in order.
3. get_screenshot for each frame you will judge. Look at the picture first; most problems are visible.
4. get_design_context for the frame to get layout, text and token usage. Treat its code as a reference to read, not output to ship.
5. get_variable_defs when you audit tokens or contrast: it returns the variables (colours, spacing, type) in use.

## Step 2: hand exact values to the checkers
- Colour pairs: take text fill and the background it sits on from get_design_context or get_variable_defs, then call check_contrast with sizePx and bold from the text style. Do not estimate contrast by eye; models get it wrong.
- Palette: pass the colour variables to check_contrast as a palette to find colours that merge under colour blindness.
- Copy: collect every text layer, one per line with its role (button:, error:, empty:, tooltip:), and call review_ui_copy.
- Heuristics: describe the flow in order, with the copy on each frame, and call heuristic_worksheet with the task; do the evaluation yourself using the worksheet and the Nielsen resource.
- Live site next to the design: call audit_page_accessibility and detect_design_slop on the URL.

## Step 3: report
Group findings by frame, then severity. Each finding has: frame name (and node id so the person can jump to it), what you see, the heuristic or WCAG criterion, the effect on the person, and a fix direction. Do not edit the Figma file unless asked. If you could not read something (a frame that did not render, a missing variable), say so and do not guess.

## Limits to state
A screenshot is one state. Say which states you did not see (hover, focus, error, empty, loading, small screen, long text). Static contrast ignores text on images and gradients; flag those for a manual check.
