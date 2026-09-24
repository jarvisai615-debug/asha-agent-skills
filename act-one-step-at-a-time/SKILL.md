---
name: act-one-step-at-a-time
description: Act on a screen one step at a time, screenshot after every step, and when reality differs from expectation stop and understand it before repeating — the method that finally withdrew 7 wrong invitations without a single misfire.
metadata:
  source: owner-taught, 2026-09-24, after the assistant sent seven connection requests to strangers
  verified: true
---
# Act one step at a time, and check the screen after every step

Owner's method, learned the hard way (2026-09-24). Before it, the assistant clicked *the first control whose
label said "Connect"* and invited **seven strangers** from a suggestion rail instead of the six people it
meant. With it, the same assistant withdrew all seven, one at a time, with no misfire.

## The steps, in his words and order

1. **Screenshot first, and make a map of it.** Know what is where before you touch anything: which window
   occupies what, and inside it which regions (navigation, main column, side rail). On this Mac the map is
   literal: window frames from System Events, the page's own regions from the browser, then both drawn on
   the capture. *Two windows can sit at the same origin* — then bare screen coordinates are unsafe.
2. **One action at a time, top to bottom.**
3. **Screenshot after EVERY step.** That is how you know whether what you are doing is happening on the
   screen — not what the code reported.
4. **Before you act, read who or what the control belongs to.** Take the name from the row or the dialog and
   say it out loud before clicking. The strangers were invited because this step was skipped.
5. **When reality differs from expectation: STOP. Do not repeat.** Write three lines and only then continue:
   - **what I thought I was doing**,
   - **what actually happened**,
   - **the correction** — then repeat with the correction.
6. **An action may have a confirmation step.** Find the confirm button *inside the card that just appeared*,
   never "the last element on the page with that label" (that error clicked a row at y=859 while the card
   sat at y=177).
7. **Do the whole action inside one script.** A dialog can vanish between two separate calls; the state
   does not wait for you.
8. **When the page state is suspect, wait, reload once, and look.**

## What "checked" means

A green script is not the check — the **screen** is. Read the number that must change (rows left, items
sent, articles withdrawn) *and* look at the picture. They catch different mistakes: the number catches "it
never happened", the picture catches "you photographed the wrong thing".

## The one-line version

Map first; one action; screenshot; read who it is; if reality differs, understand before repeating.
