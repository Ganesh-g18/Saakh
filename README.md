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

Preview normally serves http://localhost:4173. Deploy `dist/` with SPA history fallback to `index.html` if hosting later. Browser IndexedDB storage is origin-specific; development and preview histories are separate.

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
