---
project: Crymad Cash
stitch_project_id: TBD
device_type: DESKTOP
---

# Crymad Cash — Site Vision

## 1. Product Identity

**Name:** CRYMAD CA$H
**Tagline:** Digital Finance Platform
**Category:** Fantasy-futuristic fintech digital banking dashboard
**Logo:** https://res.cloudinary.com/dxvi5d6dr/image/upload/v1766762874/photo_2025-12-24_18.04.43-removebg-preview_ck9wyx.png

Crymad Cash is a unified digital banking experience that fuses a fiat e-wallet, a multi-chain custodial crypto wallet, and a Mastercard-backed physical/virtual card product into a single interface. The brand vibe is "living" — animated organic backgrounds, breathing SVG rings, flowing connection lines, and glass-morphism surfaces. It should feel like a piece of bioluminescent Web3 hardware, not a corporate SaaS dashboard.

## 2. Design Vibe (non-negotiable)

- **Fantasy futuristic fintech** — NOT generic AI/corporate slop
- **Dark mode (Emerald Pulse):** bg `#040d0a`, primary `#10b981`, secondary `#34d399`, accent `#f59e0b`
- **Light mode (Arctic Light):** bg `#f0f5fa`, primary `#0d9488`, secondary `#2563eb`
- **Glass morphism:** `backdrop-filter: blur(20px)`, borders `rgba(primary, 0.08)`, radius 20px on large cards, 12–16px on smaller ones
- **Living background:** 4 organic blob shapes morphing + drifting, bioluminescent particles floating upward, faint energy stream lines
- **Breathing rings:** SVG conic rings around wallet capsules, 5s ease-in-out loop
- **Flowing connectors:** dashed lines between wallet capsules with traveling dots
- **Gradient text:** headings use `linear-gradient(var(--primary), var(--secondary))` with `-webkit-text-fill-color: transparent`
- **Entrance anims:** every primary element fades up with stagger on mount
- **Transaction feeds:** vertical timeline with pulse dots — NOT boring tables (tables are for detailed tabular pages only)
- **Card visuals:** holographic shimmer, dark gradient, embossed Mastercard mark
- **Hover dropdowns:** tooltip-style with triangle arrow + slide-up transform
- **Sci-fi / Web3 energy** — subtle, never cheesy
- **Fonts:** `Inter` 300–800 for body & headings, `JetBrains Mono` 400–700 for balances, transaction IDs, and all numeric data
- **Theme toggle:** moon ↔ sun with rotation animation

Reference file: `reference-design.html` at project root is the canonical visual benchmark — every generated page must match its atmosphere.

## 3. Global Layout

- Fixed top nav (64px, glass): logo left, horizontal nav items center, bell + avatar right
- Fixed theme toggle panel on right edge (5 theme swatches)
- Main content: `max-width: 1280px`, centered, `padding: 88px 32px 100px`
- Animated `.bg-canvas` behind everything (z-index 0), all content z-index 1+
- Bottom status strip (optional) with live system indicators

## 4. Sitemap

Legend: `[ ]` pending · `[x]` generated · `[~]` in progress

### Auth & Onboarding
- [ ] `/login` — Login: CRYMAD CA$H logo centered, email input, password with show/hide toggle, "Forgot Password?" link, green "Sign In" button, "Create Account" link, glass card on dark animated background
- [ ] `/register` — Registration: Personal/Business pill toggle, email, password with strength bar (red/yellow/green), confirm password, Privacy Policy + Terms checkboxes, business fields conditional (company name, reg number, type dropdown), "Sign Up" button
- [ ] `/register/verify-email` — Email verification: large envelope SVG icon, "Check Your Email" heading, email in monospace, "Resend Email" button with 60s countdown, decorative floating particles
- [ ] `/register/complete` — 3-step profile completion: step dots indicator, Step 1 name + DOB, Step 2 phone with country code + full address, Step 3 language selector + profile summary card
- [ ] `/register/kyc` — KYC verification: animated pulsing shield icon, "Identity Verification" heading, status badge, 3 info cards (5 min, Gov ID, 48hrs), "Start Verification" button, "Skip" link
- [ ] `/forgot-password` — Password reset: lock icon, email input, "Send Reset Link" button, success state with email icon
- [ ] `/login/verify-2fa` — Two-factor auth: 6 individual digit inputs in a row with auto-focus, "Verify" button, 30s resend countdown

### Core Dashboard
- [ ] `/dashboard` — Main dashboard: profile card (avatar, "Joseph Obasi", email, PERSONAL ACCOUNT badge, KYC verified dot), wallet capsules (3 circular orbs with breathing SVG rings — E-Wallet $0.00, Crypto $0.00, Card $0.00 — connected by flowing lines), quick action buttons (Send, Receive, Swap, Pay), activity timeline feed (5 transactions with status dots), welcome card

### Wallets
- [ ] `/e-wallet` — E-Wallet: wallet header with balance, 4 action buttons (Transfer, Bank, Crypto, Card), transaction table (7 rows: ID, Reference, Amount colored, Fee, Email, Status badge, Date), filter dropdown + search, modals for each action
- [ ] `/e-wallet/beneficiaries` — Beneficiaries: table (Name, Bank, masked Account, Currency, Status), "Add Beneficiary" button, add/edit/delete modals, empty state
- [ ] `/crypto` — Crypto wallet: balance header, 2 rows of action buttons (Deposit, Withdraw, Buy, Sync + Card, Bank, Swap), 6 custodial wallet cards (BTC, ETH, USDT, USDC, SOL, BNB with real CoinGecko icons), deposit addresses with copy buttons, transaction table, 6 modals

### Cards
- [ ] `/cards` — Cards: KYC gate (3 states), Physical card visual (dark gradient, Mastercard logo, masked number, name, expiry, balance) + Virtual card, per-card actions (Load, Lock, Activate, Details), transaction table, 4 modals (Load with OTP, Lock, Activate with 16-digit input, Credentials with 30s auto-hide)
- [ ] `/cards/setup` — Card account setup: full KYC form (names, gender, DOB, occupation, phone, full address)
- [ ] `/cards/order` — Order card: Virtual vs Physical selection cards, fee quote breakdown, wallet source, OTP step, success state
- [ ] `/cards/fees` — Fee schedule: 4 tables (Order, Load, Transaction, Other fees with amounts and descriptions)

### Activity & History
- [ ] `/orders` — Orders: Pending/Completed tabs, orders table (Order Number, Status, Amount, Title, Total, Date), order detail modal with items + payment timeline, refund modal
- [ ] `/transactions` — Transactions: 4 sub-tabs (Internal/Crypto/Bank/Cards), table with 6+ rows per tab, filter + search, transaction detail modal with status timeline and crypto TxHash
- [ ] `/subscriptions` — Subscriptions: Pending/Active/Completed tabs, full table (Reference, Status, Product, Cost, Fees, Total, Interval, etc.), detail modal with payment history + cancel flow
- [ ] `/reports` — Reports: date range filters, transaction type + wallet type dropdowns, 4 summary cards (Inflow/Outflow/Net/Count), report table, "Export CSV" button

### Banking
- [ ] `/banking` — Banking portal: "Welcome to Personal Banking" heading, 6 benefit cards (Payable, Receivable, Treasury, On/Off Ramp, Remittance, Global Payments), subscription modal ($9 + $4.95/mo), payment modal with fee breakdown
- [ ] `/banking/dashboard` — Banking dashboard: account info (number, routing, SWIFT), 6 feature cards with "Coming Soon" badges, recent activity

### Support & Notifications
- [ ] `/help` — Help/FAQs: search bar, 5 category tabs (General/E-Wallet/Banking/Crypto/Cards), accordion FAQ with 6 items per category (30 total), contact support card
- [ ] `/notifications` — Notifications: filter (All/Read/Unread), 6 notification cards with colored left borders (Payout green, Card blue, KYC amber, Security red, System gray, Crypto green), click to expand

### Business Tools
- [ ] `/team` — Team management: table (5 members with roles Admin/Manager/Viewer/Accountant), invite modal, batch import, edit role, remove
- [ ] `/payouts` — Payouts: 4 tabs (Pending/Processing/Completed/Cancelled), table with Approve/Reject buttons on pending, create payout modal, batch payout, detail modal with timeline
- [ ] `/recurring-payments` — Recurring: card-based layout (4 cards with recipient, amount, cycle badge, next date, Pause/Edit/Cancel), create/edit/cancel modals
- [ ] `/rewards` — Rewards: prominent balance card ($1,250), 3 tabs (Payouts/Debits/History), issue/batch/debit/refund modals

### Settings
- [ ] `/settings/api` — API Settings: masked API key with copy/regenerate, webhook config (URL + event checkboxes + test), webhook logs table, integration guide with Node.js/PHP/Python code snippets
- [ ] `/profile` — Profile modal: name, KYC status, account type, country, language, phone, email, edit/save toggle
- [ ] `/security` — Security modal: 2FA enable/disable, disable account with "type DISABLE" confirmation

## 5. Roadmap

Build order (baton picks from here top-down):

1. `/dashboard` — anchor page, establishes every shared primitive (nav, wallet capsules, timeline, profile card)
2. `/login` — first impression, pure brand expression
3. `/register` + `/register/verify-email` + `/register/complete` + `/register/kyc` — onboarding funnel
4. `/forgot-password` + `/login/verify-2fa` — auth edges
5. `/e-wallet` + `/e-wallet/beneficiaries` — primary money page
6. `/crypto` — second wallet, introduces chain cards
7. `/cards` + `/cards/setup` + `/cards/order` + `/cards/fees` — card product cluster
8. `/transactions` + `/orders` + `/subscriptions` + `/reports` — activity cluster
9. `/banking` + `/banking/dashboard` — banking cluster
10. `/notifications` + `/help` — support surfaces
11. `/team` + `/payouts` + `/recurring-payments` + `/rewards` — business tools
12. `/settings/api` + `/profile` + `/security` — settings surfaces

## 6. Creative Freedom (ideas pool)

When roadmap is empty, the loop may invent additional pages that fit the vision. Candidates:
- `/insights` — personal finance AI insights page with animated charts
- `/marketplace` — crypto buy/sell marketplace with live order book
- `/referrals` — referral program with invite tree visualization
- `/limits` — account limits & tier progression page with unlock timeline

## 7. Shared Primitives (every page must use these)

- **TopNav** (glass, fixed)
- **BgCanvas** (4 morphing blobs + particles)
- **GlassCard** (radius 20px, blur 20px, 1px border)
- **GradientHeading** (primary→secondary gradient fill)
- **StatusBadge** (pill, uppercase, 11px, tracked)
- **PrimaryButton** (solid primary, glow on hover)
- **GhostButton** (transparent, border, primary text)
- **PulseDot** (animated status indicator)
- **TimelineItem** (vertical rail with pulse dot + glass row)
- **ThemePanel** (right edge, 5 swatches)
