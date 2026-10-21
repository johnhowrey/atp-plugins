# Critique rubric by stage

A critique is a conversation with a goal: help the designer make a better decision. The stage of the work decides which feedback is useful and which is noise. Use this to frame the session, to write notes, and to refuse feedback that belongs to a later stage.

## The shape of useful feedback
Observation (what I see, specific and checkable), impact (what that does for the person using it or for the goal), optional direction (something to try, not an instruction). "The Pay button and the Cancel link are the same grey, so people will not see which one finishes the order" is ready to act on. "Make it pop" and "I don't like the blue" are not.

Rules for the room: the presenter frames the work and states what feedback they want and do not want; feedback is addressed to the work, not the maker; questions come before suggestions; the presenter does not defend, they write down and ask follow-ups; the group names what is working before what is not; end by agreeing what will change and who owns it.

## Stage 1: Concept
Question: is this the right problem, for the right people, with a promising direction?
Ask: Who has this problem and how do we know? What would make us wrong? What is the strongest alternative we have not drawn? What do we need to learn to choose?
Refuse: colour, type, icon style, copy polish, pixel details. Nothing is drawn yet.
Ready to leave when: the problem statement, the audience and two or three directions are agreed, with a reason for the one chosen.

## Stage 2: Wireframe (structure)
Question: does the structure support the task?
Ask: Can someone complete the task from these screens alone? What is the most important thing on each screen and is it the most prominent? What is missing? What here does the task not need? What happens at each state change (empty, error, loading, long text)?
Refuse: visual style, brand, animation, exact copy.
Ready to leave when: the main task can be walked end to end, with open questions listed.

## Stage 3: Visual design
Question: does the look support the task and the brand, without getting in the way?
Ask: Where does the eye go first, second, third, and is that the order the task needs? What does it say about the product in five seconds? What is hard to read or to tell apart (contrast, size, colour-only cues)? Which states are not drawn? Does it hold at the smallest and largest widths?
Refuse: re-opening the task flow, taste with no effect attached, engineering edge cases (collect for build review).
Ready to leave when: key screens and states are drawn at real content lengths, contrast is checked, and tokens exist for what repeats.

## Stage 4: Prototype (behaviour)
Question: can people do the task and where do they stall?
Method: watch, do not explain. Give the task as a goal ("you want to stop this plan"), not steps. Note pauses, backtracks, misclicks, and what people say they expected.
Refuse: explaining the design mid-task, visual nitpicks that do not touch the task, "users will not get it" without anyone having used it.
Ready to leave when: the main task succeeds for most participants without help and the top three problems have a fix.

## Stage 5: Build
Question: does the build match intent and survive real data?
Ask: Where does it differ from the design and does the difference matter to the person? What happens with the longest name, the empty list, a slow network, an error, a screen reader, a keyboard only? What would we cut to ship sooner without hurting the task?
Refuse: redesigning the flow (log for next iteration), differences inside an agreed tolerance (say 2px), new features.

## Stage 6: Shipped
Question: what did people do, compared with what we expected?
Ask: Where did they drop out, repeat, or reach for help? What did we get right that we must protect? What is the single change likely to help the most people?
Refuse: opinions that ignore the data, a list of fifteen changes (pick one or two), blame for earlier decisions.

## Facilitator moves
- When feedback arrives at the wrong stage: "That sounds like a visual-stage note; I will park it."
- When feedback is vague: "What do you see that gives you that impression?"
- When feedback is a solution: "What problem would that fix?"
- When two people disagree: ask what each would need to see to change their mind.
- When the presenter starts defending: "Write it down; we will come back to it."
