# Chroma Clash — Play Console Submission Checklist

## Build
- [ ] Merge `feature/play-store-release` into `main` after review.
- [ ] Add the four release-signing GitHub Actions secrets documented in `PLAY_STORE_RELEASE.md`.
- [ ] Run `Build Play Store AAB`.
- [ ] Confirm `jarsigner -verify` succeeds in the workflow.
- [ ] Download artifact `chroma-clash-play-release-aab`.
- [ ] Confirm package name is `cloud.kosch.chromaclash`.
- [ ] Confirm `versionCode 1`, `versionName 1.0.0`, `targetSdk 36` for the first upload.

## Store listing
- [ ] App name: Chroma Clash
- [ ] Add German listing from `STORE_LISTING_DE.md`.
- [ ] Add English listing from `STORE_LISTING_EN.md`.
- [ ] Upload 512×512 32-bit PNG app icon, max 1024 KB.
- [ ] Upload 1024×500 JPEG or 24-bit PNG feature graphic with no alpha.
- [ ] Upload at least 2 phone screenshots; for stronger game presentation use at least 3 high-resolution 9:16 or 16:9 gameplay screenshots.
- [ ] Avoid price, ranking, award, download-count and misleading promotional claims.

## Privacy and App content
- [ ] Host `docs/privacy.html` at a public HTTPS URL.
- [ ] Enter the public privacy-policy URL in Play Console.
- [ ] Complete Data Safety using `DATA_SAFETY.md` as the current-build reference.
- [ ] Declare that the app does not allow account creation.
- [ ] Complete Content rating questionnaire accurately.
- [ ] Set target audience based on the intended release audience.
- [ ] Confirm whether the app contains ads: current build = No.
- [ ] Complete any required app-access section: current build has no restricted login area.

## Testing
- [ ] Upload the signed AAB to Internal testing first.
- [ ] Install from Google Play on a physical Android device.
- [ ] Test launch, color picker, all game modes, achievements, local persistence and rotation/resizing.
- [ ] Verify no network/account dependency appears during normal gameplay.
- [ ] Complete any closed-testing requirement applicable to the developer account before Production access.

## Release
- [ ] Review Play Console pre-launch report.
- [ ] Resolve blocking policy, compatibility or crash findings.
- [ ] Promote the tested release to the next eligible track.
- [ ] Keep the upload keystore and credentials in at least two secure offline backups.
- [ ] Increase `versionCode` for every future upload.
