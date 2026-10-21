---
name: design-md
description: Use when asked to create, write or review a DESIGN.md, design context file, brand or style guide for AI to follow, or to capture a product's look and voice so models stop producing generic output.
---

# DESIGN.md generator and checker

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Create or check a DESIGN.md

Create or improve a DESIGN.md: the file that tells a model how this product looks and sounds before it builds anything.

Source: [source from the person's request]
Existing file: [existing from the person's request]

1. Read the file references/design-md.md for the structure and the file references/slop-tells.md for what generic output looks like.
2. If an existing DESIGN.md was given, call lint_design_md on it and fix what it flags. Otherwise gather facts: for a live URL read its CSS values (colours, fonts, spacing) with detect_design_slop and audit_page_accessibility for what they show; for Figma If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. then call get_variable_defs for tokens. Never guess a value you can read.
3. Ask the person up to five short questions you cannot infer: who uses it and in what state of mind, three words for the feel and two it must not feel like, the one thing the design must never do, a screen they think is right and one that is wrong.
4. Write the DESIGN.md from the template with real values: hex colours with roles, typefaces with fallbacks and a scale, spacing unit and layout rule, component rules with states, a never-list of specific defaults to reject, and references. Check every text and background pair with check_contrast and fix failures.
5. Call lint_design_md on the result and fix any high or medium finding. Keep it under 1,500 words.
6. Tell the person where to save it (the project root as DESIGN.md) and how to use it ("read DESIGN.md before any UI work"). With Pro, offer to store it with save_project_context.

## Tools used

- lint_design_md
- check_contrast
- lint_token_names
