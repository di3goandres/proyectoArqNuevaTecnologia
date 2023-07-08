# Modos de funcionamiento

* Status: accepted
* Date: 2023-07-08

## Context and Problem Statement

Cada modo de funcionamiento puede requerir configuraciones y ajustes específicos para los sensores, actuadores y otros componentes del sistema. En lugar de tener condiciones lógicas complejas dentro del código del sistema para manejar cada modo individualmente

## Decision Drivers

* RF-002 Procesamiento de eventos – (modo Normal)
* RF-004 Funcionamiento en modo seguro
* RF-005 Funcionamiento modo sostenible

## Considered Options

* Patron Strategy

## Decision Outcome

Chosen option: "Patron Strategy", because comes out best.

### Positive Consequences

* Pruebas unitarias simplificadas: Las estrategias individuales se pueden probar de forma aislada, lo que facilita las pruebas unitarias y la detección de errores. Esto permite una mejor calidad del software y una mayor confianza en el comportamiento del sistema.
* Reutilización de código: Al separar los algoritmos en estrategias individuales, se promueve la reutilización de código. Puedes utilizar las mismas estrategias en diferentes partes del sistema o incluso en proyectos futuros, lo que ahorra tiempo y esfuerzo en el desarrollo.
* Mantenibilidad y extensibilidad: Al encapsular cada algoritmo o estrategia en una clase separada, facilitas la comprensión, el mantenimiento y la extensión del código. Cada estrategia se puede modificar o agregar sin afectar el resto del sistema.
* Flexibilidad y adaptabilidad: El uso del patrón Estrategia te brinda la capacidad de cambiar dinámicamente los algoritmos o estrategias utilizados en tiempo de ejecución. Esto proporciona una mayor flexibilidad y adaptabilidad a las necesidades cambiantes del sistema.

### Negative Consequences

* Necesidad de administrar las estrategias: Debes proporcionar un mecanismo para gestionar las estrategias y seleccionar la estrategia adecuada en cada momento. Esto agrega complejidad adicional en términos de gestión y mantenimiento de las estrategia

## Pros and Cons of the Options

### Patron Strategy

* Good, because Flexibilidad: El patrón Estrategia permite intercambiar algoritmos o estrategias en tiempo de ejecución. Esto brinda flexibilidad al sistema, ya que puedes cambiar la forma en que se realiza una tarea sin modificar el código existente.
* Good, because Separación de responsabilidades: Al encapsular diferentes algoritmos en estrategias separadas, se promueve la modularidad y la separación de responsabilidades en el código. Cada estrategia se encarga de un conjunto específico de reglas o comportamientos, lo que facilita el mantenimiento y la comprensión del sistema.
* Good, because Reutilización de código: El patrón Estrategia fomenta la reutilización de código, ya que los algoritmos encapsulados en las estrategias se pueden compartir y aplicar en diferentes contextos.
* Good, because Facilidad de prueba: Debido a la separación de responsabilidades y la encapsulación de algoritmos, las estrategias se pueden probar individualmente de manera aislada, lo que facilita las pruebas unitarias y la detección de errores.
* Good, because Escalabilidad: El patrón Estrategia permite agregar fácilmente nuevas estrategias sin modificar el código existente. Esto facilita la incorporación de nuevas funcionalidades o el soporte de nuevos casos de uso.
* Bad, because Complejidad adicional: El uso del patrón Estrategia puede agregar una capa adicional de complejidad al diseño del sistema. Se necesitará definir e implementar las interfaces y las estrategias concretas, lo que puede aumentar la cantidad de código y la complejidad general del proyecto.
* Bad, because Overhead de estructura: Al utilizar el patrón Estrategia, se agrega una estructura adicional al sistema, lo que puede resultar en un aumento del uso de memoria y de recursos de procesamiento.
* Bad, because Necesidad de administrar las estrategias: El sistema debe proporcionar una forma de gestionar las estrategias y seleccionar la estrategia adecuada en cada momento. Esto puede requerir una gestión adicional para garantizar la coherencia y el correcto funcionamiento del sistem
