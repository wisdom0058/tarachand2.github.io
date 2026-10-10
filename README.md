# TARACHAND MV SCHOOL — Attendance & Expenditure Register

A single-page web app (`index.html`) with two synchronised tabs, a real **database file** (`attendance-data.json`), and PDF export. No server or internet required for daily use — all data auto-saves in the browser too.

## 📋 Page 1 — Attendance
| Date | Day | Class Day / Holiday + Reason | I | II | III | IV | V | **Total LP** | VI | VII | VIII | **Total ME** | Grand Total |

- Total LP (Class I–V) and Total ME (Class VI–VIII) calculate automatically; Day auto-fills; Sundays pre-marked as Holiday.
- Footer: Monthly Total + Average per class day for every class. Enter/↑/↓ keys move through a column.

## 🧾 Page 2 — Expenditure (auto-synced from Page 1)
| Date | Day | Class Day / Holiday | Reason | **Expenditure (₹)** | Total LP | **LP Amount** | Total ME | **ME Amount** | **Total Entitled** | **Saving** |

- Date/Day/Type/Reason/Total LP/Total ME copy live from the Attendance tab — you only type daily **Expenditure (₹)**.
- **LP Amount = Total LP × ₹6.78**, **ME Amount = Total ME × ₹10.17** (rates changeable in the green box, remembered).
- **Total Entitled = LP + ME amounts**, **Saving = Total Entitled − Expenditure** (red when negative).

## 💾 Database file — how synchronisation works
Buttons in the toolbar:

- **💾 Synchronise** → saves ALL data (attendance + expenditure + rates) as the file **`attendance-data.json`** (browser download).
- **📂 Load file** → restores everything from a saved `attendance-data.json` (use it on any other computer/phone).
- When the app is **hosted online** (e.g. GitHub Pages), it automatically reads `attendance-data.json` from the same folder on every startup and loads it if it is newer than the browser's copy.

### Keeping complete data in your GitHub repository
1. Upload the contents of this folder to a GitHub repo (`index.html`, `attendance-data.json`, `README.md`).
2. Daily/monthly: in the app press **💾 Synchronise** → the fresh `attendance-data.json` downloads → in your repo choose **Add file → Upload files** and replace the old `attendance-data.json`. Done — the repo now holds the complete data.
3. Because the page loads that JSON at startup, any browser opening your GitHub Pages address sees the latest data.

### Host it on GitHub (one time)
1. Create a repository, upload the three files above.
2. **Settings → Pages → Deploy from a branch → `main` / (root) → Save.**
3. Open `https://<username>.github.io/<repo>/`.

> Note: `attendance-data.json` holds plain (non-secret) data. If the repo is public, anyone can read it. Make the repo private if you prefer (GitHub Pages on free plans still publishes the site publicly).

## 📄 PDF download
**⬇ Download PDF** exports the tab you are viewing (Attendance register or Expenditure statement) as formatted A4-landscape PDF with school header and Head Master/Mistress signature lines. Offline fallback: browser *Print → Save as PDF*.

## Files in this folder
| File | Purpose |
|---|---|
| `index.html` | The entire app — upload this to GitHub |
| `attendance-data.json` | The database file — replaced by each **💾 Synchronise** download |
| `README.md` | This guide |
