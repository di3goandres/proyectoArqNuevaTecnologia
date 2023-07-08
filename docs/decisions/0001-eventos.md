# Estilo de arquitectura

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-07-08

## Context and Problem Statement

Necesitamos recolectar los eventos que se generan en los diferentes dispositivos de IoT dentro del nuestro edificio inteligente.

## Decision Drivers

* RF-001 Recopilacion de datos.

## Considered Options

* Event driven
* Message Driven

## Decision Outcome

Chosen option: ""

### Positive Consequences

* Al basarse en eventos, el sistema puede responder de manera rápida y proactiva a los cambios y sucesos en la factoría. Los componentes pueden estar a la espera de eventos relevantes y tomar acciones inmediatas en función de ellos. Esto permite una mejor capacidad de respuesta y adaptabilidad a eventos en tiempo real, como alarmas de sensores, cambios en el estado de la producción, etc
* La arquitectura de eventos facilita la integración de nuevos componentes y servicios en el sistema. Los eventos actúan como puntos de integración, permitiendo la comunicación entre diferentes partes del sistema de manera sencilla. Además, es más fácil extender y agregar nuevas funcionalidades al sistema mediante la incorporación de nuevos componentes que generen y consuman eventos.
* Tolerancia a fallos: La arquitectura de eventos puede proporcionar mayor tolerancia a fallos. Si un componente no puede procesar un evento en un momento dado, este se puede encolar y procesar más tarde, evitando la pérdida de información crítica. Además, si un componente falla, los eventos pendientes pueden ser procesados por otros componentes disponibles, evitando interrupciones en el funcionamiento del sistema

## Pros and Cons of the Options

### Event driven

* Good, because La arquitectura de eventos permite un mayor desacoplamiento entre los diferentes componentes del sistema. Cada componente puede enviar y recibir eventos de forma independiente, lo que reduce la dependencia directa entre ellos. Esto facilita la evolución y actualización de los componentes de manera individual, sin afectar al funcionamiento de todo el sistema
* Good, because Al utilizar una arquitectura de eventos, los componentes pueden escalar de manera independiente según la carga de trabajo. Los eventos se pueden distribuir y procesar de forma paralela, lo que permite manejar grandes volúmenes de eventos de manera eficiente. Además, se pueden agregar o quitar componentes de manera fácil y flexible según las necesidades de escalabilidad del sistema.
* Good, because : Al basarse en eventos, el sistema puede responder de manera rápida y proactiva a los cambios y sucesos en la factoría. Los componentes pueden estar a la espera de eventos relevantes y tomar acciones inmediatas en función de ellos. Esto permite una mejor capacidad de respuesta y adaptabilidad a eventos en tiempo real, como alarmas de sensores, cambios en el estado de la producción, etc

### Message Driven

* Good, because Desacoplamiento: El estilo Message-Driven permite un alto nivel de desacoplamiento entre los componentes del sistema. Los componentes interactúan entre sí a través de mensajes, lo que significa que no necesitan conocer los detalles internos de los demás. Esto facilita la evolución y el mantenimiento del sistema, ya que los cambios en un componente no afectarán directamente a los demás.
* Good, because Escalabilidad: Al usar mensajes para comunicarse, es más fácil escalar verticalmente y horizontalmente el sistema. La capacidad de procesamiento se puede aumentar agregando más instancias de los componentes que consumen los mensajes o distribuyendo los mensajes entre múltiples componentes. Esto permite manejar un mayor volumen de carga y proporciona una mejor capacidad de respuesta
* Bad, because Complejidad: La implementación de un sistema basado en mensajes puede agregar complejidad al diseño y desarrollo del software. La necesidad de definir y gestionar las colas de mensajes, los enrutadores y los mecanismos de suscripción puede requerir un esfuerzo adicional en comparación con otros enfoques más simples.
* Bad, because Latencia: En un sistema Message-Driven, los mensajes se envían y procesan de manera asíncrona, lo que puede introducir cierta latencia en la comunicación. Si la sincronización inmediata es crítica en el sistema, este enfoque puede no ser la mejor opción, ya que los mensajes pueden experimentar demoras en la entrega y el procesamiento.
* Bad, because Control de transacciones: El manejo de transacciones y la consistencia de datos pueden volverse más complejos en un sistema Message-Driven. Si es necesario mantener la integridad transaccional en todo el sistema, puede requerir un diseño cuidadoso y la implementación de mecanismos de compensación en caso de fallos.
