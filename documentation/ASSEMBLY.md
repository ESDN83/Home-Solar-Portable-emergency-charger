# 🔨 Aufbauanleitung / Assembly Instructions

<div align="center">

**Schritt-für-Schritt Anleitung zum Bau des Notstrom-Ladegeräts**  
**Step-by-Step Guide to Build the Emergency Charger**

</div>

---

## 📋 Voraussetzungen / Prerequisites

**🇩🇪 Deutsch:**
- ✅ Alle Komponenten aus der [Stückliste](PARTS.md) besorgt
- ✅ 3D-Drucker für Gehäuseteile (oder alternative Befestigung)
- ✅ Grundwerkzeug (Schraubendreher, Zange, Abisolierzange, Crimpzange)
- ✅ Multimeter zum Testen
- ✅ **Elektrofachkraft empfohlen!**

**🇬🇧 English:**
- ✅ All components from the [parts list](PARTS.md) acquired
- ✅ 3D printer for housing parts (or alternative mounting)
- ✅ Basic tools (screwdrivers, pliers, wire strippers, crimper)
- ✅ Multimeter for testing
- ✅ **Qualified electrician recommended!**

---

## 🖨️ Schritt 1: 3D-Druck der Gehäuseteile / Step 1: 3D Print Housing Parts

### Druckeinstellungen / Print Settings

```
Material:    PETG oder ABS (hitzebeständig!)
Layer:       0.2mm
Infill:      20-30%
Supports:    Ja / Yes
Build Plate: beheizbar / heated
```

### Zu druckende Teile / Parts to Print

1. **DIN_RAIL_Mount_lying.stl** - Halterung für MeanWell Netzteil
2. **Solar-Box-CEE-Stecker_v3.stl** - CEE Eingangsstecker-Halterung
3. **Solar-Box-Solar.Stecker_V2.stl** - MC4 Ausgangsbuchsen-Halterung
4. **Deckplatte_Solar-charge.stl** - Abdeckplatte

📁 Alle STL-Dateien: [`documentation/3d_files/`](3d_files/)

⏱️ **Geschätzte Druckzeit:** 10-12 Stunden total

---

## 📦 Schritt 2: Gehäuse vorbereiten / Step 2: Prepare Housing

### Material:
- Wasserdichte Industriebox (empfohlen: 400x300x170mm oder größer)
- Lüftungsgitter für Luftzirkulation
- Kabelverschraubungen (M16/M20 IP67)

### Vorgehen:

1. **Lüftungsöffnungen bohren** (beide Seiten für Durchzug)
   - Eingang: Unten (kalte Luft)
   - Ausgang: Oben (warme Luft)
   - Gitter mit Insektenschutz montieren

2. **Durchführungen für Kabel bohren**
   - AC-Eingang (CEE-Stecker)
   - DC-Ausgang (MC4-Buchsen)
   - Kabelverschraubungen einsetzen

3. **DIN-Schiene montieren** (optional)
   - Für MeanWell Netzteil
   - Alternativ: Direkt verschrauben

![Gehäuse Beispiel](images/20260126_002307.jpg)

---

## ⚡ Schritt 3: MeanWell Netzteil montieren / Step 3: Mount MeanWell PSU

### Montage:

1. **Position wählen**
   - Abstand zu Wänden: min. 5cm (Luftzirkulation!)
   - Lüfter nach oben/hinten ausgerichtet
   
2. **Befestigung**
   - Option A: Mit 3D-gedrucktem DIN-Rail Mount
   - Option B: Direkt mit M4-Schrauben am Gehäuseboden

3. **Erdung sicherstellen**
   - FG (Frame Ground) mit Gehäuse verbinden
   - PE-Leiter fest anschließen

![MeanWell Montage](images/20260119_091037.jpg)

---

## 🔌 Schritt 4: AC-Eingang verkabeln / Step 4: Wire AC Input

### Benötigte Kabel:
- 3-adriges Kabel (L, N, PE) - mind. 1.5mm²
- CEE-Stecker 16A/230V

### Verkabelung:

```
CEE-Stecker          MeanWell CSP-3000-400
--------------------------------------------
L (braun)      →     AC/L (Klemme 1)
N (blau)       →     AC/N (Klemme 2)
PE (gelb-grün) →     FG (Frame Ground)
```

**⚠️ WICHTIG:**
- Alle Verbindungen fest anziehen!
- Aderendhülsen verwenden
- Zugentlastung am Kabeleingang

![AC Verkabelung](images/20260119_091052.jpg)

---

## 🔋 Schritt 5: DC-Ausgang mit Sperrdioden verkabeln / Step 5: Wire DC Output with Blocking Diodes

### Schaltplan / Wiring Diagram:

```
MeanWell (+V)  →  [ Sperrdiode 1 ] ──┐
                  [ Sperrdiode 2 ] ──┼──→  MC4 (+) → zu PV-Eingang
                  [ Sperrdiode 3 ] ──┘
                  
MeanWell (-V)  ────────────────────────→  MC4 (-) → zu PV-Eingang
```

### Wichtige Details:

1. **Sperrdioden parallel schalten** (2-3 Stück)
   - Reduziert Wärmeverluste
   - Erhöht Stromtragfähigkeit
   - **Richtung beachten!** Anode zum Netzteil, Kathode zum MC4

2. **Kabelquerschnitt: 6mm² Solarkabel**
   - Rot für + (Plus)
   - Schwarz für - (Minus)

3. **DC-Lasttrennschalter einbauen**
   - Zwischen Dioden und MC4-Ausgang
   - Ermöglicht sicheres Trennen

![DC Verkabelung](images/20260119_091100.jpg)

---

## 🎛️ Schritt 6: Steuerung anschließen (optional) / Step 6: Connect Control (Optional)

### Option A: Fertig-Kabelkit (empfohlen)

Verwende das [8-pol SYNCKABEL](https://www.henri.de/Stromversorgung/Schaltnetzteile/Kabelsaetze/8748/Kabelkit-SYNCKABEL-8pol-Steuerleitung-fuer-MeanWell-CN1-CN2-CN100-8pol-Stecker-zur-Netzteile-Serie.html):
- Stecker an CN2 Port des MeanWell
- Potentiometer extern montieren (Spannungsregelung)

### Option B: Eigenbau

Komponenten:
- DC/DC Wandler 12V → 10V
- 10K Potentiometer (22mm)
- Passender Stecker für CN2

**Anschlussplan:** Siehe MeanWell CSP-3000-400 Datenblatt Seite 7

---

## 🧪 Schritt 7: Funktionstest / Step 7: Function Test

### BEVOR das System ans PV angeschlossen wird!

1. **Visuell prüfen**
   - Alle Verbindungen fest
   - Keine blanken Drähte
   - Polarität korrekt

2. **Multimeter-Test (ohne Last)**
   - Generator starten
   - MeanWell einschalten
   - Spannung am DC-Ausgang messen
   - **Soll: 350-400V DC**

3. **Stromtest mit Dummy-Last**
   - Hochleistungs-Widerstand (falls vorhanden)
   - Strom sollte einstellbar sein

⚠️ **Erst nach erfolgreichem Test weitermachen!**

![Testaufbau](images/20260126_002311.jpg)

---

## 🏠 Schritt 8: Anschluss an PV-System / Step 8: Connect to PV System

### Vorbereitung:

1. **Freien MPPT-Eingang wählen**
   - Idealerweise ungenutzter String-Eingang
   - NICHT parallel zu bestehenden PV-Modulen!

2. **Bestehende PV-Module trennen** (falls nötig)
   - DC-Freischalter nutzen
   - Spannungen vergleichen (PV vs. Charger)

### Anschluss:

```
Charger MC4 (+) → PV String (+) Eingang am Wechselrichter
Charger MC4 (-) → PV String (-) Eingang am Wechselrichter
```

**Inbetriebnahme:**
1. Generator starten & warmlaufen lassen
2. MeanWell einschalten (prüft Ausgangsspannung)
3. DC-Lasttrennschalter einschalten
4. Nach ca. 60 Sek sollte MPPT-Tracking beginnen
5. Wechselrichter-Display beobachten: Leistung sollte ansteigen

![Anschluss Beispiel](images/20260126_002315.jpg)

---

## 🧪 Testablauf: Simulierter Blackout / Test Procedure: Simulated Blackout

### Sicherer Testablauf:

| Schritt | Aktion | Erwartetes Ergebnis |
|---------|--------|---------------------|
| 1 | Hauptsicherungen AUSSCHALTEN | Netz getrennt |
| 2 | Warten 5-10 Sekunden | Wechselrichter → Notstrombetrieb |
| 3 | Haus läuft auf Batterie | Verbraucher funktionieren |
| 4 | Generator starten (Außenbereich!) | Generator läuft stabil |
| 5 | Charger einschalten | DC-Spannung 350-400V |
| 6 | DC-Breaker einschalten | Verbindung hergestellt |
| 7 | Warten ~60 Sekunden | MPPT beginnt Tracking |
| 8 | Display prüfen | Ladeleistung sichtbar (z.B. 2kW) |
| 9 | Batterie-SOC beobachten | Ladung steigt |

✅ **Erfolg:** Batterie lädt vom Generator!

![Betrieb](images/20260126_002328.jpg)

---

## 📸 Galerie / Gallery

Hier sind weitere Fotos vom Aufbau:

<div align="center">

![Build 1](images/20260119_091030.jpg)
![Build 2](images/20260126_002339.jpg)
![Build 3](images/20260126_002357.jpg)

</div>

---

## ⚠️ Sicherheitshinweise / Safety Instructions

### 🔴 HOCHSPANNUNG / HIGH VOLTAGE

- ⚡ **400V DC kann tödlich sein!**
- Nie unter Last stecken/trennen (Lichtbogengefahr!)
- Spannungsfreiheit mit Multimeter prüfen
- Kondensatoren können Ladung halten → 5 Min warten nach Abschalten

### 🔴 VERPOLUNG / REVERSE POLARITY

- Falsche Polung = sofortige Zerstörung!
- Mehrfach mit Multimeter prüfen
- Farbcodierung beachten (rot = +, schwarz = -)

### 🔴 GENERATOR-BETRIEB / GENERATOR OPERATION

- **NUR IM AUSSENBEREICH!** - Kohlenmonoxid-Gefahr!
- Min. 3m Abstand zu Gebäuden
- Brennbare Materialien entfernen
- Erdung des Generators sicherstellen

### 🔴 WÄRMEENTWICKLUNG / HEAT GENERATION

- Netzteil erzeugt 150-300W Abwärme
- Lüftungsschlitze NICHT blockieren
- Regelmäßig Temperatur prüfen
- Bei Überhitzung: SOFORT ABSCHALTEN

---

## 🔧 Wartung / Maintenance

### Monatlich / Monthly:
- [ ] Lüftungsgitter reinigen
- [ ] Verbindungen auf Festigkeit prüfen
- [ ] Gehäuse auf Beschädigungen prüfen

### Jährlich / Yearly:
- [ ] Komplette Sichtprüfung aller Komponenten
- [ ] Sperrdioden auf Durchgang testen
- [ ] Isolationswiderstand messen
- [ ] Funktionstest durchführen

---

**[◀ Zurück zur Stückliste](PARTS.md)** | **[Weiter zum Schaltplan ▶](SCHEMATICS.md)**
