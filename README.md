# tools.qewer.dev

Static browser tool pages, deployed to GitHub Pages at `tools.qewer.dev`.

## Pages

- `/` — index with links to all tools
- `/bgremove/` — background removal, runs client-side (`@imgly/background-removal` via CDN, ONNX/WASM in-browser)
- `/qrcode/` — QR code generator (`qrcode-generator` via CDN)

Each page is a self-contained single file (`inline CSS + JS`, dependencies from CDNs) in its own folder as `index.html` for clean URLs.

All pages share a light/dark theme (toggle top-right, persisted in `localStorage` under `tools-theme`, defaults to the system preference) via an inline copy of the same CSS variables.

## Setup

1. Create the GitHub repo (e.g. `qewer33/tools`) and push this directory:
   ```
   git remote add origin git@github.com:qewer33/tools.git
   git add -A && git commit -m "Initial tools" && git push -u origin main
   ```
2. Repo Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`
3. Repo Settings → Pages → Custom domain: `tools.qewer.dev` (CNAME file is already present), then tick **Enforce HTTPS** once the certificate is issued
4. DNS: add a CNAME record `tools.qewer.dev` → `qewer33.github.io`
