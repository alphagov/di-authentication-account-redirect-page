# DI Authentication Account Redirect Page

The code in this repo allows a single page to be deployed via GitHub Pages with GOV.UK styling. It does not form part of the normal user journey. Instead users will see this page only when attempting to access the URL formerly used for account management: `account.gov.uk`. This is primarily to help users who may have bookmarked that URL. They will be offered a chance to redirect to the new URL (`home.account.gov.uk`) if they click a button on screen.

## Note on styling
This repo is so minimal that GOV.UK styling is not compiled in its entirety. If new components are required, these would need to be listed individually in index.scss

## Local setup
There are a few scripts in package.json to help with local development:

- `build` - Builds the site and places all assets in dist/, from there you can preview the site as HTML, though fonts may not work due to govuk-frontend serving them from the root path.
- `serve` - runs a HTTP server, useful for testing how it will look 'when it is deployed'.

## Deployment
Deployment is via GitHub Pages (see `.github/workflows/deploy.yml` for details of the job). The action will run whenever something is merged to `main` branch.

Similar to the build script above, GitHub Pages serves the site at a subdirectory, so things like fonts won't work entirely. This won't be an issue as the site will have its own domain.