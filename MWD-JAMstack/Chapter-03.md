---
layout: default
permalink: /jamstack/chapter-03
---

## **Capítulo #3**

# Beneficios del JAMstack

## Simplificar los Sistemas y el Pensamiento

Gracias a personas innovadoras que construyeron capas de abstracción sobre los bits y bytes de bajo nivel que utilizan las computadoras para operar, la cantidad de trabajo que puede realizar un único desarrollador al día de hoy es astronómica.

Las abstracciones, sin embargo, tiene [fugas](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/). Algunas veces, el nivel inferior del stack de repente se da a conocer. Podria estar trabajando en programación orientada a objetos de alto nivel, desarrollando una aplicación impulsada por una base de datos con un _Object-Relational Mapping (ORM)_ cuando de repente un problema de gestión de memoria de bajo nivel, en lo profundo de una dependencia compilada, provoca un desbordamiento de búfer que un usuario malintencionado inteligente puede aprovechar para secuestrar la base de datos y tomar el control total de la misma.

A menos que encontremos formas de construir _firewalls_ sólido entre las diferentes capas del stack, estos tipos de problemas siempre podrán penetrar las capas inferiores o los puntos ocultos en la cadena de dependencias.

Afortunadamente, el JAMstack crea varios firewalls de este tipo para gestionar la complejidad y centrar la atención en partes más pequeñas de forma aislada.

### Mejor comprensión y agilidad mental

Con el renderizado del lado del servidor, todas las capas del stack siempre están involucradas en cualquiera de las peticiones que un usuario hace a un sitio o aplicación. Para construir software eficiente y seguro, los desarrolladores deben comprender a fondo todas las capas por las que flujen de peticiones, incluyendo los complementos de terceros, los controladores de base de datos y los detalles de implementación de los lenguajes de programación.

Al desacoplar completamente la capa de construcción del runtime del sistema y editar partes prefabricadas, se construye un muro irrompible entre el entorno en tiempo de ejecución con el que interactuan los usuarios finales y el espacio donde se ejecuta el código. Esto hace que sea mucho más fácil diseñar, desarrollar y mantener el runtime aislado de la etapa de construcción.

Al separar APIs en microservicios más pequeños con un propósito bien definido, significa que nuestra capacidad de comprender las particularidades de cada servicio aislado se vuelva mucho más simple. Las fronteras entre los servicios son completamente claras.

Esto nos ayuda a establecer modelos mentales más claros del sistema como un todo mientras se libera de la necesidad comprender las complejidades internas de cada sistema y servicio individual. Como resultado, la carga del desarrollo y  mantenimiento del sistema puede disminuirse significativamente. Las áreas donde debemos dirigir nuestra atención pueden estar más enfocadas con la confianza de que los límites entre los servicios que se utilizan son sólidos y bien definidos.

No hay necesidad de entender las caracteristicas del runtime de JavaScript en diferentes navegadores, así como los flujos de un API al mismo tiempo.

### No necesita ser un experto en todo

En los últimos años, la complejidad de las arquitecturas frontend ha explotado, a medida que las APIs del navegador han evolucionado y los estándares HTML y CSS han crecido. Sin embargo, es muy difícil para la misma persona ser un experto en rendimiento de JavaScript del lado del cliente y desarrollado del lado del servidor, en restricciones de consultas a base de datos, en optimización de caché y en operaciones de infraestructuras.

Cuando desacoplamos el backend y el frontend, hace posible que los desarrolladores se enfoquen en una sola área. Puede ejecutar su frontend localmente con un servidor de desarrollo que se actualiza automáticamente, que se comunica directamente con un API en producción, y hacer que el cambio entre la puesta en desarrollo o producción de las API sea tan simple como configurar una variable de entorno.

Y con microservicios muy pequeños y bien enfocados, la capa de servicio se vuelve mucho más reutilizable y generalmente aplicable que cuando tenemos una gran aplicación monolítica que cubre todas nuestras necesidades.

Esto significa que estamos viendo un ecosistema mucho más amplio de APIs prefabricadas para autenticación, comentarios, comercion electrónico, búsqueda, rendimensionamiento de imágenes, etcétera. Podemos utilizar herramientas de terceros para externalizar la complejidad y estar tranquilos sabiendo que esos proveedores tienen equipos altamente especializados enfocados exclusivamente en su espacio de problemas.

### Reducir las partes móviles en tiempo de ejecución

Cuanto más podamos preconstruir, más podremos implementar como markup prefabricado sin necesidad de ejecutar código dinámico en nuestros servidores durante el ciclo de petición, y estaremos mucho mejor. Ejecutar código cero siempre será más rápido que ejecutar algo de código. El código cero siempre será más seguro que incluso la cantidad más pequeña de código. Los activos que pueden servirse sin partes móviles siempre será mucho más escalable que incluso el programa dinámico más optimizado.

Menos partes móviles en tiempo de ejecución significa menos cosas que podrían fallar en un momento crítico. Y cuanto mayor distancia podamos poner entre nuestros usuarios y la complejidad inherente en nuestros sistemas, mayor será nuestra confianza en que experimentarán lo que pretendiamos. Frente a esa complejidad en el momento de la construcción, en un entorno que no afectará a los usuarios, nos permite exponer y resolver cualquier problema que podría presentarse sin peligro y sin un impacto negativo.

El único motivo para ejecutar código del lado del servidor en tiempo de petición debería ser no podemos evitarlo. Cuanto más podamos liberarnos de esto, mejor será la experiencia para nuestros usuarios, equipos de operaciones y nuestra propia capacidad de entender los proyectos en los que estamos trabajando.

## Costos

