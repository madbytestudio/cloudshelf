# CloudShelf v0.3.5 / v0.2.8

### New Features
- **All Apps on Custom Updater** — Desktop, MacOS, Mobile, Huawei, and Moderator now use the same GitHub-based custom update flow (fetch release asset + verify minisign signature + install) instead of tauri-plugin-updater.
- **MacOS & Moderator Standardized** — MacOS now has per-platform installer support (MSI/AppImage/DMG), Moderator has its own signing key and version display.

### Platform Updates
| Platform | Version | Build |
|---|---|---|
| Windows (Desktop) | v0.3.5 | `.msi` |
| Android (Standard) | v0.2.8 | `.apk` |
| Android (Huawei) | v0.2.8 | `.apk` |

### Notes
- Version bump: Desktop 0.3.4→0.3.5, Mobile 0.2.7→0.2.8, Huawei 0.2.7→0.2.8, MacOS 0.3.2→0.3.5, Moderator 0.1.6→0.1.7.
- All artifacts signed (`.sig` files included in `apps/`).
