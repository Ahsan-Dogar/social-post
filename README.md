<div align="center">

# 📱 Social Post AI

### The Open-Source AI Social Media Post Generator SaaS

**Generate platform-native social media posts for LinkedIn, Twitter/X, Instagram, Facebook, Reddit, and LINE in seconds.** A production-ready, self-hostable Next.js SaaS boilerplate with live platform mockups, multi-tone generation, publish intents, and built-in Stripe billing. A free open-source alternative to **Buffer AI, Jasper Social, Hootsuite OwlyWriter, Publer, and Copy.ai**.

[![Next.js](https://img.shields.io/badge/Next.js-14-000000?logo=nextdotjs&logoColor=white)]()
[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)]()
[![Prisma](https://img.shields.io/badge/Prisma-2D3748?logo=prisma&logoColor=white)]()
[![Stripe](https://img.shields.io/badge/Stripe-635BFF?logo=stripe&logoColor=white)]()
[![NextAuth](https://img.shields.io/badge/NextAuth-000000?logo=nextauth&logoColor=white)]()
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)]()
[![MIT License](https://img.shields.io/badge/license-MIT-green)]()

</div>

> **Tech stack:** Next.js 14 (App Router) · Prisma · PostgreSQL · NextAuth (Google OAuth) · Stripe · Tailwind CSS · MuAPI any-llm
>
> **Use cases:** Social media managers · Content creators · Marketing agencies · Influencers · Brand managers · Startup growth teams · E-commerce stores · Newsletter writers

---

## 🚀 Try the Live Engine

**Hosted Demo:** [social-post-woad.vercel.app](https://social-post-woad.vercel.app/)

Experience the full glassmorphic, responsive interface. Sign in with Google to explore the Studio, customize dropdowns (Language, Character Length, and Tones), and preview mock social feeds directly from your browser.

---

## 💡 Why Social Post AI?

Social Post AI is not just another wrapper — it's a **production-ready, highly-optimized AI web application**. Out of the box, it seamlessly manages User Authentication, Credits & Billing, Creations Persistence, and asynchronous AI generation polling using a sleek Next.js (App Router) architecture. It's the perfect starting point for your next AI SaaS.

- 🏭 **Production-Ready SaaS** — Complete with Google OAuth and Stripe Checkout workflows built-in.
- 🎛️ **Studio Control Center** — Customize dropdowns for platform type, tone of voice, language translation, and character constraints.
- 🖼️ **Dynamic Live Previews** — Tailor-made mockup cards for LinkedIn, Twitter/X, Instagram, Facebook, Reddit, and LINE.
- 🚀 **Real Publishing Intents** — Seamlessly launch composer windows pre-filled with your generated post copy with one click.
- 📱 **Responsive UX** — Dynamic sliding dropdowns, micro-animations, and complete mobile-stacked responsiveness.

![AI Social Post Generator Dashboard UI](https://cdn.muapi.ai/data/2/549775676598/Screenshot_2026-05-26_181917.png)

---

## ✨ Core Features

### 🎨 Kinetic Studio Panel
Input topics in an expanding textarea, select platforms, tones, and toggle advanced settings (**Include Emojis**, **Include Hashtags**, and **Include Title / Headline**).

### 🔽 Custom Dropdowns
Sleek custom selectors featuring chevron up/down animations, absolute overlays, and `overscroll-contain` wheel scroll-chaining preventions.

### 📲 Dynamic Platform Mockups
Tailor-made preview cards reflecting genuine social feeds:

- **LinkedIn** — Profile headers, like counts, and professional corporate styling.
- **Twitter / X** — X-premium checkmark badges, sleek black themes, tweet formatting, and 280-character limit alerts.
- **Instagram** — Styled visual placeholder frame banner, caption layouts, and heart counts.
- **Reddit** — Standard dark `r/socialpost` community headers, author tags, upvote/downvote arrows, and markdown titles.
- **LINE** — Broadcasting chat bubble framework with official brand icons and chat timestamps.

### 📤 Publishing Intent Gateway
Segmented choice for **Manual Copy** (to clipboard) vs. **Direct Publish** (launches mock OAuth connection stepper and pre-populates X/LINE/Reddit compose editors).

### 🗂️ History Archive
A persistent gallery with complete modal detail views, copies, and updates.

### 💳 Credit Tiers & Billing
Complete Stripe integration — deduct **4 credits ($0.02)** per generated post and route users to price tier panels (Basic, Standard, Pro, Business) to buy bundles.

---

## 🛠️ Tech Stack

| Layer    | Technology |
| -------- | ---------- |
| Framework | Next.js 14 (App Router) |
| UI       | React, Tailwind CSS |
| Database | PostgreSQL + Prisma |
| Auth     | NextAuth (Google OAuth) |
| Billing  | Stripe Checkout + Webhooks |
| AI       | MuAPI any-llm engine |

---

## 🌐 Deployment: Vercel & Production

Deploying an instance to the web requires minimal configuration — the architecture is engineered explicitly for **Vercel** serverless environments.

### One-Click Deploy

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Ahsan-Dogar/social-post)

> **Pro Tip:** Fork this repository to streamline deployments for your private forks.

### Required Environment Variables

| Service               | Variable                             | Description & Source                                                    |
| :-------------------- | :----------------------------------- | :---------------------------------------------------------------------- |
| **Database**          | `DATABASE_URL`                       | PostgreSQL connection string ([Supabase](https://supabase.com))        |
|                       | `DIRECT_URL`                         | Direct DB connection for Prisma migrations and pushes                   |
| **NextAuth / Google** | `NEXTAUTH_SECRET`                    | Secure random string via `openssl rand -base64 32`                      |
|                       | `NEXTAUTH_URL`                       | Your production domain                                                  |
|                       | `GOOGLE_CLIENT_ID`                   | [Google Cloud Console](https://console.cloud.google.com/apis/credentials) |
|                       | `GOOGLE_CLIENT_SECRET`               | [Google Cloud Console](https://console.cloud.google.com/apis/credentials) |
| **Stripe Billing**    | `STRIPE_SECRET_KEY`                  | [Stripe Dashboard](https://dashboard.stripe.com/apikeys)                |
|                       | `NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY` | [Stripe Dashboard](https://dashboard.stripe.com/apikeys)                |
|                       | `STRIPE_WEBHOOK_SECRET`              | Webhook secret for resolving credit purchases                           |
| **AI Generator**      | `MU_API_KEY`                         | [muapi.ai/access-keys](https://muapi.ai/access-keys)                    |
|                       | `WEBHOOK_URL`                        | Callback URL for slow-running generation events                         |

### Launching on Vercel: Step-by-Step

1. **Provision a database** — create a Postgres DB (Vercel Postgres, Supabase, or Neon) and grab `DATABASE_URL` and `DIRECT_URL`.
2. **Import your fork** into the Vercel dashboard.
3. **Set environment variables** in the project settings.
4. **Deploy** — Vercel automatically runs `npm run build` (append `npx prisma db push &&` to the build command if needed).
5. **Set up integrations** — Google OAuth callback + Stripe webhook (`checkout.session.completed`).

---

## 🧑‍💻 Local Development

### Prerequisites

- [Node.js](https://nodejs.org/en/) (v18 or higher)
- A local PostgreSQL instance or a free cloud database URL

### Setup

```bash
# 1. Clone the repository
git clone https://github.com/Ahsan-Dogar/social-post.git
cd social-post

# 2. Install dependencies
npm install

# 3. Setup Environment
cp .env.example .env
# Open .env and insert your specific keys

# 4. Initialize Database Schema
npx prisma generate
npx prisma db push

# 5. Start the Development Server
npm run dev
```

The app should now be responsive on **http://localhost:3000**.

---

## 🗂️ Project Structure

```
social-post/
├── prisma/
│   └── schema.prisma          # Postgres tables: Users, Accounts, Creations
└── src/
    ├── app/                   # Next.js App Router
    │   ├── api/               # Backend routes (Stripe, MuAPI, Auth)
    │   ├── gallery/           # Completed user posts gallery
    │   ├── pricing/           # Tier checkout selection page
    │   ├── layout.js          # Head assets & metadata
    │   ├── globals.css        # Styling system & gradients
    │   └── page.js            # Main Studio generation interface
    ├── components/
    │   └── Navbar.jsx         # Collapsible responsive navigation
    └── lib/
        ├── prisma.js          # Shared ORM client singleton
        ├── auth.js            # Google OAuth callback options
        ├── config.js          # Platform metadata & price tiers
        └── services/          # user.js, billing.js, ai.js
```

---

## 📄 License

MIT Licensed.

---

## 🙏 Attribution

This project builds on the open-source [awesome-generative-ai-apps](https://github.com/Anil-matcha/awesome-generative-ai-apps) ecosystem, originally from [SamurAIGPT/social-post](https://github.com/SamurAIGPT/social-post). Huge thanks to the original creators for the foundation.

---

<div align="center">

⭐ **If Social Post AI helps you, please star the repo — it keeps the project alive!**

_Built for creators and builders by [Ahsan Dogar](https://github.com/Ahsan-Dogar)._

</div>