# Current Objectives
> Re-read every 3-4 tool calls

## In Progress
(none — offline standalone build complete)

## Blocked
(none)

## Done (this session)
- [x] Security: removed plaintext PAT from .git/config; auth via gh keyring helper (verified, scanned history clean)
- [x] Bugfix: pinned Babel to 7.29.7 — game renders again (verified in browser, 0 errors)
- [x] TASK-001: Acquired pinned libs — React 18.3.1, ReactDOM 18.3.1, Tone 14.8.49
- [x] TASK-002: Precompiled JSX → plain JS via Babel 7.29.7 classic runtime
- [x] TASK-003: Generated static Tailwind v3 CSS (60/60 source classes present)
- [x] TASK-004: Assembled LarryTheOctopus_standalone.html (573 KB; libs+css+js inline, music = sibling)
- [x] TASK-005: Verified in-browser — 0 errors, zero external requests, menu+START+canvas, Tailwind + music OK
- [x] TASK-006: Documented acceptance (SPECS.md) + cleanup

## Follow-ups (optional)
- Rebuild step: JSX is precompiled, so editing the source means regenerating the standalone (offer `build-standalone.sh` on request).
- Security: revoke the exposed classic PAT at github.com/settings/tokens.
