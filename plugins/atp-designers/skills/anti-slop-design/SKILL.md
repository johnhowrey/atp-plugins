---
name: anti-slop-design
description: Use when a design or page looks generic or AI-generated, when asked to make it more distinctive, to check for AI design tells, or when briefing a model to build UI without the default look.
---

# Anti-slop design review

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## AI design and writing slop review

Review this for the default generated look and voice, and say what would make it distinctive. Be specific and fair: one tell is a style; a cluster with no counterweight is a template.

Target: [target from the person's request]

Method:
1. Read the file references/slop-tells.md.
2. For a live URL call detect_design_slop; for text pass it through review_ui_copy or the Toolbox check_tells tool if available.
3. For a Figma design: If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Judge the picture against the design tells (type, colour, layout, components, imagery, motion, content).
4. List the tells you found with evidence (the selector, the value, the frame), grouped under type, colour, layout, components, imagery, copy. Note what is already distinctive; do not flatten it.
5. Give a plan: for each cluster, a specific alternative that fits this product (name a type pairing, a dominant colour with an accent and neutrals, a deliberate grid break, real photography or product screenshots, copy that says the specific thing). Avoid replacing one default with another: no "swap Inter for Poppins".
6. Close with the one or two bold moves that would change the page most, and the ones to leave alone.

## Tools used

- detect_design_slop
- review_ui_copy
