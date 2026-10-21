---
name: accessibility-review
description: Use when asked to check accessibility, WCAG compliance, contrast, colour blindness, touch target size, or whether a design, page or Figma frame is accessible. Uses exact contrast maths and a markup audit and says what still needs a human check.
---

# Accessibility review

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Accessibility review (WCAG 2.2)

Review this for accessibility against WCAG 2.2 level [level from the person's request].

Target: [target from the person's request]
Focus: [focus from the person's request]

Method:
1. Read the file references/wcag-22-quick-reference.md.
2. For a live URL call audit_page_accessibility. For pasted HTML pass html. Report its findings grouped by criterion and do not repeat low-value noise.
3. For a Figma frame or screenshots: If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Then list every text style and the background it sits on. Call check_contrast with each pair (fg, bg, sizePx, bold) rather than estimating; include non-text pairs that carry meaning (input borders, focus rings, icons, chart marks) at the 3:1 threshold. Call check_contrast with the colour palette to find colours that merge under colour blindness.
4. Review by hand what the tools cannot: target sizes against 24px (aim for 44px), whether colour is the only cue (1.4.1), focus order and visible focus (2.4.3, 2.4.7, 2.4.11), error and form patterns (3.3.1 to 3.3.8), reading order, motion and autoplay, alt text quality, text spacing and reflow at 320px, and drag interactions (2.5.7).
5. Report: a table of failures with criterion number, location (frame or selector), evidence (the measured ratio, the markup), effect on people (who is blocked), fix, severity. Then a short "needs a human" list. Do not claim the design is accessible; say what was checked and what was not. Automated checks find about a third of failures.
6. Offer the next steps: a keyboard pass, a screen reader pass on the main task, 200% zoom and 320px passes. If the person has Pro, mention audit_site_accessibility for a multi-page crawl.

## Tools used

- check_contrast
- audit_page_accessibility
- check_touch_targets
