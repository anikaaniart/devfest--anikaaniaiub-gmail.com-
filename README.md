# devfest--anikaaniaiub-gmail.com-# Tender Document Package Builder

**AI DevFest 2026: AI Vibe-Coding Contest (Solo)**

## Participant

- Name:MST NURJAHAN AKTER ANIKA
- Registration number: anikaaniaiub@gmail.com
- **Live website (HTTPS):** [https://your-username.github.io/devfest-your-registration-number/]

## About

A frontend-only web app that helps office staff turn a set of PDF files into one complete, checked and correctly ordered tender package. Everything runs in the browser. No file is uploaded to any server.

## How to run

**Online:** open the live link above in the latest Google Chrome. No login or installation is needed.

**Locally:** download or clone this repository and open `index.html` in Chrome. There is no build step. An internet connection is needed to load the pdf-lib library from a CDN.

## How to use

1. Load `requirements.json`.
2. Upload the PDF files.
3. Match each file to a required document and enter expiry dates where asked.
4. When no blocking problems remain, click Generate and download `<tender_id>_Package.pdf`.

## Main features done

- Load `requirements.json` and show tender details and the required documents sorted by order
- Upload many PDFs, show file name and page count, reject non-PDF files, remove files
- Match files to documents (one file per document, one document per file), change or clear matches at any time
- Expiry date entry for documents that have an expiry
- Live status for every document: Missing, Expiry date needed, Expired, Not provided, OK
- A document that expires on the submission deadline day is OK
- Duplicate detection by file content (SHA-256), even when file names differ; duplicates cannot be matched to different documents
- Generate button disabled while blocking problems exist, with the reasons shown
- Package PDF: English cover page, documents in requirement order, footer `<tender_id> | Page X of Y` on every page, placed in a separate strip so it does not cover the content
- Download as `<tender_id>_Package.pdf`
- Full Bangla and English language switch

## Bonus features

- Index page after the cover, showing the page number where each document starts (optional checkbox)
- Export the checklist as CSV (document, file name, pages, expiry date, status)
- Auto-match: suggests matches based on file names
- Safe handling of damaged or password-protected PDFs, with a clear message instead of a crash
- Undo for the last matching, expiry date or file removal change

## Known problems

- Bangla text is not shown on the PDF cover or index page. The PDF uses English only.
- No drag and drop upload; files are chosen with the file picker.
- Work is not saved. Refreshing the page clears the files and matches.
- The pdf-lib library is loaded from a CDN, so the app needs an internet connection.

## AI tools used

- Claude

## Most useful prompt

```text
Here are the AI DevFest rulebook and the problem statement for the Tender Document Package Builder. Build a frontend-only web app as a single index.html file (HTML, CSS and JavaScript together, no build step, no backend). It must run on GitHub Pages and in the latest Google Chrome. Load pdf-lib from a CDN.

It must have a Bangla/English language switch, store nothing on a server, and never hardcode tender data, because it will be tested with a different pack. Complete all main tasks first: load requirements.json, upload PDFs with page count, match files to documents, expiry dates, status for every document, duplicate detection by content, a disabled Generate button with reasons, the package PDF with cover page and footer "<tender_id> | Page X of Y" that does not cover the content, and download as <tender_id>_Package.pdf. Then add the bonus features. Make it simple for a non-technical office worker.
```