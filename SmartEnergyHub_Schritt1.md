
# Projekt: SmartEnergyHub – Intelligentes Energie-Monitoring & Steuerung

## 🎯 Ziel

Eine cloudbasierte Web-App, die PV-, Speicher-, Netz- und Verbraucher-Daten via MQTT erfasst, visualisiert und intelligent steuert.  
Die App soll auch von anderen Nutzern genutzt werden können und ist vollständig mandantenfähig (Multi-User).  

---

## ✅ Nutzergruppen

| Zielgruppe          | Beschreibung                                                         |
|---------------------|----------------------------------------------------------------------|
| Endkunden (Laien)   | Einfache Oberfläche, keine MQTT-Kenntnisse nötig                     |
| Bastler/Techniker   | Volle Kontrolle, Konfigurierbarkeit, MQTT-Transparenz                |
| Installateure       | Verwaltung mehrerer Anlagen, Nutzerverwaltung je Kunde möglich       |

---

## ☁️ Betriebsmodell

- **Cloud-Plattform** mit Registrierung, Login, User-Rollen
- Nutzer verbindet eigene MQTT-Broker (öffentlich erreichbar)
- Ziel: Selbstbetriebene Plattform mit optionalem Premium-Modell

---

## 🔌 Datenanbindung: MQTT (Variante 1)

- Nutzer gibt MQTT-URL, Port, Auth-Daten ein
- Die Plattform verbindet sich direkt mit dem Broker
- Mehrere parallele MQTT-Verbindungen (eine pro Nutzer)
- Optional: TLS & Zertifikatsverwaltung

---

## 📡 Geräte & Integration (Maximale Tiefe)

### Victron (Venus OS)
- PV-Leistung, Batteriedaten, Netzbezug, AC-Daten, Ladezustände
- Steuerung: Lade-Modi, MultiPlus-Status, Grid-Limit

### Deye
- PV-Leistung, Netzwerte, SOC, Batterie, Laufzeit, Ertrag
- Steuerung: Betriebsmodi, Ladezeiten, Grid-Limit

### Growatt
- PV, Batterie, Netz, Fehlercodes
- Steuerung: Lade-/Entladerate, Prioritäten

### Shelly
- Leistung, Verbrauch, Spannung, Schaltstatus
- Steuerung: Ein/Aus, Zeitpläne, Gruppensteuerung

---

## 📊 Visualisierung (UX-Ziele)

| Modul                        | Funktion                                                     |
|------------------------------|--------------------------------------------------------------|
| Live-Dashboard               | Realtime-Anzeige von PV, Verbrauch, Batterie, Netz           |
| Historische Charts           | Tages-, Wochen-, Monatsanalyse je Gerät                      |
| Vergleichsansicht            | Geräte oder Zeiträume vergleichen                            |
| Datenexport                  | CSV-/Excel-Download                                          |
| Regel-UI                     | Visuelles Regelwerk („Wenn A, dann B“)                       |
| Mobile-ready                 | Reaktionsschnelle Oberfläche, PWA-fähig                      |

---

## ⚙️ Steuerung & Automatisierung

| Typ                          | Beschreibung                                                 |
|------------------------------|--------------------------------------------------------------|
| Manuelles Schalten           | Button-Steuerung im UI                                       |
| Zeitgesteuerte Regeln        | Geräte schalten nach Zeitplan                                |
| Bedingte Regeln              | z. B. PV > 3kW & SOC > 80% → Shelly an                       |
| PV-Prognose-basiert          | z. B. lade Batterie vor, wenn morgen viel Sonne erwartet     |
| Strompreisoptimiert          | z. B. schalte nur bei negativen Strompreisen                 |
| Mehrgeräte-Strategien        | Gruppenlogik, Staffelung, Load-Shifting                      |
| Notfallübersteuerung         | Sofort abschalten / aktivieren über Webhook, UI oder API     |

---

## 🌐 Datenquellen & API-Integrationen

- PV-Vorhersage (Solcast, OpenWeather, pvforecast)
- Strompreise (Awattar, Tibber, EPEX Spot)
- Wetter (Temperatur, Regen, Gewitter)
- Sonnenstand / Standortdaten
- Kalender (z. B. „nur an Werktagen“)
- Webhooks (z. B. IFTTT, Tasker, Node-RED)

---

## 📌 Fazit

SmartEnergyHub soll eine professionelle, aber nutzerfreundliche Energieplattform werden, die intelligente Automatisierung, Visualisierung und Steuerung in einer skalierbaren Cloud-App kombiniert.

**Bereit für Schritt 2: Systemarchitektur & technische Strukturplanung.**
