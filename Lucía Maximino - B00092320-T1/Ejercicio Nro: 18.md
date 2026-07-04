# Ejercicio Nro: 18

## Enunciado
### Contexto del Caso
Una empresa de desarrollo de software ha decidido adoptar la metodología Scrum para mejorar la eficiencia y calidad de sus proyectos. Tu equipo ha sido seleccionado para liderar la implementación de Scrum en un nuevo proyecto de desarrollo de una aplicación web para una empresa de logística.

---

### Instrucciones:
1. **Construye una serie de prompts** que simulen las diferentes etapas y actividades de Scrum en este proyecto.
2. **Cada prompt debe tener una entrada** que corresponda a la salida de otro prompt, formando una secuencia lógica de ejecución.
3. **Los prompts a desarrollar son:**
   * **a. Prompt 1: Definición del Product Backlog**
     * **Entrada:** Requerimientos iniciales del proyecto proporcionados por el cliente.
     * **Salida:** Product Backlog inicial con las historias de usuario prioritarias.
   * **b. Prompt 2: Planificación del Sprint**
     * **Entrada:** Product Backlog.
     * **Salida:** Plan del Sprint con las tareas a realizar y los responsables.
   * **c. Prompt 3: Ejecución del Sprint**
     * **Entrada:** Plan del Sprint.
     * **Salida:** Incremento de software funcional.
   * **d. Prompt 4: Revisión del Sprint**
     * **Entrada:** Incremento de software funcional.
     * **Salida:** Retroalimentación del cliente y lecciones aprendidas.
   * **e. Prompt 5: Retrospectiva del Sprint**
     * **Entrada:** Retroalimentación del cliente y lecciones aprendidas.
     * **Salida:** Plan de mejora para el siguiente Sprint.

4. **Cada prompt debe:**
   * Describir claramente la actividad Scrum a simular.
   * Explicar la entrada y salida requeridas.
   * Solicitar a los alumnos que generen o completen la información de cada etapa.

---

### Guía de Estructura de los Prompts

#### 1. Prompt 1: Definición del Product Backlog
* **Entrada:** El cliente ha proporcionado los siguientes requerimientos iniciales para una aplicación web de gestión de envíos logísticos:
  * Registro y autenticación de usuarios.
  * Creación y seguimiento de envíos.
  * Generación de reportes de estado de envíos.
  * Integración con sistemas de terceros para rastreo de envíos.
* **Salida:** Product Backlog inicial con las siguientes historias de usuario prioritarias:
  1. Como usuario, puedo registrarme e iniciar sesión en la aplicación.
  2. Como usuario, puedo crear un nuevo envío y seguir su estado.
  3. Como usuario, puedo generar reportes de estado de mis envíos.

#### 2. Prompt 2: Planificación del Sprint
* **Entrada:** Product Backlog.
* **Salida:** Plan del Sprint con las siguientes tareas y responsables:
  * **Tarea 1:** Desarrollar la funcionalidad de registro e inicio de sesión. (Desarrollador A)
  * **Tarea 2:** Implementar la funcionalidad de creación y seguimiento de envíos. (Desarrollador B)
  * **Tarea 3:** Diseñar e implementar la generación de reportes de estado de envíos. (Desarrollador C)
  * **Tarea 4:** Integrar la aplicación con los sistemas de terceros para rastreo de envíos. (Desarrollador D)

#### 3. Prompt 3: Ejecución del Sprint
* **Entrada:** Plan del Sprint.
* **Salida:** Incremento de software funcional con las siguientes funcionalidades implementadas:
  * Registro e inicio de sesión de usuarios.
  * Creación y seguimiento de envíos.
  * Generación de reportes de estado de envíos.
  * Integración con sistemas de terceros para rastreo de envíos.

#### 4. Prompt 4: Revisión del Sprint
* **Entrada:** Incremento de software funcional.
* **Salida:** Retroalimentación del cliente y lecciones aprendidas:
  * **Retroalimentación del cliente:** El cliente está satisfecho con las funcionalidades implementadas y sugiere agregar la opción de enviar notificaciones a los clientes sobre el estado de sus envíos.
  * **Lecciones aprendidas:** Mejorar la comunicación con el equipo de desarrollo para tener una mejor comprensión de los requerimientos del cliente. Implementar pruebas más exhaustivas antes de la entrega.

#### 5. Prompt 5: Retrospectiva del Sprint
* **Entrada:** Retroalimentación del cliente y lecciones aprendidas.
* **Salida:** Plan de mejora para el siguiente Sprint:
  * Mejorar la coordinación entre los miembros del equipo de desarrollo.
  * Implementar un proceso más eficiente para la estimación y asignación de tareas.
  * Incorporar la funcionalidad de envío de notificaciones a los clientes sobre el estado de sus envíos en el próximo Sprint.
  
## Resolucion
Lo resolví con gemini. Lo que hice fue armar los prompts de cada rol y cada salida o respuesta que gemini me devolvía de cada prompt, la usaba como entrada para el prompt del rol siguiente. Sería una secuencia de prompts encadenados, donde la salida de cada etapa sirve como entrada para la siguiente. Técnicas que use: encadenamiento de Prompts y juego de Roles, ya que en cada etapa forcé a la gemini a adoptar una mentalidad específica (Product Owner, Scrum Master, Equipo de Desarrollo, Cliente) para adecuar el vocabulario y las prioridades de la respuesta.

## 1. Definición del Product Backlog
### Prompt 1
**Objetivo:** Transformar los requerimientos iniciales del cliente en un Product Backlog inicial priorizado con historias de usuario.
**Alcance:** Fase de relevamiento y definición de negocio para la aplicación web de gestión de envíos logísticos.
**Tareas (Input y Output):**
*   **Input:** Requerimientos iniciales: Registro y autenticación de usuarios, Creación y seguimiento de envíos, Generación de reportes de estado, Integración con sistemas de terceros.
*   **Output:** Product Backlog inicial con historias de usuario prioritarias.
**Reglas de Oro:**
*   Actúa como un Product Owner.
*   Redacta estrictamente en formato de historia de usuario: "Como [rol], quiero [funcionalidad], para [beneficio]".
**Chequeos (Tests de Aceptación):**
*   ¿Están cubiertos los 4 requerimientos iniciales?
*   ¿Están ordenados por prioridad lógica de desarrollo?

### Respuesta de Gemini (Resultado a usar en el siguiente paso)
**Product Backlog Inicial:**
1. **Historia de Usuario 1:** Como usuario, quiero poder registrarme e iniciar sesión en la aplicación, para mantener mi información y envíos seguros.
2. **Historia de Usuario 2:** Como usuario, quiero crear un nuevo envío y seguir su estado, para saber exactamente dónde están mis paquetes en todo momento.
3. **Historia de Usuario 3:** Como administrador/usuario, quiero generar reportes de estado de mis envíos, para tener un resumen claro de la logística.
4. **Historia de Usuario 4:** Como sistema, quiero integrarme con plataformas de terceros, para obtener datos de rastreo en tiempo real y mostrarlos al usuario.

## 2. Planificación del Sprint
### Prompt 2
**Objetivo:** Descomponer el Product Backlog en tareas de desarrollo técnico y asignarlas al equipo.
**Alcance:** Sprint Planning del primer ciclo de desarrollo.
**Tareas (Input y Output):**
*   **Input:** El Product Backlog Inicial generado en el paso anterior.
*   **Output:** Plan del Sprint con las tareas a realizar y sus responsables.
**Reglas de Oro:**
*   Actúa como un Scrum Master.
*   Asigna las tareas dividiéndolas entre 4 desarrolladores específicos: Desarrollador A, B, C y D.
**Chequeos (Tests de Aceptación):**
*   ¿Cada historia de usuario se convirtió en una tarea clara?
*   ¿Están asignados los 4 desarrolladores de forma equitativa?

### Respuesta de Gemini (Resultado a usar en el siguiente paso)
**Plan del Sprint:**
*   **Tarea 1:** Desarrollar la funcionalidad de registro e inicio de sesión. **Responsable:** Desarrollador A.
*   **Tarea 2:** Implementar la funcionalidad de creación y seguimiento de envíos. **Responsable:** Desarrollador B.
*   **Tarea 3:** Diseñar e implementar la generación de reportes de estado de envíos. **Responsable:** Desarrollador C.
*   **Tarea 4:** Integrar la aplicación con los sistemas de terceros para rastreo de envíos. **Responsable:** Desarrollador D.

## 3. Ejecución del Sprint
### Prompt 3
**Objetivo:** Simular la finalización del trabajo de desarrollo y consolidar el software construido.
**Alcance:** Cierre de la etapa técnica del Sprint antes de la revisión con el cliente.
**Tareas (Input y Output):**
*   **Input:** El Plan del Sprint con las tareas asignadas a los Desarrolladores A, B, C y D.
*   **Output:** Un listado que represente el Incremento de software funcional.
**Reglas de Oro:**
*   Actúa como el Equipo de Desarrollo.
*   Confirma que todas las tareas planificadas se terminaron con éxito y ahora son software funcional.
**Chequeos (Tests de Aceptación):**
*   ¿El incremento detalla claramente las 4 funcionalidades operativas?

### Respuesta de Gemini (Resultado a usar en el siguiente paso)
**Incremento de Software Funcional:**
El equipo ha finalizado el desarrollo. El incremento desplegable incluye:
*   Módulo de registro e inicio de sesión de usuarios completamente operativo.
*   Sistema de creación y seguimiento de envíos activo y guardando datos en base.
*   Módulo de generación de reportes de estado de envíos implementado.
*   Integración exitosa con sistemas de terceros para rastreo de envíos funcionando en tiempo real.

## 4. Revisión del Sprint
### Prompt 4
**Objetivo:** Obtener el feedback del cliente tras la demo del producto y documentar el aprendizaje del equipo.
**Alcance:** Reunión de Sprint Review con los stakeholders (cliente) y el equipo Scrum.
**Tareas (Input y Output):**
*   **Input:** El Incremento de software funcional desarrollado en el Sprint.
*   **Output:** Retroalimentación del cliente y lecciones aprendidas.
**Reglas de Oro:**
*   Actúa como el Scrum Master moderando la reunión.
*   El cliente debe mostrar satisfacción pero pedir obligatoriamente una funcionalidad para notificar a los clientes sobre sus envíos.
*   Las lecciones aprendidas deben enfocarse en comunicación y testing.
**Chequeos (Tests de Aceptación):**
*   ¿Existe una sección de feedback y otra de lecciones?
*   ¿El feedback pide explícitamente las notificaciones?

### Respuesta de Gemini (Resultado a usar en el siguiente paso)
**Resultados de la Revisión del Sprint:**
*   **Retroalimentación del cliente:** El cliente está satisfecho con las funcionalidades implementadas y sugiere agregar la opción de enviar notificaciones a los clientes sobre el estado de sus envíos.
*   **Lecciones aprendidas:** Mejorar la comunicación con el equipo de desarrollo para tener una mejor comprensión de los requerimientos del cliente. Implementar pruebas más exhaustivas antes de la entrega.

## 5. Retrospectiva del Sprint
### Prompt 5
**Objetivo:** Convertir las lecciones aprendidas y el feedback en acciones de mejora concretas para el próximo ciclo.
**Alcance:** Reunión interna del Scrum Team (Retrospectiva).
**Tareas (Input y Output):**
*   **Input:** Retroalimentación del cliente y lecciones aprendidas del paso anterior.
*   **Output:** Plan de mejora para el siguiente Sprint.
**Reglas de Oro:**
*   Actúa como un  Scrum Master.
*   El plan debe ser directo, sin vueltas y dar respuesta exacta a los problemas detectados.
**Chequeos (Tests de Aceptación):**
*   ¿El plan soluciona los problemas de comunicación y asignación?
*   ¿Se incluye el desarrollo de notificaciones para el próximo sprint?

### Respuesta de Gemini (Resultado Final)
**Plan de Mejora para el siguiente Sprint:**
*   Mejorar la coordinación entre los miembros del equipo de desarrollo mediante Daily Meetings más estructuradas.
*   Implementar un proceso más eficiente para la estimación y asignación de tareas.
*   Incorporar la funcionalidad de envío de notificaciones a los clientes sobre el estado de sus envíos en el próximo Sprint.