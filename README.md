Secure Ephemeral File Transfer — a Send Anywhere–style file sharing service built around short-lived, encrypted uploads — no accounts, no tracking, no long-term storage.

Files are encrypted before being stored — access is granted via a temporary link or code — and content is deleted immediately after download or automatically after ~6 hours if never retrieved.

Designed to stay simple and disposable — the system uses Azure Blob Storage for cheap, scalable storage — while keeping encryption and lifecycle control entirely in the application layer.

This project exists to explore secure file handling — stateless backend design — automated cleanup — and privacy-first data lifecycles rather than building a full enterprise transfer platform.



## TODO / Roadmap

### Core
- [ ] Finalize encryption flow (key generation, storage, disposal)
- [ ] Add integrity checks (hash verification on download)
- [ ] Enforce single-use download links
- [ ] Configurable expiration time (default ~6 hours)
- [ ] Size limits per upload
- [ ] Better error handling for expired or already-downloaded files

### Storage & Cleanup
- [ ] Azure Blob lifecycle rules for auto-expiration
- [ ] Background worker for:
  - expired files
  - completed downloads
  - abandoned uploads
- [ ] Safe deletion verification (confirm blob removal)
- [ ] Cleanup retry logic for failed deletes

### Security Hardening
- [ ] Rate limiting on upload and download endpoints
- [ ] Brute-force protection on download codes
- [ ] Optional password-based encryption
- [ ] Time-safe comparisons for access codes
- [ ] Audit encryption and key-handling logic

### API & Backend
- [ ] Streaming uploads/downloads (no full file buffering)
- [ ] Support resumable uploads
- [ ] Improve API response consistency
- [ ] Add basic health checks
- [ ] Logging (minimal, non-sensitive)

### UX / DX
- [ ] Simple upload UI
- [ ] Drag-and-drop support
- [ ] Progress indicators
- [ ] Clear expiration countdown for downloads
- [ ] Copy-to-clipboard link/code

### Optional / Future Ideas
- [ ] Client-side encryption (browser-based)
- [ ] QR code download support
- [ ] Multi-file uploads (zip on the fly)
- [ ] Temporary download limits (N downloads)
- [ ] Self-hosted deployment guide
- [ ] Docker support
