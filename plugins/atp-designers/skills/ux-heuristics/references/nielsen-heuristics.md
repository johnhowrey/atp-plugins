# Nielsen's ten usability heuristics, as a working reference

Jakob Nielsen's ten heuristics (1994, revised 2020) are broad rules of thumb, not a checklist. They find problems; they do not tell you how bad each is or what the fix should be. Use them with a task, a person and a screen in front of you.

## How to run an evaluation
1. Pick one task a real person does, in the words they would use ("change my billing address", not "test the settings area").
2. Walk it screen by screen. At each step ask what the person is trying to do, what they see, and what they would do next.
3. When something goes wrong, write one finding: where, what happens, which heuristic it breaks, and what it does to the person.
4. Rate severity after you have the whole list, so the first problem does not set the scale.
5. Several evaluators beat one. One person finds about a third of the problems; five find about three quarters. Merge lists afterwards and keep duplicates as a signal of severity.

## Severity scale (use these numbers)
- 0: I do not agree this is a usability problem.
- 1: Cosmetic. Fix only if time allows.
- 2: Minor. Low priority.
- 3: Major. Important to fix; high priority.
- 4: Catastrophe. Must be fixed before release.
Judge severity on three things together: how often it happens, how hard it is to get past, and whether it recurs for the same person once they know about it. Add a fourth: how much it costs if it goes wrong (money, data, trust).

## The ten
**1. Visibility of system status.** The interface says what is happening, within a reasonable time. Look for: actions over about one second with no feedback, saves with no confirmation, multi-step flows with no position ("step 2 of 4"), uploads and syncs with no progress, optimistic UI that never reports failure. Typical severity 2 to 3; 4 when a person cannot tell whether a payment or a deletion went through.

**2. Match between the system and the real world.** Words, concepts and order follow the person's world. Look for: internal names ("entity", "provision", "SKU"), icons only the team understands, step order that follows the database and not the task, date and number formats that ignore locale. Test by reading labels aloud to someone outside the team.

**3. User control and freedom.** People make mistakes and need a marked exit. Look for: no undo after a destructive action, modals that trap, wizards with no back, forms that lose input on cancel, auto-advancing carousels and timeouts the person cannot extend. A toast with "Undo" is usually better than a confirmation dialog.

**4. Consistency and standards.** The same thing looks and behaves the same, and follows platform and web conventions. Look for: one action with several names (Sign in, Log in, Login), primary buttons that move position between screens, components that look alike and act differently, breaking a convention (logo links home, underlined text is a link) without a reason that pays for the cost.

**5. Error prevention.** Better than good error messages is a design that prevents the error. Look for: free text where a picker would do, no constraints shown before typing (format, length), destructive actions sitting next to common ones, defaults that are the risky choice, a confirmation step that people click through because it appears every time.

**6. Recognition rather than recall.** Make options visible; do not make people remember. Look for: placeholder text standing in for labels (it vanishes when typing starts), information needed on step 3 that was shown only on step 1, commands without menus, icon-only navigation with no labels, search as the only route to content.

**7. Flexibility and efficiency of use.** Shortcuts for experts, without costing novices. Look for: no keyboard path, no bulk action, no saved or recent items, no way to skip a known step, the hundredth use being as slow as the first.

**8. Aesthetic and minimalist design.** Every extra unit of information competes with the relevant ones. Look for: five calls to action of equal weight, decorative elements that carry no meaning, long explanatory text where a label would do, repetition. This is about relevance to the task, not about looking sparse; a dense trading screen can pass.

**9. Help users recognize, diagnose, and recover from errors.** Messages in plain language, name the problem, suggest the fix. Look for: "Something went wrong", raw codes, "Invalid input" with no field named, errors that clear the form, messages that blame the person, errors shown far from the field.

**10. Help and documentation.** Best if not needed; when needed, findable, task-focused and short. Look for: help that opens away from the task, docs organised by feature and not by goal, no contact route at the moment of failure, tooltips that restate the label.

## Common mistakes in running an evaluation
- Reviewing screens, not tasks. Problems live in the transitions.
- Calling everything a violation. Tag only what would plausibly hurt a real person in the task.
- Using heuristics as a verdict on taste. Typography and colour opinions are not heuristic findings unless they hurt legibility, hierarchy or consistency.
- Skipping the positive. Record what works so it survives the redesign.
- Treating the evaluation as a substitute for watching people use it. It finds likely problems cheaply and early; usability testing finds the ones you did not predict.
