# 🔨 Aufbauanleitung / Assembly Instructions

<div align="center">

**Schritt-für-Schritt Anleitung zum Bau des Notstrom-Ladegeräts in der Alubox**  
**Step-by-Step Guide to Build the Emergency Charger using an Aluminum Box**

</div>

---

## 📋 Voraussetzungen / Prerequisites

- ✅ Alle Komponenten aus der [Stückliste](PARTS.md) (inkl. Alubox)
- ✅ 3D-Drucker für interne Halterungen
- ✅ Metallbohrer, Stichsäge oder Dremel (für Ausschnitte in der Alubox)
- ✅ Crimpwerkzeug für Ringkabelschuhe und MC4 Stecker
- ✅ **Elektrofachkraft empfohlen!** (400V DC ist lebensgefährlich)

---

## 📦 Schritt 1: Gehäuse vorbereiten / Step 1: Prepare Housing (Alubox)

Anstatt eines komplett gedruckten Gehäuses verwenden wir eine robuste **Riffelblech-Alubox (25L)**.

1. **Ausschnitte für Instrumente**:
   - Analoge Anzeigen für **Volt** und **Ampere** im Deckel oder an der Front positionieren.
   - Ausschnitte markieren und mit Stichsäge/Dremel vorsichtig ausschneiden.
2. **Potentiometer & Schalter**:
   - Bohrung für das Potentiometer-Modul setzen.
   - Einbauplatz für den DC-Sicherungsautomaten vorsehen (Hutschienen-Stück in der Box).
3. **Anschlüsse**:
   - Ausschnitte für den **CEE-Anbaustecker** (AC Eingang) und die **MC4-Buchsen** (DC Ausgang) bohren.

---

## 🖨️ Schritt 2: Interne Halterungen (3D-Druck) / Step 2: Internal Mounts

Die 3D-gedruckten Teile dienen zur stabilen Befestigung der Komponenten auf dem Lochblech innerhalb der Alubox.

- **DIN_RAIL_Mount**: Zur Montage des MeanWell Netzteils auf einer Hutschiene.
- **Stecker-Halterungen**: Zur zusätzlichen Fixierung der Buchsen.

---

## ⚡ Schritt 3: Mechanische Montage / Step 3: Mechanical Assembly

1. **Lochblech einpassen**: Das Alu-Lochblech dient als Montageplatte am Boden der Box.
2. **Netzteil fixieren**: Das MeanWell Netzteil mit den 3D-Halterungen auf das Lochblech schrauben.
3. **Sperrdiode montieren**: Die **MDK-55 Diode** muss fest auf einer metallischen Oberfläche (Kühlkörper oder Gehäusewand) montiert werden, da sie im Betrieb warm wird.

---

## 🔌 Schritt 4: Verkabelung / Step 4: Wiring

Folgen Sie exakt dieser Reihenfolge für den Plus-Pol:

```
MeanWell (+) ➔ Sperrdiode (MDK-55) ➔ Voltmeter ➔ Amperemeter ➔ DC-Sicherung ➔ MC4-Buchse (+)
```

1. **AC-Seite**: CEE-Anbaustecker -> FI/LS Schutzschalter (RCBO) -> MeanWell AC-Eingang.
2. **DC-Seite**: 
   - Verwenden Sie **6mm² Solarkabel** für die Hauptleitung.
   - Alle Verbindungen mit Ringkabelschuhen (M5) fest verschrauben.
3. **Messgeräte**: Voltmeter parallel, Amperemeter in Reihe schalten.

---

## 🎛️ Schritt 5: Steuerung / Step 5: Control

Das Potentiometer-Modul wird mit dem 8-poligen Sync-Kabel verbunden. in CN2 -> https://github.com/ESDN83/Home-Solar-Portable-emergency-charger/blob/main/documentation/SCHEMATICS.md#%EF%B8%8F-steuerung-cn2-port

1. **Pin 1 (+12V)** an Moduleingang (+).
2. **Pin 2 (-12V)** an Moduleingang (-).
3. **Pin 5 (V_ADJ)** an Modulausgang (Signal).
4. **Pin 6 (-V_ADJ )** an Modulausgang (Signal -).

Damit lässt sich der Ladestrom regeln.

---

## 🧪 Schritt 6: Test & Inbetriebnahme / Step 6: Testing

1. **Sichtprüfung**: Alle Kontakte fest? Keine Kurzschlüsse am Alugehäuse?
2. **Leerlauftest**: Generator an -> CEE einstecken -> Strom am Potentiometer regeln.
3. **Anzeige**: Prüfen, ob das Voltmeter/Ampermeter die korrekte Spannung/Strom anzeigt.
4. **Lasttest**: Erst wenn alles stabil ist, an den Wechselrichter anschließen.

---

**[◀ Zurück zur Stückliste](PARTS.md)** | **[Weiter zum Schaltplan ▶](SCHEMATICS.md)**
