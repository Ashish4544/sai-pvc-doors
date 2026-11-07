# Sai PVC Doors Billing PWA

A small installable, offline-first billing app for Android phones and desktop browsers.

## Features
- Add up to 9 door measurements per bill (matches the approved invoice template).
- Area calculation: `(length × width) / 144` square feet.
- Default rate ₹100/sq.ft, editable per bill.
- Previous customer balance is carried into the next bill without double-counting.
- Generate a PNG by filling the supplied approved invoice template (includes the original logo and GPay QR from the template).
- Save bills and record multiple partial payments.
- Export an Excel `.xlsx` workbook with `Bills` and `Payments` sheets.
- Backup and restore all local records as JSON.
- Works offline after the first successful load/install.

## Run locally
A PWA/service worker requires `localhost` or HTTPS. From this folder run:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in Chrome. For phone testing, deploy the folder to a free HTTPS host such as GitHub Pages, then open the HTTPS address in Android Chrome and choose **Install app** / **Add to Home screen**.

## Data and Excel note
The app stores working records in the browser's local IndexedDB on that device. Use **Export Excel** to download the latest `.xlsx` workbook (two sheets: Bills and Payments). Mobile browsers do not allow a website to silently overwrite an existing Excel file in Downloads; export creates a fresh, updated workbook whenever requested. Use **Backup data** for a full JSON backup and **Restore backup** to recover it.

## Important
- The app is local to the browser/device. Clearing Chrome site data can remove its records; export Excel and JSON backups regularly.
- The first version supports up to 9 doors per bill to match the approved fixed template.
- This project is a starter implementation; test calculations and QR scanning with sample bills before relying on it for live business records.
