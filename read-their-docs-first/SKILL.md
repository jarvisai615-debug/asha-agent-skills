---
name: read-their-docs-first
description: Judge a tool only from its own documentation — read it before anything else.
metadata:
  pinned: true
  source: ours — the TypeSafe AI misjudgement, 2026-09-22
  verified: true
---
# Read their docs first

Use **before** using, testing, judging, adopting or rejecting anything new: a service, an
API, a model, a library, a protocol, a plugin, another agent's tool.

## The rule

1. **Read the tool's own documentation first** — the README, the doc site, the vendor's
   usage page. Not a blog summary, not a search snippet.
2. **Write down, in your own words:** what it is for, how it is meant to be used, its
   limits, and the source you read (URL + date). If it cannot be read, say exactly that.
3. **You may not judge a tool by a usage you invented.** If your test was built from
   assumption rather than the documentation, the test is what failed — not the tool.

## Why this exists (the failure it comes from)

TypeSafe AI was judged on one compound, prose-shaped question — the exact anti-pattern its
own documentation forbids (decompose compound judgements into atomic typed questions and
combine them in code). No documentation was read; the resulting noise was reported as a
verdict on the tool. Confident and wrong. The owner: *"this is called overconfidence, and I
never want it in Asha."*

## How to apply it fast (the TypeSafe lesson, used properly)

Decompose the judgement before you make it: "what is it for?" / "how is it meant to be
used?" / "what are its limits?" / "where did I read that?" — four atomic questions with a
source each. If any answer is missing, the verdict is **"not verified"**, which is an
honest sentence, not a failure.
