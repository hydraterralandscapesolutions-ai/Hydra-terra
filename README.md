# Hydra-Terra

Single-page, animated landscape solutions site for HYDRA-TERRA. Voice-enabled AI personas (Hydra, Terra, Sol) guide visitors. Static build—no bundler.

## 🌐 Live
- Production: https://HYDRA-TERRA.COM.AU
- GitHub Pages: https://hydraterralandscapesolutions-ai.github.io/Hydra-terra/

## 🚀 Deployment
- Branch: `main`
- GitHub Actions: `.github/workflows/deploy-pages.yml` publishes the repo root (includes `CNAME`).
- CI: `.github/workflows/ci.yml` runs htmlhint, serves on :8000, then linkinator.

## 🔧 Local Dev
- Python: `python3 -m http.server 8000 --directory /workspaces/Hydra-terra`
- Node: `npm start` (uses existing http-server dependency)

## 📋 Notes
- Custom domain is set via `CNAME` with `hydra-terra.com.au`.
- Keep QR social buttons, wide logo banner, "Coming Soon" gallery cards, and female voices (Terra Australian priority).
- Contact: +61 426 398 510; socials use handle @hydraterra.com.au.
