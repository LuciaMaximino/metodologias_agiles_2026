# Ejercicio Nro: 17

## Enunciado
Objetivo: Desarrollar una aplicación web que permita a los usuarios gestionar sus finanzas personales de manera eficiente y segura. La aplicación debe cumplir con los siguientes requisitos funcionales:
1. Gestión de cuentas bancarias:
Permitir la creación y edición de cuentas bancarias.
Visualizar el saldo actual y el historial de movimientos de cada cuenta.
Realizar transferencias entre cuentas propias.
Descargar el historial de movimientos en formato CSV o PDF.
2. Gestión de ingresos y gastos:
Permitir la creación y edición de ingresos y gastos.
Categorizar los ingresos y gastos por tipo (salario, alquiler, alimentación, etc.).
Visualizar gráficos y reportes sobre los ingresos y gastos por categoría y período de tiempo.
Establecer presupuestos para diferentes categorías de gastos.
3. Gestión de deudas:
Permitir la creación y edición de deudas.
Indicar el monto total de la deuda, la tasa de interés, el plazo de pago y el monto de las cuotas.
Visualizar un calendario de pagos y realizar simulaciones de diferentes escenarios de pago.
Generar informes sobre el progreso en el pago de las deudas.

## Resolucion
ESTIMACIÓN DEL TAMAÑO DEL PROYECTO (X PFC)
Pequeña (S): 3 PFC
Mediana (M): 5 PFC
Grande (L): 7 PFC

1. Gestión de cuentas bancarias
Proceso 1.1: Crear/Editar cuenta bancaria - 3 PFC
Movimiento - Descripción
Entry - Ingresar datos de la cuenta (nombre, tipo, saldo inicial)
Write - Guardar/actualizar cuenta en BD
Exit - Confirmar operación al usuario

Proceso 1.2: Visualizar saldo e historial de movimientos - 4 PFC
Movimiento - Descripción
Entry - Seleccionar cuenta a consultar
Read - Leer datos de saldo de la cuenta
Read - Leer historial de movimientos
Exit - Mostrar saldo e historial en pantalla

Proceso 1.3: Realizar transferencia entre cuentas - 6 PFC
Movimiento - Descripción
Entry - Ingresar datos de la transferencia (cuenta origen, destino, monto)
Read - Leer saldo de cuenta origen
Write - Actualizar saldo de cuenta origen
Write - Actualizar saldo de cuenta destino
Write - Registrar movimiento en historial
Exit - Mostrar confirmación de transferencia

Proceso 1.4: Descargar historial en CSV o PDF - 3 PFC
Movimiento - Descripción
Entry - Seleccionar formato (CSV o PDF) y rango de fechas
Read - Leer historial de movimientos
Exit - Generar y entregar archivo al usuario

Total Módulo 1: 16 PFC

2. Gestión de ingresos y gastos
Proceso 2.1: Crear/Editar ingreso o gasto - 3 PFC
Movimiento - Descripción
Entry - Ingresar datos (monto, tipo, categoría, fecha)
Write - Guardar/actualizar registro en BD
Exit - Confirmar operación al usuario

Proceso 2.2: Categorizar ingreso/gasto - 4 PFC
Movimiento - Descripción
Entry - Seleccionar categoría del movimiento
Read - Leer categorías disponibles
Write - Asociar categoría al registro
Exit - Mostrar confirmación

Proceso 2.3: Visualizar gráficos y reportes - 3 PFC
Movimiento - Descripción
Entry - Seleccionar categoría y período de tiempo
Read - Leer ingresos y gastos según filtros
Exit - Mostrar gráficos y reporte en pantalla

Proceso 2.4: Establecer presupuesto por categoría - 3 PFC
Movimiento - Descripción
Entry - Ingresar monto de presupuesto y categoría
Write - Guardar presupuesto en BD
Exit - Confirmar presupuesto establecido

Total Módulo 2: 13 PFC

3. Gestión de deudas
Proceso 3.1: Crear/Editar deuda - 3 PFC
Movimiento - Descripción
Entry - Ingresar datos (monto, tasa de interés, plazo, cuotas)
Write - Guardar/actualizar deuda en BD
Exit - Confirmar operación al usuario

Proceso 3.2: Visualizar calendario de pagos - 3 PFC
Movimiento - Descripción
Entry - Seleccionar deuda a consultar
Read - Leer datos de la deuda y cuotas
Exit - Mostrar calendario de pagos en pantalla

Proceso 3.3: Simulación de escenarios de pago - 3 PFC
Movimiento - Descripción
Entry - Ingresar parámetros alternativos de pago
Read - Leer datos actuales de la deuda
Exit - Mostrar simulación comparativa

Proceso 3.4: Generar informe de progreso de pago - 3 PFC
Movimiento - Descripción
Entry - Seleccionar deuda e intervalo de tiempo
Read - Leer pagos realizados y saldo pendiente
Exit - Mostrar/exportar informe de progreso

Total Módulo 3: 12 PFC

Tamaño funcional total (X): 41 PFC

CANTIDAD DE PUNTOS DE FUNCIÓN QUE SE PUEDEN HACER EN UN MES
Este proyecto tiene 3 módulos con funcionalidades de complejidad media-alta (gráficos, simulaciones, exportación de archivos, transferencias). Un equipo razonable sería:
- Desarrollador Frontend 1
- Desarrollador Backend 1
- QA/Tester 1
- Líder técnico/PM 1
Tamaño del equipo (Z) = 4 personas
El proyecto tiene 41 PFC distribuidos en 11 procesos funcionales de complejidad baja a media (entre 3 y 6 PFC cada uno, sin lógica que sea muy compleja). Un equipo de 4 personas con un nivel intermedio de experiencia en desarrollo web podría producir de forma razonable:
Puntos de función COSMIC por mes (W) = 20 PFC/mes

CALCULO DEL COSTO POR PUNTO DE FUNCIÓN (Y USD)
Rol - Costo mensual en USD segun el mercado de latinoamérica
Desarrollador Frontend - 2.500
Desarrollador Backend - 2.800
QA/Tester - 1.800
Líder técnico/PM - 3.200
Total mensual: 10.300 USD
Costo por punto de función (Y): Y = Total mensual/W ​= 10.300​/20 = 515 USD/PFC

DURACIÓN DEL PROYECTO
A = X/W = 41/20 = 2,05 meses

COSTO DEL PROYECTO
B = X * Y = 41 * 515 = 21.115 USD