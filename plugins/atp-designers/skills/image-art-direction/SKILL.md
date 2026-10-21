---
name: image-art-direction
description: Use when asked to write prompts or a style guide for AI-generated images, brief a set of images that look coherent, or avoid the stock illustration look.
---

# Art direction for AI images

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## Art direction brief for AI image generation

Write an art direction brief for generated images that look like one considered set.

Project: [project from the person's request]
Mood and references: [mood from the person's request]
Count: [count from the person's request]

1. Read the file references/slop-tells.md for the image tells to avoid (isometric blobs, glowing gradients, floating dashboards, stock people at laptops, perfect symmetry, the same lighting on everything).
2. Choose one mode and commit: documentary-style photography (real subjects, available light, specific lens and framing), or collage (cut-outs, mixed scale, torn edges, type interacting with image), or a defined illustration system. Do not mix.
3. Write the style guide: subject matter rules, camera and framing (focal length, angle, crop, aspect ratio per placement), lighting, palette (hex values tied to the brand and checked for contrast with overlaid text via check_contrast), texture and grain, what is always in frame, what is never in frame, and how people are depicted (diversity of age, body and setting, no stock poses).
4. Write the image prompts: each names subject, setting, action, framing and aspect ratio, lighting, palette and mood in concrete terms, plus negative constraints. Write them as a photo editor would brief a photographer. Vary the framing across the set (wide, detail, mid, close) so it does not read as copies.
5. Add review criteria for choosing results: does it match the guide, are hands and text correct, does it read at small size, does it work with the text overlay, is it different from the others?
6. Add alt text guidance: describe what the image conveys in context, not "image of".
Provide a shot list table: id, placement, aspect ratio, prompt, alt text, overlay text and contrast check.

## Tools used

- check_contrast
