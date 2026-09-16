# 🔋 HA Battery Status Monitor Card

[![Open your Home Assistant instance and open this repository in HACS](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Ju0506us&repository=ha-battery-status-monitor-card&category=plugin)

🇩🇪 **Deutsch**  
Eine moderne, responsive Lovelace-Karte zur Darstellung der Daten aus **HA Battery Status Monitor**.

🇬🇧 **English**  
A modern, responsive Lovelace card for displaying data from **HA Battery Status Monitor**.

> **V1:** Die Karte wurde auf einer realen Home-Assistant-Installation getestet.  
> **V1:** The card has been tested on a real Home Assistant installation.

---

## Features · Funktionen

🇩🇪 **Deutsch**

- Moderne Lovelace-Karte speziell für **HA Battery Status Monitor**
- Responsive Darstellung für Desktop, Smartphone und Home Assistant Companion App
- Light Mode, Dark Mode und eigene Home-Assistant-Themes
- Vier anklickbare Statusbereiche: Normal, Schwach, Kritisch und Nicht erreichbar
- Detailansicht direkt innerhalb der Karte – ohne Popup
- Erneuter Klick auf den aktiven Status führt zurück zur Zusammenfassung
- Große Schaltfläche **Zur Zusammenfassung** in der Detailansicht
- Geräteeinträge öffnen die zugehörige Entity über Home Assistants More-Info-Dialog
- Grafischer Karten-Editor
- Startansicht frei wählbar
- 2 oder 3 Geräte je Kategorie in der Zusammenfassung
- Alle oder ausgewählte Kategorien in der Zusammenfassung
- MDI-Symbole und Home-Assistant-CSS-Variablen
- Optimierte Aktualisierung ohne unnötiges vollständiges Neurendern bei jedem `hass`-Update
- Registrierung im Home-Assistant-Karten-Picker über `window.customCards`
- Entity-Suggestion für `sensor.ha_battery_status_monitor_gesamt`
- Rein lokale Darstellung – die Karte benötigt keinen externen Dienst

🇬🇧 **English**

- Modern Lovelace card specifically designed for **HA Battery Status Monitor**
- Responsive layout for desktop, smartphone and the Home Assistant Companion App
- Light mode, dark mode and custom Home Assistant themes
- Four clickable status categories: Normal, Weak, Critical and Not reachable
- Detail view directly inside the card – no popup
- Clicking the active status again returns to the summary
- Large **Back to Summary** button in the detail view
- Device rows open the related entity through Home Assistant's More-Info dialog
- Visual card editor
- Configurable default view
- 2 or 3 devices per category in Summary mode
- All or selected categories in Summary mode
- MDI icons and Home Assistant CSS variables
- Optimized updates without unnecessary full re-renders on every `hass` update
- Registration in the Home Assistant card picker through `window.customCards`
- Entity suggestion for `sensor.ha_battery_status_monitor_gesamt`
- Fully local rendering – no external service is required

## Requirements · Voraussetzungen

🇩🇪 **Deutsch**

Die Karte ist für die Verwendung mit **HA Battery Status Monitor** vorgesehen und erwartet standardmäßig:

```text
sensor.ha_battery_status_monitor_gesamt
```

Die Integration liefert die von der Karte verwendeten Statusdaten als Attribute des Gesamt-Sensors.

🇬🇧 **English**

The card is designed to be used with **HA Battery Status Monitor** and expects this sensor by default:

```text
sensor.ha_battery_status_monitor_gesamt
```

The integration provides the status data used by the card as attributes of the total sensor.

## Installation · Installation

### HACS

[![Open your Home Assistant instance and open this repository in HACS](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Ju0506us&repository=ha-battery-status-monitor-card&category=plugin)

🇩🇪 **Deutsch**

Installiere die **HA Battery Status Monitor Card** über HACS unter **Frontend**.

Nach der Installation liegt die Karte im HACS-Frontend-Pfad. Die Ressource kann in Home Assistant als JavaScript-Modul registriert werden:

```text
/hacsfiles/ha-battery-status-monitor-card/battery-monitor-card.js
```

Falls deine HACS-/Home-Assistant-Konfiguration die Ressource bereits automatisch registriert, ist keine weitere Aktion erforderlich.

🇬🇧 **English**

Install **HA Battery Status Monitor Card** through HACS under **Frontend**.

After installation, the card is available through the HACS frontend path. Register the resource in Home Assistant as a JavaScript module:

```text
/hacsfiles/ha-battery-status-monitor-card/battery-monitor-card.js
```

If your HACS/Home Assistant configuration already registers the resource automatically, no further action is required.

### Manual installation · Manuelle Installation

🇩🇪 **Deutsch**

Lade `battery-monitor-card.js` aus diesem Repository herunter und kopiere die Datei nach:

```text
/config/www/battery-monitor-card.js
```

Registriere anschließend die Ressource als JavaScript-Modul unter:

```text
/local/battery-monitor-card.js
```

Danach Home Assistant neu laden bzw. neu starten.

🇬🇧 **English**

Download `battery-monitor-card.js` from this repository and copy it to:

```text
/config/www/battery-monitor-card.js
```

Then register the resource as a JavaScript module at:

```text
/local/battery-monitor-card.js
```

Reload or restart Home Assistant afterwards.

## Card configuration · Kartenkonfiguration

### Example · Beispiel

```yaml
type: custom:battery-monitor-card
entity: sensor.ha_battery_status_monitor_gesamt
show_header: true
show_summary: true
default_view: summary
summary_limit: 2
summary_categories:
  - normal
  - weak
  - critical
  - unavailable
```

### Options · Optionen

| Option | Default | Description |
|---|---|---|
| `entity` | `sensor.ha_battery_status_monitor_gesamt` | Gesamt-Sensor der Integration |
| `show_header` | `true` | Überschrift der Karte anzeigen |
| `show_summary` | `true` | Statusübersicht anzeigen |
| `default_view` | `summary` | Startansicht beim Öffnen |
| `summary_limit` | `2` | Anzahl der Geräte je Kategorie in der Zusammenfassung |
| `summary_categories` | alle vier Kategorien | Kategorien, die in der Zusammenfassung angezeigt werden |

Mögliche Werte für `default_view`:

```text
summary
normal
weak
critical
unavailable
```

Mögliche Werte für `summary_categories`:

```text
normal
weak
critical
unavailable
```

## Views · Ansichten

🇩🇪 **Deutsch**

### Zusammenfassung

Die vier Statusbereiche werden oben als Schaltflächen angezeigt. Darunter werden pro ausgewählter Kategorie bis zu 2 oder 3 Geräte eingeblendet.

### Detailansicht

Ein Klick auf einen Status öffnet dessen vollständige Geräteliste direkt in der Karte. Ein erneuter Klick auf denselben Status oder die Schaltfläche **Zur Zusammenfassung** bringt die Karte zurück in die Übersicht.

🇬🇧 **English**

### Summary

The four status categories are displayed as buttons at the top. Below them, up to 2 or 3 devices per selected category are shown.

### Detail view

Clicking a status opens the complete device list for that status directly in the card. Clicking the same status again or using **Back to Summary** returns to the overview.

## Card picker · Karten-Auswahl

Die Karte registriert sich über `window.customCards` und stellt damit Name, Beschreibung und Dokumentations-Link für den Home-Assistant-Karten-Picker bereit. Home Assistant dokumentiert diese Registrierung offiziell für Custom Cards. citeturn0search1

Seit Home Assistant 2026.6 kann eine Custom Card zusätzlich über `getEntitySuggestion()` für passende Entities im Community-Bereich des Karten-Pickers vorgeschlagen werden. Die Battery Status Monitor Card nutzt diese Funktion gezielt für:

```text
sensor.ha_battery_status_monitor_gesamt
```

Dadurch kann Home Assistant beim Erstellen einer Karte eine passende Konfiguration für diesen Gesamt-Sensor vorschlagen. citeturn0search0

## Theming · Themes

🇩🇪 **Deutsch**

Die Karte verwendet Home-Assistant-CSS-Variablen wie `--primary-color`, `--primary-text-color`, `--secondary-text-color`, `--secondary-background-color`, `--primary-background-color`, `--divider-color`, `--warning-color` und `--error-color`.

Dadurch passt sich die Darstellung an Light Mode, Dark Mode und eigene Home-Assistant-Themes an.

🇬🇧 **English**

The card uses Home Assistant CSS variables such as `--primary-color`, `--primary-text-color`, `--secondary-text-color`, `--secondary-background-color`, `--primary-background-color`, `--divider-color`, `--warning-color` and `--error-color`.

This allows the card to adapt to light mode, dark mode and custom Home Assistant themes.

## Screenshots · Screenshots

Screenshots will be added in a future update.

## Development · Entwicklung

🇩🇪 **Deutsch**

Die Karte wird eigenständig weiterentwickelt. Fehlerberichte, Verbesserungsvorschläge und neue Ideen sind über GitHub Issues willkommen.

🇬🇧 **English**

The card is developed independently and will be expanded incrementally. Bug reports, improvement suggestions and new ideas are welcome through GitHub Issues.

## CI and HACS · CI und HACS

Das Repository verwendet GitHub Actions mit der offiziellen **HACS validation** für das Frontend-Plugin. Die Validierung läuft bei Pushes und Pull Requests.

The repository uses GitHub Actions with the official **HACS validation** for the frontend plugin. Validation runs on pushes and pull requests.

## AI-assisted development · KI-Unterstützung

🇩🇪 **Deutsch**  
Teile dieses Projekts wurden mit Unterstützung von KI erstellt. Der Code wurde von Menschen überprüft und auf realer Hardware bzw. in einer realen Home-Assistant-Umgebung getestet.

🇬🇧 **English**  
Parts of this project were created with the assistance of AI. The code has been reviewed by humans and tested on real hardware and in a real Home Assistant environment.

## License · Lizenz

🇩🇪 **Deutsch**  
Dieses Projekt steht unter der **MIT License**. Siehe `LICENSE`.

🇬🇧 **English**  
This project is released under the **MIT License**. See `LICENSE`.

---

Developed with care for Home Assistant and local smart-home infrastructure.

## Version 1.0.0

- Initial standalone release of the Lovelace card.
- Added visual card editor configuration.
- Added summary and detail navigation.
- Added HACS plugin metadata and validation workflow.
- Added Card Picker registration and entity suggestion support.
