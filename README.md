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
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Set your PIN

Open `portfolio.html` in a text editor and find this line near the top of the `<script>` block:

```js
const EDIT_PIN = '123456';
```

Replace `123456` with your preferred 6-digit code and save.

### 3. Open in your browser

```bash
open portfolio.html
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
portfolio.html   ← everything: markup, styles, and logic in one file
README.md
```

---

## Customisation

| What | Where |
|---|---|
| Your name | The `eyebrow` heading in the `<header>` |
| Bio text | Click bio while in edit mode, or edit the default string in `<script>` |
| Accent colors | CSS variables `--web-accent`, `--wp-accent`, `--ui-accent` |
| PIN | `const EDIT_PIN = '...'` in `<script>` |
| Thumbnail size | Adjust the `thum.io` URL parameters in `thumbUrl()` |

---

## License

MIT — feel free to fork and make it your own.