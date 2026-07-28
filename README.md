# ptc-prod-demo

Demo repository for the PTC CI on-ramp: every push to `main` sends
`locales/en.json` to PTC and comes back as a pull request with the
translations.

The workflow is the snippet the product prints, unchanged:

- `OnTheGoSystems/ptc-action@v1` — the published action, which vendors
  `ptc-cli` and pins every third-party action by commit SHA
- no `api-url`, so it talks to production (`app.ptc.wpml.org`)

## Setup

1. **Secret** — Settings → Secrets and variables → Actions → New repository
   secret, named exactly `PTC_API_TOKEN`, holding a PTC project API token.
2. **PR permission** — Settings → Actions → General → Workflow permissions →
   turn on *Allow GitHub Actions to create and approve pull requests*.
   Without it the translation runs and the PR silently never appears.

Then push anything to `main`, or run the workflow manually.
