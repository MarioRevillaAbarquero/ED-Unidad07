
# Entornos de Desarrollo - Unidad 07: Modelado con UML



Este repositorio contiene los diagramas correspondientes a la unidad de modelado de software. Se han realizado diagramas de Casos de Uso, Actividades y Estados para tres supuestos distintos siguiendo las pautas de la entrega.

## 📂 Contenido del repositorio

La estructura de carpetas se ha organizado de la siguiente manera:
* **/Actividad 1**: Gestión del centro deportivo (Reservar pista).
* **/Actividad 2**: Lógica de la máquina de billetes de metro.
* **/Actividad 3**: Configuración y estados de una alarma inteligente.

---

## 🛠️ Justificación técnica

### Actividad 1: Centro Deportivo
En el diagrama de **Casos de Uso**, he separado las funciones del Socio y del Administrador.
* **Relaciones**: He usado un `<<include>>` para la verificación de pagos porque el enunciado dice que el sistema "siempre debe verificar" antes de reservar. Para el seguro de lesiones he usado un `<<extend>>` ya que es algo opcional que el socio decide en el momento.
* **Flujo**: El diagrama de actividades contempla el bucle de "elegir otra fecha" si no hay pistas libres, tal como se pide en el flujo de control.

### Actividad 2: Máquina de Metro
* **Proceso de pago**: En el diagrama de actividades he creado una bifurcación según el método de pago (tarjeta o efectivo). Para la tarjeta se incluye la validación del PIN con el banco y para el efectivo la comprobación del cambio.
* **Ciclo de vida del Billete**: En el diagrama de estados, el billete empieza como "No emitido" y cambia a "Emitido" tras el pago. El paso clave es la transición a "Validado" que ocurre con el evento de "picar" en el torno.

### Actividad 3: Alarma Inteligente
Es el sistema más complejo por el comportamiento dinámico de sus estados.
* **Estados**: He incluido el estado "En Espera" que actúa como un retardo de 30 segundos antes de que la alarma suene realmente.
* **Mantenimiento**: He configurado este estado para que sea accesible desde cualquier otro punto del diagrama si el técnico usa su llave.
* **Actores**: Además del Propietario, he definido al Sensor como el actor que dispara el evento de movimiento y a la Policía como el actor que recibe la alerta.

---

## 🚀 Formato de los archivos
* Los diagramas finales están en formato **.png** para facilitar su visualización directa en GitHub.
