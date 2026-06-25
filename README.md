# SIS Control - Sistema de Monitoreo y Gestión de Seguridad en Tiempo Real

Repositorio principal de documentación, gestión y evidencias del proyecto **SIS-Control**.

Mediante una arquitectura distribuida y comunicación bidireccional instantánea, SIS Control conecta al personal de seguridad y
supervisores con un motor central de datos, garantizando la continuidad operativa y la integridad de las instalaciones.

**SIS-Control** es un sistema orientado al control y supervisión de rondas de guardias de seguridad, con registro de checkpoints, ubicación GPS y trazabilidad operativa.

* **Perfil Guardia (Operaciones en Terreno):**
  - **Validación de Rango GPS (Geofencing):** Impide iniciar la jornada si el dispositivo está fuera del radio permitido (500 metros)
    de la instalación asignada.
  - **Control de Rondas con NFC:** Registro y verificación presencial mediante el escaneo físico de tags NFC en cada punto de control.
  - **Reporte de Incidentes Georreferenciados:** Envío inmediato de anomalías con carga de evidencias fotográficas, localización exacta y
    comentarios.
  - **Botón de Pánico Multimodal:** Activación instantánea de emergencias deslizando la pantalla o mediante movimiento brusco del
    dispositivo (Shake Detection).
  - **Asistente de Redacción con IA:** Genera resúmenes profesionales de turnos integrando dictado por voz e Inteligencia Artificial.

```text
SIS-Control/
├── Documentacion/
├── Gestion/
├── Producto_links/
└── README.md
```
