# Idaho Alpine Club — Jekyll site

A lightweight Jekyll and Bootstrap site for the Idaho Alpine Club. GitHub
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

Copy one of the Markdown files in `_events/`, update its front matter and body,
then commit it. An image is optional; place images in `assets/images/`. The
Events page sorts entries newest first automatically.

## Publish board notes

Place the PDF or DOCX in `assets/documents/`, then copy an entry in
`_board_notes/` and update its title, date, format, and document path. Commit
both files and the Board Meeting Notes page regenerates automatically.

## Deployment

In the GitHub repository settings, set **Pages → Source** to **GitHub Actions**.
The workflow in `.github/workflows/pages.yml` handles the build and deployment.
Dependabot checks Ruby gems and GitHub Actions monthly.
