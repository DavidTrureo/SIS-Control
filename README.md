
```markdown
# SIS Control - Sistema de Monitoreo y Gestión de Seguridad en Tiempo Real

SIS Control es una solución tecnológica integral diseñada para optimizar, auditar y controlar las operaciones de guardias de seguridad y personal en terreno en tiempo real. El sistema resuelve problemáticas críticas del rubro, como la falta de visibilidad en las rondas de vigilancia, la demora en el reporte de incidencias y la vulnerabilidad del personal en situaciones de emergencia.

Mediante una arquitectura distribuida y comunicación bidireccional instantánea, SIS Control conecta al personal de seguridad con la central de supervisión, garantizando la continuidad operativa y la integridad de las instalaciones.

---

## Arquitectura del Proyecto y Características

El ecosistema de **SIS Control** está dividido en tres módulos principales:

### 1. Aplicación de Guardia (Mobile Nativo - Android Kotlin)
* **Validación de Rango GPS (Geofencing):** Impide que el guardia inicie jornada si no se encuentra dentro del radio permitido (500 metros) de la instalación asignada.
* **Control de Rondas con NFC:** Registro y validación del patrullaje físico mediante el escaneo in situ de etiquetas NFC asignadas a cada punto de control.
* **Reporte de Incidentes Georreferenciados:** Envío inmediato de anomalías con carga de evidencia fotográfica, localización exacta y comentarios.
* **Asistente de Redacción con Inteligencia Artificial (IA):** Genera resúmenes profesionales del turno y análisis de desempeño integrando tecnologías de IA y dictado por voz.
* **Botón de Pánico Multimodal:** Dispara alertas críticas inmediatas a la central de monitoreo mediante un slider en pantalla o por movimiento físico brusco (Shake Detection).

### 2. Panel del Administrador y Supervisor (React Native / Web)
* **Mapa de Localización en Vivo:** Visualización interactiva sobre Google Maps de la ubicación de los guardias en servicio y su estado de patrullaje.
* **Consola de Alertas:** Recepción y gestión en tiempo real de pánicos e incidentes.
* **Emisión de Avisos Administrativos (Megáfono):** Envío de notificaciones y alertas globales que aparecen instantáneamente en los teléfonos de la tropa activa.
* **Reportabilidad PDF:** Generación y descarga automática de reportes consolidados de rondas y turnos.

### 3. Backend Engine (Spring Boot API)
* Servidor centralizado que gestiona la lógica de negocio, persistencia de base de datos relacional y orquestación de la mensajería asíncrona bidireccional en tiempo real a través de WebSockets (STOMP).

---

## Tecnologías Utilizadas

### Frontend & Mobile
* **Android (Kotlin):** Desarrollo nativo con Jetpack Compose para la UI, Retrofit para el consumo de la API REST, Google Play Services para localización y WebSockets (STOMP client) para la conexión en tiempo real.
* **Admin Web/Mobile (React Native):** Interfaz multiplataforma desarrollada con Expo, Axios y estilos de alta fidelidad.

### Backend & Base de Datos
* **Framework:** Spring Boot 3 (Java 17).
* **Persistencia:** Spring Data JPA + Hibernate.
* **Base de Datos:** MariaDB / MySQL.
* **Mensajería en Vivo:** Spring WebSocket Broker (STOMP).

---

### Requisitos Previos
* **Java SDK 17** o superior.
* **Android Studio** (Koala o posterior).
* **Node.js** v18+.
* **MariaDB** o **MySQL** server activo.
