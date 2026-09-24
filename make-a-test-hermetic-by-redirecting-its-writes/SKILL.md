---
name: make-a-test-hermetic-by-redirecting-its-writes
description: Point the module's artefact path constants at a temp dir ins
metadata:
  source: learned by the auto-team, 2026-09-24
  verified: true
---
# Make a test hermetic by redirecting its writes

Point the module's artefact path constants at a temp dir inside the repo's own scratch area, build the artefacts once there, run the real command in-process, and assert the before/after state is byte-identical. Then prove the assertion still fires by forcing a real rewrite, so the check is not vacuous.
