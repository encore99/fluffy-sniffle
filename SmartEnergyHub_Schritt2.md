
# Schritt 2 – Systemarchitektur: SmartEnergyHub

## 🔐 Benutzer- & Rechteverwaltung

- Jeder Nutzer hat ein eigenes Login
- Eine Installation (Anlage) kann mehreren Nutzern zugewiesen werden (Rollen: Owner, Editor, Viewer)
- Installateure erhalten Zugriff auf mehrere Installationen (Premium)
- Nutzer können eigene Anlagen erstellen und verwalten (Standard), weitere freischalten (Premium)

## 🌐 MQTT-Kommunikation (Hybrid-Modell)

- Nutzer kann:
  - externen eigenen MQTT-Broker verbinden (z. B. Mosquitto lokal)
  - oder zentralen Broker der Plattform nutzen (Premium)
- Jede Installation hat eigene MQTT-Verbindung
- Themen-Mapping per Auto-Discovery (wenn möglich) oder manuell/halbautomatisch

## 🧩 Gerätemodell

- Geräte basieren auf Templates (z. B. Victron Venus, Deye, Shelly, Growatt)
- Alternativ: manuelle Konfiguration aller Topics & Sensoren
- Sensoren können beliebige MQTT-Themen abbilden
- Geräte können durch Auto-Discovery (Shelly, dbus-mqtt) automatisch erkannt werden

## 📡 MQTT-Datenverarbeitung

- Alle MQTT-Nachrichten werden empfangen
- Nur ausgewählte Sensoren werden dauerhaft gespeichert
- Speicherung erfolgt sofort bei jeder Änderung oder neuem Wert

## 🗄️ Speicherstrategie

- Sensorwerte werden dauerhaft und mit voller Auflösung gespeichert
- Keine Datenlöschung – unbegrenzte historische Analyse möglich
- Setup:
  - PostgreSQL für Benutzer, Geräte, Regeln, Konfiguration
  - TimescaleDB für Sensorwerte & Zeitreihen
  - Redis (oder RAM) für Live-Datenpuffer

## 📈 Visualisierung & Zugriff

- Live-Dashboard (Echtzeitdaten pro Anlage)
- Historische Charts (Tag/Woche/Monat/Jahr)
- Vergleichsansichten (Anlage vs. Anlage, Jahr vs. Jahr)
- Datenexport (CSV, Excel)
- Regel-Editor mit Bedingungslogik
- Mobile-optimiert (PWA möglich)

## ⚙️ Regel-Engine

- Auslöser: Zeit, Sensorwert, Wetter, PV-Prognose, Strompreis, Webhook
- Aktionen: MQTT-Befehle, Gerät schalten, Sequenzen starten
- Mehrstufige Bedingungen möglich
- Live-Preview + Testmodus
- Webhooks & API-Trigger integriert

## 🌐 Externe Datenquellen

- Solcast, OpenWeather: PV-Prognose
- Awattar, Tibber: Strompreis-Echtzeitdaten
- OpenWeather, DWD: Wetterdaten
- Kalender (z. B. „nur werktags“)
- Webhooks: Trigger von externen Tools (Node-RED, IFTTT)

## 🧠 Systemarchitektur (Diagramm)

![Systemarchitektur](smartenergyhub_architektur.png)

---

**Bereit für Schritt 3: Automatisierungsmodell & Regeldefinition**
