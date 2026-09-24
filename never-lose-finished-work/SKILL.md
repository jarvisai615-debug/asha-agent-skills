---
name: never-lose-finished-work
description: Finished work is never discarded in silence and no item is bought twice — park it, name why, and ask.
metadata:
  source: owner, 2026-09-24 — "do something so they can never throw it away without asking you first"
  verified: true
---
# Never lose finished work

## What happened (measured, not imagined)

1. **36 runs in one day. 30 of them were two tasks that could never finish.** One item was attempted
   **14 times**; another **16 times**. Every run did real work and every patch was thrown away.
2. The reason was paperwork, not ability: the task said `test_map.py`, the work touched
   `prototype/ui/test_map.py`. Same file, different address. The checker saw a change it could not match to
   the task, and its rule was *do not land it* — so it reverted the tree **and set the item back to ready**,
   and the next tick bought the same task again.
3. Nobody was lazy. Nobody was wrong. **The pipe was.**

## The two rules that follow

1. **A finished patch is never discarded in silence.** If it cannot be landed, it is **parked** with its
   patch kept, the reason written down, and the decision asked of a human. Never silently reverted.
2. **No item is bought more than twice** without a human's say-so. After that it stops and asks. A
   retry limit is a money guard, not a nicety.

## How to apply it, whatever the system

- Before you discard, revert, or re-run: **say what you are about to lose** and who decided.
- When you cannot land something, **park it and report** — never "try again quietly".
- Count the **same item's attempts**, not just the total. A breaker that only counts spend cannot see one
  item being bought forever.
- Keep the difference: an honest "already done, here is the proof" is a **result** and must not be counted
  as a failure.
