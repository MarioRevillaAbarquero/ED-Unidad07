# ED-Unidad07
# Entornos de Desarrollo - Unidad 07: Modelado con UML

Este repositorio contiene las actividades prácticas correspondientes a la Unidad 07, centradas en el diseño de diagramas de casos de uso, actividades y estados para diferentes sistemas de gestión y control.

## Estructura del Repositorio
[cite_start]La organización de los archivos es la siguiente:
- `/Actividad 1`: Gestión de un Centro Deportivo.
- `/Actividad 2`: Máquina Expendedora de Billetes.
- `/Actividad 3`: Sistema de Alarma Inteligente.

---

## Actividad 1: Sistema de Gestión de un Centro Deportivo
### Explicación de los Diagramas
- **Casos de Uso**: Representa las interacciones de los socios (reservas y clases) y el administrador (gestión) con el sistema del centro.
- **Actividades**: Detalla el flujo lógico desde que un socio elige fecha y hora hasta que recibe la confirmación de su reserva o la denegación por impago.

### Justificación
- **Actores**: 
  - **Socio**: Usuario principal que interactúa con las reservas.
  - **Administrador**: Responsable de la gestión de pagos y alta de contenidos.
- **Relaciones**:
  - **Include**: La reserva de pista siempre requiere la verificación de pagos pendientes.
  - **Extend**: La contratación del seguro de lesiones es una opción adicional y voluntaria al apuntarse a una clase.

---

## Actividad 2: Máquina Expendedora de Billetes
### Explicación de los Diagramas
- **Actividades**: Describe el proceso de compra, diferenciando entre el pago con tarjeta (validación bancaria) y efectivo (gestión de cambio).
- **Estados**: Muestra el ciclo de vida de un billete, desde su creación hasta que queda inutilizable.

### Justificación
- **Estados y Transiciones**:
  - El billete pasa de **No emitido** a **Emitido** tras completar el pago.
  - La transición de **Emitido** a **Validado** ocurre mediante el evento "picar en el torno".
  - Finalmente, el estado pasa a **Agotado** una vez el viaje se ha completado.

---

## Actividad 3: Sistema de Alarma Inteligente
### Explicación de los Diagramas
- **Estados**: Modela el comportamiento dinámico de la alarma, incluyendo retardos de entrada y modos de emergencia.
- **Casos de Uso**: Define cómo los propietarios, técnicos y sensores interactúan con las funciones de seguridad.

### Justificación
- **Actores**: 
  - **Propietario**: Usuario que arma/desarma[cite: 42].
  - **Sensor de Movimiento**: Actor de sistema que dispara la alerta[cite: 42].
  - **Técnico**: Actor especializado para el mantenimiento[cite: 42].
  - **Central de Policía**: Receptor de alertas externas[cite: 42].
- **Estados y Transiciones**:
  - Si el sistema está **Armado** y detecta movimiento, entra en **En Espera** (retardo de 30s) antes de pasar a **Alarma Sonando** si no se introduce el código[cite: 36, 37].
  - El estado de **Mantenimiento** es accesible desde cualquier punto mediante una llave especial del técnico[cite: 39].
  - **Acciones**: Al entrar en "Alarma Sonando", se ejecutan automáticamente acciones como `llamar_policia()` y `activar_sirena()`.
