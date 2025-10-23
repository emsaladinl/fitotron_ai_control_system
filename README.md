# fitotron_ai_control_system
Sistema inteligente de control ambiental para fitotrón basado en ESP32 con sensores, actuadores, MQTT y control neuro-IA PID en modo automático y manual.


# 🌱 Fitotron Inteligente — Control Ambiental con ESP32, MQTT e IA Neuro-PID

El **Fitotron** es un sistema integral diseñado por **Willy Infante** para el control automatizado y predictivo del ambiente en cultivos de laboratorio o invernadero.  
Combina **microcontroladores ESP32**, **sensores ambientales**, **actuadores de climatización**, **servidores MQTT**, y un **modelo de inteligencia artificial Neuro-PID** que permite operar en modo **automático** o **manual**.

---

## 🚀 Objetivos del Proyecto
- Monitorear variables críticas del entorno (temperatura, humedad, luz, CO₂, pH, etc.).
- Controlar actuadores (ventiladores, calefactores, bombas, válvulas, luces).
- Implementar control **PID clásico** y **Neuro-PID adaptativo**.
- Integrar comunicación IoT mediante **MQTT**.
- Permitir supervisión remota desde aplicación móvil o panel web.
- Disponer de un **simulador** completo para pruebas de IA y PID.

---

## ⚙️ Arquitectura General
- **Módulo principal:** ESP32 con conexión Wi-Fi.
- **Sensores:** DHT22, DS18B20, BH1750, MQ135, entre otros.
- **Actuadores:** Relés, ventiladores, bombas, resistencias, LEDs.
- **Servidor MQTT:** comunicación bidireccional entre IA, interfaz y dispositivos.
- **Interfaz:** app Flet (Python) y aplicación Android (Kotlin).
- **IA Neuro-PID:** red neuronal LSTM optimizada para control adaptativo de temperatura y humedad.

---

## 🧩 Componentes Principales
| Componente | Función |
|-------------|----------|
| ESP32 | Unidad central de control |
| Sensores de temperatura, humedad, luz, CO₂ | Adquisición de variables del entorno |
| Actuadores (ventiladores, bombas, resistencias) | Control de condiciones ambientales |
| Servidor MQTT | Enlace IoT con la IA y la interfaz |
| Interfaz Flet / Android | Visualización y control remoto |
| Modelo IA Neuro-PID | Control adaptativo automático |
| Simulador Fitotron | Pruebas virtuales de sensores y actuadores |

---

## 🧠 Inteligencia Artificial Neuro-PID
El modelo Neuro-PID combina las ventajas del control PID tradicional con un módulo neuronal LSTM.  
- **Modo PID:** control proporcional, integral y derivativo clásico.  
- **Modo IA:** red neuronal LSTM multivariable que predice y ajusta el control adaptativamente.  
- **Entrenamiento:** dataset generado por simulador interno del Fitotron.  
- **Entradas:** temperatura, humedad, luz, CO₂, error PID.  
- **Salidas:** señales de control a los actuadores.

---

## 💻 Simulador Fitotron
El simulador permite ejecutar pruebas sin hardware físico:
- Emula sensores y actuadores.
- Ajusta setpoints, mínimos y máximos.
- Envia datos al servidor MQTT para el entrenamiento de la IA.
- Facilita el desarrollo, depuración y evaluación del control inteligente.

---

## 🔌 Comunicación MQTT
### Tópicos principales:
| Tópico | Descripción |
|--------|--------------|
| `fitotron/sensor/data` | Publicación de datos de sensores |
| `fitotron/actuator/cmd` | Control de actuadores |
| `fitotron/setpoint` | Definición de valores de referencia |
| `fitotron/mode` | Cambio entre modo automático / manual |
| `fitotron/ai/control` | Control enviado por la IA Neuro-PID |
| `fitotron/history` | Registro de datos históricos |

---

## 🧰 Instalación
1. Clonar el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/fitotron.git
