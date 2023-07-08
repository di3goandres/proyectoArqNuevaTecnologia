# Seleccion de patron para los sensores

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-07-08

## Context and Problem Statement

El sistema debe admitir la comunicación bidireccional entre los sensores, los actuadores IoT y el centro de control

## Decision Drivers

* RF-006 Comunicación y conectividad.

## Considered Options

* Observer
* Publish subscriber

## Decision Outcome

Chosen option: "Observer", because comes out best. El patrón Observer es adecuado en situaciones en las que se requiere una comunicación eficiente y desacoplada entre un objeto (sujeto) y múltiples objetos dependientes (observadores) cuando el sujeto experimenta cambios en su estado.
En resumen, el patrón Publish-Subscribe es una alternativa al patrón Observer en contextos donde se requiere un enfoque más centralizado y desacoplado para la comunicación entre publicadores y suscriptores. Este patrón es especialmente útil en sistemas distribuidos o en aquellos donde la escalabilidad y la flexibilidad son consideraciones clave.

### Positive Consequences

* Comunicación bidireccional: Si necesitas establecer una comunicación bidireccional entre un sujeto y sus observadores, donde los observadores puedan recibir actualizaciones del sujeto y, a su vez, interactuar con él, el patrón Observer es una buena opción.
* Actualizaciones dinámicas: Si el sujeto necesita notificar automáticamente a sus observadores cuando ocurren cambios en su estado interno sin que los observadores tengan que solicitar explícitamente la información actualizada, el patrón Observer es apropiado.
* Desacoplamiento entre sujetos y observadores: Si deseas mantener una estructura flexible y desacoplada entre los sujetos y los observadores, permitiendo que se agreguen o eliminen nuevos observadores sin afectar el código del sujeto, el patrón Observer es beneficioso.
* Escalabilidad y reutilización: Si prevés que tu sistema necesitará admitir múltiples observadores y que estos puedan variar o ampliarse en el futuro, el patrón Observer es una elección adecuada. Proporciona una estructura modular y escalable, lo que facilita la reutilización de componentes y la extensibilidad del sistema.
* Manejo de eventos y notificaciones: Si el sistema tiene eventos o cambios de estado que necesitan ser capturados y procesados por múltiples objetos interesados, el patrón Observer es útil para gestionar esas notificaciones y garantizar que los observadores sean informados adecuadamente.

## Pros and Cons of the Options

### Observer

* Good, because Desacoplamiento
* Good, because Extensibilidad
* Good, because Flexibilidad

### Publish subscriber

En resumen, el patrón Publish-Subscribe es una alternativa al patrón Observer en contextos donde se requiere un enfoque más centralizado y desacoplado para la comunicación entre publicadores y suscriptores. Este patrón es especialmente útil en sistemas distribuidos o en aquellos donde la escalabilidad y la flexibilidad son consideraciones clave.

* Good, because Distribución: El patrón Publish-Subscribe se presta bien para sistemas distribuidos, donde los publicadores y los suscriptores pueden estar en diferentes ubicaciones físicas. El bus de eventos actúa como el medio centralizado para la comunicación entre los componentes distribuidos.
* Good, because Desacoplamiento: Los publicadores y los suscriptores están desacoplados entre sí. Los publicadores no necesitan conocer los detalles de los suscriptores y viceversa. Esto facilita la extensibilidad y la modularidad del sistema.
* Bad, because Rendimiento: En sistemas con muchos eventos y suscriptores, puede haber un impacto en el rendimiento debido al procesamiento adicional necesario para enrutar los eventos a los suscriptores adecuados.
* Bad, because Complejidad: La introducción de un bus de eventos agrega cierta complejidad al sistema en comparación con el patrón Observer más simple. El bus de eventos debe manejar el enrutamiento y la entrega de eventos a los suscriptores correctos
