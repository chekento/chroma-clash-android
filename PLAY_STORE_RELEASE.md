# Chroma Clash — Google Play Release

This repository keeps debug distribution and Play Store release builds separate.

## Release artifact

Google Play release output:

`app/build/outputs/bundle/release/app-release.aab`

The workflow `.github/workflows/play-store-aab.yml` creates a signed Android App Bundle and uploads it as the artifact `chroma-clash-play-release-aab`.

## Required GitHub Secrets

Configure these under **Repository Settings → Secrets and variables → Actions**:

- `CHROMA_UPLOAD_KEYSTORE_BASE64` — base64-encoded upload keystore
- `CHROMA_UPLOAD_KEYSTORE_PASSWORD` — keystore password
- `CHROMA_UPLOAD_KEY_ALIAS` — upload key alias
- `CHROMA_UPLOAD_KEY_PASSWORD` — key password

Never commit a keystore or any of these secret values to the repository.

### Encode the keystore

Linux/macOS:

```bash
base64 < chroma-clash-upload.jks | tr -d '\n'
```

PowerShell:

```powershell
[Convert]::ToBase64String([IO.File]::ReadAllBytes('chroma-clash-upload.jks'))
```

Store the resulting one-line value in `CHROMA_UPLOAD_KEYSTORE_BASE64`.

## Build

After the four secrets exist, run **Actions → Build Play Store AAB → Run workflow** or push to `main` after this release configuration has been merged.

The workflow deliberately fails if release signing is missing. This prevents accidental production artifacts with an unstable or unsuitable signing identity.

## First Play Console release

1. Create the Play Console app with package name `cloud.kosch.chromaclash`.
2. Enable Play App Signing when prompted.
3. Upload `app-release.aab` to Internal testing first.
4. Complete Store listing, App content, Data safety, Content rating and Target audience.
5. Add a public privacy-policy URL.
6. Test installation and game progress on at least one physical Android device.
7. Promote through the required testing track(s), then Production when the account is eligible.

## Versioning

Current first-release values:

- `versionCode 1`
- `versionName 1.0.0`
- `targetSdk 36`

Every subsequent Play upload must use a higher `versionCode`.
