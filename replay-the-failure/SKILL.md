---
name: replay-the-failure
description: Catch the real request, replay it, bisect to the field that breaks it.
metadata:
  uses: 1
  last_used: 2026-09-23
  pinned: true
---
# Replay the failure

Use when something a user can see fails and reasoning is not reproducing it: a red bubble,
"model X doesn't work", a provider error, a request that *should* be fine.

Do not change anything until you can make the failing call fail on purpose.

## Steps

1. **Catch the exact input from the app's own record** — never from what you think it sends.
   Where to look, in order:
   - the app log for the request/response pair (`prototype/data/app-launch.log`);
   - the SDK's own request logging: run the app with `OPENAI_LOG=debug` and it logs the full
     outgoing body ("Request options: {… 'json_data': {…}}").
2. **Replay it verbatim** — same headers, same body, nothing tidied:
   `curl -d @prototype/data/her-request.json <same url> -H <same headers>`. Reproduce the
   same failure code. If it does not fail, you replayed something that is not the failure.
3. **Bisect to the smallest failing piece.** Halve it: last N messages, then first N, then
   remove one field at a time. Stop at the boundary — "the first 2 pass, the first 3 fail" —
   and name the single field/value responsible.
4. **Fix that, then re-run the ORIGINAL request** (the full, untrimmed one) through the real
   path. The bisected case passing proves nothing about the product.

## Worked example (2026-09-23)

Owner, on her screen: pick deepseek-v4.1-flash → ask → `400 {'model': 'deepseek-v4.1-flash'}`.
The model, key, base, tools, streaming and max_tokens were all cleared one by one from a
shell — all fine. Replaying her actual body: 101 messages → 400, last 3 messages → 200.
Binary search: `{"role": "bot"}` — our store's word for an assistant turn, which the model
API does not accept, copied into the context by the resume path. One mapping fixed it.

## Rules

- **Name the field.** "It was something in the history" is not a finding.
- **Never edit the replay** to make it pass, and never assume your invented usage is the
  product's usage.
- A 4xx is the request; a 5xx is the service. Bisect 4xx; retry/or-route 5xx.
- Write the boundary and the fixed field into the record — that is the evidence.
