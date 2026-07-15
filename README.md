# calguard.github.io

GitHub Pages site for SmartScan app verification and legal documents.

## Purpose

This repo serves files at `https://calguard.github.io/` for two reasons:

### 1. Android App Links (`.well-known/assetlinks.json`)

Google Play needs this file to verify that `calguard.github.io` owns the SmartScan app (`com.example.smartscan`). Required for:

- **Deep links** — clicking a `https://calguard.github.io/*` link directly opens the SmartScan app instead of a browser
- **Google Cloud Console OAuth verification** — Drive API consent screen links to this domain

**Where it's configured:**
- `AndroidManifest.xml` — `<data android:scheme="https" android:host="calguard.github.io" />`
- Google Cloud Console → OAuth consent screen → **Authorized domains**: `calguard.github.io`

### 2. Legal pages for Google Cloud Console

Google requires publicly accessible Privacy Policy and Terms of Service URLs when the app uses sensitive scopes (like `DRIVE_FILE`).

**Where it's configured:**
- Google Cloud Console → OAuth consent screen → **Application privacy policy link**: `https://calguard.github.io/privacy.html`
- Google Cloud Console → OAuth consent screen → **Application terms of service link**: `https://calguard.github.io/terms.html`

## Files

| File | Serves at | Purpose |
|------|-----------|---------|
| `.well-known/assetlinks.json` | `/.well-known/assetlinks.json` | Android App Links verification |
| `index.html` | `/` | Landing page |
| `privacy.html` | `/privacy.html` | Privacy Policy (web version) |
| `terms.html` | `/terms.html` | Terms of Service (web version) |

## Updating

The app's Privacy Policy and Terms of Service are compiled into the Android app source in `PrivacyScreen.kt` and `TermsScreen.kt`. If you update them in the app, also update the corresponding `.html` files here to keep the web versions in sync.

## Verification

Check the .well-known is valid:

```
https://calguard.github.io/.well-known/assetlinks.json
```
