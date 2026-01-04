# Hydra-terra

A tiny static site (single-page) — no build step is required.

## Local development 🔧

- Quick (Python):

  ```bash
  python3 -m http.server 8000 --directory /workspaces/Hydra-terra
  # open http://localhost:8000
  ```

- Node (recommended for convenience):

  ```bash
  npm install
  npm start    # runs http-server on port 8000
  ```

## Deployment 🚀

This repository is configured to auto-deploy to **GitHub Pages** on pushes to `main` via a GitHub Actions workflow (`.github/workflows/deploy-pages.yml`). The workflow uploads the repo root as the Pages artifact, including the `CNAME` file if present.

If you'd like a different provider (Netlify/Vercel) or a build step added (e.g., using a static site generator), say the word and I can add it.