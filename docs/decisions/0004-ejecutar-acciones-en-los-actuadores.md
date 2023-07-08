# Ejecutar acciones en los actuadores

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-07-08

## Context and Problem Statement

en determinados ocasiones es necesario enviar acciones, como encender luz, activar aspersores, abrir la talanquera del parqueadero.

## Decision Drivers

* RF-012 Activación de Actuador IoT según Evento

## Considered Options

* Patron Command

## Decision Outcome

Chosen option: "Patron Command", because comes out best.

### Positive Consequences

* Desacoplamiento: El patrón Command permite desacoplar el objeto que realiza la solicitud (llamado invocador) del objeto que lleva a cabo la acción (llamado receptor). En el contexto de un edificio inteligente, el invocador podría ser un controlador centralizado que recibe comandos para realizar acciones específicas, mientras que el receptor sería el componente real del edificio que ejecuta la acción, como un actuador, un sistema de iluminación o un sistema de climatización. Esto permite que los componentes del edificio no dependan directamente de los comandos, lo que facilita la modificación y extensión del sistema.
* Flexibilidad: El patrón Command permite agregar fácilmente nuevos comandos sin modificar el código existente del invocador o del receptor. En un edificio inteligente, es probable que se necesiten diferentes tipos de comandos para controlar una variedad de acciones, como encender o apagar luces, ajustar la temperatura o activar sistemas de seguridad. El patrón Command permite encapsular cada una de estas acciones en un objeto de comando separado, lo que facilita la incorporación de nuevas funcionalidades sin afectar a los componentes existentes.
* Historial y reversibilidad de acciones: El patrón Command permite mantener un historial de acciones realizadas, lo que puede ser útil en un edificio inteligente para realizar seguimiento de las operaciones realizadas en diferentes momentos. Además, el patrón Command permite implementar fácilmente la funcionalidad de deshacer/rehacer, lo que brinda la capacidad de revertir acciones anteriores en caso de errores o cambios de requerimientos.
* Integración con otros patrones: El patrón Command puede integrarse eficientemente con otros patrones de diseño. Por ejemplo, puede combinarse con el patrón Observer para notificar a los observadores sobre la ejecución de un comando específico. También puede combinarse con el patrón Decorator para agregar funcionalidades adicionales a los comandos.
* Mantenibilidad: El patrón Command facilita el mantenimiento y la evolución del código a lo largo del tiempo. Debido a que los comandos encapsulan acciones específicas, es más fácil modificar o extender el comportamiento de una acción específica sin afectar a otros comandos o componentes del sistema. Esto permite una mayor modularidad y flexibilidad en el diseño del edificio inteligente.
