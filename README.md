# 🛒 বাজার দর (BazarDor)

### প্রয়োজনীয় পণ্যের দাম এক নজরে।

BazarDor is a Bangla-first market price tracker designed to help people across Bangladesh check the prices of everyday essentials. Explore daily price updates, discover which products have become more or less expensive, and compare prices across 12 bazaars in 6 divisions.

🔗 **Live Demo:** https://bazardor-sorna.vercel.app/

---

## ✨ Key Features

1. **📈 Live Price Ticker** — An infinitely scrolling ticker displays product prices and daily price changes. It pauses on hover and respects reduced-motion preferences.

2. **📊 Today's Price Movers** — Dedicated sections highlight the top 6 products with rising prices (আজ দাম বেড়েছে ▲) and falling prices (আজ দাম কমেছে ▼).

3. **🗂️ Smart Category Browsing** — Browse 8 product categories and sort products by default order, lowest price, or highest price. Bengali numerals are correctly converted for numerical sorting.

4. **🔍 Detailed Product Pages** — Authenticated users can explore minimum, maximum, and average prices, identify the cheapest and most expensive markets, compare historical prices, and view market-wise price tables.

5. **🔐 Secure Authentication** — Better Auth supports email/password registration and login, Google and GitHub authentication, protected routes, redirect-back behavior, and toast notifications.

6. **👤 Profile Management** — View account information, access profile settings, sign out, and update your name through a dedicated profile page.

7. **🇧🇩 Bangla-First Experience** — A Bengali interface featuring the Hind Siliguri font, Bengali numerals for prices and dates, and localized date formatting.

8. **📱 Responsive Design** — Optimized layouts for mobile, tablet, and desktop, with skeleton loaders, empty states, and a custom 404 page.

---

## 🛠️ Technologies Used

| Purpose           | Technology              |
| ----------------- | ----------------------- |
| Framework         | Next.js 16 (App Router) |
| Language          | TypeScript              |
| UI Library        | React 19                |
| Styling           | Tailwind CSS v4         |
| Component Library | DaisyUI 5               |
| Authentication    | Better Auth             |
| Database          | MongoDB                 |
| Notifications     | React Hot Toast         |
| Typography        | Hind Siliguri           |
| Data Source       | BazarDor REST API       |
| Deployment        | Vercel                  |

---

## 📄 Pages & Routes

| Route              | Description                                                             | Access         |
| ------------------ | ----------------------------------------------------------------------- | -------------- |
| `/`                | Homepage featuring price movers, the price ticker, and product listings | Public         |
| `/category/[slug]` | Category-specific products with sorting and loading states              | Public         |
| `/product/[slug]`  | Product price analysis and market-wise comparisons                      | Login Required |
| `/signin`          | Sign in with email/password or a supported OAuth provider               | Public         |
| `/signup`          | Create an account using email/password                                  | Public         |
| `/profile`         | View account information and sign out                                   | Login Required |
| `/profile/update`  | Update profile name                                                     | Login Required |
| Any unknown route  | Custom 404 page with a link to the homepage                             | Public         |

---

## 🚀 Getting Started

Follow these steps to run BazarDor locally.

### Prerequisites

Make sure you have the following installed:

* Node.js
* npm
* MongoDB database
* Google and GitHub OAuth credentials (if using social login)

### Installation

**1. Clone the repository**

```bash
git clone  https://github.com/sorna14-hub/BAZARDOR
```

**2. Navigate to the project directory**

```bash
cd Assignment_07
```

**3. Install dependencies**

```bash
npm install
```

**4. Configure environment variables**

Create a `.env` file in the project root and add the required variables listed below.

**5. Start the development server**

```bash
npm run dev
```

**6. Open the application**

Visit http://localhost:3000 in your browser.

---

## 🔑 Environment Variables

Create a `.env` file in the root directory.

| Variable                  | Description                    |
| ------------------------- | ------------------------------ |
| `BETTER_AUTH_SECRET`      | Secret key used by Better Auth |
| `BETTER_AUTH_URL`         | Base URL of the application    |
| `BETTER_AUTH_MONGODB_URL` | MongoDB connection string      |
| `GOOGLE_CLIENT_ID`        | Google OAuth client ID         |
| `GOOGLE_CLIENT_SECRET`    | Google OAuth client secret     |
| `GITHUB_CLIENT_ID`        | GitHub OAuth client ID         |
| `GITHUB_CLIENT_SECRET`    | GitHub OAuth client secret     |

Generate a secret for Better Auth using:

```bash
npx @better-auth/cli secret
```

For local development, set `BETTER_AUTH_URL` to:

```text
http://localhost:3000
```

For production, use your deployed application URL.

### OAuth Callback URLs

Configure the following callback URLs in your OAuth provider settings:

**Google**

```text
http://localhost:3000/api/auth/callback/google
```

**GitHub**

```text
http://localhost:3000/api/auth/callback/github
```

For production, replace `http://localhost:3000` with your deployed application URL.

> **Security Note:** Never commit your `.env` file, database credentials, OAuth secrets, or authentication secret to GitHub. Keep sensitive environment variables private.

---

## 📁 Project Structure

```text
BAZARDOR/
├── public/                     # Static assets
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   └── auth/
│   │   │       └── [...all]/   # Better Auth API routes
│   │   ├── category/
│   │   │   └── [slug]/         # Category pages
│   │   ├── product/
│   │   │   └── [slug]/         # Product details
│   │   ├── profile/
│   │   │   └── update/         # Profile update page
│   │   ├── signin/             # Sign-in page
│   │   ├── signup/             # Sign-up page
│   │   ├── globals.css         # Global styles and theme
│   │   ├── layout.tsx          # Root layout
│   │   └── page.tsx            # Homepage
│   ├── components/
│   │   ├── auth/               # Authentication components
│   │   ├── profile/            # Profile components
│   │   └── ...                 # Shared UI components
│   ├── lib/
│   │   ├── api.ts              # API utilities
│   │   ├── auth.ts             # Better Auth server configuration
│   │   ├── auth-client.ts      # Better Auth client
│   │   └── format.ts           # Bengali formatting utilities
│   └── proxy.ts                # Route protection
├── .env.example                # Environment variable template
├── package.json
└── README.md
```

---

## 🎨 Design & Localization

BazarDor focuses on accessibility and a familiar experience for Bangladeshi users.

* **Language:** Bangla-first user interface.
* **Typography:** Hind Siliguri.
* **Number Formatting:** Bengali numerals for prices, percentages, and dates.
* **Color Theme:** Custom `bazardor` theme using DaisyUI.
* **Responsive Layout:** Mobile, tablet, and desktop support.
* **Motion Accessibility:** The price ticker pauses on hover and respects reduced-motion preferences.

---

## 🔒 Authentication & Route Protection

BazarDor uses Better Auth to manage authentication.

* Email and password authentication.
* Google OAuth integration.
* GitHub OAuth integration.
* Protected product-detail pages.
* Protected profile and profile-update pages.
* Redirect-back support for protected routes.
* User feedback through toast notifications.

---

## 🌐 Live Application

Explore BazarDor here:

**https://bazardor-atik.vercel.app/**

---

## ⚠️ Disclaimer

Market prices may vary by location, vendor, product quality, and date. Prices displayed by BazarDor are indicative and should not be treated as guaranteed quotations.

---

### Built with ❤️ for Bangladesh 🇧🇩
