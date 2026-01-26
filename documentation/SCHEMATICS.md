# ⚡ Schaltplan & Anschlüsse / Schematics & Connections

<div align="center">

**Detaillierte Verdrahtung und elektrische Anschlüsse**  
**Detailed Wiring and Electrical Connections**

</div>

---

## 📊 Systemübersicht / System Overview

### Blockschaltbild / Block Diagram

```mermaid
graph LR
    subgraph AC_Input [AC Eingang]
        Gen[🔌 Generator] --> CEE[CEE Stecker]
        CEE --> RCBO[FI/LS Schutzschalter]
    end

    subgraph Power_Unit [Ladegerät Gerät]
        RCBO --> MW[📦 MeanWell CSP-3000]
        
        subgraph DC_Output_Chain [DC Ausgangskette]
            MW --> Diode[🔒 Sperrdiode<br/>MDK-55]
            Diode --> Volt[📟 Voltmeter]
            Volt --> Amp[📊 Amperemeter]
            Amp --> Fuse[⚡ DC Sicherung<br/>10A Automat]
        end
    end

    subgraph PV_Connection [PV Anschluss]
        Fuse --> MC4[MC4 Buchse]
        MC4 --> WR[🏠 Wechselrichter<br/>MPPT Eingang]
    end

    Poti[🎛️ Potentiometer] -.->|CN2| MW

    %% Styles für bessere Lesbarkeit
    style Gen fill:#fff,stroke:#ff9800,stroke-width:2px,color:#000
    style MW fill:#fff,stroke:#2196f3,stroke-width:2px,color:#000
    style Diode fill:#fff,stroke:#f44336,stroke-width:2px,color:#000
    style Fuse fill:#fff,stroke:#4caf50,stroke-width:2px,color:#000
    style WR fill:#fff,stroke:#9c27b0,stroke-width:2px,color:#000
    style RCBO fill:#fff,stroke:#607d8b,stroke-width:2px,color:#000
```

---

## ⚡ Vollständiger Schaltplan / Detailed Wiring

### Reihenfolge der DC-Komponenten (Plus-Pol)

1. **MeanWell CSP-3000-400 (+V)**
2. **Sperrdiode (MDK-55)** - Verhindert Rückstrom vom PV-System.
3. **Voltmeter** - Anzeige der aktuellen Ausgangsspannung.
4. **Amperemeter** - Anzeige des Ladestroms (bis 7.5A).
5. **DC Sicherung (10A)** - Schutz vor Überlast/Kurzschluss.
6. **MC4 Ausgangsbuchse (+)**

*Der Minus-Pol (-V) wird direkt vom Netzteil zur MC4-Buchse (-) geführt.*

---

## 🎛️ Steuerung (CN2 Port)

Die Steuerung erfolgt über ein **0-10V Potentiometer-Modul**, welches an den CN2 Port des MeanWell Netzteils angeschlossen wird.

### MeanWell CN2 Pinbelegung

Bitte beachten Sie das offizielle Handbuch für die exakte Pinbelegung. Hier ist die schematische Darstellung für das Potentiometer:

- **Pin 8 (+12V AUX)**: Stromversorgung für das Potentiometer-Modul.
- **Pin 6 (V_ADJ)**: Ausgang des Potentiometers (Steuerspannung 0-10V).
- **Pin 1-5 (GND)**: Gemeinsame Masse.

> 📷 <img width="1066" height="436" alt="grafik" src="https://github.com/user-attachments/assets/46e13910-a17f-4f5d-b26e-490be6be1b89" />
https://www.meanwell.com/Upload/PDF/CSP-3000/CSP-3000-SPEC.PDF
> 

---

## ⚠️ Sicherheitshinweise

- **Sperrdiode**: Die Diode muss als erstes Bauteil nach dem Netzteil sitzen! Sie schützt das Netzteil vor den Spannungen der Solarpanele.
- **Sicherung**: Der 10A DC-Automat dient als Lasttrennschalter und Absicherung.
- **Analoge Anzeige**: Voltmeter und Amperemeter sind im Deckel der Alubox montiert für eine direkte Kontrolle ohne Zusatzgeräte.

---

**[◀ Zurück zur Aufbauanleitung](ASSEMBLY.md)** | **[Zurück zur Hauptseite](../README.md)**
