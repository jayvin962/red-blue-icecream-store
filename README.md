# 🍦 Red & Blue Ice Cream — Quick Commerce Frontend

A production-ready React + TypeScript quick-commerce frontend for Red & Blue Ice Cream.

## Tech Stack

| Tool | Purpose |
|------|---------|
| Vite 5 | Build tool |
| React 18 | UI framework |
| TypeScript | Type safety |
| React Router v6 | Lazy-loaded routing |
| Zustand | Cart + lang state with localStorage |
| canvas-confetti | Payment success animation |
| Lucide React | Icons |
| CSS Modules | Scoped styles |

## Getting Started

```bash
# 1. Install dependencies
npm install

# 2. Set your API URL
cp .env.example .env
# Edit .env and set VITE_API_URL=http://your-backend:3000

# 3. Run dev server
npm run dev

# 4. Build for production
npm run build
```

## Project Structure

```
src/
├── components/
│   ├── layout/        # Navbar
│   ├── product/       # ProductCard
│   ├── cart/          # FloatingCart
│   └── ui/            # Spinner, Skeleton, Error, Empty states
├── pages/
│   ├── Home.tsx           # Catalog with category filter + search
│   ├── ProductDetail.tsx  # Full product info + related
│   ├── Checkout.tsx       # Order form + cart summary
│   ├── OtpVerify.tsx      # 6-digit OTP with auto-focus + resend
│   └── OrderTracking.tsx  # Visual timeline + pay button
├── store/
│   └── index.ts       # Zustand: cart, language, pending order
├── utils/
│   ├── api.ts         # API calls with mock fallback
│   └── confetti.ts    # Canvas confetti helper
├── i18n/
│   └── translations.ts # English + Hindi strings
├── types/
│   └── index.ts       # All TypeScript types
└── styles/
    └── globals.css    # Design tokens + global CSS
```

## API Endpoints

| Method | Path | Purpose |
|--------|------|---------|
| GET | /api/catalog | List all products |
| GET | /api/catalog/:id | Single product + related |
| POST | /api/order | Place order → returns orderRef |
| POST | /api/order/verify | Verify OTP |
| POST | /api/order/resend-otp | Resend OTP |
| GET | /api/track/:order_ref | Order tracking data |

> **Mock mode:** If `VITE_API_URL` is empty or the API is unreachable, all calls gracefully fall back to realistic mock data so you can develop the frontend independently.

## Features

- 🌙 Dark glassmorphism theme with `#7C6FE9` purple + `#34D399` green
- 📱 Mobile-first 2-col grid → 4-col on desktop
- 🌐 English / Hindi toggle (custom i18n, persisted)
- 🛒 Cart with localStorage persistence via Zustand
- ⚡ Lazy-loaded routes via React.lazy + Suspense
- 🎉 Confetti on successful payment
- ⌛ OTP auto-focus, paste support, 30s resend countdown
- 📦 Visual order status timeline
- 💳 Pay Now button when order is accepted

## Design System

| Token | Value |
|-------|-------|
| `--purple` | `#7C6FE9` |
| `--green` | `#34D399` |
| `--bg` | `#0d0d14` |
| `--font-display` | Playfair Display |
| `--font-body` | DM Sans |
