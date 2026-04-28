# 📅 Wochenplaner

Eine browserbasierte To-do-App mit wöchentlichem Planungsassistenten – als einzelne HTML-Datei, ohne Installation, ohne Anmeldung, komplett offline.

---

## ✨ Features

- **Aufgabenverwaltung** mit Kategorien, Dringlichkeitsstufen und optionaler Beschreibung
- **Wochenplan-Modus**: Die App schlägt automatisch eine Aufgabe pro Kategorie vor – gewichtet nach Dringlichkeit und Aufgabenalter
- **Wiederkehrende Aufgaben**: Landen nach Erledigung automatisch wieder im Pool
- **Statistik**: Balkendiagramm der letzten Wochen + Aufschlüsselung nach Kategorie
- **Anpassbare Kategorien**: Bis zu 6 Kategorien mit eigenem Namen, Farbe und Icon
- **Konfigurierbares Scoring**: Gewichte und Altersdivisor frei einstellbar
- **Datensicherung**: Export und Import als JSON
- **Keine Cloud, keine Cookies, keine Tracker** – alle Daten lokal im Browser

---

## 🚀 Schnellstart

```bash
# Einfach die Datei im Browser öffnen – keine weiteren Schritte nötig
open wochenplaner_v2.html
```

Oder per Doppelklick auf `wochenplaner_v2.html`. Fertig.

---

## 🗂 Navigation

Die App besteht aus drei Tabs in der unteren Navigationsleiste:

| Tab | Inhalt |
|---|---|
| **Aufgaben** | Alle offenen und erledigten Aufgaben; Filter nach Kategorie |
| **Wochenplan** | Automatisch generierter Plan mit einer Aufgabe pro Kategorie |
| **Statistik** | Balkendiagramm und Auswertung je Kategorie |

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

### Bearbeiten & Löschen

- **Tippe** auf eine Karte → Bearbeitungsformular öffnet sich
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

Ältere und dringlichere Aufgaben erscheinen dadurch häufiger im Wochenplan.

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
| Aufgabe löschen | Karte nach links wischen |
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

## 📄 Lizenz

Dieses Projekt steht zur freien Nutzung zur Verfügung.
