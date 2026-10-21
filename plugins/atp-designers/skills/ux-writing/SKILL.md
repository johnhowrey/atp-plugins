---
name: ux-writing
description: Use when asked to write or review interface text: buttons, error messages, empty states, tooltips, onboarding copy, confirmations or microcopy, or to remove AI-sounding language from product copy.
---

# UX writing and microcopy

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## UX writing and microcopy review

Review interface copy as a UX writer. The aim is that a person in a hurry does the right thing, and that the product sounds like people made it.

Copy: [copy from the person's request]
Voice: [voice from the person's request]
Reader: [audience from the person's request]

Method:
1. If given a Figma link, pull every text layer (If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file.) and label each with its role: button, error, empty, tooltip, placeholder, heading, toast, label, body.
2. Call review_ui_copy with the strings, one per line, prefixed with the role. Use its findings as a starting point; add what a human reader would catch.
3. Read the file references/slop-tells.md for the writing tells and fix any you find.
4. For each string that needs work, give the original, the problem in one line, and a rewrite. Rewrites follow these rules: buttons name the outcome in one to three words; errors say what happened and what to do, never blame, never "Oops"; empty states say what lives here and give the next action; tooltips stay under about 15 words; no "successfully"; sentence case unless the brand says otherwise; consistent words for the same action everywhere (pick Sign in or Log in); no exclamation marks except where delight is earned.
5. Report the set-level problems separately (inconsistent terms, mixed casing, error tone).
6. Offer a short voice sheet: three adjectives, one do and one do not each, taken from what the existing good strings already do.
Write the rewrites as a person would speak. Avoid the AI tells: triads in every list, "not just X but Y", em-dashes, tidy closing lines.

## Write empty states, errors and microcopy

Write the interface text for these situations, in a voice that sounds like people made it.

Situations: [screens from the person's request]
Voice: [voice from the person's request]
Reader: [audience from the person's request]

1. If given a Figma link, read the frames (If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file.) and list each place that needs text with its role.
2. For each, write one primary version and one alternative. Rules: an empty state says what lives here, why it is empty, and offers the one action to fill it; an error says what happened, then what to do, never blames and never says Oops; a confirmation says what changed and, if it matters, how to undo; a tooltip is one short sentence and adds information the label does not; a button names the outcome in one to three words; the same action has the same word everywhere.
3. Keep it plain. No exclamation marks unless delight is earned. No triads in every list, no "not just X but Y", no em-dashes, no tidy closing line.
4. Call review_ui_copy on everything you wrote (prefix each line with its role) and fix every flag.
5. Output a table: place, role, copy, alternative, note. Add a four-line voice sheet drawn from what you wrote.

## Tools used

- review_ui_copy
