# Datenschutz, KI- & Drittanbietertransparenz — Chroma Clash

**Stand:** 1. Oktober 2026  
**App:** Chroma Clash 1.0.0 (`cloud.kosch.chromaclash`)  
**Projekt:** https://github.com/chekento/chroma-clash-android  
**Kontakt / Anbieterinformationen:** https://kosch.cloud

## 1. Kurzfassung

Chroma Clash ist als offline-first Android-Spiel ausgelegt.

- Kein Benutzerkonto.
- Keine Werbung.
- Kein Analytics-/Tracking-SDK.
- Keine Android-Laufzeitberechtigungen.
- Keine `INTERNET`-Berechtigung.
- Kein Remote-API-Zwang.
- Kein Remote-KI-Modell.
- Fortschritt und Einstellungen werden lokal im Android-WebView gespeichert.
- Android-App-Backup ist deaktiviert.

## 2. Welche Daten werden lokal gespeichert?

Je nach Nutzung können lokal gespeichert werden:

- Rang und XP,
- Achievements,
- Scores,
- Streaks,
- Lifetime-Statistiken,
- Spielmodus und Schwierigkeitsoptionen,
- UI-/Spieleinstellungen.

Diese Daten werden nicht an einen Chroma-Clash-Server übertragen, weil die aktuelle App keinen solchen Nutzerdienst verwendet.

Löschen der App-Daten oder Deinstallation kann den lokalen Fortschritt dauerhaft entfernen.

## 3. KI-Transparenz

### Chroma Clash verwendet keine KI im Gameplay

Die aktuelle Version enthält **kein LLM, kein generatives Modell und kein Machine-Learning-Modell**.

Die Farbbewertung basiert auf klassischer Mathematik:

- RGB/HSV-Farbwerte,
- Umrechnung in CIE Lab,
- **CIEDE2000 ΔE** als Wahrnehmungsdifferenz,
- deterministische Punkte-, Rang- und Schwierigkeitslogik.

Auch die adaptive Schwierigkeit ist regel-/rangbasiert und **keine KI-Personalisierung**.

Es werden keine Farbeingaben, Scores oder Nutzerdaten an ChatGPT/OpenAI oder andere KI-Anbieter übertragen.

## 4. Drittanbieter-Komponenten und Tools

### App-Laufzeit

- **Android System WebView** — rendert die lokal gebündelte Spieloberfläche.
- **Android Plattform-APIs** — App-Lifecycle, Hardwarebeschleunigung und lokaler Speicher.

Die aktuelle Runtime enthält kein Werbe-, Analytics-, Social-Login- oder Remote-AI-SDK.

### Build und Distribution

- **Android SDK 36**
- **Gradle 9.5**
- **JDK 17**
- **GitHub / GitHub Actions / GitHub Releases**

Diese Werkzeuge werden für Entwicklung, CI und Distribution verwendet; sie sind keine Laufzeit-Tracker der installierten App.

## 5. Netzwerk

Das aktuelle Manifest fordert keine Internetberechtigung. Das Spiel benötigt für das Kern-Gameplay keine Netzwerkverbindung.

Externe GitHub-/kosch.cloud-Links werden nur außerhalb der App bzw. nach einer bewussten Browseraktion geöffnet.

## 6. Zertifikate und Signierung

Der über GitHub veröffentlichte direkte Test-Build entsteht aus dem **Debug-APK-Workflow**. Eine separate Play-/Release-Signierung ist im Projekt vorgesehen und wird nur aktiviert, wenn externe Signing-Secrets über geschützte Umgebungsvariablen bereitgestellt werden.

Signing-Secrets gehören nicht in das öffentliche Repository.

Wichtig:

- Eine Android-Signatur ist eine technische Build-Identität, keine unabhängige Qualitäts-, Sicherheits- oder Datenschutz-Zertifizierung.
- SHA-256-Prüfsummen dienen der Integritätskontrolle.
- Chroma Clash installiert keine eigene Root-CA und fordert keine Benutzerzertifikate an.

## 7. Keine Drittanbieter-Profile

Die aktuelle App enthält:

- keine Werbung,
- keine Analytics,
- keine Tracking-Pixel,
- keinen Login,
- keine Cloud-Synchronisation,
- keine Social-Profile,
- keine Remote-KI.

Daher wird kein serverseitiges Chroma-Clash-Nutzerprofil aufgebaut.

## 8. Kinder / Accounts

Die App stellt keine Benutzerkonten oder Social-Login-Funktionen bereit und überträgt in der aktuellen Version keine persönlichen Spielerdaten an den Entwickler.

## 9. Änderungen

Wenn spätere Versionen Online-Funktionen, Cloud-Saves, Accounts, Analytics, Werbung, KI/ML oder neue Berechtigungen erhalten, muss diese Seite vor Veröffentlichung aktualisiert werden.

---

**Repository:** https://github.com/chekento/chroma-clash-android  
**Anbieter / Kontakt:** https://kosch.cloud
