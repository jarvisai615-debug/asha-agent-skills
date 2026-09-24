# Agent skills

Nine small, hard-won methods for making an AI agent's work trustworthy: check the screen after every step,
prove a change with a screenshot, never let finished work be discarded silently, measure before and after,
replay the failure before you fix it, read a tool's own docs before judging it.

They follow the open **Agent Skills** format — a folder with a `SKILL.md` whose front-matter carries a
kebab-case `name` and a `description`. That means they load in any harness that reads skills, including
**DeepSeek Harness** (`dsh`), Claude Code, Codex and others.

## Install

Copy any folder into a skills root your harness scans.

| harness | roots |
|---|---|
| DeepSeek Harness | `~/.agents/skills/` or `<project>/.agents/skills/` (also `<project>/.dsh/skills/`) |
| others | the skills directory that harness documents |

```sh
git clone https://github.com/jarvisai615-debug/asha-agent-skills
cp -R asha-agent-skills/act-one-step-at-a-time ~/.agents/skills/
```

## What is here

| skill | the mistake it prevents |
|---|---|
| `act-one-step-at-a-time` | acting on a screen without checking what happened |
| `verify-with-a-screenshot` | calling a visible change done from a log line |
| `never-lose-finished-work` | throwing finished work away in silence, then buying it again |
| `own-the-job-not-the-task` | answering a job with one artifact |
| `measure-before-and-after` | believing a change helped |
| `replay-the-failure` | fixing the wrong cause |
| `read-their-docs-first` | judging a tool by an invented usage |
| `check-git-history-for-an-existing-fix-before-redoi` | redoing a fix that already exists |
| `make-a-test-hermetic-by-redirecting-its-writes` | a test that writes into the repo it is testing |

Each skill says what it cost to learn. They are written the way they were learned: from real failures.

## Licence

MIT — see `LICENSE`. The Agent Skills format is an open convention, not ours; these skills are our own
write-up of things that went wrong.
