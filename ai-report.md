# Mtasks — AI handoff report
1.2 · build 144 · generated 2026-06-26 · from web · last 2 builds (b143–b144) · since build 144 committed

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
- b144 — Reply/flag fix, stacked checkbox, Copy-all on the HTML handoff + GitHub releases & build tree. Needs the new server.py deployed (for releases). Auto-flag (#1172 note): replies never flagged items — the 🤖 flag is auto-set when you log a bug/idea. That’s now a toggle on the AI handoff panel (auto-flag new bugs & ideas, default on); turn it off for fully manual flagging. #1172 layout: in mobile / actions-below mode the verify checkbox + status badge now sit on their own line above the text, so the description gets the full width. #1185: the HTML handoff page has a 📋 Copy all button top-right that copies the whole report (clean markdown) and flips to ✓ Copied. Releases & tree: the 🐙 GitHub panel now shows a 🌳 Builds & releases tree — a vertical timeline of every build tag, newest first, with date + commit subject. Each un-released build has a + Release button (publishes it as a GitHub Release with that build’s notes + a downloadable snapshot); released builds show ◆ Released ↗ linking to GitHub. New server endpoints: /git-release, and /git-info now also returns which tags are released.
- b143 — Custom sidebar shortcuts (#1180) + Leads placeholder (#1186). #1180: a ＋ button at the bottom of the left rail adds your own sidebar items — pick an emoji, a label and a link (e.g. testtagrepair.co.nz or the ChookNation stream) and it pins a shortcut that opens in a new tab. Right-click a shortcut to edit; the ＋ opens a little manager to add/edit/remove them. They save in your data file. (Built as link shortcuts, not full custom pages — that’s a much bigger job if you want it.) #1186 (placeholder): a new 🆕 Leads tab in the TTR hub. Add web-form enquiries manually as new leads (name, phone, email, device, fault) and → Job converts a lead straight into a job. The data store is the foundation the real auto-import fills later — your site emails enquiries to Gmail, so the plan (noted in-app) is a Google Apps Script that reads those emails into a Leads tab on the Job Tracker, pulled in here like Jobs sync. We’ll iron that out next.