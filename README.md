# Blocked

This repository hosts a static page and workflow that deploy a blocking notice to [Cloudflare Pages](https://pages.cloudflare.com/). The site consists of HTML files inside the `pages/` directory and requires no build step.

## Requirements

- A Cloudflare account with a Pages project named `blocked`.
- Repository secrets used by the workflow:
  - `CF_API_TOKEN`
  - `CF_ACCOUNT_ID`

## Deployment

Pushes to `main` trigger `.github/workflows/deploy.yaml`, which uploads the `pages/` directory to Cloudflare Pages.

## Local development

Open `pages/index.html` in your browser to view the page. `pages/404.html` provides the same message for missing resources.

Optional HTML linting is available via [HTMLHint](https://htmlhint.com):

```bash
npm install
npm test
```

## License

This project is licensed under the GNU General Public License v3.0. See `LICENSE` for the full text.
