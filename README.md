# ED-Unidad07
# Entornos de Desarrollo - Unidad 07: Modelado con UML

[cite_start]Este repositorio contiene las actividades prácticas correspondientes a la Unidad 07, centradas en el diseño de diagramas de casos de uso, actividades y estados para diferentes sistemas de gestión y control[cite: 4, 51].

## Estructura del Repositorio
[cite_start]La organización de los archivos es la siguiente[cite: 50]:
- `/Actividad 1`: Gestión de un Centro Deportivo.
- `/Actividad 2`: Máquina Expendedora de Billetes.
- `/Actividad 3`: Sistema de Alarma Inteligente.

---

## Actividad 1: Sistema de Gestión de un Centro Deportivo
### Explicación de los Diagramas
- [cite_start]**Casos de Uso**: Representa las interacciones de los socios (reservas y clases) y el administrador (gestión) con el sistema del centro[cite: 8, 11].
- [cite_start]**Actividades**: Detalla el flujo lógico desde que un socio elige fecha y hora hasta que recibe la confirmación de su reserva o la denegación por impago[cite: 15, 18].

### Justificación
- **Actores**: 
  - [cite_start]**Socio**: Usuario principal que interactúa con las reservas[cite: 8].
  - [cite_start]**Administrador**: Responsable de la gestión de pagos y alta de contenidos[cite: 11].
- **Relaciones**:
  - [cite_start]**Include**: La reserva de pista siempre requiere la verificación de pagos pendientes[cite: 9].
  - [cite_start]**Extend**: La contratación del seguro de lesiones es una opción adicional y voluntaria al apuntarse a una clase[cite: 10].

---

## Actividad 2: Máquina Expendedora de Billetes
### Explicación de los Diagramas
- [cite_start]**Actividades**: Describe el proceso de compra, diferenciando entre el pago con tarjeta (validación bancaria) y efectivo (gestión de cambio)[cite: 24, 25].
- [cite_start]**Estados**: Muestra el ciclo de vida de un billete, desde su creación hasta que queda inutilizable[cite: 28, 29].

### Justificación
- **Estados y Transiciones**:
  - [cite_start]El billete pasa de **No emitido** a **Emitido** tras completar el pago[cite: 29].
  - [cite_start]La transición de **Emitido** a **Validado** ocurre mediante el evento "picar en el torno".
  - [cite_start]Finalmente, el estado pasa a **Agotado** una vez el viaje se ha completado.

---

## Actividad 3: Sistema de Alarma Inteligente
### Explicación de los Diagramas
- [cite_start]**Estados**: Modela el comportamiento dinámico de la alarma, incluyendo retardos de entrada y modos de emergencia[cite: 35].
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
  - **Acciones**: Al entrar en "Alarma Sonando", se ejecutan automáticamente acciones como `llamar_policia()` y `activar_sirena()`[cite: 40].
