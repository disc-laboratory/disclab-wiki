# DISC Lab Wiki Starter

This repository is a starter template for a lab wiki built with MkDocs and Material for MkDocs.

## Quick start

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Then open the local URL printed in the terminal.

## Deploy to GitHub Pages

```bash
mkdocs gh-deploy --force
```

Before deploying, update these fields in `mkdocs.yml`:
- `site_url`
- `repo_url`
- `repo_name`

## Suggested repository name

- `disclab-wiki`

## Notes

- All content is written in Markdown.
- The navigation is controlled from `mkdocs.yml`.
- Replace placeholders with your actual lab-specific content.
