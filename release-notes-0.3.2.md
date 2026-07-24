# CloudShelf v0.3.2 / v0.2.5

### New Features
- **Multi-Provider App Updates** — App downloads now use the same 5-tier fallback chain as books: GDrive → Dropbox → OneDrive → Supabase Vault → installer_url. Zero egress until all cloud providers fail.
- **DB Migration** — `app_releases` table gained `dropbox_url` and `onedrive_url` columns for update distribution.

### Bug Fixes
- Debug traces removed from Mobile and Huawei projects (`offlineBooks.ts`, `MyCollection.tsx`).

### Platform Updates
| Platform | Version | Build |
|---|---|---|
| Windows (Desktop) | v0.3.2 | `.msi` |
| Android (Standard) | v0.2.5 | `.apk` |
| Android (Huawei) | v0.2.5 | `.apk` |

### Notes
- App update download chain matches the book download flow. All 4 projects (Desktop, MacOS, Mobile, Huawei) updated.
- All versions bumped: Desktop 0.3.1→0.3.2, Mobile 0.2.4→0.2.5, Huawei 0.2.4→0.2.5.
