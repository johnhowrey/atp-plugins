# DESIGN.md template

A DESIGN.md is read by a model before it builds anything for your product. It works when it changes what comes out: concrete values, named rejects, real examples. Keep it under about 1,500 words; link out for detail. Check yours with the lint_design_md tool.

Copy everything below the line, delete the guidance in brackets, and fill in real values.

---

# [Product name] design context

## Purpose and audience
[Two or three sentences. Who uses this, what they are trying to do, in what state of mind (in a hurry, anxious, expert). The job the interface does, not the company's mission.]

## Voice and feel
[Three words for the feel and two it must not feel like. Then one real sentence in the product's voice, and one it would never say.]
- Feels: [e.g. dry, exact, warm]
- Must not feel: [e.g. corporate, cute]
- Sounds like: "[example line]"
- Never sounds like: "[example line]"

## Colour
[Hex values with roles, one dominant colour, one accent, neutrals. Name the text and background pairs and check them with check_contrast.]
- Background (page): #[hex]
- Surface (card): #[hex]
- Text (primary): #[hex]
- Text (muted): #[hex], used only at 18px and above or where contrast has been checked
- Accent: #[hex], used for the single primary action on a screen
- Danger: #[hex]
Never: gradients, a second accent, colour as the only signal.

## Typography
[Real typefaces with fallbacks, a scale, and what each is for.]
- Display: [Typeface], [weight], [size range], tight tracking
- Text: [Typeface], 16px body, 1.5 line height, 65 characters per line
- UI and labels: [Typeface], 14px
- Scale: [e.g. 14, 16, 20, 28, 44, 72]

## Spacing and layout
[Base unit, grid, how it breaks.]
- Unit: 8px. Page margin [value]. Content max width [value].
- Layout is [asymmetric: describe the intentional break]. Collapses to one column below [breakpoint].
- Radius: [value]. Shadows: [none or value].

## Components
[Only the ones that need a rule. Each with states.]
- Button: one primary per screen, [height]px tall, sentence case verb labels, states: default, hover, focus (2px outline in accent, 3:1), disabled, loading.
- Form fields: labels above, errors below in danger colour with an icon and text, never colour alone.

## Imagery and motion
- Imagery: [photography with a specific direction, or illustration style]; never stock people at laptops.
- Motion: [one or two moves, under 300ms, ease-out]; respects prefers-reduced-motion.

## Accessibility
WCAG 2.2 AA. Text 4.5:1, large text and components 3:1. Targets 44px on touch. Visible focus on everything. Plain language, errors that say what to do.

## Do and do not
Do: [three real habits of the product's design.]
Never: [three defaults you reject, for example three identical feature cards, eyebrow labels above headings, purple gradients, lorem ipsum, "Oops!"]

## References
- [Link or file of a screen that is right, and what makes it right.]
- [Link or file of a screen that is wrong, and what is wrong with it.]
