# Daily Run: Adding A New Day
1. Vision researches 3–5 ideas; each must have a real source URL (no invented facts).
2. Prepend an object to ideas.json: `{"date":"YYYY-MM-DD","ideas":[...]}`. Idea fields: id (`date-n`), date, title (Title Case), app, why, effort (S/M/L), owner, source {title,url}, format (`card` | `mockup` + `mockup:[...]` | `steps` + `steps:[...]` | `beforeafter` + `before`,`after`).
3. Validate: `python3 -m json.tool ideas.json`. Preview: `python3 -m http.server` and check 390x844, 768x1024, 1440x900.
4. Republish: `git add ideas.json && git commit -m "Ideas YYYY-MM-DD" && git push` (GitHub Pages rebuilds from main in ~1 min). Votes/notes live only in each browser's localStorage, so old ids must never change.
5. Requires `gh auth status` to show WebermanApps. One-time setup: `gh repo create WebermanApps/daily-ideas --public --source . --push` then `gh api -X POST repos/WebermanApps/daily-ideas/pages -f "source[branch]=main" -f "source[path]=/"`.
