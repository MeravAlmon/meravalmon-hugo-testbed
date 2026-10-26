# Merav Almon-Feigin — Hugo redesign

A self-contained Hugo site using the custom `merav` theme. It restores the original website’s bamboo illustration, logo, portrait, and clinic photography with a responsive ivory-and-green design.

## Preview

```sh
hugo server --port 1314
```

Open http://localhost:1314/. To build the production site:

```sh
hugo --gc --minify
```

Upload the contents of `public/` to your static host. The production base URL remains https://meravalmon.com/. Nothing has been published by this redesign.

## GitHub Pages testbed

The `.github/workflows/pages.yml` workflow builds and deploys on every push to `main`. In the GitHub repository, go to **Settings → Pages → Build and deployment → Source → GitHub Actions**.

The workflow discovers the repository’s Pages URL automatically, including its repository subdirectory. It adds `hugo.preview.toml`, which asks search engines not to index the testbed. This is public preview hosting, not password protection. There is no custom-domain/CNAME configuration, so it does not replace meravalmon.com.

To simulate the project-subdirectory deployment locally:

```sh
hugo --config hugo.toml,hugo.preview.toml --baseURL https://example.github.io/meravalmon-hugo-testbed/
```

The source lives in Git; generated `public/` and Hugo caches are ignored. After editing, commit and push to `main`; check the repository’s Actions tab for the deployment result.

## Editing

- Service and first-visit copy: `content/*.md`.
- Homepage sections: `themes/merav/layouts/index.html`.
- Shared contact details: `themes/merav/layouts/partials/contact.html` and `footer.html`.
- Colors, typography, and responsive layouts: `themes/merav/static/css/merav.css`.
- Images: `static/img/`; intake PDF: `static/files/`.
- No Node packages, external fonts, JavaScript, or theme downloads are required.

The homepage is rendered by the theme’s homepage template; its original migrated Markdown is retained in `content/_index.md` for reference. All three internal page URLs and the intake form URL are preserved. Appointment buttons lead to the contact section with telephone and email links.

## Review before publishing

The supplied skin-care copy contains both a $350 introductory price and a $500 session price, as well as a $1,500 package. These figures are preserved from the migration and should be reconciled by the practice. Confirm that first-visit fees, address, contact information, treatment descriptions, and the 2024 intake form remain current.

The original migration project was not modified. This redesigned copy is independent and does not need the Blowfish submodule.
