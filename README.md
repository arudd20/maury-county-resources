# Maury County Resource Directory

A mobile-first, searchable directory of nonprofit and community resources serving Columbia and Maury County, Tennessee.

**Live site:** [maurycountyresources.org](https://maurycountyresources.org) *(once deployed)*

---

## About

Built from the [TCFD Maury County Resource Guide 2026](https://mytcfd.org/wp-content/uploads/2026/07/Maury-County-Resource-Guide-2026.pdf). Single-file HTML/CSS/JS — no framework, no backend, no build step required.

**Features**
- Live search + category filtering
- Tap-to-call phone links (mobile-friendly)
- Staleness indicators for entries not verified in 12+ months
- Password-protected admin panel for adding, editing, and removing listings
- Export to JSON and CSV for backup and data portability
- Auto-updating copyright year and last-updated date in footer

---

## Hosting (GitHub Pages)

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, root folder (`/`)
4. Add your custom domain under **Custom domain**
5. At your registrar, add a CNAME record pointing `maurycountyresources.org` → `<your-github-username>.github.io`

GitHub will handle the SSL certificate automatically.

---

## Managing Listings

### Via the admin panel (in-browser)
1. Open the site and click **Admin** in the header
2. Password: *(set in `index.html` as `ADMIN_PW`)*
3. Add, edit, or remove listings — changes save to `localStorage`
4. Use **Export JSON** to download a snapshot of current data

### Updating the source data (recommended for permanent changes)
1. Export JSON from the admin panel
2. Replace the `SEED` array in `index.html` with the exported data
3. Commit with a descriptive message, e.g.:
   ```
   Update listings: add XYZ org, remove defunct ABC org
   ```

---

## Data Exports

The `data/` folder is for periodic JSON snapshots exported from the admin panel. Commit these alongside code changes to keep a full history of the directory contents.

```
data/
  maury-county-resources-YYYY-MM-DD.json
```

---

## Admin Password

The admin password is stored in plain text in `index.html` as the `ADMIN_PW` constant. Change it before deploying to a public URL. This is intentional — there's no backend, so the password only protects casual access, not the source code.

---

## Source

Data sourced from the [Tennessee Center for Family Development (TCFD)](https://mytcfd.org) Maury County Resource Guide. Verify all listings before publishing updates — organizations change hours, locations, and services frequently.

---

*© Maury County Resource Directory · Columbia, TN*
