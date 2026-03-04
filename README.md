# 🚗 Distributed Automotive Dashboard System using CAN Protocol on STM32F429ZIT6

## 📌 Project Overview

This project implements a **multi-node automotive dashboard system** using the CAN (Controller Area Network) protocol on the STM32F429ZIT6 microcontroller.

The system simulates a real vehicle dashboard where multiple Electronic Control Units (ECUs) communicate over CAN and a central node displays real-time vehicle data.

---

## 🧠 System Architecture

The project consists of **3 CAN nodes**:

### 🔹 Node 1 – Vehicle Status Transmitter
- Indicator Status
- Vehicle Speed
- Engine Temperature

### 🔹 Node 2 – Engine & Time Transmitter
- Gear Position
- Engine RPM (via ADC)
- RTC Time (HH:MM:SS)

### 🔹 Node 3 – Central Dashboard Receiver
- Receives CAN messages from all nodes
- Hardware CAN filtering
- Displays formatted data over UART (TERA TERM)

---

## 🛠 Hardware Used

- STM32F429ZIT6 Microcontroller (3 Boards)
- CAN Transceiver (e.g., MCP2551 / TJA1050)
- UART Terminal (TERA TERM)
- On-board LEDs for Debugging
- Potentiometer (for RPM via ADC)
- Switches
- LEDs
- DHT11 Sensor

---

## 🔄 Communication Protocol

- CAN Mode: Normal Mode
- Identifier Type: Standard (11-bit)
- Interrupt-based Reception
- Hardware Filter Configuration
- Multi-node distributed architecture

### CAN Message IDs

| Parameter     | CAN ID |
|--------------|--------|
| Indicator    | 0x101  |
| Speed        | 0x201  |
| Temperature  | 0x301  |
| Gear         | 0x401  |
| RPM          | 0x501  |
| Time         | 0x601  |

---

## ⚙️ Key Features

- ✅ Interrupt-driven CAN communication
- ✅ Hardware-based CAN filtering
- ✅ ADC-based RPM measurement
- ✅ RTC peripheral integration
- ✅ UART real-time dashboard display
- ✅ ISR-safe architecture (minimal processing in interrupt)
- ✅ Multi-node embedded system simulation

---

## 🧩 Software Architecture

- HAL Drivers (STM32CubeMX generated)
- CAN RX interrupt callback
- Flag-based main loop processing
- Structured embedded design
- Volatile shared variables for ISR safety

---

## 📊 Sample UART Output

IND Speed Temp Gear RPM Time
L    45    32   G2   67 12:45:33


---

## 🎯 Learning Outcomes

- Understanding CAN Bus architecture
- Configuring CAN filters (ID Mask mode)
- Handling interrupts in embedded systems
- Designing distributed ECU systems
- Implementing real-time embedded communication
- Automotive embedded software principles

---

## 🚀 Future Improvements

- Add FreeRTOS for task-based design
- Implement CAN error frame detection
- Add watchdog timer integration
- Add OLED/LCD dashboard display
- Implement CAN diagnostic messages (UDS simulation)

---


