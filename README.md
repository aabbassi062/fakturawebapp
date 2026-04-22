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


- Keine externen Analytics
- Keine Cookies
- Keine Tracking-Scripts
- Alle Daten client-side (kein Server)
- LocalStorage nur für Admin-Status & Changelog

---


## 📄 Lizenz

**Interne Verwendung only**  
© 2026 KEP Filiale 62 - Alle Rechte vorbehalten



---

**Made with ❤️ for Filiale 62**
