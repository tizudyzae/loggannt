# CSV Rota Viewer

This repository contains a single-page web application for previewing rota CSV exports, exploring line and schedule views, and exporting share-ready landscape PDFs with [pdf-lib](https://github.com/Hopding/pdf-lib). Upload a CSV file (or the PDF table export from the Logile mobile app) to your browser and the interface renders interactive summaries plus a PDF preview without relying on any backend services.

## Privacy and GDPR compliance

* **Client-side only.** All rota processing, visualization, and PDF generation happen entirely within your browser using JavaScript. The application never transmits rota data to any server or third party.
* **Local storage only.** If you choose to save a week, those details are cached in `localStorage` on your device so you can revisit them later. You may clear these saved weeks at any time via the UI controls or your browser settings.
* **No retention by the project.** The maintainers do not receive, collect, or retain any of the rota data that you load into the viewer.
* **Your responsibilities.** While the client-side workflow is designed to support GDPR compliance by keeping data on-device, you remain responsible for ensuring you have the right to process any personal data contained in the rota, for informing affected individuals as required, and for clearing saved weeks when necessary.

## Development

Open `index.html` in any modern browser to use or modify the viewer. The bundled `pdf-lib.min.js` dependency is included for offline development.

## Choosing between CSV and PDF inputs

* **CSV remains the source of truth.** The viewer is designed around the CSV export, which preserves structured rows and columns without guesswork.
* **PDF parsing is best-effort.** The PDF test harness can help iterate on improvements, but PDFs are inherently harder to interpret (fonts, layout shifts, extraction differences). Treat the PDF preview and interpreted CSV export as debugging tools rather than production inputs.
* **Recommendation.** For reliable downstream results, upload CSV files whenever possible and use PDFs only when you need to diagnose how a particular table is being read.
