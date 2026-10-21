# Design system audit checklist

A design system is a product with users (designers and engineers). Audit it for adoption and consistency, not for completeness. The goal is a short list of changes that increase correct reuse.

## 1. Inventory what exists
- Foundations: colour, type, spacing, radius, elevation, motion, grid, iconography. Are they tokens (named, in one place) or values copied by hand?
- Components: list each with variants and states. Which are used in product, which are unused, which have been detached and rebuilt?
- Patterns: forms, tables, navigation, empty states, errors, loading.
- Documentation and governance: who owns it, how a change is proposed, how it is released, how consumers are told.

## 2. Tokens
- Naming: semantic (color.text.primary, color.surface.raised) over literal (blue-500) in components; a primitive layer beneath and a semantic layer above. Flag tokens named by value or location.
- Coverage: how many distinct hard-coded colours, font sizes and spacings in product? A good system shows few unique values. Use get_variable_defs on the file and check_contrast_tokens (free up to about 30 colours, Pro for 200) to test every foreground and background combination for 4.5:1 and 3:1, and to find colour pairs that merge under colour blindness.
- Scale discipline: spacing on a base unit (4 or 8), a type scale with a ratio, no one-off sizes. Count near-duplicates (two greys 3 percent apart, 15px and 16px text).
- Modes: light and dark (and high contrast) as token sets, not copies of components.

## 3. Components
For each component check:
- Anatomy and variants documented; states complete (default, hover, focus, active, disabled, loading, error, selected).
- Accessibility built in: focus ring contrast, accessible name, keyboard behaviour, ARIA pattern, target size, error association. A component that is inaccessible by default spreads the problem to every product.
- Content rules: min and max text lengths, truncation, localisation, right-to-left.
- Responsive behaviour defined, not left to the consumer.
- Props or variants kept small. A component with 30 variants is two or three components.
- Do designers and engineers agree on names and behaviour (parity between Figma and code)?

## 4. Usage and drift
- Adoption: share of product screens built from system components. Where do teams go around the system and why? Interview two or three of them; the reasons are the roadmap.
- Detached or overridden instances in Figma; custom CSS overriding component styles in code.
- Duplicated components under different names across products.

## 5. Governance
- A contribution path with a time to answer; a changelog; versioning and deprecation rules; visual regression tests; a place to ask questions that someone watches.

## 6. Output
A scorecard (foundations, tokens, components, accessibility, documentation, adoption, governance, each 0 to 4 with one line of evidence), a top-ten fix list by impact and effort, and a 30-60-90 day plan. Report what you could not verify (code you could not see, products you did not sample).
