# Tracking plan naming guide

A tracking plan is a contract between product, design, data and engineering: each event exists to answer a question someone will actually ask. Start from the questions, then name the events.

## Name events for what happened
- Object then past-tense verb, snake_case: project_created, invite_sent, checkout_started, subscription_canceled. Past tense because the event records something that already happened.
- One event per meaning. If two names mean the same thing (sign_up, user_signed_up, SignUp) the data splits and nobody trusts the dashboard.
- Put the variation in properties, not in the name. Not clicked_pricing_button_header and clicked_pricing_button_footer: pricing_viewed with source = header | footer.
- Never put a UI element or a number in the name (button_clicked_3). The element goes in a property; the meaning is the name.
- Avoid vague events: click, page, event, action, interaction. They answer no question.
- Keep names under about 40 characters and under five words. Longer usually means two events.

## Properties
- Snake_case, one style across the plan. Same name, same type, same meaning on every event that uses it.
- Send identifiers, not personal data. No email, name, phone, address, IP, token or card in a property. Use user_id, account_id, order_id.
- Prefer enumerated values (plan: free | pro | team) to free text. Store money as a number with a currency field. Store durations in one unit (ms).
- Standard properties to attach to every event (usually by the SDK): user_id or anonymous_id, timestamp, platform, app_version, locale, session_id.

## Structure of a good plan
1. Questions the business asks (activation rate, drop-off between step 2 and 3, which feature predicts retention).
2. For each question: the events and properties needed to answer it.
3. Event table: name, trigger (exact moment it fires), properties with type and allowed values, owner, status.
4. A short list of what is deliberately not tracked, and why (privacy, noise).

## Funnels worth instrumenting first
- Activation: account_created, onboarding_step_completed (step_name, step_index), the first core_action_completed.
- Conversion: checkout_started, payment_submitted, subscription_started (plan, billing_period, trial).
- Retention: a return core action by day, and the feature that predicts it.
- Friction: error_shown (error_type, screen), search_performed with zero results, form_abandoned (field_name of last touched).

## Design's part
Designers decide the moments. For every flow, mark on the design where each event fires, name the properties the screen can supply, and note the states to track (empty, error, success). When a design changes, update the plan in the same pull request or the data silently rots.

## Tools
lint_tracking_plan checks naming drift, duplicates, vague events, UI-element names and personal data in properties, and can draft a starter plan for a SaaS, shop, marketplace, content or mobile product.
