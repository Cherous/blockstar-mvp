# Blockstar (MVP)

Blockstar is an MVP for a real-estate tokenization/investing experience. This repo currently focuses on the **core marketing + browse experience** and an **interactive 3D property demo**, with backend scaffolding for user accounts.

<img src="./public/readme.jpg" alt="Blockstar preview" style="width:100%; height:auto;" />

## What’s in this MVP right now

- **Frontend (React / CRA)**:
  - Home, Properties (list), Property Detail, 3D property demo, About, FAQ, Privacy, Blog
  - Client-side routing via `react-router-dom`
  - UI currently uses Bootstrap/Reactstrap + custom styling
- **3D Property demo**:
  - Three.js via React Three Fiber (`@react-three/fiber`, `@react-three/drei`)
- **Backend (Express)**:
  - `/api/user/*` endpoints (auth + profile/admin user endpoints)

## What’s intentionally not complete yet (expected for MVP stage)

- **Wallet connect / on-chain purchasing** (deps exist, but flow is not wired end-to-end)
- **KYC/AML workflow**
- **Property data from a database / admin property CRUD**
- **Invest/Checkout flow + Portfolio dashboard**
- **Dividend distribution / smart contracts / secondary trading**

## Repo structure

- `src/` — React app (frontend)
- `server/` — Express app (backend)
- `public/` — static assets

## Getting started (local)

### Clone the Repo
### Prerequisites

- **Node.js**: 18, 20, 22 recommended (https://nodejs.org/en/download)
- **npm**: comes with Node

### Install

From the repo root:

```bash
npm install
```

### Run (frontend + backend)

This runs both the React app and the Express server:

```bash
npm start
```

### Run backend only

```bash
npm run server
```

## Environment variables

The backend uses `dotenv` and expects environment variables for things like JWT, DB connection, and email (SendGrid) / Cloudinary in some flows.

If you don’t have environment variables set up yet, you can still run the frontend MVP pages, but backend features may fail.

## Main routes (frontend)

- `/` — Home
- `/properties` — Properties list (currently mocked data)
- `/properties/:id` — Property detail (currently mocked data)
- `/property-3d` — 3D property demo
- `/about`, `/faq`, `/privacy`
- `/blog`, `/blog/:slug`

## Notes for contributors

- Keep UI changes scoped and MVP-friendly (avoid large refactors unless needed).
- Prefer incremental wiring: mock → API → persistence.
- Security-sensitive work (auth, wallet, transactions) should be reviewed carefully.
