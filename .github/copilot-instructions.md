# Copilot Instructions

## Project Overview

**Hydra-Terra** is an interactive landscape company website featuring three AI chatbots (Hydra, Terra, Sol) with modern futuristic animations. Built for customer engagement with animated logos, interactive elements, and conversational AI experiences. **Admin device constraints: NO new npm installs, CDN-only libraries, vanilla JS.**

## Core Features & Sections

1. **Animated Hero**: Logo animations (GSAP/Three.js via CDN), parallax effects, interactive CTA buttons
2. **AI Bot Interface**: Three chatbots - Hydra (design), Terra (maintenance), Sol (sustainability) - conversational customer engagement
3. **Connect Hub**: Social links + animated QR codes that pulse/glow on hover
4. **Interactive Gallery**: Project showcase with scroll-triggered animations, lightbox/modal views
5. **Smart Inquiry Form**: Contextual questions based on bot conversation history
6. **Bot Avatar Area**: Floating/docked bot selector with character animations

## Animation & Interactivity Strategy

- **Logo Animation**: GSAP (CDN) for timeline-based logo reveals, morphing, or Three.js (CDN) for 3D rotating logos
- **Scroll Effects**: Intersection Observer API for scroll-triggered animations (fade-in, slide-up, parallax)
- **Hover States**: CSS transforms + transitions for cards/buttons; vanilla JS for complex interactions
- **Bot Interactions**: Modal or sidebar chat UI with typing indicators, message bubbles, smooth transitions
- **Performance**: Use `will-change`, `transform` (GPU-accelerated), lazy-load animations below fold

## Design & Animation Patterns

- **Color Palette**: Dark theme (#0b1220 bg, #e8eefc text), #1f2937 cards, #16a34a primary accent
  - **Bot Colors**: Hydra (#3b82f6 blue), Terra (#16a34a green), Sol (#f59e0b amber/gold)
- **Layout**: Flex/grid with `clamp()` typography; fluid spacing with `min()`, `max()`, `clamp()`
- **Motion Design**: 
  - Ease curves: `cubic-bezier(0.4, 0.0, 0.2, 1)` for smooth, natural motion
  - Duration: 0.3s for micro-interactions, 0.6-1.2s for hero animations
  - Stagger: 0.1s delay between gallery items, bot avatar reveals
- **Glassmorphism**: `backdrop-filter: blur(10px)` on bot panels, floating cards
- **Futuristic Accents**: Gradient borders, glow effects (`box-shadow` with accent colors), scan-line animations

## Bot Integration & Configuration

- **Bot Backend**: 
  - **Option 1 (Recommended)**: Client-side fetch to OpenAI/Claude API (user provides API key in browser or hardcode temporarily)
  - **Option 2**: Static decision tree initially (no API), upgrade to serverless function later
  - **Option 3**: Serverless (Vercel/Netlify Functions) if deploying beyond GitHub Pages
- **Bot Personalities**:
  - **Hydra**: Design consultant (hardscaping, irrigation, layout planning)
  - **Terra**: Maintenance expert (plant care, soil health, seasonal tips)
  - **Sol**: Sustainability advisor (native plants, water conservation, eco solutions)
- **Chat UI**: Vanilla JS modal/sidebar; CSS transitions; no React/Vue (cannot install)
- **Form Integration**: Pre-fill inquiry form with bot conversation context (localStorage for session data)
- **API Keys**: Prompt user or use `<script>` variable (temporary); serverless function ideal for production
- **Domain (CNAME)**: `HYDRA-TERRA.COM.AU` - preserve casing for GitHub Pages

## Asset Management

- **Logos**: logo_*.png at root; **prefer SVG** for crisp scaling and GSAP morphing animations
- **Bot Avatars**: Create hydra-avatar.svg, terra-avatar.svg, sol-avatar.svg with character illustrations
- **QR Codes**: Root level (whatsapp-qr.png, etc.); add CSS animations (pulse, glow) on hover
- **Project Photos**: `img/` folder, WebP format preferred (smaller size), fallback PNG/JPG
- **Animation Assets**: Lottie JSON files for complex animations (export from After Effects) in `animations/`
- **3D Models**: If using Three.js, store GLB/GLTF models in `models/` folder (keep under 500KB each)

## Developer Workflows

### Local Dev (Admin Device - NO New Downloads)
```bash
npm start  # Uses existing http-server on port 8000, cache disabled
# Alternative: python3 -m http.server 8000 --directory /workspaces/Hydra-terra
```

### Libraries via CDN (NO npm install - Use Script Tags)
```html
<!-- GSAP for animations (timeline, ScrollTrigger) -->
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/ScrollTrigger.min.js"></script>

<!-- Three.js for 3D logo effects -->
<script src="https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.min.js"></script>

<!-- Lottie for After Effects animations -->
<script src="https://cdn.jsdelivr.net/npm/lottie-web@5.12.2/build/player/lottie.min.js"></script>

<!-- All bot logic: vanilla JS, fetch API for OpenAI/Claude (API key in code or prompt user) -->
```

### Pre-Push Checks
```bash
npm run lint:html        # htmlhint validation (already installed)
npm start &              # Test animations/interactions locally
npm run check:links      # Linkinator recursive check (already installed)
# NO build step - everything loads via CDN, inline scripts, or static JS files
```

### CI/Deployment
- **CI** (`.github/workflows/ci.yml`): Node 18, htmlhint, linkinator (NO new dependencies)
- **Pages** (`.github/workflows/deploy-pages.yml`): Auto-deploy main branch from repo root (no build process)
- **Performance**: Manual Lighthouse test in browser DevTools (cannot add CI tools)
- **Network Constraints**: All external libraries via CDN; admin device cannot install packages

## Conventions & Constraints

- **CRITICAL: Admin Device Restrictions**
  - **NO npm install** for new packages (use existing: http-server, htmlhint, linkinator only)
  - **NO bundlers/build tools** (no Vite, Webpack, Parcel)
  - **Use CDN links** for all libraries (GSAP, Three.js, Lottie from jsdelivr/unpkg)
  - **Inline or external .js files** for custom code (no module bundling)
  - **Network unchanged**: Cannot modify network settings
- **Architecture**: Static HTML + vanilla JS + CDN libraries; keep everything browser-executable
- **Animation Performance**: 
  - Use `transform` and `opacity` (GPU-accelerated), avoid `width`/`height`/`top`/`left` animations
  - `will-change` sparingly (only active animations)
  - Reduce motion: Respect `prefers-reduced-motion` media query
- **Bot UX Principles**:
  - Initial greeting auto-appears after 3s on page
  - Show typing indicators (0.5-1.5s delay) for realistic feel
  - Keep responses under 2-3 sentences; offer actionable buttons
  - Allow users to switch bots mid-conversation
- **Accessibility**: 
  - Animations respect `prefers-reduced-motion`
  - Bot chat keyboard-navigable (Tab, Enter, Escape)
  - ARIA labels on interactive elements (`role="dialog"` for bot panel)
  - Color contrast 4.5:1 minimum on text
- **Mobile-First**: Animations scale down on mobile (fewer particles, simpler effects), bot UI slides from bottom
