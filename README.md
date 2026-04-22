# 📊 Faktura 62 - Dashboard & Verwaltung

> **Internes Dashboard für Filiale 62 - Monatsdaten, Kundenpreise & Analysen**

Eine Single-Page-Application zur Verwaltung und Visualisierung von Monatsumsätzen, Paketmengen und Kundenpreisen für KEP Filiale 62.

---

## 🎯 Features

### **Dashboard & Analytics**
- 📈 **Jahresübersichten** für 2024, 2025, 2026
- 📊 **Interaktive Charts** (Chart.js)
  - Monatsumsatz über das Jahr
  - Anzahl Pakete pro Monat
  - Durchschnittspreis pro Paket
  - Top 5 Kunden nach Umsatz
- 💰 **KPI-Cards** mit Jahresumsatz Total/Netto, Paketanzahl, Durchschnittspreisen
- 📋 **Detaillierte Monatstabellen** mit Arbeitstagen, Umsatz, Paketen und Deltas

### **Monatsdaten-Erfassung**
- ✏️ **Neue Monate erfassen** mit Formular
- 🔄 **Bestehende Monate bearbeiten**
- 🗑️ **Monate löschen**
- 📝 **Felder:** Arbeitstage, Total, Netto, Pakete, Treibstoff, Notizen

### **Kundenverwaltung**
- 💰 **Kundenpreise** nach Jahr/Monat verwalten
- 🔍 **Suche & Filter** nach Kundennummer oder Name
- 📊 **Top 10 Charts** (Umsatz, Pakete, Preis pro Paket)
- 🏢 **443 Kunden** aus Excel-Import integriert
- 📁 **Kundenliste** mit Status, Eröffnungsdatum, Notizen

### **Admin-System**
- 🔐 **Passwortschutz** (View-Only vs. Admin-Modus)
- 👁️ **View-Only Badge** für Read-Only Nutzer
- ✏️ **Vollzugriff** nur mit Admin-Passwort
- 🔒 **Alle Inputs deaktiviert** im View-Only Modus

### **Changelog & Backup**
- 📋 **Automatisches Änderungsprotokoll** (letzte 50 Einträge)
- 💾 **Backup-Export** (JSON)
- ⬆️ **Backup-Import** zur Wiederherstellung
- 🕐 **Timestamps** für alle Änderungen

---

## 🚀 Live Demo

**URL:** `https://[username].github.io/faktura-62/`

> ⚠️ **Hinweis:** App ist passwortgeschützt. View-Only Modus ist öffentlich, Bearbeitung erfordert Admin-Login.

---

## 🛠️ Technologie

### **Frontend**
- **HTML5** - Semantic markup
- **CSS3** - Custom design system mit Gradients & Glassmorphism
- **Vanilla JavaScript** - Kein Framework, nur moderne ES6+
- **Chart.js 4.4.1** - Interaktive Diagramme
- **SheetJS (XLSX)** - Excel-Import/Export

### **Architektur**
- ✅ **Single-File Application** - Alles in einer HTML-Datei
- ✅ **Embedded Data** - JSON-Daten inline gespeichert
- ✅ **No Backend** - Rein client-side
- ✅ **Responsive** - Mobile-friendly Design
- ✅ **Offline-fähig** - Funktioniert auch ohne Internet

### **Design System**
- **Fonts:** DM Mono (Code), Syne (Headlines)
- **Colors:** Dark theme mit Accent-Colors (Teal, Blue, Orange, Red)
- **Animations:** Smooth transitions & fades
- **Glassmorphism:** Backdrop blur & transparency

---

## 📦 Installation & Setup

### **Lokale Entwicklung**

```bash
# Repository klonen
git clone https://github.com/[username]/faktura-62.git
cd faktura-62

# Datei öffnen
open index.html
# oder
start index.html
```

### **GitHub Pages Deployment**

1. **Repository Settings** → **Pages**
2. **Source:** Main branch
3. **Save**
4. Nach 1-2 Minuten live unter: `https://[username].github.io/faktura-62/`

---

## 🔐 Admin-Zugang

### **Standard-Passwort:**
```
1899062
```

> ⚠️ **Sicherheit:** Passwort bitte nach Deployment ändern!

### **Passwort ändern:**

Öffne `index.html` und suche nach:
```javascript
const ADMIN_PASSWORD = '1899062';
```

Ersetze mit neuem Passwort:
```javascript
const ADMIN_PASSWORD = 'DeinNeuesPasswort123';
```

---

## 💾 Daten aktualisieren

### **Embedded Data im Code:**

Die Daten sind direkt in der HTML-Datei gespeichert:

```javascript
const EMBEDDED_DATA = [
  {
    "id": "2026-3",
    "year": 2026,
    "month": 3,
    "monatLabel": "Mär 2026",
    "arbeitstage": 22,
    "total": 1075943.34,
    "netto": 986199.21,
    "pakete": 167177
  },
  // ... weitere Monate
];
```

### **Update-Workflow:**

**Option A: Manuell**
```bash
1. index.html in Editor öffnen
2. Suche: "const EMBEDDED_DATA = ["
3. Ersetze Daten mit neuem Backup
4. Speichern & committen
5. Git push
```

**Option B: Script (empfohlen)**
```bash
# Coming soon: Auto-Update Script
python update_data.py --backup backup.json
```

---

## 📊 Datenstruktur

### **Monatsdaten**
```javascript
{
  "id": "2026-3",           // Unique ID: YYYY-M
  "year": 2026,             // Jahr
  "month": 3,               // Monat (1-12)
  "monatLabel": "Mär 2026", // Display-Label
  "arbeitstage": 22,        // Arbeitstage im Monat
  "total": 1075943.34,      // Umsatz Total (CHF)
  "netto": 986199.21,       // Umsatz Netto (CHF)
  "pakete": 167177,         // Anzahl Pakete
  "treibstoff": 1,          // Treibstoffzuschlag (%)
  "notiz": ""               // Optionale Notiz
}
```

### **Kundendaten**
```javascript
{
  "nr": "173808",           // Kundennummer
  "name": "Firma AG",       // Firmenname
  "status": "Aktiv",        // Status
  "eroeffnung": "2024-01",  // Eröffnungsdatum
  "notiz": ""               // Optionale Notiz
}
```

### **Kundenpreise**
```javascript
{
  "173808": {               // Kundennummer
    "2026": {               // Jahr
      "3": {                // Monat
        "w1": 156.00,       // Woche 1 Preis
        "w2": 158.50,       // Woche 2 Preis
        "w3": 157.20,       // Woche 3 Preis
        "w4": 159.80        // Woche 4 Preis
      }
    }
  }
}
```

---

## 🎨 Design Anpassungen

### **Farben ändern:**

Suche in der `<style>` Sektion nach CSS-Variablen:

```css
:root {
  --accent: #4fffb0;      /* Teal */
  --accent2: #3b7ff5;     /* Blue */
  --accent3: #f5a623;     /* Orange */
  --accent4: #ff6b6b;     /* Red */
}
```

### **Fonts ändern:**

```html
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
```

---

## 📝 Changelog

### **Version 1.0.0** (2026-04-22)
- ✅ Initial Release
- ✅ Dashboard mit 3 Jahresansichten (2024-2026)
- ✅ Monatsdaten-Erfassung
- ✅ Kundenverwaltung mit 443 Kunden
- ✅ Admin-System mit Passwortschutz
- ✅ Changelog-Feature
- ✅ Backup/Import Funktionalität
- ✅ Single-File Standalone Version

---

## 🔒 Sicherheit

### **Best Practices:**

✅ **Admin-Passwort ändern** nach Deployment  
✅ **Repository privat halten** (nur für interne Nutzung)  
✅ **Keine sensiblen Kundendaten** in öffentlichem Repo  
✅ **HTTPS nur** (GitHub Pages automatisch)  
✅ **View-Only Default** für alle Nutzer  

### **Datenschutz:**

- Keine externen Analytics
- Keine Cookies
- Keine Tracking-Scripts
- Alle Daten client-side (kein Server)
- LocalStorage nur für Admin-Status & Changelog

---

## 🐛 Bekannte Limitierungen

- ⚠️ **SharePoint-Vorschau** - Funktioniert nicht direkt in SharePoint (nutze GitHub Pages)
- ⚠️ **Browser-Kompatibilität** - Benötigt modernen Browser (Chrome 90+, Firefox 88+, Safari 14+)
- ⚠️ **LocalStorage** - Changelog & Admin-Status nur im aktuellen Browser
- ⚠️ **Mobile** - Optimiert für Desktop, funktioniert auf Mobile aber mit eingeschränkter UX

---

## 📞 Support

Bei Fragen oder Problemen:
- 📧 Email: [deine-email]
- 💬 Teams: [dein-teams-handle]

---

## 📄 Lizenz

**Interne Verwendung only**  
© 2026 KEP Filiale 62 - Alle Rechte vorbehalten

---

## 🙏 Credits

- **Chart.js** - https://www.chartjs.org/
- **SheetJS** - https://sheetjs.com/
- **Google Fonts** (DM Mono, Syne)
- **Entwickelt mit Claude** (Anthropic)

---

**Made with ❤️ for Filiale 62**
