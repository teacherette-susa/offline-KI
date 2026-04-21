# Schul-KI Portal

Eine browserbasierte, lokal betriebene Webanwendung für schulische KI-Workflows. Das Projekt ist für den Einsatz im Schulkontext gedacht und verbindet eine lokale KI-Infrastruktur mit praxistauglichen Oberflächen für wiederkehrende Aufgaben wie Elternbriefe, Zeugnisbemerkungen, Konferenzprotokolle, Unterrichtsmaterialien und Förderdokumentation.

Die Anwendung läuft als einzelne HTML-Datei direkt im Browser und kann lokal oder auf einem Schulserver bereitgestellt werden. Die Konfiguration wird im Browser gespeichert. Die KI-Anfragen laufen über eine lokale Instanz von Open WebUI und LM Studio; optional kann ein Obsidian-Vault angebunden werden. Laut Anleitung ist außerdem eine Anmeldung per OIDC/SSO mit PKCE vorgesehen, zusätzlich gibt es einen Demo-Modus. fileciteturn1file6 fileciteturn1file3

## Funktionen

- Browserbasierte Ein-Datei-Anwendung ohne Build-Prozess
- Lokale KI-Anbindung über Open WebUI und LM Studio
- OIDC/SSO-Anmeldung per PKCE sowie Demo-Modus
- Use Cases für:
  - Elternbriefe und Rundschreiben
  - Zeugnisbemerkungen und Beurteilungen
  - Konferenzprotokolle
  - differenziertes Unterrichtsmaterial
  - Förderdokumentation und Förderpläne
  - personenbezogene Korrespondenz
  - Verarbeitung handgeschriebener Notizen / OCR
- Chat-Bereich mit Skills-Bibliothek
- optionale Obsidian-Anbindung per Local REST API
- Konfiguration und Modellwahl direkt in der Oberfläche
- lokaler Fokus für datensensible schulische Kontexte fileciteturn1file2 fileciteturn1file3

## Projektdateien

```text
.
├── schul-ki-portal.html
├── schul-ki-anleitung.html
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── .gitignore
└── .github/
    ├── ISSUE_TEMPLATE/
    │   ├── bug_report.md
    │   └── feature_request.md
    └── pull_request_template.md
```

## Voraussetzungen

Damit die Anwendung wie vorgesehen funktioniert, sollten laut Anleitung folgende Komponenten verfügbar sein:

- **LM Studio** mit gestartetem Server
- **Docker Desktop**
- **Open WebUI** (typisch unter `http://localhost:3000`)
- optional **Obsidian** mit Plugin **Local REST API** fileciteturn1file1

Zusätzlich werden für die SSO-Anmeldung benötigt:

- OIDC Issuer URL
- Client-ID
- Redirect-URI
- Schulname / Instanzname fileciteturn2file1

## Schnellstart

### 1. Repository klonen

```bash
git clone https://github.com/DEIN-USERNAME/schul-ki-portal.git
cd schul-ki-portal
```

### 2. Lokale KI-Infrastruktur starten

- LM Studio öffnen und den lokalen Server starten
- Docker Desktop starten
- prüfen, ob Open WebUI unter `http://localhost:3000` erreichbar ist fileciteturn1file1

### 3. Anwendung öffnen

Öffne `schul-ki-portal.html` direkt im Browser oder stelle die Datei über einen internen Schulserver bereit. Die Anleitung beschreibt genau dieses Nutzungsszenario. fileciteturn1file6

### 4. Ersteinrichtung durchführen

In der Anwendung:

- **Einstellungen / Ersteinrichtung** öffnen
- Tab **SSO / Anmeldung** konfigurieren
- Tab **Open WebUI** konfigurieren
- optional Obsidian-URL und API-Key eintragen fileciteturn1file2

## Standardkonfiguration

Die HTML-Datei verwendet laut Quelltext standardmäßig diese Werte:

- `webuiUrl`: `http://localhost:3000`
- `model`: `meta-llama-3.1-8b-instruct`
- Konfigurationsspeicher: Browser-`localStorage`
- Demo-Login ist vorhanden fileciteturn1file3 fileciteturn1file9

## Bereitstellung auf GitHub

Das Repository eignet sich gut für die Veröffentlichung des Quellcodes und der Dokumentation. Für den produktiven Einsatz im Schulkontext sollte beachtet werden:

- **Keine echten API-Keys, Tokens oder institutionellen OIDC-Daten committen**
- produktive Konfigurationswerte nur lokal im Browser oder in einer separaten, nicht versionierten Datei verwenden
- prüfen, ob die Veröffentlichung des Codes mit internen Schulvorgaben vereinbar ist
- Datenschutzaussagen im README oder Wiki nur so konkret formulieren, wie sie in eurer realen Infrastruktur auch tatsächlich eingehalten werden können

## Datenschutz und Verantwortung

Die mitgelieferte Anleitung beschreibt das Projekt als lokal betriebenes System, bei dem Daten das Schulnetz nicht verlassen. Außerdem weist sie darauf hin, dass bei Konferenzaufnahmen Einwilligungen erforderlich sind. Diese Aussagen gelten nur, wenn die Anwendung tatsächlich in genau dieser lokalen Infrastruktur betrieben wird. Vor einem produktiven Einsatz sollten Datenschutz, Hosting und Berechtigungen immer mit der zuständigen Stelle abgestimmt werden. fileciteturn1file5

## Bekannte Grenzen

- Die Anwendung ist aktuell als große, eigenständige HTML-Datei organisiert.
- Es gibt derzeit keinen automatisierten Build-, Test- oder Release-Prozess.
- Konfigurationen werden clientseitig gespeichert.
- Für produktive Nutzung in größeren Umgebungen wären Review, Härtung und Dokumentation der Sicherheitsannahmen sinnvoll.

## Roadmap-Ideen

- Aufteilung in HTML, CSS und JavaScript-Module
- Beispielkonfigurationen ohne sensible Daten
- Versionsmanagement und Releases
- Screenshots und GIF-Demos im README
- Deployment-Hinweise für internen Webserver oder GitHub Pages für Demo-Zwecke
- optionale englische Dokumentation

## Beitrag leisten

Verbesserungsvorschläge, Bugreports und Pull Requests sind willkommen. Bitte beachte vor Beiträgen die Hinweise in [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Lizenz

Dieses Repository enthält standardmäßig eine **MIT-Lizenz**. Wenn du strengere Bedingungen möchtest, solltest du die Lizenz vor Veröffentlichung anpassen.
