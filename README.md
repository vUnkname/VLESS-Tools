# VLESS Tools

Single-page web toolkit for working with **VLESS** proxy configs: build multi-IP configs, extract addresses from config lists, and morph settings in bulk. No install, no backend — open an HTML file in any modern browser.

**Languages:** English · فارسی · Русский (switch in the header; preference saved in `localStorage`).

---

## Features

### 1. Config Builder (Generator)

- Paste one base `vless://` link; replace `@host:` with many IPs or CIDR ranges.
- **IP list** tab: manual input, drag & drop, or file import (`.txt`, `.csv`, `.log`, `.json`).
- **IP ranges** tab: CDN presets (Cloudflare, Fastly, Gcore) loaded online from [cdn-ip-ranges](https://github.com/vUnkname/cdn-ip-ranges); shuffle and limit output count.
- Large CDN ranges are auto-sampled to `/24` blocks.
- Split output into **parts** with configurable size; copy or download per part or all at once.
- Live metrics: expanded IP count, output configs, part count.

### 2. IP Extractor

- Parse VLESS links (or raw IP/CIDR lines) from a textarea.
- Optional **WS + TLS** filter (`type=ws` and `security=tls`).
- Extract **@address**, **sni=**, and **host=** fields.
- Optional CIDR → individual IP expansion.
- Duplicate IP report with copy action.

### 3. Config Morph

- Batch-transform many VLESS configs:
  - **Quick spoof mode:** redirect `@IP:Port` to a local address (127.0.0.1:40443 by default).
  - **Advanced mode:** toggle changes to Address, SNI, and HOST; rotate through a domain list.

### UI & UX

- Two visual themes: **CyberDeck** (CP2077 HUD) and **Simple** (minimal dark UI).
- Toast notifications for copy, build, and errors.
- Responsive layout; RTL support for Persian.

---

## Files

| File | Description |
|------|-------------|
| `index.html` | GitHub Pages landing — pick Cyber or Simple theme. |
| `vless-tools-all-in-one.html` | **Standalone** — all CSS, JS, and both themes in one file (~150 KB). Best for download & offline use. |
| `vless-tools-cyber.html` | CyberDeck theme; links to Simple version. Requires `cyber-theme.css`. |
| `vless-tools-simple.html` | Simple theme; links to Cyber version. Requires `simple-theme.css`. |
| `cyber-theme.css` | Cyberpunk / HUD stylesheet. |
| `simple-theme.css` | Minimal NextGen-style stylesheet. |

---

## Quick start

1. **GitHub Pages:** open `index.html` and choose **Cyber** or **Simple**.
2. **Easiest offline:** download `vless-tools-all-in-one.html` and open it in Chrome, Firefox, or Edge.
3. **Themed pair:** keep `vless-tools-cyber.html` + `cyber-theme.css` (or simple + `simple-theme.css`) in the same folder and open the HTML file.

> CDN range buttons need internet access to fetch IP lists from GitHub. Everything else works offline.

---

## Theme switching

| Variant | How |
|---------|-----|
| **All-in-one** | Use **Simple / Cyber** buttons in the header; choice stored as `vless-ui-theme` in `localStorage`. |
| **Cyber ↔ Simple** | Each themed HTML links to the other file (`vless-tools-simple.html` ↔ `vless-tools-cyber.html`). |

Language preference is stored separately as `vless-lang`.

---

## Privacy

All processing runs **locally in your browser**. Nothing is uploaded to a server except optional CDN IP list fetches from GitHub.

---

## License

Use and modify freely for personal or educational purposes. Attribution appreciated.

---

## Other languages

- [فارسی (README.fa.md)](README.fa.md)
- [Русский (README.ru.md)](README.ru.md)
