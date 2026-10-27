# Schlafzyklus-Rechner

© 2026 Benedikt Diel

Berechnet optimale Einschlaf- und Aufwachzeiten nach Schlafzyklen. Ein Projekt, zwei Apps:

- **iPhone:** Web-App über GitHub Pages, in Safari „Zum Home-Bildschirm“ hinzufügen. Läuft danach ohne Browserleiste und auch offline.
- **Android:** APK, wird bei jedem Push automatisch gebaut und unter *Releases* veröffentlicht.

## Einrichtung (einmalig)

1. Neues **öffentliches** Repository auf github.com anlegen, z. B. `schlafrechner`.
2. Den Inhalt dieses Ordners hochladen (inklusive des versteckten Ordners `.github`).
3. **Settings → Pages → Source:** „GitHub Actions“ wählen.
4. Unter **Actions** beide Workflows einmal laufen lassen („Run workflow“), falls sie nicht von selbst starten.

Danach:

- Web-App: `https://<dein-github-name>.github.io/schlafrechner/`
- APK: Repository → **Releases** → `Schlafrechner-<version>.apk`

## Installation

**iPhone:** Link in Safari öffnen → Teilen-Symbol → „Zum Home-Bildschirm“.

**Android:** APK aus *Releases* herunterladen und öffnen. Einmalig die Installation aus dieser Quelle erlauben.

## Versionen

Die Version steht an genau einer Stelle: `APP_VERSION` in `web/index.html`. Daraus entstehen automatisch die Anzeige in der Fußzeile, der Offline-Cache der Web-App, `versionName`/`versionCode` der APK und der Name des Releases.

| Version | Änderung |
|---|---|
| 1.1.0 | Fußzeile mit Copyright und Version, iPhone-Web-App, Android-APK |
| 1.0.0 | Erste Version des Rechners |

## Hinweis zur Signatur

`android/app/release.keystore` signiert die APK. Er muss bei jedem Update gleich bleiben, sonst lässt Android die neue Version nicht über die alte installieren. Da er im öffentlichen Repository liegt, könnte ihn jemand anderes nutzen. Für eine private Hobby-App ist das unkritisch; für eine Veröffentlichung im Play Store bräuchte es einen geheimen Schlüssel.
