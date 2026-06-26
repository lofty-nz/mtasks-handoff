# Mtasks — AI handoff report
1.2 · build 146 · generated 2026-06-26 · from web · last 2 builds (b145–b146) · since build 146 committed

## 🤖 NEXT TO FIX — Andrew flagged these for you (0)
These are the tasks to work on this round, highest priority first. Treat everything below as reference only — don’t pick up unflagged items unless they inform these.
_nothing flagged for this round_

## 🧠 Coding tips — how Andrew likes to work (0)
_none_

## Bugs fixed since last commit (0)
_none_

## Ideas realised since last commit (0)
_none_

## Recent build notes
- b146 — Subscription cancel reminders (#65), mobile dev-note padding (#1172), release-error message + fullscreen tidy. #65: every recurring expense now has a 🔕 bell — tap it to set a reminder to cancel X days before it renews (e.g. 3 days before). When that window arrives, a 🔔 Cancel before renewal card appears at the top of the Budget page listing what’s about to auto-renew and the date to cancel by, and the row itself highlights. #1172: on a phone the dev-note rows lose their boxed container and tight up the padding — flat rows with a thin divider, reclaiming the wasted space (the capture bar already commits on Enter, so no newline change needed there). #1125: the fullscreen button now blocks the long-press menu; full-screen + the top-right exit icon already worked, and removing the OS window bar is handled by the browser’s own full-screen. Release fix: when a release fails because the new server.py isn’t deployed, you now get a plain-English message (“deploy the new server.py”) instead of a raw JSON error.
- b145 — Shipped → verify-or-retry loop. When a bug/idea is marked 🚀 shipped (resolved in a build) it now (1) jumps to the top of the verify list so you check the freshest fixes first, and (2) gets flagged 🤖 for the AI automatically. From there it goes one of two ways: you tick ✓ to verify it → the flag clears and it moves to Version history; or you leave it (still broken) → it stays flagged, so on the next handoff the AI sees it in NEXT TO FIX marked ↩ shipped, awaiting verify and retries that bug. Shipped-and-flagged items show in NEXT TO FIX (not the "fixed since last commit" list) so they’re never double-counted, and the report tells the AI to retry only if your notes say it’s still broken — otherwise it just needs your tick.