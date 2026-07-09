# CloudShelf v0.2.8 / v0.2.1 / v0.2.1-hotfix.1

### New Features
- **Forgot Password** — Self-service password reset via email OTP. No more contacting support for lost passwords.
- **Canvas DRM Hardening** — Canvas protection uses WeakSet (closure variable) instead of CSS class. Bypass via DevTools class removal no longer works.
- **Watermark Baked into Canvas** — Watermark text is now drawn directly onto canvas pixel data. Screenshots and screen recordings always contain user-identifiable watermarks, even if DOM overlay is removed.
- **PDF Text Layer Blocked** — `getTextContent()` monkey-patched to return empty. Prevents programmatic text extraction from PDF.js.
- **F12 DevTools Intercept** — F12 key is blocked, preventing easy DevTools access.
- **Text Selection Blocker** — JavaScript-level `selectstart` prevention on page content. Bypassing CSS `user-select: none` no longer works.
- **Version Gating** — Server-side version blocking via `app_config` table, RLS policies, and Edge Function checks. Old app versions cannot fetch new books or download content.
- **Device Name Tracking** — Hostname/model saved to `devices` table at binding time (replaces hardcoded `'Student Desktop'`).

### Bug Fixes
- **Forgot Password → `otp_expired`** — Input field was `maxLength={6}` but Supabase sends 8-digit codes. Changed to 8, switched from publishable key to anon key (JWT decode issue).
- **Security: Anon Key** — Switched from `sb_publishable_...` to anon `eyJ...` key in all projects. Publishable key is not a JWT and caused Auth endpoint confusion.
- **Security: Data Leakage** — `gdrive_url` stripped from cached books in localStorage. Column whitelist replaces `select("*")` in MyCollection queries.

### Platform Updates
| Platform | Version | Build |
|---|---|---|
| Windows (Desktop) | v0.2.8 | `.msi` |
| Android (Standard) | v0.2.1 | `.apk` |
| Android (Huawei / No Worker) | v0.2.1-hotfix.1 | `.apk` |

### Huawei Variant
Separate APK for Huawei devices where the standard APK's PDF.js worker fails (WebView blob: URL limitation). Uses Android PdfRenderer API via JNI instead.
