# RPMVault

> Your digital motorcycle garage. Track maintenance, fuel, mileage, and ownership costs, then explore and compare 18,000+ motorcycles on the web, iPhone, and Android.

Solo-built production product: Next.js web, Expo iOS and Android, and a Node API. One account across all three, bilingual EN/TR, listed on the [App Store](https://apps.apple.com/tr/app/rpmvault-motorcycle-garage/id6799125794) and [Google Play](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault). Source is private. This README is the public engineering summary.

## Get RPMVault

[![Web](https://img.shields.io/badge/Web-rpm--vault.com-orange?style=flat-square&logo=vercel)](https://rpm-vault.com)
[![App Store](https://img.shields.io/badge/App%20Store-iPhone-black?style=flat-square&logo=apple)](https://apps.apple.com/tr/app/rpmvault-motorcycle-garage/id6799125794)
[![Google Play](https://img.shields.io/badge/Google%20Play-Android-green?style=flat-square&logo=google-play)](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault)

[![React Native](https://img.shields.io/badge/Mobile-Expo%20%2F%20React%20Native-blue?style=flat-square&logo=react)](https://reactnative.dev)
[![Next.js](https://img.shields.io/badge/Web-Next.js%2014-black?style=flat-square&logo=nextdotjs)](https://nextjs.org)
[![Node.js](https://img.shields.io/badge/API-Node.js%20%2B%20Express%205-green?style=flat-square&logo=nodedotjs)](https://nodejs.org)
[![MongoDB](https://img.shields.io/badge/DB-MongoDB%20Atlas-brightgreen?style=flat-square&logo=mongodb)](https://mongodb.com)
[![Firebase](https://img.shields.io/badge/Auth-Firebase-yellow?style=flat-square&logo=firebase)](https://firebase.google.com)
[![TypeScript](https://img.shields.io/badge/Lang-TypeScript-blue?style=flat-square&logo=typescript)](https://www.typescriptlang.org)

## Product

<p align="center">
  <img src="screenshots/01-garage.webp" width="240" alt="Motorcycle garage with mileage, fuel, and service actions" />
  <img src="screenshots/02-maintenance.webp" width="240" alt="Maintenance history with dates, mileage, and cost" />
  <img src="screenshots/03-costs.webp" width="240" alt="Ownership cost analytics for fuel, service, and spending" />
</p>
<p align="center">
  <img src="screenshots/04-compare.webp" width="240" alt="Side-by-side motorcycle comparison" />
  <img src="screenshots/05-catalog.webp" width="240" alt="Motorcycle catalog with specs and match score" />
  <img src="screenshots/06-ai.webp" width="240" alt="RPMVault AI using the selected bike and garage records" />
</p>

<p align="center">
  <a href="https://rpm-vault.com">Web app</a>
  &nbsp;·&nbsp;
  <a href="https://apps.apple.com/tr/app/rpmvault-motorcycle-garage/id6799125794">App Store</a>
  &nbsp;·&nbsp;
  <a href="https://play.google.com/store/apps/details?id=com.ballioz.rpmvault">Google Play</a>
</p>

## What it is

RPMVault is a motorcycle garage and maintenance tracker. Riders keep the bikes they own in one account: service history, fuel, mileage, expenses, and a catalogue for the next one.

It ships as three layers:

- **Web app.** Next.js 14 with the App Router. Garage, catalogue, and side-by-side comparison at [rpm-vault.com](https://rpm-vault.com).
- **Mobile app.** Expo SDK 54 / React Native 0.81 on [iPhone](https://apps.apple.com/tr/app/rpmvault-motorcycle-garage/id6799125794) and [Android](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault). Same garage, with offline-resilient caching and in-app Premium.
- **API.** Node.js and Express 5, deployed on Vercel. A shared TypeScript package keeps domain rules aligned across web and mobile.

## Why I built it

Motorcycle ownership usually lives in notes, photos, and memory. Service dates slip, costs stay vague, and research for the next bike happens somewhere else.

I wanted one place to log the bike I already ride and compare the next one with the same account. RPMVault started as a side project and is now a production product: web, iOS, Android, API, and the store releases around them.

## What I own

If it ships, I wrote it, reviewed it, and operate it:

- Product direction and UX
- Web, mobile, and API implementation
- Data model and catalogue pipeline
- Auth, billing, and store releases (App Store and Google Play)
- Deployment, monitoring, and bilingual copy (English and Turkish)

## Engineering decisions

**Shared domain, two clients.** Web and mobile share TypeScript types, the API client, and garage math so a service interval does not drift between platforms. The API consumes a compiled snapshot of that package, because it deploys on its own.

**Store billing, account entitlement.** Premium is purchased on iOS or Android. The server verifies the store, then the same account sees it on the web. There is no second web checkout.

**Garage as the source of truth.** Mileage, fuel, service, and expenses hang off the bike you own. Catalogue and compare live in the same account, not a second product.

**Ship, don't demo.** App Store, Google Play, production web, bilingual SEO. The work is release and operations, not a prototype screen.

## Core features

| Feature | Web | Mobile |
| --- | :---: | :---: |
| Digital garage (mileage, fuel, service, expenses) | ✅ | ✅ |
| Maintenance history and PDF ownership report | ✅ | ✅ |
| Maintenance calendar, including the device calendar | | ✅ |
| Catalogue of 18,000+ motorcycles, 80+ brands | ✅ | ✅ |
| Side-by-side comparison and spec sheets | ✅ | ✅ |
| RPMVault AI on the selected bike and garage context | ✅ | ✅ |
| Bilingual UI (EN / TR) and costs in TRY, EUR, GBP, USD | ✅ | ✅ |
| Premium (App Store / Google Play, entitlement on web) | ✅ | ✅ |

Premium is optional. It raises RPMVault AI and PDF export quotas. AI answers are informational and are not a substitute for a mechanic.

## Tech stack

| Layer | Technology |
| --- | --- |
| Web | Next.js 14, React Server Components, Tailwind CSS 4, shadcn/ui |
| Mobile | Expo SDK 54, React Native 0.81, React Navigation 7 |
| Language | TypeScript, shared across web, mobile, and domain logic |
| API | Node.js, Express 5 |
| Database | MongoDB Atlas |
| Auth | Firebase Authentication: email, Google, Sign in with Apple |
| Data fetching | TanStack Query v5 |
| Forms and validation | React Hook Form, Zod |
| Payments | Apple In-App Purchase and Google Play Billing, verified on the server |
| Logging | Pino |
| Mobile release | Expo EAS Build |
| Deployment | Vercel for the web app and the API |
| Workspace | pnpm workspaces: web, mobile, shared domain |

## In production

- Live web app, iOS app, and Android app
- One account across all three
- English and Turkish
- Costs in TRY, EUR, GBP, and USD
- 18,000+ public catalogue records across 80+ brands

## Architecture

```
Web (Next.js)     ─┐
                   ├─ HTTPS, signed-in requests ─► API (Node / Express on Vercel)
iOS / Android     ─┘                                      │
                                                          ├─ MongoDB Atlas
                                                          ├─ Firebase Auth
                                                          └─ App Store / Play billing
```

**Shared package.** Web and mobile consume the same TypeScript package for domain types, the API client, garage analytics, the maintenance calendar model, and ride-profile matching.

**Garage.** Mileage, fuel, service, and expenses stay on the motorcycle you own. A PDF report packages that history. On iOS and Android, upcoming maintenance can also be written to the device calendar.

**RPMVault AI.** Questions run against the selected motorcycle and a short garage summary (mileage, maintenance, fuel, expenses). Answers are for information, not workshop advice.

**Privacy.** Private garage data is available only to a signed-in account. Implementation details stay with the private source.

**Client cache.** TanStack Query v5 keeps garage and catalogue views consistent after writes.

**SEO.** Dynamic sitemap, JSON-LD, and meta coverage in English and Turkish.

## About

RPMVault is an independent product. I design, build, ship, and maintain it: architecture, clients, API, store listings, and operations.

[![Web](https://img.shields.io/badge/Open-rpm--vault.com-orange?style=for-the-badge&logo=vercel)](https://rpm-vault.com)
[![App Store](https://img.shields.io/badge/Download-App%20Store-black?style=for-the-badge&logo=apple)](https://apps.apple.com/tr/app/rpmvault-motorcycle-garage/id6799125794)
[![Google Play](https://img.shields.io/badge/Download-Google%20Play-green?style=for-the-badge&logo=google-play)](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault)

_This repository is a public engineering showcase: README and screenshots only. Source code is private. All rights reserved._
