# Google Play Data Safety — Current Chroma Clash Build

This file documents the declarations that match the current offline-first Android build. Re-check every answer before each Play submission if the app changes.

## Data collection

**Does the app collect or share any of the required user data types?**

No.

Current implementation notes:
- no account system
- no analytics SDK
- no advertising SDK
- no tracking pixel
- no remote API dependency required for gameplay
- no Android runtime permissions declared
- gameplay progress and statistics remain local to the device
- Android backup is disabled in the release manifest

## Data sharing

**Does the app share user data with other companies or organizations?**

No, based on the current build.

## Security practices

Recommended Play Console answers for the current build:
- Data is not collected: Yes
- Data is not shared: Yes
- Account creation: The app does not allow users to create an account
- Data deletion request: Not applicable while no account or developer-side user data exists

## Privacy policy

Google Play still requires a public privacy-policy URL even when an app declares that it collects no user data. A publishable HTML version is included at `docs/privacy.html`; host it at a publicly accessible HTTPS URL and use that URL in Play Console.

## Change control

Revisit this declaration before release if any of the following are added:
- multiplayer or cloud saves
- crash analytics or telemetry
- advertising
- authentication/accounts
- social login
- remote leaderboards
- push notifications
- external AI/model APIs
- payments/subscriptions
- device identifiers or attribution SDKs

Any such change can alter the required Data Safety answers and privacy-policy wording.
