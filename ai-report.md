# Mtasks — AI handoff report
1.2 · build 142 · generated 2026-06-26 · from web · last 2 builds (b141–b142) · since build 142 committed

## 🤖 NEXT TO FIX — Andrew flagged these for you (0)
These are the tasks to work on this round, highest priority first. Treat everything below as reference only — don’t pick up unflagged items unless they inform these.
_nothing flagged for this round_

## 🧠 Coding tips — how Andrew likes to work (2)
- #1186 b140 i want to pull leads entered thru test tag repair web form and enter them in job tracker as new customer etc with as much info filled out as possible, they will have status new lead (Dev)
- #1180 b138 the add button needs to be joined with the bug/idea/tip etc, so we click the note button if defaults to bug report, but clicking it again brings all the other options, like task photo, file etc. there will be a add button at the bottom of the sidebar for adding new sidebar items (Dev)

## Bugs fixed since last commit (0)
_none_

## Ideas realised since last commit (0)
_none_

## Recent build notes
- b142 — Clean git: one file, a tag per build, one-tap rollback (#1178). Needs the new server.py deployed. Git now tracks a single canonical mtasks.html (plus server.py and .gitignore) instead of a pile of mtasks-130/131/… files. Each Commit & push tags the build b<n> (with your latest build note as the tag message), so every build is a named restore point. The 🐙 GitHub panel gains a ↩ Roll back to build picker + Restore button: pick a build, confirm, and the server rewrites mtasks.html to that build and the app reloads onto it — your current build is backed up first and history is never rewritten, so you can roll forward again. The numbered build files stay on your disk for offline rollback but are git-ignored, and the migration also stops tracking mtasks-data.json / backups if they were ever committed (kept on disk). Server changes: find_html serves the canonical file (falls back to highest build if it doesn’t exist yet), deploy writes mtasks.html + a numbered archive, /git-push commits-then-tags-then-pushes --follow-tags, new /git-restore, and /git-info now returns the build tags. Going-forward only — your existing history is left exactly as-is.
- b141 — Handoff backlog dropped (#1182) + deploy-newest lands on Dev (#1184). #1182: the Open backlog section is gone from the AI handoff — both the HTML page and the markdown report now run Next-to-fix → Coding tips → Bugs fixed → Ideas realised → Recent build notes, nothing else. With new bugs/ideas auto-flagging 🤖 the moment they’re logged (b134), the backlog was just duplicating the flagged list; flag an older item to surface it. #1184: ⚡ Deploy newest from Downloads now switches to the Dev tools page and refreshes onto the new build automatically — for an mtasks.html swap it reloads to the newest build, and for a server.py swap it reloads after the restart. It drops a one-shot #dev URL hash so the page lands back on Dev after the reload instead of the calendar.