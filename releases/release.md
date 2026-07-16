# CloudShelf v0.3.1 / v0.2.4

### New Features
- Multi-Provider File Hosting — Books now support GDrive, Dropbox, and OneDrive URLs. 7-tier fallback chain ensures downloads succeed even if multiple providers fail.
- Vitest Unit Tests — Added test suites for offlineBooks.ts across all 4 projects (Desktop, MacOS, Mobile, Huawei). Covers PDF validation, URL transformation, and fallback chain logic.

### Bug Fixes
- *(none in this release)*

### Platform Updates
| Platform | Version | Build |
|---|---|---|
| Windows (Desktop) | v0.3.1 | `.msi` |
| Android (Standard) | v0.2.4 | `.apk` |
| Android (Huawei) | v0.2.4 | `.apk` |

### Notes
- All versions bumped: Desktop 0.3.0→0.3.1, Mobile 0.2.3→0.2.4, Huawei 0.2.3→0.2.4.
