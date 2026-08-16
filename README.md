# Anusha Portfolio Content

This repository is the external content source for the Angular portfolio.

## Files

- `portfolio-content.json` — navigation, hero, about, skills, experience, projects, research-note metadata, contact and footer.
- `blog/*.md` — long-form Research Notes.

## Unique content

Every experience, project and research note has a stable `id`. Projects and research notes also have a URL-friendly `slug`.

Examples:

- project id: `titanic-survival-prediction`
- blog id: `data-leakage-titanic`

Do not reuse an ID for a different item.

## Use from Angular

After pushing this repository to GitHub, use the raw URL:

`https://raw.githubusercontent.com/<YOUR_USERNAME>/<CONTENT_REPO>/main/portfolio-content.json`

Your Angular app can fetch this while running locally on `localhost:4200` and when deployed to Netlify.

## Important edits before publishing

1. Confirm whether the current employer should display as **Brave New World** or **Eve Networks**. The generated content uses the 2026 CV name, Brave New World; the old portfolio used Eve Networks.
2. Add the real GitHub URL for the Titanic project when it is published.
3. Add your actual Titanic results before publishing the data-leakage article.
4. Keep the planned Human Activity Recognition project `visible: false` until you start it.
5. If you want to hide Instagram, leave `visible: false` as generated.
