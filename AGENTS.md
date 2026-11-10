# Agent Guidelines for PlayCanvas Newsletter Content

## Project Overview

Source markdown and media for the PlayCanvas newsletter. The CLI that operates on this content is the team's internal `mailchimp-cli` tool, which lives in a private repository. Don't link to it from this repo.

This repo is **public** so that `media/` can be served via GitHub Pages for email clients to fetch without authentication. Because of that, commit a newsletter's markdown only after it has been sent.

## Directory Structure

```
newsletters/        # YYYY-MM-DD-slug.md files (newsletter content)
media/              # Images, GIFs, organised by YYYY-MM/
.github/workflows/  # Pages deploy workflow (publishes media/ only)
```

## Writing Style

- American English
- No Oxford commas
- Keep it concise - most readers skim

## Email Authoring Rules

- All image URLs must be absolute `https://`. Use media hosted at `https://playcanvas.github.io/newsletter/media/...`.
- Animated GIFs work everywhere except Outlook on Windows (classic), which shows only the first frame.
- HTML5 `<video>` tags and iframes are stripped by most email clients. Use a GIF, or a poster image linked to a hosted video.
- Gmail clips messages over ~102 KB of HTML. Keep things lean.

## Publishing media

1. Drop the file into `media/YYYY-MM/` (or use `newsletter upload <file>` from the CLI).
2. Commit and push.
3. The GitHub Pages workflow publishes it automatically within a minute.
