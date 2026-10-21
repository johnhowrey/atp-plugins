---
name: tracking-plan
description: Use when asked to plan analytics, define events, write or review a tracking plan, name events and properties, or work out what to measure for a flow or product.
---

# Analytics tracking plan

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Tracking plan for a design or product

Write a tracking plan. Start from the questions, then name the events.

Product or flow: [product from the person's request]
Questions: [questions from the person's request]
Type: [type from the person's request]

Method:
1. Read the file references/tracking-plan-naming.md. If the person gave a product type, call lint_tracking_plan with productType for a starter and adapt it; do not paste it unchanged.
2. If given a Figma link: If the input is a Figma link: parse it (figma.com/design/:fileKey/..., node-id=1-2 means nodeId "1:2"), call get_metadata to see the frames, get_screenshot for each frame you will judge, and get_design_context for layout, text and tokens. Read the picture before the code. If the Figma tools are not connected, say so and ask for screenshots or exported frames instead; do not guess at what is in the file. Mark on each frame the moments worth recording and the states (empty, error, success).
3. List the questions the business will ask (activation, drop-off between steps, which feature predicts retention). If none were given, propose five and ask for confirmation.
4. For each question list the events and properties needed. Name events object then past-tense verb in snake_case; put variation in properties; no UI element names; no personal data in properties.
5. Produce the table: event, exact trigger, properties with type and allowed values, question it answers.
6. Call lint_tracking_plan on the event list and fix every high and medium finding.
7. Add: the funnels to build first, the standard properties to attach everywhere, and what is deliberately not tracked and why.

## Tools used

- lint_tracking_plan
