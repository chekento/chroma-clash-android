# Chroma Clash — Universia Coloralis (Android)

Android edition of **Chroma Clash** by **KoSch**. The original browser prototype has been rebuilt as an offline-first Android game with a full long-term progression layer.

## Highlights

- **100 ranks** across 10 named leagues, ending in *Universia Coloralis X*
- Rising XP curve (~465k cumulative XP to Rank 100 before achievement rewards)
- **40 achievements** with permanent XP rewards
- Standard Run (10 rounds), Marathon (25 rounds, Rank 10 unlock), Endless (Rank 25 unlock)
- Four difficulty profiles: Flow, Clash, Precision and rank-aware Adaptive
- Strict **CIE Lab / CIEDE2000 ΔE** judgment instead of forgiving RGB distance
- Full-gamut HSV picker (Hue + saturation/value field)
- Persistent local statistics, streaks, daily streak, lifetime accuracy and score
- Offline-first: no account, API key, ad SDK, analytics SDK or network service is required to play
- GitHub Actions workflow builds a downloadable debug APK on every push to `main`

## Rank model

Each rank has a unique league/division title. Cumulative rank threshold:

`XP(rank) = floor(140 × (rank-1)^1.75 + 300 × (rank-1))`

This deliberately starts quickly, then becomes progressively harder. Rank 100 is a long-term mastery goal rather than a short onboarding loop.

## Strict grading

| Grade | CIEDE2000 ΔE |
|---|---:|
| S+ | ≤ 0.60 |
| S | ≤ 1.50 |
| A | ≤ 3.00 |
| B | ≤ 6.00 |
| C | ≤ 10.00 |
| D | ≤ 16.00 |
| F | > 16.00 |

Gameplay accuracy is derived from ΔE (`100 − 4×ΔE`, clamped to 0–100). Difficulty, remaining time and streak quality influence points and XP.

## Build

### GitHub Actions
Open **Actions → Build Android APK**. After a successful run, download the artifact **chroma-clash-debug-apk**.

### Local
Requirements: JDK 17+, Android SDK 36 and Gradle 9.5.

```bash
gradle :app:assembleDebug
```

APK output: `app/build/outputs/apk/debug/app-debug.apk`

## Project layout

- `app/src/main/assets/www/` — production web game bundled into the APK
- `web/` — convenient browser-source mirror
- `app/src/main/java/.../MainActivity.java` — minimal hardened Android WebView shell
- `.github/workflows/android-apk.yml` — repeatable APK build

## Privacy

Progress is stored in Android WebView local storage on the device. This edition contains no analytics SDK, advertising SDK, tracking pixel, login requirement or remote model/API dependency.
