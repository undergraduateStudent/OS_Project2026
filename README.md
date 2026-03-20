# OS_Project2026

**Bus-Stop Shade & Street Light Controller – Wiring Summary**

---

### 🔌 1. Power Connections

* Arduino **5V →**

  * LCD VDD
  * LDR circuits (top side)
  * Servo VCC (if using same supply in simulation)

* Arduino **GND →**

  * LCD VSS
  * LCD RW (fixed to write mode)
  * LCD backlight K (LED−)
  * All LED cathodes (via resistors)
  * LDR resistor bottom
  * Servo GND

---

### 💡 2. LED Groups (Streetlights)

**West Zone LEDs**

* Arduino **Pin 2 → 4 LEDs (in parallel)**
* Each LED:

  * Anode → Pin 2
  * Cathode → Resistor → GND

**East Zone LEDs**

* Arduino **Pin 4 → 4 LEDs (in parallel)**
* Each LED:

  * Anode → Pin 4
  * Cathode → Resistor → GND

---

### 🌞 3. LDR Sensors (Light Detection)

**LDR 0 (West Zone)**

* One side → **5V**
* Other side → **A0**
* A0 → **5kΩ resistor → GND**

**LDR 1 (East Zone)**

* One side → **5V**
* Other side → **A1**
* A1 → **5kΩ resistor → GND**

---

### ⚙️ 4. Servo Motors (Shade Control)

**Servo 1 (West Zone)**

* Signal → **Pin 5**
* VCC → 5V
* GND → GND

**Servo 2 (East Zone)**

* Signal → **Pin 6**
* VCC → 5V
* GND → GND

---

### 🖥️ 5. LCD (HD44780 – 20x4, 4-bit mode)

**Control Pins**

* RS → **Pin 8**
* EN → **Pin 9**
* RW → **GND**

**Data Pins**

* D4 → **Pin 10**
* D5 → **Pin 11**
* D6 → **Pin 12**
* D7 → **Pin 13**

**Power & Contrast**

* VSS → GND
* VDD → 5V
* V0 → Middle pin of potentiometer

  * Pot sides → 5V and GND

**Backlight (optional)**

* A (LED+) → 5V
* K (LED−) → GND

---

### 📌 Final Pin Usage Summary

| Function   | Pin |
| ---------- | --- |
| West LEDs  | 2   |
| East LEDs  | 4   |
| Servo West | 5   |
| Servo East | 6   |
| LCD RS     | 8   |
| LCD EN     | 9   |
| LCD D4     | 10  |
| LCD D5     | 11  |
| LCD D6     | 12  |
| LCD D7     | 13  |
| LDR West   | A0  |
| LDR East   | A1  |

---

### ✅ Notes

* Each LED must have its **own resistor**
* LCD RW is fixed to **GND (write mode)**
* LDR must be connected as a **voltage divider**
* Avoid using Pin 0 and 1 (reserved for Serial)

---
