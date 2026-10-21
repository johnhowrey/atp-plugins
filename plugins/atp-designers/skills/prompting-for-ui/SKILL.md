---
name: prompting-for-ui
description: Use when asked to write a design brief or prompt for a UI generator or coding agent (Figma Make, v0, Stitch, Lovable, Claude), or to get a model to design something without the generic template look.
---

# Prompting for UI generation

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Brief a model to design UI without the slop

Write a design brief that another model can build a screen from without defaulting to the generic template. Then, if the person agrees, build it.

Idea: [idea from the person's request]
References: [references from the person's request]
Stack: [stack from the person's request]
Generator: [tool from the person's request]

Read the file references/slop-tells.md first. A model told "clean and modern" produces the median interface. Give it a point of view instead.

Produce the brief in these sections:
1. Purpose and person: who, what they are trying to do, in what state of mind. One paragraph.
2. Point of view: three words for the feel and two things it must not feel like. Name real references and the specific thing taken from each (a grid, a scale of type, a way of using colour), not "inspired by".
3. Type: one display face with character, one text face built for reading, one for UI if needed; sizes on a scale with a big jump between headline and body; weights. Name real typefaces and fallbacks.
4. Colour: one dominant colour, one sharp accent, neutrals. Give hex values and the contrast of each text and background pair; call check_contrast to verify rather than asserting. No gradients unless one is asked for.
5. Layout: where the grid is broken on purpose (offset columns, one oversized element, uneven sizes), and how it collapses on a phone. Forbid the centred hero then three equal cards.
6. Content: the real copy, or the real data shapes. Never lorem ipsum. Give actual lengths, including the longest name and the empty state.
7. Components and states: only what the screen needs, with default, focus, error, empty and loading.
8. Motion: one or two moves with a purpose, under 300ms, honouring reduced motion.
9. Hard constraints: WCAG 2.2 AA, 44px touch targets, no emoji or eyebrows or glow blobs, text a person would actually say.
10. Acceptance checks the result must pass: run detect_design_slop on the built page, check_contrast on the final colours, review_ui_copy on the strings, audit_page_accessibility on the markup.
Keep the brief under 600 words. A short brief with real decisions beats a long one with adjectives.
Adapt it to the generator named above: tools that take a short prompt (Figma Make, v0, Lovable, Stitch) want the point of view, type, colour and the never-list in the first paragraph, one screen at a time, with real copy pasted in; Claude and other coding agents can take the full brief and a DESIGN.md. Say which version you are giving.

## Tools used

- check_contrast
- detect_design_slop
- review_ui_copy
