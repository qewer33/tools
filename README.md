# tools.qewer.dev

Static browser tool pages, deployed to GitHub Pages at `tools.qewer.dev`.

## Pages

- `/bgremove/` — background removal, runs client-side (`@imgly/background-removal` via CDN, ONNX/WASM in-browser)
- `/qrcode/` — QR code generator (`qrcode-generator` via CDN)

Each page is a self-contained single file (`inline CSS + JS`, dependencies from CDNs) in its own folder as `index.html` for clean URLs.

## Setup

1. Create the GitHub repo (e.g. `qewer33/tools`) and push this directory:
   ```
   git remote add origin git@github.com:qewer33/tools.git
   git add -A && git commit -m "Initial tools" && git push -u origin main
   ```
2. Repo Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`
3. Repo Settings → Pages → Custom domain: `tools.qewer.dev` (CNAME file is already present), then tick **Enforce HTTPS** once the certificate is issued
4. DNS: add a CNAME record `tools.qewer.dev` → `qewer33.github.io`
