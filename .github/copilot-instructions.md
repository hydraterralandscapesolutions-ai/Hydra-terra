# Copilot Instructions

## Project Overview
Hydra-Terra is a single-page, animated landscaping site with three AI personas (Hydra, Terra, Sol) and voice-enabled chat. It is static, runs from the repo root, and deploys via GitHub Pages on `main` with the custom domain `hydra-terra.com.au` (CNAME).

## Constraints
- **No new npm installs**; use existing deps only (http-server, htmlhint, linkinator). Libraries via CDN/script tags.
- **Stack**: Vanilla HTML/CSS/JS, GSAP via CDN, Web Speech API for voice. No bundlers/build tools.
- **Hosting**: GitHub Pages, deploys from `main` with `CNAME` present.

## Core Features
- Hero with animated logo, parallax accents, CTA buttons.
- Three chatbots: Hydra (design), Terra (maintenance; Australian female voice priority), Sol (sustainability). Auto-greeting after ~3s; typing indicators; short replies with quick-action buttons.
- Bot avatar selector that pops in; glassy panels; glow/gradient accents.
- Social hub with QR-code buttons (WhatsApp, Instagram, Facebook, TikTok, Google); pulse/glow hover.
- Gallery cards marked "Coming Soon"; irrigation planning/installation copy; no composting references.
- Wide logo banner (16:4 aspect, contain) with figure-like bot avatars.

## Design & Motion
- Palette: bg #0b1220, text #e8eefc, cards #1f2937; accents Hydra #3b82f6, Terra #16a34a, Sol #f59e0b.
- Use `clamp()` typography, flex/grid layouts; glassmorphism on floating panels; meaningful staggered animations.
- Performance: favor `transform`/`opacity`, respect `prefers-reduced-motion`, light gradients and shadows.

## Assets & Content
- Logos at root (logo_*.png), icons; QR PNGs at root. Bot avatars use existing illustrated styles.
- Custom domain: `hydra-terra.com.au` stored in `CNAME` (uppercase filename).
- Contact number: +61 426 398 510; social handle `@hydraterra.com.au` where applicable.

## Dev Workflow
- Local quickstart: `npm start` (http-server) or `python3 -m http.server 8000 --directory /workspaces/Hydra-terra`.
- Checks: `npx htmlhint "**/*.html"`; `npm run serve &` then `npx wait-on http://localhost:8000`; `npx linkinator http://localhost:8000 --recursive --silent`.
- Deployment: Push to `main` → CI (lint/link) → Pages → custom domain.

## Practices
- Keep HTML semantic; add alt text; maintain responsive/mobile-first layout.
- Avoid new assets >1MB; prefer WebP if adding photos; keep QR/branding as-is.
- Preserve voice logic (female voices; Terra prefers en-AU). Keep QR backgrounds and "Coming Soon" gallery labels.
