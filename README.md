# RPMVault

> Your digital motorcycle garage. Track maintenance, fuel, mileage, and ownership costs, then explore and compare 18,000+ motorcycles on the web, iPhone, and Android.

Solo-built and in production: [web](https://rpm-vault.com), [iOS](https://apps.apple.com/tr/app/rpmvault-motorcycle-garage/id6799125794), and [Android](https://play.google.com/store/apps/details?id=com.ballioz.rpmvault). One account, English and Turkish. Source is private. This repo is the public engineering summary.

I built it because ownership usually lives in notes and memory. I wanted one place to log the bike I ride and compare the next one without switching products.

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

## What I shipped

Web, mobile, and API. Store releases. Billing. Bilingual copy and SEO. If it ships, I own it.

Three calls that keep the product one system:

- **Shared domain.** Web and mobile use the same TypeScript types, API client, and garage math, so a service interval does not drift between platforms.
- **Store billing, account entitlement.** Premium is purchased on iOS or Android. The server verifies the store. The same account sees it on the web. There is no second checkout.
- **Garage first.** Mileage, fuel, service, and expenses hang off the bike you own. Catalogue and compare sit in the same account.

| | Web | Mobile |
| --- | :---: | :---: |
| Garage, fuel, service, expenses, PDF report | ✅ | ✅ |
| Catalogue (18,000+ bikes) and side-by-side compare | ✅ | ✅ |
| RPMVault AI on the selected bike and garage context | ✅ | ✅ |
| Device calendar for upcoming maintenance | | ✅ |
| Premium (App Store / Play, entitlement on web) | ✅ | ✅ |

Premium is optional. It raises AI and PDF quotas. AI is informational, not a mechanic.

## Stack

| | |
| --- | --- |
| Web | Next.js 14, Tailwind CSS 4, shadcn/ui |
| Mobile | Expo SDK 54, React Native 0.81 |
| API | Node.js, Express 5, Vercel |
| Data | MongoDB Atlas, TanStack Query v5, Zod |
| Auth | Firebase: email, Google, Sign in with Apple |
| Billing | App Store and Google Play, verified on the server |

```
Web (Next.js)  ─┐
                ├─ HTTPS, signed-in requests ─► API (Node / Express)
iOS / Android  ─┘                                 │
                                                  ├─ MongoDB
                                                  ├─ Firebase Auth
                                                  └─ App Store / Play billing
```

Private garage data is available only to a signed-in account. Implementation details stay with the private source.

_README and screenshots only. Source is private. All rights reserved._
