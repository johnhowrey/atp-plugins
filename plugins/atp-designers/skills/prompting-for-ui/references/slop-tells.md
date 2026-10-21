# Slop tells catalogue: design and writing

"Slop" is the default output of a model or a template with no point of view. One tell is a style; a cluster with no counterweight is a template. Use this list to review work, to brief a model so it avoids the tells, and to explain to a stakeholder what feels generic.

## Design tells (what generated interfaces share)
Typography: Inter, Roboto, Geist or system-ui as the only family; one weight ramp; headings and body in the same face; centred multi-line hero text; uniform letter-spacing.
Colour: purple to blue or indigo to pink gradients; gradient-filled text; a dark navy background with neon accents; every surface a slightly different grey; colour used decoratively and not to carry hierarchy.
Layout: a centred hero, then a row of three identical feature cards, then a centred testimonial, then a centred call to action; symmetry everywhere; zig-zag alternating image and text; 12px to 24px rounded corners on everything; soft shadows on every card.
Components: pill buttons with an arrow glyph; small uppercase tracked labels above headings ("eyebrows"); emoji or generic icons as feature bullets; glass panels with backdrop blur; blurred glow blobs behind the hero; avatars-in-a-row social proof; "trusted by" logo strips with invented names.
Imagery: abstract blobs, isometric 3D shapes, stock illustrations of people at laptops, dashboard screenshots floating at an angle with a glow, no real photography or product in context.
Motion: everything fades up on scroll at the same distance and delay; hover lifts on every card.
Content: lorem ipsum or invented companies and people left in; perfectly even copy lengths; the same icon style at the same size beside every item.

What to do instead: choose a typeface pairing on purpose (a display face with character against a text face built for reading); commit to one dominant colour, one sharp accent, and neutrals; break the grid deliberately (offset columns, one oversized element, uneven card sizes); use real content and real product imagery; make one or two bold moves and let the rest be quiet; write copy that sounds like the people who made it.

## Writing tells (what generated copy shares)
Vocabulary: delve, tapestry, testament, beacon, vibrant, plethora, robust, seamless, leverage, elevate, empower, unlock, game-changer, landscape, realm, holistic, cutting-edge, ever-evolving, "it is important to note".
Shapes: "not just X, but Y" and "it is not about X, it is about Y"; triads in every list ("fast, simple, and secure"); a rhetorical question to open; a neat closing epigram; a summary sentence that restates the paragraph; headings that are all the same length and pattern; bullets that all begin with a bold label and a colon; paragraphs of equal length; sentences of similar length.
Punctuation and tone: em-dashes in quantity; exclamation marks in UI; chirpy openers ("Oops!", "Great news!"); hedging adverbs (arguably, notably, essentially).
Structure: report skeletons (Overview, Key Findings, Recommendations); audience splitting ("Whether you are a designer or a developer"); a stat in every sentence.

What to do instead: say the specific thing with a real example or number; vary sentence and paragraph length; use two items or four, not always three; cut the summary; use contractions; let a point stand without an epigram; write errors and empty states as plain help.

## How to use this with the tools
- detect_design_slop reads a live page for the design tells above and returns weighted signals.
- review_ui_copy and Toolbox's check_tells find the writing tells in strings and prose.
- When briefing a model to build UI, put the "what to do instead" list in the brief first, name the typeface pairing and palette yourself, and attach a real content sample. A model with a point of view in the brief produces less slop than one told "make it clean and modern".
