# RONA Stores

RONA Stores is a browser-based, local-first retail management app for a neighborhood shop. It brings everyday store operations—inventory, checkout, sales, customers, suppliers, purchases, expenses, alerts, and reports—into one interface.

> **Important:** This repository contains a front-end prototype, not a hosted online shop or a complete multi-user retail platform. Records are saved in the current browser with `localStorage`. Although the interface can work offline, data does not automatically sync between devices or to a server. Online synchronization requires a separately configured backend.

## Features

- **Dashboard:** View daily sales totals, transactions, catalogue size, stock alerts, and recent activity.
- **Point of Sale:** Build a basket, select a customer and payment method, complete a sale, and print a receipt. Completing a sale reduces product stock.
- **Inventory:** Add, edit, search, and remove products; update stock; and see low-stock and out-of-stock indicators.
- **Sales and orders:** Search the local sales ledger, export it as a CSV file, print receipts, and mark eligible sales as refunded. Refunding returns recorded item quantities to stock.
- **Customers:** Keep a basic customer directory and track visits and spending.
- **Suppliers and purchases:** Store supplier contacts and record received stock. Receiving a purchase increases stock and updates product cost.
- **Expenses:** Record and review operating expenses.
- **Alerts and activity:** Review stock warnings and recent local activity.
- **Reports:** See sales, estimated gross profit, expenses, and inventory summaries based on locally recorded data.
- **Settings and backups:** Configure the store profile, switch appearance, export or import a JSON backup, or restore the starter dataset.
- **First-run account setup:** Create an administrator sign-in the first time the app is opened. No default username or password is included.

The app starts with sample products and sales so you can explore the interface. These are demonstration records, not live store data.

## Run the app

The app is a static HTML, CSS, and JavaScript prototype. No package installation or build step is required.

1. Download or clone this repository.
2. Open `index.html` in a modern browser, or serve the repository from a local web server. For example, with Python installed, run `python -m http.server 8000` from the repository directory and visit `http://localhost:8000`.
3. On first launch, create an administrator username and password. Sign in to open the store workspace.

Use `localhost` or HTTPS for the strongest browser cryptography support. The app includes a compatibility fallback when opened directly as a local file; that fallback is not a substitute for production-grade authentication.

## Typical store workflow

1. **Set up products:** Open **Inventory**, add products, and set their selling price, cost, available quantity, and reorder threshold.
2. **Add contacts:** Add customers and suppliers as needed.
3. **Record purchases:** Use **Purchases** when stock arrives. Select or enter a supplier, add received products and quantities, and save the purchase.
4. **Make a sale:** Open **Point of Sale**, add products to the basket, choose a customer and payment method, then complete checkout. Print a receipt from the sales ledger if needed.
5. **Track costs:** Record rent, transport, wages, utilities, and other operating expenses under **Expenses**.
6. **Monitor the shop:** Check the dashboard and **Alerts** for low stock, and use **Reports & Analytics** to review recorded activity.
7. **Back up records:** Export a JSON backup from **Settings** regularly and store it somewhere safe.

## Data, privacy, and limitations

- Business records are stored in the browser's `localStorage` on the device where the app is used. They are not automatically backed up, shared with other users, or synchronized across devices.
- Clearing site data, changing browsers, or losing the device can remove the records. Export backups regularly and test restoring them when appropriate.
- The sign-in is a local access gate for this browser app. It does not provide server-side identity management, encrypted cloud storage, or protection from someone with access to the browser or device.
- Staff and access screens describe role-oriented operations, but full staff account management requires a server-side implementation.
- Payment methods are recorded for bookkeeping; the app does not process card, mobile-money, or bank payments.
- Reports reflect the data entered in this browser. Treat sample data and illustrative dashboard charts accordingly.
- The interface mentions offline readiness and online status, but a backend is not configured in this repository. Do not rely on it for shared, centralized, or business-critical records without adding and testing a suitable backend and backup process.
- `index.html` references `manifest.json` and `sw.js`, but those files are not included in the repository's current root contents. Installable-app and service-worker behavior therefore requires those assets to be supplied and tested.

## Repository contents

- `index.html` — the application interface and client-side behavior.
- `rona-logo.svg` — RONA Stores logo used by the interface.
- `rona-store-photo.png` — store photo displayed on the About page.

## Suggested production work

Before using this prototype as a live retail system, add a secure backend and database, server-side authentication and role permissions, cross-device synchronization, payment-provider integration if needed, automated backups, and tests for sales, refunds, imports, and stock changes. Deploy over HTTPS and review data protection requirements for your location.

## License

No license is specified in this repository. Contact the repository owner before redistributing or reusing the project.
