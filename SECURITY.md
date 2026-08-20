# Security

The Android shell loads only bundled assets from `android_asset`. Content access is disabled and the app does not request the INTERNET permission. External URL handling is delegated to the device browser if future links are added.

Do not place API keys, signing keys or secrets in this repository. For production signing, use GitHub Actions secrets or a secure CI secret store.
