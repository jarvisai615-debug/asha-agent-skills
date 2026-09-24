---
name: verify-with-a-screenshot
description: Prove a visible change landed with a screenshot of the live thing, looked at — not with a string check, and not with a screenshot of the wrong part.
metadata:
  source: owner, 2026-09-24 — "always verify with the help of screenshot if changes landed or not"
  verified: true
---
# Verify with a screenshot

**The rule.** If a human can see the change, a screenshot of the live thing — scrolled into view, captured,
and **actually looked at** — is the proof. A log line, a return value or a green script is preparation.

## Why both checks are needed (each one caught a different mistake)

1. **The string check catches "it never saved."** Read the value back from the page and quote it.
2. **The screenshot catches "you photographed the wrong thing."** Measured 2026-09-24: a loose
   `section:has-text('About')` locator captured the top card instead of the About section, so a change
   that HAD landed looked unverified — one step from a wrong conclusion.

## How

- Scroll the changed part into view, then capture the **viewport** (`page.screenshot()`), not an element.
- Look at the image and quote what it shows, in words, in the report.
- Beware normalised punctuation: LinkedIn rewrites `'` to `’` and `-` to `–`, so an exact-string check can
  report failure on a save that worked. Compare normalised text.
- For her own app: `screencapture` + a crop, and the same rule — the screen, not the DOM.

## When it does not apply

Nothing visible changed (a config value, a log, a queue marker): then the record *is* the proof — say where
you read it. The rule is about things a human can see.
