# D3lta | Predictive Edge AI Risk Terminal

> **Current Status:** 🧠 **Phase 4: TinyML Model Training & Optimization**


---
**D3lta** is a high-fidelity IoT terminal designed for real-time market volatility monitoring and capital preservation. By moving financial inference from the cloud to the **Edge**, D3lta identifies market anomalies in a **3-minute heartbeat**, allowing for a localized "Veto" on asset allocation via a physical Human-in-the-Loop (HITL) interface and a graphical command center.
## Repository Structure
This repository is a collaborative effort between the hardware and data engineering domains:
* **/firmware**: C++ source code for the ESP32-WROOM and µLCD-144-G2 interface. (In Progress)
* **/data**: Time-series datasets (BTC/XAU) with engineered Z-score features. 
* **/scripts**: Python implementation of the quantitative data pipeline and EMA filtering. 
* **/model**: Exported TensorFlow Lite / Edge Impulse TinyML model files.(In Progress) 
## System Architecture
The project utilizes a multi-stage pipeline bridging low-latency embedded firmware with high-level cloud business intelligence.

### 1. Edge Intelligence & TinyML
* **Inference:** Utilizing a **Neural Network** trained via Edge Impulse to classify market states (Crash vs. Stable). The model is optimized for the ESP32 using **TensorFlow Lite for Microcontrollers**.
* **Feature Engineering:** Raw price data is transformed into **Z-scores** and passed through an **Exponential Moving Average (EMA)** filter to isolate structural trends from high-frequency noise.

### 2. Advanced Visualization
* **Graphical UI:** An intelligent **µLCD-144-G2** module (Serial/UART) provides live sparklines (trend graphs) and dynamic, color-coded risk alerts.
* **Control:** A physical analog joystick provides a low-latency manual override to "Veto" trades during high-volatility events.

### 3. Cloud Analytics
* **Telemetry:** Execution logs and AI confidence scores are transmitted via **Stateless HTTPS POST** to a serverless Google Apps Script gateway.
* **Dashboard:** A collaborative **Power BI** suite tracks "Loss Avoidance" metrics and validates model accuracy against real-world market movements.

---

## The Mathematics of D3lta
The system identifies anomalies by calculating the statistical significance of price shifts within a 30-minute lookback window:

$$Z = \frac{x - \mu}{\sigma}$$

* **$x$:** Current EMA-Filtered Price  
* **$\mu$:** Rolling 30-minute Mean  
* **$\sigma$:** Rolling Standard Deviation (Volatility)  

The TinyML model performs inference on these vectors to predict the probability of a structural market failure before standard retail dashboards update.

---

## Hardware & Tech Stack
* **Firmware:** C++ / Arduino Framework (ESP32-WROOM)
* **AI/ML:** Edge Impulse, Neural Network Classifiers
* **Display:** 4D Systems µLCD-144-G2 (Intelligent Graphics Processor)
* **Data Science:** Python (Pandas/NumPy) for dataset labeling and augmentation
* **Cloud/BI:** Google Apps Script (REST API), Power BI (DAX Modeling)

---

## Development Roadmap
- [x] **Phase 1:** Hardware architecture & Graphical Module selection.
- [x] **Phase 2:** Network Infrastructure (Stateless HTTPS pipeline).
- [x] **Phase 3:** Quantitative Data Engineering (Z-score & EMA Processing).
- [ ] **[CURRENT] Phase 4: TinyML Model Training & F1-Score Optimization.**
- [ ] **Phase 5:** µLCD-144-G2 UI/UX Design & Graphical Sparkline implementation.
- [ ] **Phase 6:** End-to-End System Validation and Power BI Integration.

---

## Project Collaborators
* **Theresia (Systems Architect):** Hardware Architecture, C++ Firmware, and TinyML Implementation.
* **Daffa (Quantitative Analyst):** Data Engineering, Python Modeling, and Business Intelligence (Power BI).
