# DI Authentication Account Redirect Page

The code in this repo allows a single page to be deployed via GitHub Pages with GOV.UK styling. It does not form part of the normal user journey. Instead users will see this page only when attempting to access the URL formerly used for account management: `account.gov.uk`. This is primarily to help users who may have bookmarked that URL. They will be offered a chance to redirect to the new URL (`home.account.gov.uk`) if they click a button on screen.

## Note on styling
This repo is so minimal that GOV.UK styling is not compiled in its entirety. If new components are required, these would need to be listed individually in index.scss

## Local setup
The recommended way to preview this code locally is to use a live preview server in an IDE. 

In order for the page to render correctly, certain elements of the GOV.UK Frontend npm package are required. First run `npm i`. These can then be copied across into the application by running `npm run govuk-frontend-setup`. This in turn comprises two steps (spelled out in `package.json` under `scripts` - but please not that you do not need to run these directly):
- `compile-css`: compiles index.scss into index.css and copies assets (fonts and images) from `node_modules` into an `assets` folder at the root of the project
- `run copy-js`: copies base JavaScript from `node_modules` into an `assets/js` folder at the root of the project

## Deployment
Deployment is via GitHub Pages (see `.github/workflows/deploy.yml` for details of the job). The action will run whenever something is merged to `main` branch.