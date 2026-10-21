# Design skills for working with AI

Thirteen free skills that teach an AI assistant to do design work properly: critique, accessibility review, Nielsen heuristic evaluation, anti-slop design review, UX writing, research planning, tracking plans, handoff, design system and token audits, prompting for UI, a DESIGN.md generator, and art direction for images.

Made by [All the Possibles](https://allthepossibles.com). Docs and the server: https://designers.allthepossibles.com/docs/start

## New to this? Three plain explanations

- **MCP server.** An add-on that gives your AI assistant extra abilities. You connect it by pasting one web address into the assistant's settings. Nothing is installed on your computer.
- **Skill.** A folder of expert instructions your assistant loads on its own when your request matches (for example "critique this design"). You do not have to pick it.
- **Tool.** One ability the server gives the assistant, such as checking whether a text colour is readable. The assistant uses the exact answer instead of guessing.

The skills work on their own. Connect the server as well and they can also run exact checks.

## Install

Claude Code (skills and server together):

```
/plugin marketplace add johnhowrey/atp-plugins
/plugin install atp-designers@atp-plugins
```

Other agents that read SKILL.md folders: copy the folders you want from `skills/` into your skills directory.

Connect the server (optional, free): `https://designers.allthepossibles.com/mcp` . Steps for Claude Desktop, claude.ai, Cursor, VS Code, Codex and ChatGPT: https://designers.allthepossibles.com/docs/install

## First win

Ask your assistant: "Check the contrast of #8a8a8a text on a white background at 16px." With the server connected it answers with the exact ratio (3.45 to 1, which fails AA) and the nearest colour that passes. Then try: "Critique this wireframe: <paste a Figma link to a frame>. It is at the wireframe stage."

## Skills

- **start-here**: Start here: find the right design skill
- **design-critique**: Design critique
- **accessibility-review**: Accessibility review
- **ux-heuristics**: Nielsen heuristic evaluation
- **anti-slop-design**: Anti-slop design review
- **ux-writing**: UX writing and microcopy
- **user-research-plan**: User research plan and synthesis
- **tracking-plan**: Analytics tracking plan
- **design-handoff**: Design handoff and QA
- **design-system-audit**: Design system and token audit
- **prompting-for-ui**: Prompting for UI generation
- **design-md**: DESIGN.md generator and checker
- **image-art-direction**: Art direction for AI images

## Troubleshooting

Server connected but nothing happens, 401 or 403, limits, Figma links: https://designers.allthepossibles.com/docs/troubleshooting . In your assistant, say: "Call the doctor tool. My problem is: ..."

## Free and Pro

Everything here is free. The server has a Pro tier ($5 a month, 7-day trial) for higher caps, a site-wide accessibility crawl, scored heuristic reports, saved project context and industry playbooks: https://designers.allthepossibles.com/docs/pricing

MIT licence.
