# Saakh (साख) · v1.2.0

Credit Intelligence Beyond the Credit Score

A local-first MSME credit intelligence demonstration for Hackathon 4.0, Track 3: FinTech AI, IES MCRC Mumbai. All businesses, transactions, scores and estimates are synthetic. No lending decisions or financial integrations occur.

## Requirements and setup

Developed with Node 26.11.1 and npm 11.20.0 on Linux. Use a modern Node version supporting Vite 6.

```sh
cd /home/thunder/shared/Saakh
npm ci
npm run dev
```

Open http://localhost:5173. No environment variables, API keys, login, backend, or cloud account is required.

```sh
npm run typecheck
npm run lint
npm test
npx playwright install chromium
npm run test:e2e
npm run build
npm run preview
npm run format
```

Production preview normally serves http://localhost:4173/Saakh/. Publish only `dist/`; production uses hash routes and a generated legacy-route 404 migration. Browser IndexedDB storage is origin-specific; development and preview histories are separate.

## Product

- Public product story and interactive synthetic surplus sensitivity.
- Overview with explainable score, cash charts, source coverage, interactive trade network and time inspection.
- Generate Simulation: borrower CRUD, source toggles, financial twin editing and up to three scenario comparisons.
- Verify & Investigate: identifier search, evidence links, graph inspection, notes and audit stages.
- Attack Lab: six repeatable scenarios, expected/actual outcomes and regression indicators.
- Impact Dashboard: editable lender cost and benefit model.
- Reports: reproducible JSON, daily ledger CSV, history export, stage replay, print/save-PDF.
- Responsible AI, Settings and a five-checkpoint guided demonstration.

## Structure

`src/domain` schemas/types; `src/fixtures` synthetic borrowers; `src/engines` pure calculations; `src/state` Zustand pipeline and IndexedDB; `src/components` graph/charts; `src/pages` workspace routes; `src/utils` exports; `tests` browser acceptance; `docs` methodology and limitations.

Read [methodology](docs/FINANCIAL-METHODOLOGY.md), [limitations](docs/LIMITATIONS.md) and [test report](docs/TEST-REPORT.md) before interpreting results. This is a functional prototype, not a validated production lending system.

## Disclaimer

Saakh is a prototype simulation for demonstration and educational purposes. Scores, forecasts, alerts, recommendations, and financial-impact estimates use synthetic data and illustrative assumptions. They are not credit ratings, lending offers, fraud determinations, or financial advice.

## GitHub Pages deployment

The verified repository is `Ganesh-g18/Saakh`, published at https://ganesh-g18.github.io/Saakh/. Production builds default to `/Saakh/`; local development remains at `/`. Production uses hash routes, such as `/Saakh/#/app/verify`, so static hosting can refresh and open direct application links. The generated `404.html` migrates legacy clean `/app` URLs.

```sh
npm ci
npm run typecheck
npm run lint
npm test
npm run build
npm run test:pages
npm run preview:pages
```

`preview:pages` serves only the built files under http://127.0.0.1:4175/Saakh/ with no implicit SPA fallback. `npm run test:e2e` retains the development regression suite; `npm run test:pages` validates the real production artifact at its deployment prefix. Chromium must be installed (`npx playwright install chromium`).

In GitHub **Settings → Pages → Build and deployment**, select **GitHub Actions**. Push the source and `.github/workflows/deploy.yml` to `main`, or dispatch the workflow manually. It installs locked dependencies, runs checks/tests, builds, validates the actual Pages metadata path, uploads only `dist`, and deploys using official Pages Actions. No API keys or manually created secrets are required; the workflow uses GitHub's scoped token. Do not publish the source tree or `docs/` as the website.

For a root/custom-domain deployment, build with `SAAKH_BASE_PATH=/ npm run build`; use the same override for local Pages preview/tests. The workflow derives this setting from `actions/configure-pages` metadata instead of guessing a repository name.

Detailed deployment instructions and the actual verification status are in [GITHUB-PAGES-DEPLOYMENT.md](docs/GITHUB-PAGES-DEPLOYMENT.md), [GITHUB-PAGES-FIX-REPORT.md](docs/GITHUB-PAGES-FIX-REPORT.md), [FILE-CHANGES-REPORT.md](docs/FILE-CHANGES-REPORT.md), and [DEPLOYMENT-VALIDATION.md](docs/DEPLOYMENT-VALIDATION.md). Local validation is not evidence that GitHub has published the repaired version.
