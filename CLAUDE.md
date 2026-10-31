## Agent skills

### Issue tracker

Issues and specs live as GitHub Issues on `Ditmanson/griz`. See `docs/agents/issue-tracker.md`.

### Domain docs

Single-context layout (`CONTEXT.md` + `docs/adr/` at the repo root). See `docs/agents/domain.md`.

## New content workflow

When asked to "review new content" (or similar):
1. Read `newcontent.md`. Each entry is a YouTube URL plus the user's description of the video.
2. Create a post in `content/dogs/` (or the section that fits best) using `{{<youtube ID  >}}` shortcodes. Match existing posts: front matter with `date` (today), `title`, `tags`; `#` title, `##` section per video, light edits to the user's descriptions only.
3. Run `scripts/fetch-transcripts.py` if the project's scripts README says to for new videos.
4. Rebuild `public/` per `docs/deploys.md` (`rm -rf public/* && hugo`), since Amplify publishes `public/` as-is.
5. Commit the post and `public/` and push to `main`.
6. Empty `newcontent.md` (keep the file, delete its contents). It is untracked; don't commit it.
