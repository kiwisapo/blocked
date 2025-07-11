# Blocked

This repository contains the static HTML page and GitHub Actions workflow used to deploy a simple block message to [Cloudflare Pages](https://pages.cloudflare.com/).

The site consists of a single `index.html` file located in the `pages/` directory. When deployed, it displays a notice informing the user that the resource they attempted to access has been categorised as a security risk and has been blocked.

## Requirements

- A Cloudflare account with a Pages project named `blocked`.
- API credentials stored as repository secrets:
  - `CF_API_TOKEN`
  - `CF_ACCOUNT_ID`

These secrets are used by the GitHub Actions workflow to authenticate with Cloudflare when deploying.

## Deployment

On pushes to the `main` branch, the workflow located at `.github/workflows/deploy.yaml` installs dependencies (if any), runs tests, and then uploads the contents of the `pages/` directory to Cloudflare Pages.

```yaml
name: Deploy to Cloudflare Pages
```

To trigger a deployment manually, push a commit to `main` or run the workflow from the GitHub Actions interface.

## Local development

The site is completely static and requires no build step. You can view the page locally by opening `pages/index.html` in your browser.

## License

This project is licensed under the GNU General Public License v3.0. See `LICENSE` for the full text.
