# 📦 Stückliste / Parts List

<div align="center">

**Vollständige Komponentenliste für das Notstrom-Ladegerät**  
**Complete Component List for the Emergency Charger**

</div>

---

## 🔋 Hauptkomponenten / Main Components

### 1. Netzteil / Power Supply Unit

| Artikel | Hersteller | Modell | Spezifikation | Preis | Link |
|---------|------------|--------|---------------|-------|------|
| **Schaltnetzteil** | MeanWell | CSP-3000-400 | 400V DC, 7.5A, 3000W | 349,95€ | [Voelkner](https://www.voelkner.de/products/1412939/MEAN-WELL-CSP-3000-400-Schaltnetzteil-400-V-DC-7.5A-3000W.html) |

**Technische Daten:**
- Eingangsspannung: 230V AC
- Ausgangsspannung: einstellbar 200-400V DC
- Max. Ausgangsstrom: 7.5A
- Max. Leistung: 3000W
- Modi: CV (Constant Voltage) / CC (Constant Current)
- Kühlung: Aktiver Lüfter (temperaturgesteuert)

---

### 2. Steuerung / Control System

| Artikel | Beschreibung | Preis | Link |
|---------|--------------|-------|------|
| **Steuerkabel** | 8-pol Kabelkit für MeanWell CN1/CN2 | 19,90€ | [Henri.de](https://www.henri.de/Stromversorgung/Schaltnetzteile/Kabelsaetze/8748/Kabelkit-SYNCKABEL-8pol-Steuerleitung-fuer-MeanWell-CN1-CN2-CN100-8pol-Stecker-zur-Netzteile-Serie.html) |

**Alternative: Eigenbau-Regelung** (optional):
- DC/DC Spannungswandler 12V → 10V (z.B. DEBO DCDC UP 3 - Reichelt)
- Potentiometer 10K, 22mm (z.B. LA42DWQ-22)
- Passender Stecker für CN2 Port

---

### 3. Sicherheitskomponenten / Safety Components

| Komponente | Spezifikation | Menge | Preis | Beispiel-Link |
|------------|---------------|-------|-------|---------------|
| **Sperrdioden** | 1000V, 30A Schottky/Standard | 2-3x (parallel) | 8,29€ | [Amazon B0DXKYR1FZ](https://www.amazon.de/dp/B0DXKYR1FZ) |
| **DC-Lasttrennschalter** | 1000V DC, 32A (z.B. Hager SB432PV) | 1x | 8,69€ | [Amazon B07G35GMS6](https://www.amazon.de/dp/B07G35GMS6) |
| **MC4-Stecker** | Standard PV-Stecker/Buchsen | 1 Paar | 4,00€ | [Amazon B0DJ7J3V5K](https://www.amazon.de/MC-kompatibel-Geh%C3%A4usestecker-Aufbaudosenstecker-Paar/dp/B0DJ7J3V5K) |

**⚠️ Wichtig:** Sperrdioden sind essentiell! Sie verhindern Rückstrom vom PV-System ins Netzteil.

---

### 4. Verkabelung / Cabling

| Artikel | Spezifikation | Preis | Link |
|---------|---------------|-------|------|
| **AC-Kabel** | 3x1.5mm² (L, N, PE) | variabel | Amazon/Baumarkt |
| **DC-Solarkabel** | 6mm², PV-geeignet, rot/schwarz | variabel | [Amazon B0CFYQY5YW](https://www.amazon.de/dp/B0CFYQY5YW) |
| **CEE-Stecker** | 16A/230V (Generator-Anschluss) | variabel | [Amazon B0D5LVCKJT](https://www.amazon.de/dp/B0D5LVCKJT) |

---

### 5. Gehäuse & Montage / Housing & Mounting

| Artikel | Beschreibung | Preis | Link |
|---------|--------------|-------|------|
| **Gehäuse/Box** | Wasserdichte Industriebox (z.B. 400x300x170mm) | 30-50€ | [Amazon B0CVXCFMLY](https://www.amazon.de/dp/B0CVXCFMLY) |
| **DIN-Rail Mount** | Halterung für Netzteil (3D-gedruckt) | Filament | [STL-Datei](3d_files/DIN_RAIL_Mount_lying.stl) |
| **Lüftungsgitter** | Für Gehäusebelüftung | variabel | Baumarkt |
| **Kabelverschraubungen** | M16/M20 IP67 | variabel | Amazon |

---

### 6. Kleinmaterial / Small Parts

| Position | Preis | Link | Vermutete Komponente |
|----------|-------|------|---------------------|
| 1 | 6,99€ | [Amazon B0DN6DRGG2](https://www.amazon.de/dp/B0DN6DRGG2) | Schrauben/Befestigung |
| 2 | 8,30€ | [Amazon B077LZMKLQ](https://www.amazon.de/dp/B077LZMKLQ) | Klemmen/Anschlüsse |
| 3 | 9,99€ | [Amazon B0C8NNLCDH](https://www.amazon.de/dp/B0C8NNLCDH) | Sicherungselement |
| 5 | 1,84€ | [Amazon B00SJFDI16](https://www.amazon.de/dp/B00SJFDI16) | Aderendhülsen |
| 7 | 8,49€ | [Amazon B06Y2HDS1X](https://www.amazon.de/dp/B06Y2HDS1X) | Gehäuseteile |
| 8 | 19,88€ | [Amazon B0DZN5TVRW](https://www.amazon.de/dp/B0DZN5TVRW) | Zusatzlüfter? |
| 9 | 89,95€ | [Amazon B0FFT9QJZR](https://www.amazon.de/dp/B0FFT9QJZR) | Größere Komponente |
| 10 | 11,88€ | [Amazon B0BKQHH6NZ](https://www.amazon.de/dp/B0BKQHH6NZ) | Zubehör |
| 11 | 9,59€ | [Amazon B0D32VCTH4](https://www.amazon.de/dp/B0D32VCTH4) | Anschlussklemmen |
| 14 | 9,49€ | [Amazon B0DXCDVQ6L](https://www.amazon.de/dp/B0DXCDVQ6L) | Elektro-Zubehör |
| 15 | 6,34€ | [Amazon B0CDWTM1FH](https://www.amazon.de/dp/B0CDWTM1FH) | Kabel/Stecker |
| 17 | 8,99€ | [Amazon B0D5LVCKJT](https://www.amazon.de/dp/B0D5LVCKJT) | Stecker |

> **📝 Hinweis:** Die genauen Produktnamen können sich über die Amazon-Links ändern. Bitte vor dem Kauf überprüfen!

---

## 🖨️ 3D-Druck Teile / 3D Printed Parts

Alle STL-Dateien sind im Ordner [`3d_files/`](3d_files/) verfügbar:

| Datei | Beschreibung | Material | Druckzeit |
|-------|--------------|----------|-----------|
| [`DIN_RAIL_Mount_lying.stl`](3d_files/DIN_RAIL_Mount_lying.stl) | Halterung für MeanWell Netzteil | PETG/ABS | ~2h |
| [`Solar-Box-CEE-Stecker_v3.stl`](3d_files/Solar-Box-CEE-Stecker_v3.stl) | Halterung für CEE-Eingangsstecker | PETG/ABS | ~3h |
| [`Solar-Box-Solar.Stecker_V2.stl`](3d_files/Solar-Box-Solar.Stecker_V2.stl) | Halterung für MC4-Ausgangsbuchsen | PETG/ABS | ~2h |
| [`Deckplatte_Solar-charge.stl`](3d_files/Deckplatte_Solar-charge.stl) | Abdeckplatte | PETG/ABS | ~4h |

**Druckeinstellungen:**
- Layer Height: 0.2mm
- Infill: 20-30%
- Material: PETG oder ABS (hitzebeständig!)
- Supports: Ja, wo nötig

---

## 💰 Kostenzusammenfassung / Cost Summary

| Kategorie | Kosten (ca.) |
|-----------|--------------|
| MeanWell CSP-3000-400 | 350€ |
| Sicherheitskomponenten | 20€ |
| Kabel & Stecker | 30€ |
| Gehäuse & Montage | 50€ |
| Kleinmaterial | 50€ |
| 3D-Druck Filament | 10€ |
| **Gesamt** | **~510€** |

**Plus:** Generator (falls nicht vorhanden): 300-1000€+

---

## 🛒 Einkaufsliste / Shopping Checklist

- [ ] MeanWell CSP-3000-400 Netzteil
- [ ] Steuerungskabel oder Eigenbau-Komponenten
- [ ] Sperrdioden (min. 2x, besser 3x parallel)
- [ ] DC-Lasttrennschalter
- [ ] MC4-Steckverbinder (Paar)
- [ ] DC-Solarkabel 6mm² (rot + schwarz)
- [ ] AC-Netzkabel mit CEE-Stecker
- [ ] Wasserdichtes Gehäuse
- [ ] Kabelverschraubungen
- [ ] 3D-Druck Filament (PETG/ABS)
- [ ] Kleinmaterial (Schrauben, Klemmen, etc.)

---

**[◀ Zurück zur Hauptseite](../README.md)** | **[Weiter zur Aufbauanleitung ▶](ASSEMBLY.md)**
