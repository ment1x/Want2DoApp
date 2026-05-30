# 📅 Wochenplaner

Eine browserbasierte To-do-App mit wöchentlichem Planungsassistenten – als einzelne HTML-Datei, ohne Installation, ohne Anmeldung, komplett offline.

---

## ✨ Features

- **Aufgabenverwaltung** mit Kategorien, Dringlichkeitsstufen und optionaler Beschreibung
- **Sortierung nach Auswahlwahrscheinlichkeit**: Aufgaben werden nach ihrem internen Score (Dringlichkeit × Alter) absteigend sortiert angezeigt
- **Wochenplan-Modus**: Die App schlägt automatisch eine Aufgabe pro Kategorie vor – gewichtet nach Dringlichkeit und Aufgabenalter
- **Aufgaben direkt erledigen**: Im Aufgaben-Tab Karte nach rechts wischen → sofort als erledigt markieren
- **Wiederkehrende Aufgaben**: Landen nach Erledigung automatisch wieder im Pool
- **Statistik**: Gestapeltes Balkendiagramm der letzten 8 Kalenderwochen + Ø-Aufgaben pro Woche + Aufschlüsselung nach Kategorie
- **Anpassbare Kategorien**: Bis zu 6 Kategorien mit eigenem Namen, Farbe und Icon
- **Konfigurierbares Scoring**: Gewichte und Altersdivisor frei einstellbar
- **Datensicherung**: Export und Import als JSON
- **Keine Cloud, keine Cookies, keine Tracker** – alle Daten lokal im Browser

---

## 🚀 Schnellstart

```bash
# Einfach die Datei im Browser öffnen – keine weiteren Schritte nötig
open wochenplaner_v3.html
```

Oder per Doppelklick auf `wochenplaner_v3.html`. Fertig.

---

## 🗂 Navigation

Die App besteht aus drei Tabs in der unteren Navigationsleiste:

| Tab | Inhalt |
|---|---|
| **Aufgaben** | Alle offenen und erledigten Aufgaben; Filter nach Kategorie |
| **Wochenplan** | Automatisch generierter Plan mit einer Aufgabe pro Kategorie |
| **Statistik** | Gestapeltes Balkendiagramm (8 Wochen) und Auswertung je Kategorie |

---

## 📝 Aufgaben

### Neue Aufgabe anlegen

Tippe auf den schwarzen **`+`**-Button (rechts unten).

| Feld | Pflicht | Beschreibung |
|---|---|---|
| Titel | ✅ | Kurze Bezeichnung |
| Beschreibung | — | Optionaler Zusatztext |
| Kategorie | ✅ | Thematische Zuordnung |
| Dringlichkeit | ✅ | Heute / Diese Woche / Irgendwann |
| Wiederholung | — | Nach Erledigung zurück in den Pool |

### Sortierung

Offene Aufgaben werden nach ihrer **Auswahlwahrscheinlichkeit** absteigend sortiert – dieselbe Formel, die auch der Wochenplan verwendet. Dringende und ältere Aufgaben erscheinen ganz oben.

### Bearbeiten, Erledigen & Löschen

- **Tippe** auf eine Karte → Bearbeitungsformular öffnet sich
- **Nach rechts wischen** → Aufgabe sofort als erledigt markieren ✓
- **Nach links wischen** → Aufgabe sofort löschen

### Filtern

Die Chip-Leiste unter der Kopfzeile filtert die Ansicht nach Kategorie. Erledigte Aufgaben erscheinen am Ende der Liste in einem ausklappbaren Abschnitt.

---

## 🗓 Wochenplan

Beim ersten Besuch des Wochenplan-Tabs fragt die App, ob ein neuer Plan erstellt werden soll.

| Geste | Aktion |
|---|---|
| Nach **rechts** wischen | Aufgabe für diese Woche annehmen |
| Nach **links** wischen | Andere Aufgabe für diesen Slot laden |
| Auf Karte tippen | Datum, Uhrzeit und Dauer festlegen |
| „Als erledigt markieren" | Aufgabe abhaken; neuer Vorschlag folgt automatisch |

> **Tipp:** Zu Beginn einer neuen Woche zeigt die App einen Dialog für nicht erledigte Aufgaben aus der Vorwoche – diese können zurück in den Pool gelegt werden.

### Scoring-Formel

Die gewichtete Zufallsauswahl basiert auf:

```
Score = Dringlichkeitsgewicht × (1 + Alter in Tagen / Altersdivisor)
```

Ältere und dringlichere Aufgaben erscheinen dadurch häufiger im Wochenplan – und stehen im Aufgaben-Tab ganz oben.

---

## ⚙️ Einstellungen

Erreichbar über das **`⋮`**-Menü oben rechts.

### Kategorien verwalten
- Bis zu **6 Kategorien** mit Name, Farbe (8 Optionen) und Icon (12 Optionen)
- Bestehende Kategorien bearbeiten oder löschen

### Dringlichkeitsstufen
- Labels und **Gewichte** (1–10) der drei Stufen frei konfigurierbar
- **Altersdivisor** (1–30 Tage): steuert den Einfluss des Aufgabenalters auf das Scoring

### Daten sichern

```
Einstellungen → Daten exportieren (JSON)   # Backup erstellen
Einstellungen → Daten importieren (JSON)   # Backup wiederherstellen
```

---

## ⌨️ Gesten & Tastenkürzel

| Aktion | Bedienung |
|---|---|
| Aufgabe als erledigt markieren | Karte im Aufgaben-Tab nach **rechts** wischen |
| Aufgabe löschen | Karte im Aufgaben-Tab nach **links** wischen |
| Wochenplan-Slot: annehmen | Karte nach rechts wischen |
| Wochenplan-Slot: neu laden | Karte nach links wischen |
| Aufgabe speichern | `Enter` im Titelfeld |
| Kategorie speichern | `Enter` im Namensfeld |
| Sheet schließen | Auf den Hintergrund tippen |

---

## 🔧 Technische Details

| Eigenschaft | Wert |
|---|---|
| Technologie | Vanilla HTML/CSS/JavaScript (Single File) |
| Datenspeicherung | Browser LocalStorage |
| Datenschutz | Keine externe Verbindung, kein Tracking |
| Datenbereinigung | Erledigte Aufgaben nach 12 Wochen automatisch |
| Kompatibilität | Chrome 90+, Firefox 88+, Safari 14+, Edge 90+ |
| PWA-fähig | Ja (Add to Home Screen auf iOS/Android) |
| Abhängigkeiten | [Lucide Icons](https://lucide.dev/) via CDN, [DM Sans](https://fonts.google.com/specimen/DM+Sans) via Google Fonts |

> **Hinweis:** Private/Inkognito-Fenster speichern keine Daten dauerhaft. Für geräteübergreifende Synchronisierung bitte den JSON-Export nutzen.

---

## 📋 Änderungshistorie

### Version 3
- **Aufgaben-Tab – Sortierung**: Aufgaben werden jetzt nach ihrem tatsächlichen Auswahlscore (`Dringlichkeit × Alter`) absteigend sortiert, nicht mehr nur nach Dringlichkeitsstufe
- **Aufgaben-Tab – Erledigen per Swipe**: Karte nach rechts wischen markiert eine Aufgabe sofort als erledigt und aktualisiert die Statistik automatisch
- **Statistik – Stacked Bar Chart**: Der Gesamt-Bereich zeigt jetzt ein gestapeltes Balkendiagramm der letzten 8 Kalenderwochen (pro Balken eine Woche, pro Segment eine Kategorie); aktuelle KW wird hervorgehoben
- **Statistik – Ø-Aufgaben pro Woche**: Neue Kennzahl zeigt den Durchschnitt erledigter Aufgaben pro Woche über die gesamte Laufzeit

### Version 2
- Initiale Veröffentlichung

---

## 📄 Lizenz

Dieses Projekt steht zur freien Nutzung zur Verfügung.
