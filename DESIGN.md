# Design System: CRYMAD CA$H
**Project ID:** 9505690438983037118
**Design System:** Emerald Pulse — "Bioluminescent Sovereignty"
**Anchor Screen:** `/dashboard` ([.stitch/designs/dashboard.html](.stitch/designs/dashboard.html))

---

## 1. Visual Theme & Atmosphere

CRYMAD CA$H inhabits a **deep-ocean bioluminescent laboratory** — a fantasy-futuristic fintech habitat where interface elements feel suspended in viscous, pressurized dark matter rather than placed on a flat canvas. The mood is *alive, breathing, and chemically reactive*: four slow-morphing organic blobs drift behind everything at sub-perceptual speeds, fine diagonal energy-streams etch the background at 5% opacity, and every numeric readout pulses subtly like a piece of sentient financial hardware.

This is explicitly **not** dark mode as aesthetic — it is darkness as a medium in which light is generated from within. The density sits in a deliberate middle ground: generous negative space at the macro level (1280px centered canvas, 88/64px vertical gutters, 32px between major sections) while micro-surfaces layer with intentional asymmetry and translucent overlap. The dominant sensation is "holding a piece of hardware from the year 2099" — sci-fi without cheese, premium without corporate sterility.

Key atmospheric signatures:
- **Living background canvas** — 4 blurred 300–600px emerald/teal blobs drifting at opacity 0.3, blur 80px
- **Breathing conic SVG rings** around the three wallet capsules (E-Wallet, Crypto, Card) connected by dashed flow lines
- **Glass morphism everywhere** — never solid panels, always translucent `rgba(44,55,51,0.4)` at `blur(20px)`
- **Gradient text as data flow** — emerald→teal fills every heading to represent energy moving through the interface
- **Pulse dots and animated rings** — status indicators breathe at 5s loops rather than snapping between states

---

## 2. Color Palette & Roles

### Backgrounds (Surface Hierarchy — "Deep Water Floating Up")
| Descriptive Name | Hex | Role |
| --- | --- | --- |
| Abyssal Emerald-Black | `#040d0a` | Absolute canvas floor — the deepest point of the interface, used only for the `<body>` substrate |
| Deep-Sea Charcoal-Green | `#0b1512` | Primary page surface (`background`, `surface`, `surface-dim`) — the "water" all content floats in |
| Trench Slate | `#06100d` | `surface-container-lowest` — reserved for the darkest nested wells |
| Kelp Shadow | `#131e1a` | `surface-container-low` — the first step upward from the canvas for subtle sectioning |
| Moss Fog | `#17221e` | `surface-container` — default glass panel substrate before opacity is applied |
| Tide Stone | `#222c29` | `surface-container-high` — hovered/active glass panels, "ignited" interaction state |
| Reef Mineral | `#2c3733` | `surface-container-highest` / `surface-variant` — the brightest ambient layer, used at 40% opacity as the `.glass-panel` base |
| Living Rock | `#313b38` | `surface-bright` — rare, used for selected-list "lift" states |

### Brand & Accent (Bioluminescent Core)
| Descriptive Name | Hex | Role |
| --- | --- | --- |
| Electric Emerald | `#10b981` | `primary-container` — the load-bearing brand anchor; borders, gradient origin, signature glow color |
| Bioluminescent Jade | `#4edea3` | `primary` / `primary-fixed-dim` — the "lifeblood" hotspot color for icons, active nav, pulse dots, active ring segments |
| Teal Aura | `#34d399` | Gradient terminus — paired with Electric Emerald in every gradient heading and on-hover button fill |
| Reef Mint | `#45dfa4` | `secondary` — supporting aura color on secondary chips and breathing ring midtones |
| Plankton Glow | `#6ffbbe` | `primary-fixed` — ultra-bright highlight, reserved for text on hover or pinnacle-of-glow moments |
| Molten Amber | `#f59e0b` | `tertiary` accent — "hot" financial data: outgoing amounts, warnings, gas fees, swap indicators. Used sparingly |
| Flare Orange | `#ffb95f` | `tertiary-fixed-dim` — softer amber on tertiary labels and icons |
| Warning Coral | `#ffb4ab` | `error` — negative transaction amounts, destructive actions, failure states |

### Text & Outlines
| Descriptive Name | Hex | Role |
| --- | --- | --- |
| Arctic Mist | `#d9e5df` | `on-surface` / `on-background` — primary body text (never `#ffffff`) |
| Sea-Glass Gray | `#bbcabf` | `on-surface-variant` — secondary/metadata text, muted labels, timestamp captions |
| Moss Outline | `#86948a` | `outline` — faint dividers, rare structural borders |
| Ghost Border | `#3c4a42` | `outline-variant` — used at 10–30% opacity as the near-invisible "ghost border" around floating glass panels |

### Signature Color Rules
- **Gradient Headings** always use `linear-gradient(to right, #10b981, #34d399)` with transparent webkit text fill — the gradient *is* the brand signature
- **Glass panels** always use `rgba(44, 55, 51, 0.4)` background + `1px solid rgba(16, 185, 129, 0.08)` border + `backdrop-filter: blur(20px)`
- **Never use pure white** — `#d9e5df` is the absolute brightest allowed text color
- **Outgoing money is coral** (`#ffb4ab`), **incoming is jade** (`#4edea3`), **swaps are amber** (`#ffb95f`)
- **Interactive glows** layer as `box-shadow: 0 0 20px rgba(16, 185, 129, 0.15)` on hover — never a Y-axis lift

---

## 3. Typography Rules

Three font families carry three distinct roles — the hierarchy is non-negotiable and reinforces the "System Info vs Interface Narrative" separation from the design-system spec.

- **Inter** (body & headline): 400 / 600 / 800 weights. Handles all narrative text — page headings, card titles, button labels, body copy. Headings always use weight 800 with the emerald→teal gradient fill.
- **JetBrains Mono** (data layer): 400 / 700 weights. **Mandatory** for every numeric value, transaction hash, wallet address, account tier, timestamp, asset ticker, and system-status readout. If it is a number or a machine-readable identifier, it is mono. This is how the interface signals "System Info" vs "Interface Narrative."
- **Space Grotesk** (label accent): 400 / 500. Reserved for technical metadata chips and rare small uppercase labels.

**Hierarchy of Authority:**
- **Display** — `text-3xl` (30px) Inter 800 gradient, tracking-tight, leading-none — reserved for user identity headings ("Joseph Obasi")
- **Title** — `text-xl` (20px) Inter 800 gradient — section headings like "Recent Activity"
- **Body** — `text-sm` (14px) Inter 600 `#d9e5df` — transaction titles, card paragraphs
- **Caption** — `text-xs` (12px) Inter 400 `#bbcabf` — secondary copy, muted descriptions
- **Label Tech** — `text-[10px]` JetBrains Mono, uppercase, `tracking-widest` (0.2em) — wallet category labels ("E-WALLET"), system strip readouts ("SYSTEM OPERATIONAL")
- **Data** — `text-2xl` JetBrains Mono 700 — balances, security score
- **Micro Data** — `text-[10px]` JetBrains Mono 400 — transaction IDs, timestamps, email addresses

**Tracking rules:** gradient headings use tight tracking (`tracking-tight`), mono labels use extra-wide tracking (`tracking-[0.2em]`/`tracking-widest`). Mono is never sized below 10px in display UI, and never below 12px for long transaction strings (accessibility floor).

---

## 4. Component Stylings

### Glass Panels (the universal container)
Every meaningful surface in the system is a **GlassCard**. Never a solid fill.
- Background: `rgba(44, 55, 51, 0.4)` (Reef Mineral at 40%)
- Backdrop filter: `blur(20px)`
- Border: `1px solid rgba(16, 185, 129, 0.08)` — the "ghost border"
- Radius: `rounded-lg` = **2rem (32px)** on main cards, `rounded-[DEFAULT]` = **1rem (16px)** on smaller cards, `rounded-xl` = **3rem (48px)** for hero containers, `rounded-full` (9999px) for pill-shaped timeline rows and chips
- On hover: the glass "ignites" — background opacity lifts toward `surface-container-high`, ghost border intensity climbs from 10% → 30%, optional emerald glow `0 0 20px rgba(16, 185, 129, 0.15)` appears. **Never translate upward on Y.**

### Buttons
- **Primary action button** — no solid background. `1px` border of `primary-container` (Electric Emerald), JetBrains Mono label, tracking-widest, uppercase. On hover, fills with `linear-gradient(to right, #10b981, #34d399)` and text flips to `on-primary` (#003824). Example: `COMPLETE YOUR SETUP`.
- **Quick-action glass button** — full glass panel, icon stacked above a mono uppercase label (SEND / RECEIVE / SWAP / PAY). Icon uses Material Symbols Outlined at `text-2xl`, primary color. On hover, background tints to `bg-primary/10`, icon scales to 110%, glow shadow ignites.
- **Tertiary / text link** — JetBrains Mono, primary color, with an arrow glyph `->` that nudges its margin-left on hover (e.g. `VIEW ALL ->`).
- **Ghost / icon-only** — Material Symbols in `on-surface-variant`, transitions to `primary` on hover. Used for nav bell and ring-wrapped avatar.

### Wallet Capsules (signature hero component)
The three circular orbs that define the dashboard:
- 128px outer container wrapping an 80px inner glass disc (`bg-surface-container-low` + glass-panel treatment)
- Material Symbols icon (32px) centered, primary color
- **Breathing conic SVG ring**: `viewBox="0 0 100 100"`, radius 45, stroke-width 2, two paths — a faint `rgba(16,185,129,0.1)` track and an active `#4edea3` arc with `stroke-dasharray="283"` and a rotating `stroke-dashoffset`
- Connected horizontally by a dashed SVG path `stroke-dasharray="8 8"` at `rgba(16,185,129,0.15)` — traveling glow dots optional along the path
- Below each capsule: 10px mono uppercase category label + 24px mono data balance with a smaller `USD` suffix in muted variant color

### Status Badges & Chips
- Pill shape (`rounded-full`), padding `px-2 py-0.5`
- JetBrains Mono, `text-[10px]`, uppercase
- Three standard variants:
  - **Neutral** (PERSONAL ACCOUNT): `bg-surface-container-high` + `border-outline-variant`, body text color
  - **Verified / positive** (KYC VERIFIED): `bg-primary/10` + `border-primary/20` + `text-primary`, paired with a tiny `w-1.5 h-1.5` `bg-primary` pulse dot using `animate-ping`
  - **Warning**: tertiary amber versions of the above using `bg-tertiary-container/20`

### Timeline / Activity Feed
Emphatically **not a table**. Vertical rail at `left-[19px]` (`before:w-[2px] before:bg-outline-variant/30`) with `space-y-4` between pill rows:
- Each row is a `rounded-full` glass panel
- 40px circular icon container on the left: `bg-primary/20` + `border-primary/30` for standard, `bg-tertiary-container/20` + `border-tertiary/30` for swap/warning
- Left cluster: bold 14px Inter title + 10px mono transaction hash (e.g. `TX: 0x82f...a12c`)
- Right cluster: mono bold amount in semantic color (`text-primary` positive / `text-error` negative / `text-tertiary` swap) + 10px mono timestamp
- Hover state: `bg-surface-container-high`

### Navigation & Shell
- **TopNav**: fixed 64px, `bg-emerald-950/40` + `backdrop-blur-xl` + `border-b border-emerald-500/10` + soft emerald shadow. Gradient wordmark left, centered horizontal nav with underline on active, bell + avatar right. Avatar wrapped in `border border-primary/20` ring.
- **Active nav item**: `text-emerald-400 font-bold border-b-2 border-emerald-400`
- **Theme Toggle Panel**: fixed right edge, `rounded-l-2xl`, 5 stacked circular swatches (active at 32px with ring-offset, inactive at 24px at 50% opacity), vertical "THEME" rotated-90deg mono label
- **Status Strip (footer)**: fixed 32px bottom, `bg-emerald-950/30` + `backdrop-blur-md` + top border at `emerald-500/5`. Left: pulsing `bg-emerald-500` dot with glow shadow + "SYSTEM OPERATIONAL". Right: live BTC / ETH / LAST SYNC readouts in 10px mono

### Inputs (projected — not present on dashboard)
Per the design system spec:
- Background-less, only a `surface-container-highest` bottom border
- On focus, bottom border expands to `2px` primary gradient and label pulses
- Never box-style inputs with full borders

---

## 5. Layout Principles

### Canvas & Rhythm
- **Max-width 1280px** centered main canvas, horizontal padding `px-4` (mobile) scaling to `px-8` (desktop)
- **Vertical rhythm**: `pt-[96px]` to clear the fixed TopNav + `pb-[64px]` to clear the Status Strip
- **Section gap**: `space-y-8` (32px) between major dashboard sections — profile → wallets → actions → split — creates the "pressurized suspension" feel without cramping
- **Grid rules**:
  - Wallet capsules: `grid-cols-1 md:grid-cols-3 gap-8` with SVG connector lines centered via absolute positioning
  - Quick actions: `grid-cols-2 md:grid-cols-4 gap-4`
  - Split section: `grid-cols-1 lg:grid-cols-3 gap-8` with activity feed spanning 2/3 (`lg:col-span-2`) and secondary column 1/3

### Radius Scale (Tailwind extension)
| Token | Value | Usage |
| --- | --- | --- |
| `DEFAULT` | 1rem (16px) | Small buttons, status chips, compact cards |
| `lg` | 2rem (32px) | Profile header, quick-action buttons, welcome card, security score card |
| `xl` | 3rem (48px) | Reserved for hero / future modal shells |
| `full` | 9999px | Timeline pill rows, badges, wallet capsules, avatar |

### Layering & Depth
- `z-[-2]` → living background canvas (blobs + diagonal lines)
- `z-0` → default content plane
- `z-10` → elevated icons inside timeline rail
- `z-40` → right-edge theme panel
- `z-50` → TopNav and Status Strip
- **No drop shadows** for structural elevation — only ambient radiance glows on interactive states. Floating modals (when introduced) use a dual-layer atmospheric shadow: `0 20px 40px rgba(4,13,10,0.5), 0 0 20px rgba(16,185,129,0.1)`

### Asymmetry & Overlap
Reject pure symmetric Bauhaus grids. Let gradient headings overlap glass containers visually, let blurred emerald halos from inside cards bleed past their radius (e.g. the welcome card uses `absolute -right-10 -bottom-10 w-40 h-40 bg-primary/10 rounded-full blur-3xl`), and allow the background canvas to read through every surface via blur rather than hide behind it.

### Motion Budget
- Background blobs: 60s+ loops (sub-perceptual)
- Breathing rings: 5s ease-in-out
- Pulse dots: `animate-pulse` / `animate-ping` on status and KYC indicators
- Entrance: every primary element fades up with stagger on mount
- Hover: 300ms transitions on all interactive elements — never instant snaps

---

## 6. Prompting Directives for Future Screens

When generating additional screens via Stitch `generate_screen_from_text`, every prompt **must** include the following anchor phrases to preserve coherence with the dashboard:

1. "Emerald Pulse dark mode, background `#040d0a`, primary `#10b981`, secondary `#34d399`, tertiary `#f59e0b`"
2. "Glass morphism panels: `rgba(44,55,51,0.4)` + `backdrop-filter: blur(20px)` + `1px solid rgba(16,185,129,0.08)` borders + `rounded-lg` (32px)"
3. "Living background: 4 organic blurred emerald/teal blobs drifting + faint diagonal energy lines at 5% opacity"
4. "Inter 400/600/800 for body and headings, JetBrains Mono 400/700 for all numeric data, transaction hashes, balances, and system readouts"
5. "Gradient headings use `linear-gradient(to right, #10b981, #34d399)` with transparent webkit text fill"
6. "Fixed 64px glass top nav (logo left, centered nav links, bell + avatar right) and fixed right-edge theme toggle panel with 5 swatches"
7. "Never pure white — body text is `#d9e5df`. Never solid button fills — always glass or gradient-on-hover"
8. "Use pulse dots, breathing SVG rings, and flowing dashed connectors — NOT static tables or plain boxes"
9. "Max-width 1280px centered canvas, `pt-[96px] pb-[64px] px-8`, `space-y-8` between major sections"
10. "Outgoing amounts in coral `#ffb4ab`, incoming in jade `#4edea3`, swaps in amber `#ffb95f`"

The atmosphere phrase that must survive every prompt: **"bioluminescent financial hardware, alive and breathing, not corporate SaaS."**
