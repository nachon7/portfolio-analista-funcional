# Portfolio de Análisis Funcional

**Ignacio Neirot** | Analista Funcional Técnico / Estudiante de Ingeniería en Informática



---



## Proyecto Destacado: SENNA PROJECT (Sistema de Gestión para Kartódromo)

**Rol:** Analista Funcional / Relevamiento y Documentación de Requisitos.

**Descripción:** Diseño y documentación completa de un sistema web para la digitalización de reservas, gestión de torneos y control de mantenimiento de flota para un establecimiento deportivo.



A continuación, presento extractos clave de la documentación funcional que demuestran mi enfoque analítico, capacidad de definir reglas de negocio y estructuración de casos de uso (base para Testing).



---



### 1. Definición de Reglas de Negocio (Políticas vs. Sistema)

*Demostración de capacidad para modelar lógicas comerciales complejas y de seguridad.*



*   **RN-RD-11 | Programa de Fidelidad:** El sistema aplicará un descuento automático del 25% sobre el valor del turno regular en la tercera reserva concretada por un mismo cliente dentro de un período de 2 meses. Una vez utilizado el beneficio, el ciclo de conteo se reinicia.

*   **RN-FM-06 | Mantenimiento por Desgaste:** El ciclo de uso de todo karting está sujeto a revisiones. Al alcanzar las 20 vueltas acumuladas desde su último servicio, la unidad requiere revisión. Queda estrictamente prohibida la utilización de cualquier unidad que alcance el límite crítico de 30 vueltas sin servicio técnico.



---



### 2. Trazabilidad: Historias de Usuario a Requisitos Funcionales

*Ejemplo de cómo traduzco una necesidad operativa en requisitos técnicos verificables.*



**Historia de Usuario (Empleado de Pista):**

> "Como Empleado de pista, quiero poder cambiar el estado operativo de un karting a 'En mantenimiento' adjuntando una nota técnica, para retirar inmediatamente la unidad rota de la oferta pública y evitar que un cliente reserve un vehículo en mal estado."



**Requisitos Funcionales Derivados:**

*   **RF-37:** Permitir al Empleado modificar el estado operativo según categorías estrictas (Disponible, Reservado, En pista, En mantenimiento, Fuera de servicio).

*   **RF-38:** Exigir obligatoriamente el ingreso de una justificación técnica cuando un usuario modifique el estado a "En mantenimiento".

*   **RF-39:** Permitir restablecer el estado a "Disponible" únicamente tras certificar la finalización de sus reparaciones.



---



### 3. Especificación de Casos de Uso (Preparación para Testing QA)

*Documentación detallada de flujos normales y alternativos, ideal para la generación de Planes de Prueba.*



**Caso de Uso: CU3 - Reservar Turno**

*   **Precondición:** El cliente tiene una cuenta activa y ha iniciado sesión.

*   **Secuencia Normal (Extracto):**

    1. El cliente accede a la sección de reservas y selecciona fecha/horario.

    2. El sistema muestra turnos y solicita indicar si utilizará karting propio o del local.

    3. El sistema verifica disponibilidad de pista y/o unidades.

    4. El sistema registra la reserva y genera código único.

*   **Flujos Alternativos (Gestión de Errores):**

    *   *FA1:* El horario seleccionado ya no se encuentra disponible. -> El sistema informa y solicita nuevo turno.

    *   *FA2:* El cliente solicita alquilar y no existen unidades disponibles. -> El sistema sugiere utilizar karting propio o seleccionar otro horario.



---



### 4. Diagramado UML y Flujos de Actividad
*Demostración de capacidad para modelar visualmente los procesos y la arquitectura del sistema.*

Para este proyecto, estructuré el comportamiento del sistema utilizando estándares profesionales de modelado. A continuación, se presentan los diagramas principales:

#### A. Diagrama de Flujo del Proceso de Reserva (UML Actividad)
Este diagrama modela visualmente el comportamiento lógico del sistema al momento de procesar una reserva. Contempla bifurcaciones críticas como la validación de la disponibilidad del karting, la verificación de instructores asignados y la aplicación automática del beneficio del programa de fidelidad.

<img width="5504" height="13536" alt="diagrama_clases" src="https://github.com/user-attachments/assets/ab08a4e0-b205-4c6a-b1e0-4697f8d142af" />


#### B. Modelo de Dominio y Relaciones (UML Clases)
Diseño de la estructura de datos que soporta la lógica del negocio, definiendo las entidades principales (Usuario, Reserva, Kart, Torneo, Inscripción, Pago), sus atributos y sus multiplicidades para guiar el desarrollo de la base de datos y la arquitectura del backend.

<img width="1600" height="1153" alt="WhatsApp Image 2026-06-23 at 18 17 16" src="https://github.com/user-attachments/assets/c257a891-2696-40df-8f37-a72536f37f82" />


*(Nota para el evaluador: En este repositorio se adjuntan los diagramas de flujo completos del sistema).*
