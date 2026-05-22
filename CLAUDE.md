# US Jobs Board — Claude Instructions

## Git workflow
Always commit and push directly to `main`. Do not use feature branches.

## Job board update routine
1. Read `last_run.txt` for the last processed date (default `2026-05-19` if missing).
2. Search Gmail: `label:usjobs after:YYYY/MM/DD`
3. Fetch full body of each thread and extract genuine job postings.
4. Prepend new job objects to the top of the `JOBS` array in `job-board-final.html`.
5. Update the "Updated [date]" text in the topbar to today's date.
6. Write today's date to `last_run.txt`.
7. `git add job-board-final.html last_run.txt && git commit -m "Auto-update: added N new jobs — YYYY-MM-DD"`
8. `git push origin main`
9. If no new jobs found, exit without committing.
