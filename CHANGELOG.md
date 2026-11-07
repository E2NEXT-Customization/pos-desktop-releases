# Changelog

What changed in each A1ERP POS version. Newest first.

## 1.11.29 — 2026-11-07

- **Purchases create Purchase Invoices.** A purchase from the app now creates a standard Purchase Invoice with Update Stock, one per supplier. A paid purchase is a cash purchase from the shift and is deducted from the expected cash at closing, like expenses; unpaid purchases stay owed to the supplier.
- **Stock Count creates a Stock Reconciliation directly.** Only items whose count differs from the system go in, at the count's date and time.
- **Add stock at closing.** On Qty Sync Failures each item has an **Add stock** button. It opens Purchases with the item, missing quantity and warehouse filled in (or Stock Count when the item can't be purchased). Once it syncs, the failed invoices are retried automatically.
- **Closing summary** shows cash purchases next to cash expenses.
- Closing no longer requires a Purchase Direct Entry; `purchase_direct` is no longer needed by the app.
- Needs the matching `pos_offline` server update.

## 1.11.28 — 2026-11-07

- **Two restaurants in one POS Profile.** A tab per restaurant on the sale screen; each line uses its restaurant's warehouse, cost center and price list, and the closing is split by restaurant.
- **Prices tab.** Edit selling prices from the app, with a maximum change percent and a change history.
- **Expenses tab.** Cash expenses with a receipt photo; amounts above the limit wait for approval in the app; approved cash expenses are deducted from the closing cash.
- **Purchases and Stock Count tabs.** Buy from an outside supplier into the branch warehouse; count stock and reconcile only the changed items.
- **Material Requests tab.** Request materials from the main kitchen and follow their status.
- **Reports tab.** Sales, closings, item movement, purchases, expenses, stock movement and stock balance, with today's summary, print and export.
- **App version on opening and closing.** Each shift records the app version that opened and closed it.
- **Restart fix.** The app closes fully and reopens without Task Manager; after a restart without "Remember me" it asks you to sign in again instead of reporting "offline".
- **Closing with stock shortages.** After the missing stock is added, Sync Now and the new **Retry failed invoices** button resend the invoices so the shift can close.
- **Fixes.** Cashier roles now load, so the new tabs appear for non-admin users; the camera works on Windows for receipt photos and the barcode scanner; the new pages match the app's design; messages say A1ERP.

## 1.11.27 — 2026-10-20

- **Search printer routing lists.** Find Items and Item Groups using the search
  box. Existing selections stay selected when hidden by the search.
- **Check for updates from Settings.** Settings → System now shows the current
  app version and a **Check for update** button, with download progress and
  update status.

## 1.11.26 — 2026-10-17

- **Checkbox selection for printer routing.** Select Items and Item Groups by
  checking their boxes, without holding Ctrl/Cmd. Each selection can be removed
  independently; saved selections and printing rules are unchanged.

## 1.11.25 — 2026-10-17

- **Printer item routing.** Each printer can include multiple Items and Item
  Groups. An item prints when either its code or its group matches. With no
  selections, the printer prints all items.
- **No empty tickets.** Printers with no matching items receive no print job,
  including automatic printing and receipt reprints.
- **Existing settings stay compatible.** Saved kitchen exclusions keep working
  until you explicitly change that printer's item routing.
- **Startup fix.** Fixed an updater-loading error that could prevent the
  packaged app window from opening.

## 1.11.24 — 2026-10-10

- **Automatic updates.** On startup the app checks for a new version and offers
  **Update / Later**. Update downloads, installs, and restarts the app. This
  version must be installed by hand once; later versions arrive through the app.
- **No setup wizard when the local database fails to open.** The app shows a
  Retry screen (English and Arabic) instead, and waits up to 60 seconds for a
  large database to open.
- **Local cleanup.** On startup, synced invoices and closings older than 7 days
  are removed from the PC. Failed, pending, or unsynced records and the current
  opening are never removed. A return against an invoice older than 7 days will
  not find that invoice locally.

## 1.11.23 — 2026-08-30

- A sale rejected because the login session expired is now retried instead of
  being parked as permanently failed.

## 1.11.22 — 2026-08-30

- Failed syncs now show the server's actual reason instead of a bare
  "FORBIDDEN" style error.

## 1.11.21 — 2026-08-30

- Faster invoice sync: fewer server round-trips per invoice, and clearer sync
  error messages.

## 1.11.20 — 2026-08-29

- When the server is down, checkout switches to offline immediately instead of
  hanging for about two minutes; startup no longer hangs either.
- The server address is saved correctly for offline invoices, and setup stays
  on the connection step if saving settings fails.
- Windows build fix for the local database module.

## 1.11.18 — 2026-08-08

- POS closing completes without waiting for the receipt to print.
- A closed POS opening can no longer be reused for new sales.

## 1.11.16 — 2026-08-05

- POS closing captures a diagnostic snapshot and uploads it in the background,
  retrying until it succeeds.
- A POS closing interrupted on the PC resumes the existing attempt instead of
  starting a new one.
- Packaging, sign-in security, and conflict-resolution shutdown fixes.
