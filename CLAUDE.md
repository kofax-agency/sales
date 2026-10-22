# CLAUDE.md

## Communication
- Always reply to the user in **Ukrainian** in chat.
- Everything inside the repo is in **English**: code, identifiers, code comments, commit messages, PR titles/descriptions, docs.
  (Existing Ukrainian comments may stay; new or touched code uses English. UI strings shown to end users stay in Ukrainian.)

## Git authorship
- The user is the **only** author of every commit, push, merge, tag and PR.
- Never add `Co-Authored-By`, "Generated with Claude Code" or any other AI attribution to commits or PRs.
- Use the existing local git identity; never change `git config user.*`.
- Commit / push / merge only when the user asks.

## Code style
- Keep comments short: one line explaining *why*, not *what*. No comment blocks or change-history narratives.
- Follow DRY, SOLID, KISS, YAGNI: reuse existing helpers, small single-purpose functions, no duplicated logic, no speculative abstractions.
- Match the surrounding code's naming and idioms.
- Prefer clear names over comments; remove dead code instead of commenting it out.

## Project
- Kofax Agency internal CRM: a single-page app in `index.html` (HTML + CSS + vanilla JS, no build step).
- Data is stored in Firebase Firestore (`kofax/crm` document plus `coldBaseContacts` and `attachments` collections).
- Deployed via GitHub Pages from `main` (`https://kofax-agency.github.io/sales/`): every push to `main` goes live.
- Before saving to Firestore, respect the `fbReady` / `everHadCoreData` guards — they prevent wiping the cloud data.
