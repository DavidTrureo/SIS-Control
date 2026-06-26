# SIS-Control - Sistema Inteligente de Control y Bitácora de Seguridad

SIS-Control es un ecosistema tecnológico de seguridad privada diseñado para optimizar el registro de patrullajes, la gestión de personal y el reporte de incidentes en tiempo real. Con un enfoque arquitectónico "Offline-First", el sistema está preparado para operar en condiciones extremas de conectividad (como sótanos, estacionamientos subterráneos o perímetros aislados), garantizando la integridad de los datos de seguridad.

---

## Resumen del Proyecto

El control de rondas tradicional suele sufrir de pérdida de datos debido a la falta de cobertura de red y la vulnerabilidad ante reportes manuales imprecisos. **SIS-Control** resuelve esta problemática integrando:
1. **Validación Física en Terreno:** Uso de tecnología NFC y geolocalización GPS para certificar que el guardia estuvo físicamente en el
   punto de control.
2. **Redacción y Análisis Automatizado con IA:** Integración de la API de **Google Gemini 1.5 Flash** para examinar la evidencia fotográfica
   de incidentes y redactar reportes formales y detallados automáticamente.
3. **Comunicación Instantánea:** Canalización en tiempo real vía WebSockets para emitir alertas de pánico y avisos masivos de la
   administración de forma inmediata.

---

## Stack Tecnológico y Herramientas

El proyecto ha sido desarrollado utilizando tecnologías nativas estables, robustas y de alto rendimiento:

### Frontend (Aplicación Móvil)
*   **Lenguaje:** Kotlin
*   **Framework UI:** Jetpack Compose (Material Design 3 para una interfaz moderna, limpia y responsiva).
*   **Base de Datos Local:** Room Database (SQLite) para garantizar la disponibilidad "Offline-First".
*   **Peticiones de Red:** Retrofit y OkHttp para la comunicación fluida con la API.
*   **Concurrencia:** Corrutinas de Kotlin y Flow para flujos de datos asíncronos y sincronización en segundo plano.

### Backend (Servidor de API)
*   **Lenguaje:** Java 17
*   **Framework:** Spring Boot (Spring Web, Spring Security, Spring Data JPA).
*   **Seguridad:** Autenticación y autorización sin estado (Stateless) mediante tokens JWT (JSON Web Tokens).
*   **Comunicación en Tiempo Real:** WebSocket con protocolo STOMP para la transmisión en vivo de alertas.
*   **Servicio de IA Multimodal:** Cliente HTTP nativo (`java.net.http.HttpClient`) para la comunicación segura con la API de **Gemini 1.5
   Flash**.

### Base de Datos y Almacenamiento
*   **Base de Datos Relacional:** MySQL para el almacenamiento persistente de usuarios, rondas, sedes e incidentes.
*   **Gestión Local:** XAMPP (servidor Apache y MySQL local) y MySQL Workbench para el modelado, diseño físico y administración de la base de datos.
*   **Almacenamiento Cloud:** Firebase Storage para guardar y servir las fotografías tomadas en terreno e imágenes de perfil de los guardias.

### Herramientas de Desarrollo y Pruebas
*   **Entornos de Desarrollo (IDE):**
    *   **Android Studio:** Para el desarrollo, depuración y emulación de la app en Kotlin.
    *   **IntelliJ IDEA:** Para la codificación, refactorización y compilación del backend Spring Boot.
    *   **Visual Studio Code:** Para la edición de scripts, análisis de base de datos y documentación del proyecto.
*   **Pruebas de API:** Postman (para el diseño, prueba y validación de endpoints y cabeceras JWT).

---

## 💡 Principales Logros y Características Implementadas

*   **Arquitectura Offline-First y Sincronización en Segundo Plano:** El guardia puede realizar su patrullaje completo sin internet. Todos
    los escaneos, omisiones e incidentes se guardan en el caché local de Room. Al recuperar la conexión a internet, un gestor de sincronización
    (`SyncManager`) sube automáticamente los datos en lotes al backend.
*   **Inteligencia Artificial Multimodal (Gemini 1.5 Flash):** Al capturar una foto de evidencia en un incidente (ej: puerta forzada, luces
    rotas), el guardia puede presionar **"Redacción IA"**. El servidor analiza los bytes comprimidos de la foto junto con la nota corta del
    guardia y Gemini genera un reporte detallado, profesional y formal en español latino neutro.
*   **Respaldo Local Inteligente (Fallback):** En zonas sin cobertura o ante fallos del servidor, la app recurre automáticamente a un motor
    local (Google ML Kit Image Labeling) para autocompletar descripciones y títulos de manera offline.
*   **Botón de Pánico y Alertas en Tiempo Real:** En caso de emergencia, el guardia puede activar el botón de pánico. Esto dispara un evento
    WebSocket instantáneo que se refleja de inmediato en los paneles administrativos de los supervisores.
*   **Avisos Administrativos Masivos:** Los administradores pueden redactar avisos importantes desde su panel, los cuales son guardados en
    base de datos e irradiados en tiempo real a los guardias en terreno mediante ventanas emergentes persistentes.
*   **Validación por NFC y Geolocalización:** Bloqueo de escaneo de puntos mediante chips NFC físicos. Además, se verifica mediante GPS que
    el guardia se encuentre en el rango perimetral (coordenadas de la sede) utilizando mapas integrados.

---

## Estructura del Ecosistema

El proyecto se divide en dos repositorios principales que componen el ecosistema:

1.  **SIS-Control-Frontend (App Móvil):** Código nativo Android Kotlin en Jetpack Compose.
2.  **SIS-Control-Backend (API REST):** Código servidor Spring Boot en Java 17 y base de datos relacional MySQL.

---

## Estructura del Equipo de Trabajo

| Integrante | Rol |
| :--- | :--- |
| **David Trureo Ahumada** | Backend / Base de datos / QA técnico de datos |
| **Benjamin Burgos Morales** | Backend / Base de datos / QA técnico backend |
| **Freddy Sepúlveda Vásquez** | Desarrollo móvil / Scrum Master / Documentación funcional |



```text
SIS-Control/
├── Documentacion/
├── Gestion/
├── Producto_links/
└── README.md
```
