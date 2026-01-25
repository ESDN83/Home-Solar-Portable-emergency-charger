# Anschluss & Schaltplan / Connections & Schematics

## Konzept / Concept

Das System wandelt die AC-Spannung eines Notstromgenerators mittels eines regelbaren Netzteil (MeanWell CSP-3000-400) in eine DC-Spannung um, die kompatibel mit den PV-Eingängen (MPPT) des Heimspeichers (z.B. E3/DC) ist.
The system converts the AC voltage of an emergency generator using a adjustable power supply (MeanWell CSP-3000-400) into a DC voltage compatible with the PV inputs (MPPT) of the home battery system.

## Blockschaltbild / Block Diagram

```mermaid
graph LR
    G[Generator (AC 230V)] -->|CEE / Schuko Cable| P[MeanWell CSP-3000-400]
    P -->|DC 7.5A / ~300-400V| D[Blocking Diode / Sperrdiode]
    D -->|MC4 Cable| E[E3/DC PV Input (MPPT)]
    
    subgraph "Portable Box"
    P
    D
    end
    
    subgraph "House / Haus"
    E
    end
```

## Verdrahtung / Wiring

### 1. Eingang (AC Side)
*   **Quelle / Source**: Generator (230V AC).
*   **Verbindung / Connection**: Schuko oder CEE Stecker auf 3-adriges Kabel (L, N, PE).
*   **Ziel / Target**: Eingangsklemmen des MeanWell CSP-3000-400 (AC/L, AC/N, FG/Erde).

### 2. Ausgang (DC Side)
*   **Quelle / Source**: MeanWell Ausgang (+V, -V).
*   **Verbindung / Connection**:
    *   **Plus (+)**: Vom Netzteil (+) -> Anode der Sperrdiode (Blocking Diode). Kathode der Diode zum MC4-Plus-Stecker.
    *   **Minus (-)**: Vom Netzteil (-) -> Direkt zum MC4-Minus-Stecker.
*   **Ziel / Target**: DC-Kabel zu den PV-Eingängen des Wechselrichters.

## Wichtige Komponenten / Critical Components

### Sperrdioden (Blocking Diodes)
Um Rückstrom (Fehlstrom) vom Wechselrichter oder parallel geschalteten Modulen in das Netzteil zu verhindern, **MUSS** eine geeignete Sperrdiode installiert werden.
To prevent reverse current from the inverter or parallel modules into the power supply, a suitable blocking diode **MUST** be installed.
*   **Spannung / Voltage**: Mindestens 1000V DC (oder höher als die maximale Systemspannung des PV-Strings).
*   **Strom / Current**: Mindestens 10A-15A (passend zur max. Leistung des Netzteils, 7.5A).
*   **Position**: In Reihe in der Plus-Leitung (oder Plus und Minus, üblicherweise Plus).

### Einstellungen am MeanWell / Settings
*   **Modus**: PC-Modus (Programmable Constant Current/Voltage) oder PV-Modus (falls unterstützt).
*   **Spannung (V_set)**: Muss im MPPT-Bereich des Wechselrichters liegen (z.B. 350V - 400V). Nicht höher als die max. zulässige Spannung des MPPT!
*   **Strom (I_set)**: Begrenzen Sie den Strom so, dass der Generator nicht überlastet wird. (Beispiel: 2000W Generator -> Max ca. 5-6A bei 350V).

## Anschluss an E3/DC / Connection to E3/DC
1.  Generator starten und warmlaufen lassen.
2.  Portable Charger einschalten (Netzteil fährt hoch).
3.  Prüfen der Ausgangsspannung am Charger.
4.  Verbindung zum freien MPPT-Eingang des E3/DC herstellen (oder per Umschalter, falls Eingang belegt ist).
5.  Der E3/DC sollte die Spannung erkennen und beginnen, Leistung zu ziehen (MPPT Tracking).

**Warnung**: Niemals das Netzteil an einen PV-Strang parallel anschließen, ohne sicherzustellen, dass die Spannungen passen und Dioden vorhanden sind! Am sichersten ist ein separater, freier Eingang.
**Warning**: Never connect the PSU in parallel to a PV string without ensuring matching voltages and diodes! The safest option is a separate, free input.
