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

The homepage is rendered by the theme’s homepage template; its search metadata is in `content/_index.md`. All three internal page URLs and the intake form URL are preserved. Appointment buttons lead to the contact section with telephone and email links.

## Review before publishing

One-hour facial rejuvenation sessions are $400 per the practice owner, with no discounts or packages. Acupuncture fees remain $125 initial / $85 follow-up from the supplied migration. All appointments are one hour. Accepted payments: cash, check, credit card, Venmo, and Zelle. The owner requests at least 24 hours’ notice for cancellations or rescheduling; no cancellation charge has been specified. Insurance information is omitted at the owner’s request. Detailed access arrangements and precise cosmetic-session inclusions still need owner confirmation. Facial rejuvenation refers to the microneedling/skin-care service, not individual facial acupuncture needles. Confirm professional credentials before adding license designations or numbers. The clinic address and parking details are based on the shared clinic’s public information. The 2024 intake form is retained.

The original migration project was not modified. This redesigned copy is independent and does not need the Blowfish submodule.
