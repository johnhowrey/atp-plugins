# WCAG 2.2 quick reference, by criterion

Level A and AA are the usual legal and contractual target; AAA is rarely required for a whole site. Criteria new in 2.2 are marked (new). "Check" says what to test and with what.

## Perceivable
- **1.1.1 Non-text Content (A).** Every image that carries meaning has alt text that does the job of the image; decorative images have alt="". Icons that act as buttons are named by the button. Check: audit_page_accessibility for missing alt; read alt text aloud for meaning. Do not start with "image of".
- **1.2.1 to 1.2.5 Time-based media (A, AA).** Captions for prerecorded video with speech; audio description or a text alternative for video-only content. Check by hand.
- **1.3.1 Info and Relationships (A).** Structure in markup, not only in looks: real headings in order, lists, table headers, labels tied to inputs. Check: audit_page_accessibility (heading jumps, no h1, no main).
- **1.3.2 Meaningful Sequence (A).** Reading order in the source matches the visual order. Check by tabbing and with CSS off.
- **1.3.4 Orientation (AA).** Do not lock to portrait or landscape unless essential.
- **1.3.5 Identify Input Purpose (AA).** autocomplete tokens on personal-data fields (name, email, tel, address-line1, cc-number).
- **1.4.1 Use of Color (A).** Colour is never the only cue (error red alone, link colour alone). Add text, icon, underline or pattern.
- **1.4.3 Contrast (Minimum) (AA).** 4.5:1 for normal text, 3:1 for large (24px, or 18.66px bold). Check: check_contrast. Placeholder text and disabled text are the usual failures people forget; disabled controls are exempt, placeholders are not.
- **1.4.4 Resize Text (AA).** Text scales to 200% without loss. Do not block zoom in the viewport tag.
- **1.4.5 Images of Text (AA).** Use real text.
- **1.4.10 Reflow (AA).** At 320 CSS px width there is no horizontal scrolling for text content.
- **1.4.11 Non-text Contrast (AA).** 3:1 for UI component boundaries and states (input borders, focus rings, icons that carry meaning, chart marks against their background). Check: check_contrast, treating the component edge as the foreground.
- **1.4.12 Text Spacing (AA).** Content survives line height 1.5, paragraph spacing 2x, letter spacing 0.12em, word spacing 0.16em without clipping.
- **1.4.13 Content on Hover or Focus (AA).** Tooltips and popovers can be dismissed, hovered over, and persist until dismissed.

## Operable
- **2.1.1 Keyboard (A).** Everything works from the keyboard. A div with a click handler and no role or tabindex does not. Check: audit_page_accessibility, then tab through.
- **2.1.2 No Keyboard Trap (A).** Focus can always leave a component, including modals (Escape closes).
- **2.1.4 Character Key Shortcuts (A).** Single-key shortcuts can be turned off or remapped.
- **2.2.1 Timing Adjustable (A).** Time limits can be turned off, adjusted, or extended.
- **2.2.2 Pause, Stop, Hide (A).** Moving content that starts automatically and lasts over 5 seconds can be paused (carousels, autoplay video).
- **2.3.1 Three Flashes (A).** No more than three flashes a second.
- **2.4.1 Bypass Blocks (A).** A skip link, or landmarks, to jump past repeated navigation.
- **2.4.2 Page Titled (A).** A unique, descriptive title for each page or view, updated on route change in a single-page app.
- **2.4.3 Focus Order (A).** Focus order follows meaning. tabindex above zero breaks it.
- **2.4.4 Link Purpose (In Context) (A).** Link text tells where it goes. "Click here" and "Read more" do not, when read as a list.
- **2.4.6 Headings and Labels (AA).** Headings and labels describe their topic or purpose.
- **2.4.7 Focus Visible (AA).** A visible keyboard focus indicator. Never outline: none without a replacement.
- **2.4.11 Focus Not Obscured (Minimum) (AA, new).** The focused element is not entirely hidden by sticky headers, cookie banners or chat widgets.
- **2.5.1 Pointer Gestures (A).** Multipoint and path gestures (pinch, drag along a path) have a single-pointer alternative.
- **2.5.2 Pointer Cancellation (A).** Actions fire on the up event, so a slipped press can be cancelled.
- **2.5.3 Label in Name (A).** The accessible name contains the visible label text (voice control users say what they see).
- **2.5.7 Dragging Movements (AA, new).** Anything done by dragging can be done with a click or tap alternative (sortable lists need move up and move down).
- **2.5.8 Target Size (Minimum) (AA, new).** Targets at least 24 by 24 CSS px, or spaced so a 24px circle on each does not overlap another. Inline links in text are exempt. For touch design aim for 44px.

## Understandable
- **3.1.1 Language of Page (A).** html lang is set and valid.
- **3.2.1 and 3.2.2 On Focus, On Input (A).** Focusing or changing a control does not change context unexpectedly (no auto-submit on select).
- **3.2.3 and 3.2.4 Consistent Navigation, Consistent Identification (AA).** Navigation order and component naming stay the same across pages.
- **3.2.6 Consistent Help (A, new).** Help links (contact, chat, FAQ) appear in the same place on every page.
- **3.3.1 Error Identification (A).** Errors are identified in text and the field is named.
- **3.3.2 Labels or Instructions (A).** Every input has a visible label or clear instruction. A placeholder alone does not count.
- **3.3.3 Error Suggestion (AA).** If a fix is known, say it.
- **3.3.4 Error Prevention (Legal, Financial, Data) (AA).** For commitments, allow reversal, checking, or confirmation.
- **3.3.7 Redundant Entry (A, new).** Do not ask for the same information twice in a flow; autofill from earlier steps.
- **3.3.8 Accessible Authentication (Minimum) (AA, new).** No cognitive-function test to log in (remembering a password, solving a puzzle) unless an alternative exists: paste into password fields must work, password managers must work, passkeys or email links as options.

## Robust
- **4.1.2 Name, Role, Value (A).** Every control exposes a name, a role and its state to assistive tech. Icon-only buttons need aria-label. Custom widgets need the right ARIA pattern. Prefer native elements; ARIA that contradicts the element makes it worse.
- **4.1.3 Status Messages (AA).** Status updates (saved, 3 results, error summary) are announced without moving focus: role=status or aria-live.

## What automated checks miss
Automated tools find about a third of failures. They cannot judge: whether alt text is accurate, reading order, whether focus is visible and obscured, keyboard traps in widgets, caption quality, cognitive load, or whether error messages help. Always add a keyboard pass, a screen reader pass on the main task, a 200% zoom pass and a 320px pass.
