# Desarrollo de un Nodo Sensor para la Red Universitaria de Monitoreo Meteorológico

[![Hardware](https://img.shields.io/badge/Hardware-Open%20Source-brightgreen)](https://github.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Framework](https://img.shields.io/badge/Framework-PlatformIO%20%7C%20Arduino-orange)](https://platformio.org/)
[![Microcontroller](https://img.shields.io/badge/MCU-ESP32--C3%20%7C%20RISC--V-blue)](https://www.espressif.com/)

Repositorio oficial para el diseño, desarrollo e implementación del **Nodo Sensor Meteorológico Autónomo de Bajo Costo**, desarrollado en la **Facultad de Instrumentación Electrónica** y el **Centro de Ciencias de la Tierra** de la **Universidad Veracruzana (UV)**.

---

## 📌 Descripción del Proyecto

Este proyecto consiste en una estación y registrador de datos (*datalogger*) meteorológico multiparámetro de bajo consumo, orientado a redes de monitoreo ambiental distribuido y agricultura de precisión. El sistema realiza la adquisición de variables atmosféricas mediante buses industriales y digitales, ejecuta algoritmos de agregación y descomposición vectorial de viento, y ofrece almacenamiento local redundante junto con telemetría inalámbrica en tiempo real.

El proyecto está concebido bajo la filosofía de **Hardware y Software Libre (Open Source)**, permitiendo su estudio, réplica, mejora y adaptación para fines académicos, científicos y comunitarios.

---

## 🛠️ Características Principales

- **Unidad de Procesamiento:** SoC ESP32-C3 (Arquitectura RISC-V a 160 MHz) / Compatibilidad con ESP32 Dual-Core.
- **Buses de Comunicación Industrial y Digital:**
  - **RS485 (Modbus RTU):** Anemómetro, veleta y sensor termohigrométrico industrial (CWT).
  - **I²C:** Barómetro/Termohigrómetro BME280, RTC de alta precisión DS3231 y ADC de 16 bits ADS1115.
  - **SPI:** Módulo MicroSD para almacenamiento local en formato CSV mensual/diario.
- **Telemetría y Conectividad IoT:**
  - Transmisión inalámbrica vía Wi-Fi mediante protocolo ligero **MQTT** hacia backend (FastAPI / Base de Datos).
  - Integración y compatibilidad con plataformas IoT (ThingSpeak / Paneles Web en tiempo real).
- **Gestión Energética y Monitoreo de Batería:**
  - Circuito de acondicionamiento y telemetría de tensión de batería (Divisor de precisión + ADS1115).
  - Alimentación autónoma compatible con panel solar, cargador MPPT y batería de respaldo.

---

## 📂 Estructura del Repositorio

```text
├── docs/                   # Diagramas de bloques, manuales y hojas de datos
├── firmware/               # Código fuente del firmware (PlatformIO / C++)
│   ├── src/                # Archivo principal (main.cpp) y módulos
│   └── platformio.ini      # Dependencias y configuración de compilación
├── hardware/               # Esquemas, diseño de PCB (KiCad / Gerber) y modelos 3D
│   ├── schematics/         # Diagramas esquemáticos del circuito
│   └── pcb/                # Archivos de fabricación de la placa
├── backend/                # Servidor de recepción de datos (FastAPI + MQTT + SQLite)
├── web/                    # Dashboard web para visualización en tiempo real
└── LICENSE                 # Licencia de uso libre (MIT / CERN-OHL)
