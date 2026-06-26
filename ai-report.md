# Mtasks — AI handoff report
1.2 · build 143 · generated 2026-06-26 · from web · last 2 builds (b142–b143) · since build 143 committed

## 🤖 NEXT TO FIX — Andrew flagged these for you (0)
These are the tasks to work on this round, highest priority first. Treat everything below as reference only — don’t pick up unflagged items unless they inform these.
_nothing flagged for this round_

## 🧠 Coding tips — how Andrew likes to work (1)
- #1180 b138 the add button needs to be joined with the bug/idea/tip etc, so we click the note button if defaults to bug report, but clicking it again brings all the other options, like task photo, file etc. there will be a add button at the bottom of the sidebar for adding new sidebar items (Dev)

## Bugs fixed since last commit (0)
_none_

## Ideas realised since last commit (0)
_none_

## Recent build notes
- b143 — Custom sidebar shortcuts (#1180) + Leads placeholder (#1186). #1180: a ＋ button at the bottom of the left rail adds your own sidebar items — pick an emoji, a label and a link (e.g. testtagrepair.co.nz or the ChookNation stream) and it pins a shortcut that opens in a new tab. Right-click a shortcut to edit; the ＋ opens a little manager to add/edit/remove them. They save in your data file. (Built as link shortcuts, not full custom pages — that’s a much bigger job if you want it.) #1186 (placeholder): a new 🆕 Leads tab in the TTR hub. Add web-form enquiries manually as new leads (name, phone, email, device, fault) and → Job converts a lead straight into a job. The data store is the foundation the real auto-import fills later — your site emails enquiries to Gmail, so the plan (noted in-app) is a Google Apps Script that reads those emails into a Leads tab on the Job Tracker, pulled in here like Jobs sync. We’ll iron that out next.
- b142 — Clean git: one file, a tag per build, one-tap rollback (#1178). Needs the new server.py deployed. Git now tracks a single canonical mtasks.html (plus server.py and .gitignore) instead of a pile of mtasks-130/131/… files. Each Commit & push tags the build b<n> (with your latest build note as the tag message), so every build is a named restore point. The 🐙 GitHub panel gains a ↩ Roll back to build picker + Restore button: pick a build, confirm, and the server rewrites mtasks.html to that build and the app reloads onto it — your current build is backed up first and history is never rewritten, so you can roll forward again. The numbered build files stay on your disk for offline rollback but are git-ignored, and the migration also stops tracking mtasks-data.json / backups if they were ever committed (kept on disk). Server changes: find_html serves the canonical file (falls back to highest build if it doesn’t exist yet), deploy writes mtasks.html + a numbered archive, /git-push commits-then-tags-then-pushes --follow-tags, new /git-restore, and /git-info now returns the build tags. Going-forward only — your existing history is left exactly as-is.