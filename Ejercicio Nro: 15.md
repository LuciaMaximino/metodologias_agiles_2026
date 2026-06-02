# Ejercicio Nro: 15

## Enunciado
Generar un plan de trabajo basado en SCRUM para resolver la siguiente tarea
Objetivo:
El objetivo de este ejercicio es que los alumnos universitarios practiquen la creación de historias de usuario para un sistema informático de presupuesto de construcción de galpones, utilizando la metodología ágil.
Descripción del ejercicio:
1. Los alumnos deberán formar equipos de trabajo, de preferencia de 3 a 5 personas por equipo.
2. Cada equipo deberá seleccionar la temática de construcción de galpones para su sistema informático de presupuesto.
3. Los equipos deberán generar al menos tres historias de usuario para su sistema, basadas en la temática seleccionada. Cada historia de usuario debe incluir un título y una descripción que contenga los criterios de aceptación.
4. Las historias de usuario deben enfocarse en las funcionalidades y características clave del sistema informático, considerando aspectos como la creación de presupuestos detallados, seguimiento del presupuesto durante la construcción, inclusión de etapas, generación de informes, entre otros.
5. Los equipos deben asegurarse de que las historias de usuario sean claras, concisas y comprensibles, siguiendo las buenas prácticas de redacción de historias ágiles.
6. Al finalizar, cada equipo deberá presentar sus historias de usuario al resto de la clase, explicando el contexto de su sistema y los criterios de aceptación de cada historia.
7. Se fomenta el intercambio de ideas y la retroalimentación constructiva entre los equipos durante las presentaciones.
Nota:
Los equipos pueden utilizar ejemplos y situaciones hipotéticas para desarrollar las historias de usuario, considerando las necesidades y requisitos típicos de un sistema de presupuesto de construcción de galpones. Además, se recomienda utilizar herramientas como tarjetas o post-its para escribir y visualizar las historias de usuario durante el ejercicio.

## Resolución
Historias de usuario

HU-01 
Título: Creación de presupuesto detallado
Puntos estimados: 8pts
Prioridad: Alta  
Descripción: Como cliente, quiero ingresar los datos de mi galpón para que el sistema genere un presupuesto detallado automáticamente.
Criterios de aceptación:
El sistema acepta dimensiones (largo, ancho, alto) y tipo de material.
Se calcula el costo total desglosado por ítem (estructura, cubierta, mano de obra).
El presupuesto puede exportarse en PDF.
El cálculo se realiza en menos de 3 segundos.

HU-02 
Título: Seguimiento del presupuesto durante la construcción
Puntos estimados: 5pts 
Prioridad: Alta  
Descripción: Como administrador de obra, quiero registrar los gastos reales por etapa para que pueda comparar el presupuesto original con la ejecución real.
Criterios de aceptación:
Se pueden registrar gastos por etapa (cimientos, estructura, cubierta, etc.).
El sistema muestra la diferencia entre lo presupuestado y lo gastado.
Se emite una alerta visual cuando el gasto supera el 10% del presupuesto por etapa.
El historial de registros es editable con trazabilidad de cambios.

HU-03 
Título: Generación de informes de avance
Puntos estimados: 3pts
Prioridad: Media 
Descripción: Como director de proyecto, quiero generar informes periódicos del estado del presupuesto para que pueda tomar decisiones informadas a tiempo.
Criterios de aceptación:
El informe incluye gráfico comparativo de presupuesto vs. gasto real.
Se puede filtrar por etapa, fecha o categoría de gasto.
El informe es exportable en PDF y Excel.
La generación no supera los 5 segundos.