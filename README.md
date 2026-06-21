# IoT MQTT Docker Stack

Stack base para prototipos IoT industriales con **MQTT, Docker, PostgreSQL, Nginx y servicios web**.

Este repositorio presenta una arquitectura inicial para proyectos de monitoreo, captura de datos, comunicación entre dispositivos y prototipos de Edge AI conectados a servicios locales o en la nube.

---

## Objetivo

Ofrecer una base simple para desarrollar soluciones IoT industriales donde distintos dispositivos, sensores o sistemas embebidos puedan enviar datos mediante MQTT y almacenarlos para análisis, visualización o integración con aplicaciones web.

---

## Arquitectura propuesta

El stack está pensado para integrar:

- **Mosquitto MQTT** como broker de mensajería
- **PostgreSQL** como base de datos relacional
- **Nginx** como servidor web o proxy reverso
- **Backend de servicios** para recibir, procesar o consultar datos
- **Dispositivos Edge** como ESP32, gateways industriales o controladores
- **Aplicaciones web** para monitoreo o visualización

---

## Flujo básico de datos

```text
Sensor / ESP32 / Gateway
        ↓
      MQTT
        ↓
Servicio backend
        ↓
Base de datos
        ↓
Dashboard / API / Sistema web
```

---

## Casos de uso

- Monitoreo de sensores industriales
- Registro de variables de proceso
- Prototipos de mantenimiento predictivo
- Integración de equipos con plataformas web
- Comunicación entre ESP32, gateways y servidores
- Pruebas de Edge AI con almacenamiento local o remoto
- Desarrollo de pilotos industriales de bajo costo

---

## Tecnologías consideradas

- Docker
- Docker Compose
- MQTT
- Eclipse Mosquitto
- PostgreSQL
- Nginx
- Python o Node.js para backend
- ESP32 o dispositivos industriales compatibles
- Linux
- VPS o servidor local

---

## Estructura sugerida del proyecto

```text
iot-mqtt-docker-stack/
│
├── docker-compose.yml
├── README.md
│
├── mosquitto/
│   └── config/
│
├── postgres/
│   └── init/
│
├── nginx/
│   └── config/
│
├── backend/
│   └── app/
│
└── docs/
    └── architecture.md
```

---

## Ejemplo de aplicación

Un sensor industrial, ESP32 o gateway puede publicar datos en un tópico MQTT como:

```text
planta/linea1/motor1/temperatura
```

Mensaje de ejemplo:

```json
{
  "device_id": "motor_01",
  "variable": "temperatura",
  "value": 68.5,
  "unit": "C",
  "timestamp": "2026-06-21T16:00:00"
}
```

Luego un servicio backend puede recibir ese dato, validarlo y almacenarlo en PostgreSQL para consulta posterior, visualización o generación de alertas.

---

## Relación con Edge AI

Este stack puede funcionar como base para proyectos donde modelos de IA se ejecutan cerca del proceso, sensor o equipo, enviando solo resultados relevantes al servidor.

Ejemplos:

- Clasificación local de eventos
- Detección de anomalías en el borde
- Procesamiento previo de señales
- Visión artificial en dispositivos Edge
- Alertas inteligentes con baja latencia
- Reducción de dependencia de la nube

---

## Estado del proyecto

Repositorio en etapa inicial.

Próximos pasos:

- Agregar archivo `docker-compose.yml`
- Configurar Mosquitto MQTT
- Agregar PostgreSQL
- Agregar Nginx
- Incorporar backend mínimo
- Documentar despliegue local
- Documentar despliegue en VPS
- Agregar ejemplos de publicación MQTT
- Agregar estructura de base de datos inicial

---

## Autor

**Adolfo Dario Saavedra**  
Licenciado en Inteligencia Artificial y Robótica  
Sur Robotics & AI  

**LinkedIn:** https://www.linkedin.com/in/adolfo-dario-saavedra/  
**Sitio web:** https://surroboticsai.net/  
**Email:** adolfodsaavedra@gmail.com  

---

> Base técnica para prototipos IoT industriales, Edge AI y soluciones de monitoreo conectadas.
