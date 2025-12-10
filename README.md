# Kindle Book Parser & Exporter

A userscript that automates parsing of your Kindle content list from Amazon’s *Manage Your Content and Devices* page. It collects metadata (title, author, acquired date, devices, read status, shared info), tracks pagination, detects gaps, and exports the full dataset to CSV for offline analysis.

## ✨ Features
- **Automatic parsing** of Kindle book rows across all pages.
- **Deduplication** of items by ASIN to avoid duplicates.
- **Pagination handling**:
  - Detects current page and last page.
  - Tracks processed pages and identifies gaps.
  - Auto‑navigates through pages until complete.
- **Read status tracking** (`READ` badge included).
- **Device & sharing info** extraction.
- **CSV export**:
  - Union of all keys across items (no missing columns).
  - Arrays flattened with semicolons.
  - Auto‑download with timestamped filename.
- **Recheck button** to reset and reprocess all pages.

## ⚙️ How It Works
1. The script runs on Amazon’s Kindle content list (`booksAll/dateAsc/?pageNumber=*`).
2. Script will only run on /dateAsc (date ascending) so as books are added the checked items shouldn't be affected.
3. Each page’s rows are parsed into structured JSON and stored in `localStorage`.
4. Pagination is automatically advanced until all pages are processed.
5. Once complete, a CSV file is generated and downloaded.
6. You can re‑run the process at any time with the **Recheck All Pages** button.

## 📦 Installation
1. Install [Tampermonkey](https://www.tampermonkey.net/) or [Violentmonkey](https://violentmonkey.github.io/) or your script manager of choice.
2. Add the userscript from this repository.
3. Visit your [Amazon Kindle content list](https://www.amazon.co.uk/hz/mycd/digital-console/contentlist/booksAll/dateAsc/?pageNumber=1).
4. The script will begin parsing automatically.
5. For large collections leave the browser page active but it shouldn't take too long.

## 📝 License
GNU GPL V3
