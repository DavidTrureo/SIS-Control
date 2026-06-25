# SIS Control - Sistema de Monitoreo y Gestión de Seguridad en Tiempo Real

SIS Control es una solución tecnológica integral diseñada para optimizar, auditar y controlar las operaciones de guardias de seguridad y
personal en terreno en tiempo real. El sistema resuelve problemáticas críticas del rubro, como la falta de visibilidad en las rondas de vigilancia, la demora en el reporte de incidencias y la vulnerabilidad del personal en situaciones de emergencia.

Mediante una arquitectura distribuida y comunicación bidireccional instantánea, SIS Control conecta al personal de seguridad y
supervisores con un motor central de datos, garantizando la continuidad operativa y la integridad de las instalaciones.

---

## Arquitectura del Proyecto y Características

El ecosistema de **SIS Control** está estructurado en dos grandes componentes:

### 1. Aplicación Móvil SIS Control (Android Nativo - Kotlin)
Una única aplicación móvil que adapta su interfaz dinámicamente según el rol del usuario conectado:

* **Perfil Guardia (Operaciones en Terreno):**
  - **Validación de Rango GPS (Geofencing):** Impide iniciar la jornada si el dispositivo está fuera del radio permitido (500 metros)
    de la instalación asignada.
  - **Control de Rondas con NFC:** Registro y verificación presencial mediante el escaneo físico de tags NFC en cada punto de control.
  - **Reporte de Incidentes Georreferenciados:** Envío inmediato de anomalías con carga de evidencias fotográficas, localización exacta y
    comentarios.
  - **Botón de Pánico Multimodal:** Activación instantánea de emergencias deslizando la pantalla o mediante movimiento brusco del
    dispositivo (Shake Detection).
  - **Asistente de Redacción con IA:** Genera resúmenes profesionales de turnos integrando dictado por voz e Inteligencia Artificial.

* **Perfil Administrador / Supervisor (Monitoreo y Gestión):**
  - **Mapa de Localización en Vivo:** Visualización interactiva en tiempo real sobre Google Maps de la ubicación de los guardias activos
    y su estado de patrullaje.
  - **Centro de Alertas:** Recepción inmediata y control de botones de pánico e incidentes activos.
  - **Emisión de Avisos Administrativos (Megáfono):** Envío de comunicados globales en tiempo real que aparecen directamente en las
    pantallas de los guardias en servicio.
  - **Reportabilidad PDF:** Generación y descarga directa de informes consolidados de jornadas.

### 2. Backend Engine (Spring Boot API)
* Servidor central que gestiona la lógica de negocio, persistencia de base de datos relacional y orquestación de la mensajería asíncrona bidireccional en tiempo real a través de WebSockets (STOMP).

---

## Tecnologías Utilizadas

### Frontend & Mobile
* **Android (Kotlin):** Desarrollo nativo con Jetpack Compose para la interfaz de usuario, Retrofit para el consumo de la API REST,
  Google Play Services para geolocalización y mapas, y WebSockets (STOMP client) para notificaciones y alertas en tiempo real.

### Backend & Base de Datos
* **Framework:** Spring Boot 3 (Java 17).
* **Persistencia:** Spring Data JPA + Hibernate.
* **Base de Datos:** MariaDB / MySQL.
* **Mensajería en Vivo:** Spring WebSocket Broker (STOMP).

---

## Requisitos

### Requisitos Previos
* **Java SDK 17** o superior.
* **Android Studio** (Koala o posterior).
* **MariaDB** o **MySQL** server activo.
