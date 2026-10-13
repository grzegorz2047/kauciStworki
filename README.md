# KaucjaStworki

A small, browser-first collection game: scan the EAN barcode on a returnable bottle or can to discover an original creature.

## MVP
- Camera barcode scanning when supported by the browser.
- Manual EAN entry as a fallback.
- Local collection persistence through a replaceable `CollectionStore` adapter.
- First scan of an EAN discovers a creature; repeat scans grant XP.
- No accounts, server, deposits, or refund processing.

## Run locally
Open `index.html` in a modern browser. Camera access generally requires HTTPS or localhost; manual entry works without camera access.

## Persistence architecture
The game uses a small storage adapter. The current `LocalCollectionStore` saves data in this browser profile. A future remote adapter can implement the same interface without rewriting game rules. Local data is device/browser-specific and can be lost if browser storage is cleared.

## Important
Scanning a barcode does not prove that a container was returned. This is a collection game only; deposits and refunds remain outside the app.
