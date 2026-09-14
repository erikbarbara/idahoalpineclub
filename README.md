# Idaho Alpine Club — Jekyll site

A lightweight single-page Jekyll and Bootstrap site for the Idaho Alpine Club. GitHub
Actions builds and deploys it to
<https://erikbarbara.github.io/idahoalpineclub/> whenever `main` changes.

## Run locally

```sh
bundle install
bundle exec jekyll serve --livereload
```

Open <http://127.0.0.1:4000>.

Navigation lives in `_data/navigation.yml`, shared page chrome is in `_includes`,
and all styles are in `assets/css/main.css`.

## Publish an event

Edit `_data/events.yml`. Each list item is one event or update. The events
section sorts entries newest first automatically.

```yaml
- title: Big Elk Creek Hike
  date: 2026-10-12
  label: Sunday, October 12
  description: Meet at 8:00 AM. Members receive route details by email.
  contact: true
  link_text: Join this hike
```

Add a new item, edit an existing item, or remove an item from the list. Use
`contact: true` for a button that emails the Club, or replace it with `link:`
and a complete external URL.

## Publish board notes

Place the PDF or DOCX in `assets/documents/`, then add one list item to
`_data/board_notes.yml` with its title, date, format, and document path. Commit
both changes and the board notes section regenerates automatically.

```yaml
- title: IAC Board Meeting Notes
  date: 2026-10-14
  format: PDF
  document: /assets/documents/board-notes-2026-10-14.pdf
```

The newest five records are displayed automatically.

## Membership links

The external form and PayPal destinations live in `_config.yml`. The PayPal
button only appears when `paypal_url` contains a verified payment URL.

## Deployment

In the GitHub repository settings, set **Pages → Source** to **GitHub Actions**.
The workflow in `.github/workflows/pages.yml` handles the build and deployment.
Dependabot checks Ruby gems and GitHub Actions monthly.
