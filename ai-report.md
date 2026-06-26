# Mtasks — AI handoff report
1.2 · build 145 · generated 2026-06-26 · from web · last 2 builds (b144–b145) · since build 144 committed

## 🤖 NEXT TO FIX — Andrew flagged these for you (4)
These are the tasks to work on this round, highest priority first. Treat everything below as reference only — don’t pick up unflagged items unless they inform these.
- 🤖 #65 with some expenses they are subscriptions, have a check box to reminder to cancel subscription x days before it due to renew
- 🤖 #101 add a live job timer so i can time my sessions, this will be able to tagged to any job or task
- 🤖 #1125 b92 remove the window bar in full screen mode, have a exit fullscreen icon clickable top right to exit — notes: if you long click the exit full screen button it minimises the app
- 🤖 #1172 b129 Layout of devtools is terrible for mobile, can we removed the container around the notes in mobile version, or close the gaps up, there cm of padding that is wasting space on a small screen, hitting enter when writing this will update the note, we dont need a next line featture from enter button being pressed (Dev)

## 🧠 Coding tips — how Andrew likes to work (0)
_none_

## Bugs fixed since last commit (0)
_none_

## Ideas realised since last commit (0)
_none_

## Recent build notes
- b145 — Shipped → verify-or-retry loop. When a bug/idea is marked 🚀 shipped (resolved in a build) it now (1) jumps to the top of the verify list so you check the freshest fixes first, and (2) gets flagged 🤖 for the AI automatically. From there it goes one of two ways: you tick ✓ to verify it → the flag clears and it moves to Version history; or you leave it (still broken) → it stays flagged, so on the next handoff the AI sees it in NEXT TO FIX marked ↩ shipped, awaiting verify and retries that bug. Shipped-and-flagged items show in NEXT TO FIX (not the "fixed since last commit" list) so they’re never double-counted, and the report tells the AI to retry only if your notes say it’s still broken — otherwise it just needs your tick.
- b144 — Reply/flag fix, stacked checkbox, Copy-all on the HTML handoff + GitHub releases & build tree. Needs the new server.py deployed (for releases). Auto-flag (#1172 note): replies never flagged items — the 🤖 flag is auto-set when you log a bug/idea. That’s now a toggle on the AI handoff panel (auto-flag new bugs & ideas, default on); turn it off for fully manual flagging. #1172 layout: in mobile / actions-below mode the verify checkbox + status badge now sit on their own line above the text, so the description gets the full width. #1185: the HTML handoff page has a 📋 Copy all button top-right that copies the whole report (clean markdown) and flips to ✓ Copied. Releases & tree: the 🐙 GitHub panel now shows a 🌳 Builds & releases tree — a vertical timeline of every build tag, newest first, with date + commit subject. Each un-released build has a + Release button (publishes it as a GitHub Release with that build’s notes + a downloadable snapshot); released builds show ◆ Released ↗ linking to GitHub. New server endpoints: /git-release, and /git-info now also returns which tags are released.