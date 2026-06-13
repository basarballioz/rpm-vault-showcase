# RPMVault

> A full-stack motorcycle intelligence platform — catalogue, compare, track, and match 18,000+ bikes across web and mobile.

## Get RPMVault Today
[![Web](https://img.shields.io/badge/Web-rpm--vault.com-orange?style=flat-square&logo=vercel)](https://rpm-vault.com)
[![Android](https://img.shields.io/badge/Android-Google%20Play-green?style=flat-square&logo=google-play)](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault)

---

[![React Native](https://img.shields.io/badge/Mobile-React%20Native-blue?style=flat-square&logo=react)](https://reactnative.dev)
[![Next.js](https://img.shields.io/badge/Web-Next.js%2014-black?style=flat-square&logo=next.js)](https://nextjs.org)
[![Node.js](https://img.shields.io/badge/API-Node.js%20%2B%20Express-green?style=flat-square&logo=node.js)](https://nodejs.org)
[![MongoDB](https://img.shields.io/badge/DB-MongoDB%20Atlas-brightgreen?style=flat-square&logo=mongodb)](https://mongodb.com)
[![Firebase](https://img.shields.io/badge/Auth-Firebase-yellow?style=flat-square&logo=firebase)](https://firebase.google.com)
[![TypeScript](https://img.shields.io/badge/Lang-TypeScript-blue?style=flat-square&logo=typescript)](https://typescriptlang.org)

---

## Screenshots

### Web

<p align="center">
  <img width="1000" alt="Web Screenshot" src="https://github.com/user-attachments/assets/c016e433-1672-43b4-a766-fc8a1fb3d844" />
</p>

### Android

<img width="300" alt="Android App" height="600" src="https://github.com/user-attachments/assets/02c68ca4-d8ec-4d8b-869d-2d6b603cfd76" /> <img width="300" height="600" alt="Google Play" src="https://github.com/user-attachments/assets/aa1d7152-341e-4d82-9b56-60b927c0e49c" />

## What is RPM Vault?

RPM Vault is a **full-stack motorcycle intelligence platform** that helps riders explore, compare, and manage motorcycles. It covers the full spectrum of a rider's journey — from first research through day-to-day ownership.

The platform ships as three tightly integrated layers built from a single codebase:

- **Web app** — Next.js 14 with advanced catalogue browsing, side-by-side comparisons, and a personalised rider-matching engine
- **Mobile app** — Expo / React Native with full feature parity, offline-resilient caching, and in-app purchase support (Android)
- **REST API** — Node.js / Express 5 serving both clients, secured with Firebase Auth and deployed on Vercel's serverless infrastructure

---

## Mission & Why I Built RPM Vault

Make motorcycle research and ownership management accessible to every rider — whether they're buying their first bike or tracking maintenance on their fifth. RPM Vault combines a comprehensive technical database with intelligent personalisation tools so riders spend less time searching and more time riding.

As both a software engineer and motorcycle enthusiast, I wanted a platform that helps riders make informed decisions, compare motorcycles objectively, and manage ownership data in a single place.

RPM Vault started as a side project and evolved into a full-stack platform spanning web, mobile, backend, cloud infrastructure, and product design.

---

## My Role

RPM Vault is developed as a solo-engineered product.

Responsibilities include:

- Product strategy
- UX design
- Frontend development
- Mobile development
- Backend development
- Database design
- Cloud infrastructure
- Security hardening
- CI/CD and deployment
- Analytics and monitoring

## Core Features

| Feature | Web | Mobile |
|---------|:---:|:------:|
| Browse 18,000+ motorcycles | ✅ | ✅ |
| Filter by brand, category, search | ✅ | ✅ |
| Full technical spec sheets | ✅ | ✅ |
| Side-by-side comparison | ✅ | ✅ |
| Rider profile quiz + personalised match score | ✅ | ✅ |
| Ride-profile radar chart | ✅ | ✅ |
| Favourites list | ✅ | ✅ |
| Virtual garage | ✅ | ✅ |
| Maintenance record tracking | ✅ | ✅ |
| Fuel log & consumption analytics | ✅ | ✅ |
| Community reviews & ratings | ✅ | ✅ |
| Community bike data submissions | ✅ | ✅ |
| Purchase enquiry forms | ✅ | ✅ |
| In-app purchases / premium tier | — | ✅ |
| Bilingual UI (EN / TR) | ✅ | ✅ |
| Multi-currency cost display (TRY, EUR, GBP, USD) | ✅ | ✅ |
| Blog | ✅ | ✅ |
| Admin panel | ✅ | ✅ |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Web framework** | Next.js 14 — App Router, React Server Components, Edge Middleware |
| **Mobile framework** | Expo SDK 54 / React Native 0.81 |
| **Language** | TypeScript 5 (shared across all packages) |
| **API** | Node.js 20 + Express 5 |
| **Database** | MongoDB Atlas — replica set, compound indexes, TTL collections |
| **Auth** | Firebase Authentication — email/password + Google OAuth |
| **Data fetching** | TanStack Query v5 — hierarchical cache invalidation, SSR dehydration |
| **UI (web)** | Radix UI + shadcn/ui + Tailwind CSS 4 |
| **UI (mobile)** | React Navigation v7, react-native-svg, Expo Linear Gradient |
| **Forms** | React Hook Form + Zod validation |
| **Payments** | Google Play Billing API (server-side verification) + expo-iap |
| **Logging** | Pino + pino-http (structured JSON in production) |
| **Build / CI** | Expo EAS Build — cloud-based iOS & Android builds |
| **Deployment** | Vercel — web app + serverless API on global edge network |
| **Monorepo** | pnpm workspaces — `frontend`, `mobile`, `shared` packages |

---

## Project Scale

- 18,000+ motorcycle records
- Web platform
- Android application
- Shared TypeScript monorepo
- Multi-language support
- Multi-currency support
- Real-world production deployment

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                         Clients                              │
│  ┌─────────────────────┐    ┌──────────────────────────────┐ │
│  │  Next.js Web App    │    │  Expo / React Native Mobile  │ │
│  │  (Vercel Edge)      │    │  (iOS + Android)             │ │
│  └──────────┬──────────┘    └──────────────┬───────────────┘ │
│             │   HTTPS + Firebase JWT        │                │
└─────────────┼───────────────────────────────┼────────────────┘
              ▼                               ▼
┌──────────────────────────────────────────────────────────────┐
│               REST API  (Vercel Serverless)                  │
│                                                              │
│  Helmet · CORS · Rate-limit · HPP · Mongo-sanitize · Zod     │
│  Firebase JWT verification → RBAC role resolution            │
│                                                              │
│  /api/bikes    /api/reviews    /api/leads                    │
│  /api/users    /api/purchase   /api/bikeSubmissions          │
└────────────────────────┬─────────────────────────────────────┘
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
   MongoDB Atlas    Firebase Auth   Google Play
   (replica set)                   Billing API
```

**Shared package** — A `shared` TypeScript workspace package consumed by both the web and mobile apps. It exports all domain types (Zod schemas), the API client, and pure business logic functions: the rider-matching algorithm, ride-profile computation, and garage analytics. Zero type drift between platforms by design.

**Rider-matching engine** — A quiz captures 7 dimensions of rider preference (experience, usage, style, build, etc.) and maps them onto 6 scoring axes (road, offroad, comfort, speed, agility, touring). Each motorcycle has its own profile computed from raw specs. A weighted distance function produces a 0–100% match score shown on every detail page — entirely client-side, no API call needed.

**Security** — Defence-in-depth: Helmet CSP + HSTS preload, strict CORS allowlist, per-IP rate limiting, HTTP Parameter Pollution prevention, MongoDB injection sanitisation, AES-256-GCM encryption for collected PII, Firebase token revocation checks, and RBAC on all protected routes.

**Caching** — TanStack Query v5 with a hierarchical key taxonomy and per-query stale times (30 min for static brand/category lists down to 30 s for live search suggestions). Mutations invalidate only the affected subtree, not the full cache.

**SEO** — Dynamic sitemap (individual URLs per motorcycle), JSON-LD structured data, canonical URL normalisation via Vercel Edge Middleware, and full meta tag coverage in both English and Turkish.

---

## About

RPM Vault is an independent product designed, built, and maintained as a solo full-stack engineering project. It covers the complete product lifecycle — from system architecture and API design through frontend engineering, mobile development, cloud deployment, and security hardening.

[![Web](https://img.shields.io/badge/Try%20it-rpm--vault.com-orange?style=for-the-badge&logo=vercel)](https://rpm-vault.com)
[![Android](https://img.shields.io/badge/Download-Google%20Play-green?style=for-the-badge&logo=google-play)](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault)

---

_This repository is a public engineering showcase. Source code is proprietary._

