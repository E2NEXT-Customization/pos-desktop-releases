# Changelog

What changed in each A1ERP POS version. Newest first.

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
