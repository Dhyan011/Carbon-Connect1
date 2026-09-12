# Carbon-Connect

**Live demo:** [https://carbon-connect-mauve.vercel.app/](https://carbon-connect-mauve.vercel.app/)

A B2B marketplace for the physical trade of industrial CO₂ — connecting sellers (capture sources like cement, steel, and power plants) with buyers (food & beverage, algae/biotech, chemicals, greenhouse operators). Covers the full trade lifecycle: registration & compliance, listings, quoting, contracts, payment, logistics, quality verification, and post-delivery impact/MRV reporting.

This is a front-end prototype (no backend) — all data is mocked in-app and interactions are simulated with local React state.

## Features / Screens

- **Landing & Auth** — Landing, Login, Role selection, Registration, Compliance (KYB/KYC)
- **Seller flow** — Seller Dashboard, Create Listing (multi-step wizard)
- **Buyer flow** — Buyer Dashboard, Buyer Requirement, Marketplace, Supplier Details, Product Detail
- **Deal flow** — Pricing Breakdown, Quote & Order, Contract, Payment
- **Fulfillment** — Logistics, Quality Verification, Digital Passport, Dispute Resolution
- **Reporting** — Impact / MRV (measurement, reporting & verification)
- **Admin** — Admin Dashboard, Anomaly Monitoring

## Tech Stack

- [React 19](https://react.dev/) + TypeScript
- [Vite 8](https://vitejs.dev/)
- [Tailwind CSS 4](https://tailwindcss.com/)
- No router — screen navigation is handled via simple React context/state (`src/context.ts`, `src/App.tsx`)

## Getting Started

### Prerequisites

- Node.js 22+
- npm (or pnpm)

### Install & run locally

```bash
npm install
npm run dev
```

The app will be available at `http://localhost:8443` (or the port shown in your terminal).

### Build for production

```bash
npm run build
npm run preview
```

The production build is output to `dist/`.

## Deployment (Vercel)

This project is preconfigured for Vercel via `vercel.json`:

- **Framework:** Vite
- **Build command:** `npm run build`
- **Output directory:** `dist`

To deploy your own copy:

1. Push this repo to GitHub/GitLab/Bitbucket.
2. Import the repo in [Vercel](https://vercel.com/new).
3. Vercel will auto-detect the settings from `vercel.json` — no extra configuration needed.
4. Deploy.

Live instance: **[https://carbon-connect-mauve.vercel.app/](https://carbon-connect-mauve.vercel.app/)**

## Project Structure

```
src/
├── App.tsx            # Screen router (switch statement) + top-level state
├── context.ts          # App-wide navigation/role context
├── main.tsx             # React entry point
├── index.css            # Global styles / Tailwind
├── types.ts              # Screen & Role type definitions
├── components/
│   ├── Nav.tsx           # Top navigation bar
│   └── ui.tsx            # Shared UI primitives (Card, Btn, Badge, Table, etc.)
└── screens/              # One file per screen (see Features above)
```

## Notes

- All buttons and interactive elements are wired up with working handlers (approvals, document uploads, step wizards, navigation, etc.) using local component state — there is no persistent backend, so state resets on page reload.
- Built and exported from Figma Make.
