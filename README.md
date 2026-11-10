# PlayCanvas Newsletter

Source markdown and media for the PlayCanvas newsletter.

Newsletters are built, previewed and sent with the PlayCanvas team's internal Mailchimp CLI.

## Layout

```
newsletters/            # One markdown file per newsletter (YYYY-MM-DD-slug.md)
media/                  # Images, GIFs, and other assets, organised by YYYY-MM/
  2026-04/
    my-screenshot.png
.github/workflows/      # GitHub Actions workflow that publishes media/ to Pages
```

## Media hosting

All files under `media/` are published to GitHub Pages at:

**https://playcanvas.github.io/newsletter/**

So `media/2026-04/demo.gif` is reachable at `https://playcanvas.github.io/newsletter/media/2026-04/demo.gif`. Use those absolute URLs in newsletter markdown.

To add a new asset, either copy it into `media/YYYY-MM/` by hand, or use the CLI helper:

```bash
newsletter upload path/to/image.gif
# -> copies into media/2026-04/image.gif and prints the hosted URL
```

Then commit and push. The Actions workflow deploys Pages automatically (usually within a minute).

## Authoring

With the CLI installed:

```bash
cd path/to/newsletter           # this repo
newsletter new april-recap      # creates newsletters/2026-04-21-april-recap.md
newsletter preview              # live preview at http://localhost:3000
```

The CLI auto-detects the content directory from the current working directory. You can also set `NEWSLETTER_CONTENT_DIR` in the CLI's `.env` or pass `--content-dir`.

The CLI's own README covers the full workflow: test send, then send to the audience.

Commit a newsletter here only after it has been sent. This repo is public, so anything pushed is visible straight away.

## Linting

```bash
npx markdownlint-cli2 "newsletters/**/*.md"
```
