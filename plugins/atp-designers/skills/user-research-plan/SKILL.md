---
name: user-research-plan
description: Use when asked to plan user research, write an interview guide, survey or usability test, check research questions for bias, choose a research method, work out a sample size or SUS score, or synthesise feedback into themes.
---

# User research plan and synthesis

These steps use tools from the Designers MCP server (https://designers.allthepossibles.com/mcp). If it is not connected, do the same checks by reasoning, say plainly that the numbers were not machine-verified, and tell the person they can connect it (see the start-here skill). Reference files are in references/.

## User research plan and interview guide

Write a research plan a team can run next week.

Decision to inform: [decision from the person's request]
Questions: [questions from the person's request]
Audience: [audience from the person's request]
Constraints: [constraints from the person's request]

Method:
1. Read the file references/research-methods-selector.md to choose the method from the question.
2. State the objective as the decision it informs, then three or four research questions. Reject questions that no decision depends on.
3. Choose the method with a one-sentence reason and the sample size: use usability_stats mode discovery for test rounds, mode survey for survey size.
4. Write the screener: behaviour-based questions (what they did recently), no demographic proxies, a screen-out for design and research professionals, and quotas for the segments that matter, including people who struggle.
5. Write the guide: a warm-up, six to ten open questions about the last time they did the thing, tasks stated as goals not steps, probes ("what happened next", "what did you expect"), and a close ("what should I have asked?"). No hypotheticals, no leading words, no yes or no openers.
6. Call lint_research_questions on the question list (mode interview or survey) and fix every flag before showing it.
7. Add: logistics (consent, recording, incentive), a note-taking template, and a synthesis plan (observations on notes, cluster, name findings with counts, write insights, separate observation from inference).
8. End with the decision rule: what result would change what we do.

## Synthesise feedback into themes and decisions

Synthesise this feedback. Work bottom-up: do not start with the themes you expect.

Goal: [goal from the person's request]
Feedback:
[feedback from the person's request]

Method:
1. Split into single observations, one idea each, keeping the person's own words. Tag each with who said it and the context, if known.
2. If the feedback is design critique from colleagues, call lint_design_feedback and mark which notes are ready to act on; set aside opinions and solutions-without-problems, but keep the underlying problem if one can be recovered.
3. Cluster by theme. Name each theme as a finding in a full sentence ("People do not notice the save state after editing"). Count how many sources support each, and note how strongly each person felt.
4. Separate what was observed from what you infer. Mark where the evidence is thin or comes from one person.
5. Rate each theme for impact on the goal and frequency; put the cost of getting it wrong in the severity.
6. Output: a table of themes (finding, evidence count, example quotes, severity, suggested action), then a short list of decisions to make this week, and questions the data cannot answer plus the cheapest way to answer each.
Do not average opinions. Disagreement between people is a finding.

## Tools used

- lint_research_questions
- usability_stats
- lint_design_feedback
