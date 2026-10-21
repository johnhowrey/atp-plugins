---
name: design-system-audit
description: Use when asked to audit a design system, review design tokens, check token naming or colour tokens for contrast, find duplicates or drift, or plan system improvements.
---

# Design system and token audit

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Design token and colour audit

Audit these design tokens.

Source: [source from the person's request]

Method:
1. If a Figma link: If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Call get_variable_defs for the collection and modes. If tokens are pasted, parse them.
2. Naming: are tokens semantic (color.text.primary, color.surface.raised) over literal (blue-500) at the component layer, with a primitive layer beneath? List tokens named by value or by location.
3. Duplication: find near-duplicate colours (within about 3 percent), sizes that differ by 1px, spacing off the base unit. Propose merges.
4. Scale: spacing on a 4 or 8 base, type on a ratio, radius from a short set.
5. Contrast: pair every text colour with every background colour it can sit on. Call check_contrast with pairs and the palette. Use check_contrast_tokens to run the whole matrix in one call (free up to about 30 colours, Pro for 200). Report failing pairs (4.5:1 text, 3:1 large text and components) with the nearest passing colour, and colour pairs that merge under colour blindness.
6. Modes: light and dark as value sets over the same semantic names, with contrast checked in each.
Output: a short scorecard (naming, coverage, scale, contrast, modes) with evidence, a table of proposed merges and renames, the failing pairs with fixes, and the ten highest-impact changes.

## Design system audit chain

Audit this design system for adoption and correct reuse, not completeness.

System: [system from the person's request]
Consumers: [products from the person's request]

Read the file references/design-system-audit-checklist.md and follow its six sections in order. Work as a chain; finish each step before the next, and keep a running findings list.
Step 1 inventory: If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Use get_metadata to list pages, components and variants; get_variable_defs for tokens. Count components, variants and states; list the unused and the duplicated.
Step 2 tokens: run the prompt token_audit logic and call check_contrast_tokens on the token set for the full contrast matrix and lint_token_names for the names and colour-blind merge check.
Step 3 components: sample the ten most used. For each, check states, accessible name and keyboard behaviour on paper, target size, content rules, and parity with code if the repo is available. Use get_design_context on a few.
Step 4 accessibility: run check_contrast on component states (focus ring, error, disabled) and note which components lack accessible defaults.
Step 5 adoption: ask the person for two or three consuming teams and why they work around the system; if you can see a live product call detect_design_slop and audit_page_accessibility on it to compare against the system.
Step 6 governance: ask or infer ownership, contribution path, releases, deprecation.
Output: a scorecard (foundations, tokens, components, accessibility, documentation, adoption, governance, each 0 to 4 with one line of evidence), a top-ten fix list ordered by impact and effort, a 30-60-90 day plan, and a list of what you could not verify. Be specific enough that a team could start Monday.

## Tools used

- check_contrast_tokens
- lint_token_names
- check_contrast
