---
name: measure-before-and-after
description: Prove a change moved a number — baseline, one change, same measurement.
metadata:
  uses: 1
  last_used: 2026-09-23
  pinned: true
---
# Measure before and after

Use for every claim of improvement or repair: faster, cooler, smaller, fixed, "works now".
"Feels faster" and "the code is right" are not evidence — a number, taken the same way twice, is.

## Steps

1. **Baseline first, before touching anything.** Name the instrument and the conditions:
   `ps` CPU share, wall-clock seconds, bytes, `df`, a median pitch in Hz, added lines in a
   diff, `cmp` of two screenshots. Write the number down while it is still embarrassing.
2. **Change exactly one thing.**
3. **Measure again the same way, same conditions.** Different conditions mean you measured
   the conditions, not the change.
4. **Report both numbers and the condition.** If the number did not move, the change did not
   work — say that plainly instead of describing the change as if it had.

## Worked examples (all ours, 2026-09-23)

| claim | instrument | before | after |
|---|---|---|---|
| her page no longer heats the laptop | `ps` CPU of Edge's GPU process, window visible | 90–100% | 1–3% |
| her filler clips are no longer a male voice | median F0 of the WAV, autocorrelation | 126–155 Hz | 205–223 Hz |
| the writing rule cut code | added lines in the diff, same task | 119 | 44 |
| her answer about disk space is true | `df -h /` vs what she said | said "about 49 GB" | real 49Gi — true |

## Rules

- **Same instrument, same conditions, both times** — and name both in the report.
- A number in a screenshot beats an adjective in a sentence.
- Keep the "before" even when the fix looks obvious; it is the only thing that proves the fix.
- When the other side of the claim is a *fact* (free space, a file, a count), check it
  independently rather than trusting the assistant's own report.
