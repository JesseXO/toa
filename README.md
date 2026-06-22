# TOA — Fit-Aware Commerce

A fit-aware e-commerce platform: capture body measurements in the browser with
computer vision, build a structured fit profile, and re-rank the entire catalog
around it. Monorepo.

```
.
├── app/        # React 18 front-end (CRA, styled-components, framer-motion, TF.js)
└── backend/    # Express 5 + Sequelize + Postgres API
    ├── src/            # API source
    ├── scripts/        # seeders + migrations (ANSUR, H&M, gender, images)
    ├── datasets/       # ANSUR II CSVs (H&M articles.csv is gitignored — download separately)
    ├── evaluation/     # JS metrics harness + Python (Keras) training pipeline
    └── docs/           # FEATURES, THESIS, PROJECT_CONTEXT, EVALUATION, DEPLOYMENT, CHANGES
```

## Quick start

```bash
# Backend (needs a Postgres + a .env — see backend/docs/DEPLOYMENT.md)
cd backend && npm install && npm start

# Front-end (set REACT_APP_API_BASE_URL in app/.env)
cd app && npm install --legacy-peer-deps && npm start
```

## Docs
- **Features:** [backend/docs/FEATURES.md](backend/docs/FEATURES.md)
- **Deployment (Render):** [backend/docs/DEPLOYMENT.md](backend/docs/DEPLOYMENT.md)
- **Evaluation & datasets:** [backend/docs/EVALUATION.md](backend/docs/EVALUATION.md)
- **Thesis narrative:** [backend/docs/THESIS.md](backend/docs/THESIS.md)

## Notes
- Secrets live in `app/.env` and `backend/.env` (gitignored). Never commit them.
- The H&M dataset (`backend/scripts/data/articles.csv`, ~36 MB) and `kaggle.json`
  are gitignored — see [backend/scripts/ANSUR_README.md](backend/scripts/ANSUR_README.md)
  and the docs for how to fetch data.
