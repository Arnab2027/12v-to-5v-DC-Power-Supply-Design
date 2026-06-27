# 12V to 5V DC Power Supply Board

A compact, high-reliability DC-DC power supply PCB designed to step down a standard 12V DC input rail to a stable, regulated 5V DC output.This repository contains the complete hardware design files, production-ready manufacturing packages, and documentation demonstrating proper power integrity and layout practices.

## 📸 Hardware Showcase

| PCB Layout Preview | Schematic Diagram |
| --- | --- |
| ![PCB Layout](Images/pcb_top_layout.png) | ![Schematic Preview](Images/schematic_screenshot.png) |



---

## ⚙️ Technical Specifications & System Architecture

### 1. Black Box Parameters
* Input Voltage ($V_{in}$): 12V DC Nominal
* **Output Voltage ($V_{out}$): 5V DC Regulated 
* **Target Application:** Common internal rail generation for embedded systems, microcontrollers (e.g., Arduino/ATmega chips), and automotive accessories

### 2. Design Topology (Select Yours & Delete the Other)

* **Option A: Linear Regulation (e.g., LM7805)
    * **Architecture:** Linear Regulator[cite: 20].
    * **Design Choice:** Selected for its simple footprint and noise-free operation, providing an exceptionally clean and smooth output rail ideal for sensitive analog circuits. Thermal dissipation considerations were integrated into the copper layout to handle the dropped voltage ($7\text{V} \times I_{out}$) safely.
    
* **Option B: Switching Regulation (Buck Converter)**
    * **Architecture:** Synchronous Buck Converter.
    * **Design Choice:** Selected to maximize power efficiency (typically >90%), reducing thermal generation and eliminating the need for bulky heatsinks.

---

## 🛠️ PCB Layout & Engineering Choices

The physical circuit layout was optimized using standard electronics manufacturing guidelines:
* **Power Integrity:** Trace widths calculated according to IPC standards to minimize temperature rise under full load conditions.
* **Thermal Management:** Placed strategic copper pours and stitching thermal vias to act as integrated heatsinks, optimizing heat dissipation directly through the board.
* **EMI Suppression:** (For Buck Converters) Prioritised component placement to keep critical high $di/dt$ switching loop areas as small as possible, suppressing parasitic radiated electromagnetic interference.
* **Layer Stackup:** 2-layer board design utilizing a solid, continuous bottom ground plane to maintain low impedance and excellent signal integrity.

---

## 📂 Repository Structure

To make review efficient for engineering managers and recruiters, the repository follows a clean, standardized structure:

```text
├── Schematic/              # Clean, highly legible PDF export of the circuit schematic
├── Hardware/               # Native CAD project files (Schematic and PCB layout data)
├── Manufacturing/          # Production-ready fabrication files
│   ├── Gerber/             # Individual RS-274X Gerber layers
│   ├── Drill/              # NC Drill files (.DRL)
│   └── BOM/                # Bill of Materials with Manufacturer Part Numbers (MPNs)
└── Images/                 # Documentation assets and 3D layout renders
