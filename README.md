# Jack K. Osei — Portfolio

Single-file portfolio website built with vanilla HTML/CSS/JS. Features project categories, live screenshot previews via thum.io, localStorage persistence, light/dark mode, and a `?edit` URL flag with 6-digit PIN for owner-only project management.

---

## Features

- **Three project categories** — Web App, WordPress, and UI/UX Design
- **Live screenshot previews** — thumbnails auto-generated from project URLs via [thum.io](https://thum.io) (no API key required)
- **PIN-protected edit mode** — visit `?edit` in the URL to unlock a 6-digit PIN pad; visitors see a clean, controls-free page
- **Light / Dark theme toggle** — preference saved to `localStorage`
- **Add & delete projects** — manage your portfolio entirely in the browser; data persists via `localStorage`
- **Zero dependencies** — single `.html` file, no build step, no framework

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/jackosei/lean-portfolio.git
cd lean-portfolio
```

### 2. Set your PIN

Your PIN is stored as a SHA-256 hash — the real number never appears in the code.

**Step 1** — Hash your chosen 6-digit PIN:

```bash
# Mac / Linux
echo -n "YOUR_PIN" | sha256sum

# Or use the online tool:
# https://emn178.github.io/online-tools/sha256.html
```

**Step 2** — Open `index.html` and paste the resulting hash:

```js
const EDIT_PIN_HASH = 'paste_your_hash_here';
```

### 3. Open in your browser

```bash
open index.html
```

Or just double-click the file — no server required.

---

## Deploying

Since it's a single static file, it works on any static host:

| Host | Steps |
|---|---|
| **GitHub Pages** | Push to repo → Settings → Pages → Deploy from branch |
| **Netlify** | Drag and drop the `.html` file into the Netlify dashboard |
| **Vercel** | `vercel --prod` from the project folder |

---

## Using Edit Mode

1. Navigate to your portfolio URL with `?edit` appended — e.g. `https://yoursite.com?edit`
2. A PIN pad will appear — enter your 6-digit PIN
3. Edit controls unlock: add projects, delete projects, edit your bio
4. To exit, simply reload the page without the `?edit` flag

> Visitors browsing the normal URL will never see the edit controls or any hint of the PIN system.

---

## Project Structure

```
index.html   ← everything: markup, styles, and logic in one file
README.md
```

---

## Customisation

| What | Where |
|---|---|
| Your name | The `eyebrow` heading in the `<header>` |
| Bio text | Click bio while in edit mode, or edit the default string in `<script>` |
| Accent colors | CSS variables `--web-accent`, `--wp-accent`, `--ui-accent` |
| PIN | Hash your PIN via `sha256sum`, paste into `const EDIT_PIN_HASH` |
| Thumbnail size | Adjust the `thum.io` URL parameters in `thumbUrl()` |

---

## License

MIT — feel free to fork and make it your own.