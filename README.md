# City App Schema - Standardisierte Beschreibung von Smart City Anwendungen

Dieses Repository stellt ein standardisiertes Schema zur Beschreibung von City Apps und ihren Modulen bereit. Es wurde vom Fraunhofer-Institut für Experimentelles Software Engineering (IESE) im Rahmen des Modellprojekte Smart Cities (MPSC) Programms entwickelt und dient der Förderung von Transparenz, Interoperabilität und Zusammenarbeit zwischen Kommunen.

## 🎯 Zielsetzung

City Apps sind mobile oder webbasierte Anwendungen, die Bürger:innen, Tourist:innen und Unternehmen mit Informationen rund um das städtische oder regionale Leben versorgen und mit kommunalen Dienstleistungen vernetzen. Sie sind in verschiedene Module unterteilt – vom Abfall- und Eventkalender über ÖPNV-Informationen bis hin zu Bürgerbeteiligung.

Dieses Schema-Repository ermöglicht:

- **Standardisierte Beschreibung**: Einheitliche Dokumentation von City Apps und ihren Modulen
- **Vergleichbarkeit**: Kommunen können verschiedene App-Lösungen systematisch vergleichen
- **Interoperabilität**: Erleichterung des Austauschs und der Wiederverwendung von Modulen
- **Transparenz**: Klare Dokumentation von Funktionen, Schnittstellen, Abhängigkeiten und Kosten
- **Open Source Förderung**: Unterstützung von Entwicklungspartnerschaften durch strukturierte Dokumentation

## 📂 Repository-Struktur

```
├── README.md                           # Diese Datei
├── schemas/                            # JSON-Schema Definitionen
│   ├── city-app-schema.json           # Schema für City App Beschreibungen (v2.1.0)
│   └── app-module.schema.json         # Schema für App-Module (v1.0.0)
└── Smart-City-Platform/                # Beispiel-Implementierung
    ├── city_app.yml                   # Beispiel einer City App Beschreibung
    └── modules/                        # Beispiel-Module
        ├── citizen-participation.yml  # Bürgerbeteiligungsmodul
        ├── environmental-monitoring.yml # Umweltmonitoring-Modul
        └── images/                     # Screenshots und Logos
```

## 📋 Schema-Übersicht

### City App Schema (`city-app-schema.json`)

Das Haupt-Schema beschreibt eine gesamte City App mit folgenden Kernelementen:

**Basis-Informationen:**
- Name, Anbieter, App-Typ
- Kurzbeschreibung und Website
- Kontaktinformationen und Entwicklungspartnerschaften

**Technische Details:**
- Open-Source Repository
- Dokumentation und Lizenzierung
- Entwicklungsstatus und letzte Aktualisierung
- Liste der enthaltenen Module (als Referenzen)

**Visuelle Elemente:**
- Logo und Screenshots
- Eingesetzte Kommunen

### App-Modul Schema (`app-module.schema.json`)

Das Modul-Schema beschreibt einzelne Funktionsmodule einer City App:

**Funktionale Beschreibung:**
- Name und Themenbereich (z.B. Bürgerbeteiligung, Umweltmonitoring, ÖPNV)
- Verwendungsszenario und detaillierte Beschreibung
- Optional/Pflichtmodul-Status

**Technische Spezifikation:**
- Schnittstellen (APIs, Protokolle)
- Abhängigkeiten (Datenbanken, Frameworks)
- Externe Services
- Anpassungsoptionen

**Organisations-Details:**
- Beteiligte Akteure und deren Rollen
- Kosteninformationen
- Eingesetzte Kommunen
- Entwicklungsstatus und Roadmap

**Dokumentation:**
- Screenshots
- Technische Dokumentation
- Open-Source Repository

## 🚀 Verwendung

### YAML-Dateien validieren

Die YAML-Dateien sollten gegen die entsprechenden JSON-Schemas validiert werden. Sie können dafür Tools wie [ajv-cli](https://github.com/ajv-validator/ajv-cli) verwenden:

```bash
# Installation
npm install -g ajv-cli ajv-formats

# Validierung einer City App
ajv validate -s schemas/city-app-schema.json -d Smart-City-Platform/city_app.yml

# Validierung eines Moduls
ajv validate -s schemas/app-module.schema.json -d Smart-City-Platform/modules/citizen-participation.yml
```

### Eigene City App beschreiben

1. Erstellen Sie eine neue YAML-Datei basierend auf `city-app-schema.json`
2. Füllen Sie die erforderlichen Felder aus (mindestens `name`)
3. Beschreiben Sie Ihre Module in separaten YAML-Dateien basierend auf `app-module.schema.json`
4. Referenzieren Sie die Module in Ihrer City App über die `modules`-Liste
5. Validieren Sie Ihre Dateien gegen die Schemas

### Beispiel: Minimale City App

```yaml
name: "Meine Smart City App"
city-app-yml-version: "1.1"
provider: "Stadt Musterstadt"
short_description: "Zentrale App für Bürgerservices und städtische Informationen"
app_type: "Progressive Web App"
modules:
  - "./modules/event-calendar.yml"
  - "./modules/waste-management.yml"
development_status: "Beta"
last_update: "2025-12-30"
```

## 🏛️ Hintergrund: Arbeitsgruppe City Apps

Dieses Schema wurde im Rahmen der Arbeitsgruppe "City Apps" des MPSC-Programms entwickelt. Die Arbeitsgruppe:

- Vergleicht verschiedene City App Lösungen aus MPSC-Projekten
- Identifiziert Gemeinsamkeiten und Unterschiede
- Unterstützt Entwicklungspartnerschaften wie:
  - [Open Smart City App (OSCA)](https://www.solingen.digital/projekte/entwicklungspartnerschaft-open-smart-city-app-gemeinsam-den-fortschritt-gestalten)
  - [KODI App](https://community.kodi-app.de/)
  - [Smart Village App (SVA)](https://smart-village.app/)
- Fördert Community Management und gemeinsame Weiterentwicklung
- Entwickelt Betreibermodelle und Wirkungsmessungen

Mehr Informationen: [smart-city-dialog.de/netzwerk/arbeitsgruppen/city-apps](https://www.smart-city-dialog.de/netzwerk/arbeitsgruppen/city-apps)

## 🤝 Beitragen

Dieses Schema ist ein lebendes Dokument und wird kontinuierlich weiterentwickelt. Beiträge sind willkommen:

- **Issues**: Melden Sie Probleme oder schlagen Sie Verbesserungen vor
- **Pull Requests**: Tragen Sie Erweiterungen oder Korrekturen bei
- **Feedback**: Teilen Sie Ihre Erfahrungen mit dem Schema

## 📚 Weiterführende Ressourcen

- [Smart City Dialog Plattform](https://www.smart-city-dialog.de/)
- [Kurzstudie Bürger Apps (2023)](https://www.wik.org/veroeffentlichungen/veroeffentlichung/kurzstudie-buerger-apps)
- [Smart-City-Apps im Vergleich: Wegweiser für Kommunen](https://www.smart-city-dialog.de/aktuelles/news/smart-city-apps-im-vergleich-wegweiser-fuer-kommunen)
- [City-Apps: Smarte Anwendungen für die Jackentasche](https://www.smart-city-dialog.de/aktuelles/news/city-apps-smarte-anwendungen-fuer-die-jackentasche)

## 📄 Lizenz

Dieses Schema-Repository wird unter einer offenen Lizenz bereitgestellt, um die größtmögliche Wiederverwendung in Smart City Projekten zu ermöglichen.

## 📧 Kontakt

**Fachliche Leitung:**
- Adeline Schaefer, Fraunhofer IESE
  E-Mail: adeline.schaefer@iese.fraunhofer.de

**Arbeitsgruppe "City Apps":**
- Tizia Grether, Fraunhofer IESE
  E-Mail: tizia.grether@iese.fraunhofer.de

---

**Hinweis:** Die in diesem Repository enthaltenen Beispiele wurden teilweise mithilfe von KI erstellt und repräsentieren keine konkreten, produktiv eingesetzten Anwendungen. Sie dienen ausschließlich der Illustration des Schemas.
