# 🔧 L7805 Thermal Optimized PCB

A compact, robust, and thermally aware 5V regulated power supply module using the L7805 linear regulator — designed in KiCad. Supports both DC jack and terminal block inputs with reverse polarity protection and ripple filtering.

---

## 🚀 Features

- ✅ 12V to 5V regulated supply using L7805
- ✅ Dual input support: DC Jack + Terminal Block
- ✅ Reverse polarity protection with Schottky diode
- ✅ Copper pour GND plane for better thermal dissipation
- ✅ Mounting holes for enclosure integration
- ✅ Status LED to indicate VIN presence
- ✅ Clean output with ripple filtering capacitors
- ✅ Gerber + drill files ready for PCB fabrication

---

## 📦 Folder Structure

L7805-Thermal-PCB
│
├── schematic → KiCad schematic file (.kicad_sch)
├── pcb→ KiCad PCB layout (.kicad_pcb)
├── gerbers → Fabrication-ready Gerber + drill files
├── outputs → Netlist, BOM, PDF exports
├── screenshots → Preview images and 3D renders

---

## 🧩 Components Used

| Label   | Component                  | Description                        |
|---------|----------------------------|------------------------------------|
| U1      | L7805 (TO-220)             | 5V linear voltage regulator        |
| J1      | Terminal Block (2-pin)     | Screw terminal for 12V input       |
| J_DC    | DC Barrel Jack (PJ-102A)   | Standard adapter input             |
| D1      | 1N5819 Schottky Diode      | Reverse polarity protection        |
| C1      | 0.33µF Capacitor           | Input ripple filter                |
| C2      | 0.1µF Capacitor            | Output ripple filter               |
| C3      | 10µF Electrolytic (optional) | Output surge smoothing           |
| LED1    | Red LED                    | VIN power indicator                |
| R1      | 1kΩ Resistor               | Limits LED current                 |
| J2      | Terminal Block (2-pin)     | 5V output terminal                 |

---

## 🔌 Connections

### 🔋 Input
- **DC Jack center pin** → Anode of D1
- **D1 cathode** → +12V rail (feeds L7805 IN and J1.2)
- **J1.1** → GND
- **J1.2** → +12V input (merged with D1 output)

### ⚙️ Regulator Section
- **L7805 IN** → +12V rail  
- **L7805 OUT** → +5V output  
- **L7805 GND** → GND plane  

### 🔋 Output
- **J2.1** → +5V  
- **J2.2** → GND  

### 💡 Power LED
- **+12V rail** → R1 (1kΩ) → LED1 (anode) → LED1 cathode → GND

---

## 🧪 Testing Instructions

1. Power using either:
   - 12V DC via barrel jack
   - Bench supply via J1
2. Use multimeter at J2:
   - Output should be ~5.0V
3. Check LED lights up when power is applied
4. Verify L7805 doesn’t overheat under normal load

---

## 👤 Author

Made by Suman Ghorai
Designed in **KiCad**  
Last updated: June 2025


