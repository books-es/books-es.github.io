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

### **Mejor comprensión y agilidad mental**

Con el renderizado del lado del servidor, todas las capas del stack siempre están involucradas en cualquiera de las peticiones que un usuario hace a un sitio o aplicación. Para construir software eficiente y seguro, los desarrolladores deben comprender a fondo todas las capas por las que flujen de peticiones, incluyendo los complementos de terceros, los controladores de base de datos y los detalles de implementación de los lenguajes de programación.

Al desacoplar completamente la capa de construcción del runtime del sistema y editar partes prefabricadas, se construye un muro irrompible entre el entorno en tiempo de ejecución con el que interactuan los usuarios finales y el espacio donde se ejecuta el código. Esto hace que sea mucho más fácil diseñar, desarrollar y mantener el runtime aislado de la etapa de construcción.

Al separar APIs en microservicios más pequeños con un propósito bien definido, significa que nuestra capacidad de comprender las particularidades de cada servicio aislado se vuelva mucho más simple. Las fronteras entre los servicios son completamente claras.

Esto nos ayuda a establecer modelos mentales más claros del sistema como un todo mientras se libera de la necesidad comprender las complejidades internas de cada sistema y servicio individual. Como resultado, la carga del desarrollo y  mantenimiento del sistema puede disminuirse significativamente. Las áreas donde debemos dirigir nuestra atención pueden estar más enfocadas con la confianza de que los límites entre los servicios que se utilizan son sólidos y bien definidos.

No hay necesidad de entender las caracteristicas del runtime de JavaScript en diferentes navegadores, así como los flujos de un API al mismo tiempo.

### **No necesita ser un experto en todo**

En los últimos años, la complejidad de las arquitecturas frontend ha explotado, a medida que las APIs del navegador han evolucionado y los estándares HTML y CSS han crecido. Sin embargo, es muy difícil para la misma persona ser un experto en rendimiento de JavaScript del lado del cliente y desarrollado del lado del servidor, en restricciones de consultas a base de datos, en optimización de caché y en operaciones de infraestructuras.

Cuando desacoplamos el backend y el frontend, hace posible que los desarrolladores se enfoquen en una sola área. Puede ejecutar su frontend localmente con un servidor de desarrollo que se actualiza automáticamente, que se comunica directamente con un API en producción, y hacer que el cambio entre la puesta en desarrollo o producción de las API sea tan simple como configurar una variable de entorno.

Y con microservicios muy pequeños y bien enfocados, la capa de servicio se vuelve mucho más reutilizable y generalmente aplicable que cuando tenemos una gran aplicación monolítica que cubre todas nuestras necesidades.

Esto significa que estamos viendo un ecosistema mucho más amplio de APIs prefabricadas para autenticación, comentarios, comercion electrónico, búsqueda, rendimensionamiento de imágenes, etcétera. Podemos utilizar herramientas de terceros para externalizar la complejidad y estar tranquilos sabiendo que esos proveedores tienen equipos altamente especializados enfocados exclusivamente en su espacio de problemas.

### **Reducir las partes móviles en tiempo de ejecución**

Cuanto más podamos preconstruir, más podremos implementar como markup prefabricado sin necesidad de ejecutar código dinámico en nuestros servidores durante el ciclo de petición, y estaremos mucho mejor. Ejecutar código cero siempre será más rápido que ejecutar algo de código. El código cero siempre será más seguro que incluso la cantidad más pequeña de código. Los activos que pueden servirse sin partes móviles siempre será mucho más escalable que incluso el programa dinámico más optimizado.

Menos partes móviles en tiempo de ejecución significa menos cosas que podrían fallar en un momento crítico. Y cuanto mayor distancia podamos poner entre nuestros usuarios y la complejidad inherente en nuestros sistemas, mayor será nuestra confianza en que experimentarán lo que pretendiamos. Frente a esa complejidad en el momento de la construcción, en un entorno que no afectará a los usuarios, nos permite exponer y resolver cualquier problema que podría presentarse sin peligro y sin un impacto negativo.

El único motivo para ejecutar código del lado del servidor en tiempo de petición debería ser no podemos evitarlo. Cuanto más podamos liberarnos de esto, mejor será la experiencia para nuestros usuarios, equipos de operaciones y nuestra propia capacidad de entender los proyectos en los que estamos trabajando.

## Costos

Hay una variedad de costos asociados con el diseño, desarrollo y operación de aplicaciones y sitios web, y están indudablemente influenciados por el stack que escogimos. Aunque los costos financieros a menudo resultan más obvios, deberíamos considerar los costos para la experiencia, creatividad e innovación del desarrollador.

### **Costos financieros**

Cualquier proyecto de desarrollo web de escala significativa probablemente incluirá un ejercicio para estimar los niveles de tráfico previstos u objetivo y de un plan para la infraestructura de alojamiento requerida para servir este tráfico. Este ejercicio de planificación de capacidad es un paso importante para determinar cuanto costará operar el sitio. Es difícil de estimar cuanto tráfico recibirá un sitio antes de tiempo, por lo que es una práctica común planificar la capacidad suficiente para satisfacer los niveles de tráfico más allá incluso de las estimaciones más altas.

Con las arquitecturas tradicionales, en las que las peticiones de página pueden requerir actividad en todos los niveles del stack, esa capacidad deberá extenderse a través de cada nivel, lo que a menudo resulta en servidores múltiples y altamente específicos de base de datos, servidores de aplicación, servidores de caché, balanceadores de carga, pilas de mensajes y más. Cada una de estas piezas de infraestructura tiene un costo financiero asociado. Anteriormente, esto podría haber incluido los costos de las máquinas físicas, pero hoy estas máquinas a menudo estan virtualizadas. Ya sea física o virtual, los costos financieros de estas piezas de infraestructura pueden aumentar con las licencias de software, costos de máquina, mano de obra, etcétera.

Además, la mayoria de los proyectos de desarrollo web tendrán más de un entorno, lo que significa que mucha de esa infraestructura necesitará duplicarse para proporcionar entornos adecuados de puesta en marcha, pruebas y desarrollo, además del entorno de producción.

Los sitios JAMstack se benefician de una arquitectura técnica mucho más simple. La carga de escalar un sitio JAMstack para satisfacer grandes picos de tráfico generalmente recae en el Content Delivery Network (CDN) que da servicio a los activos del sitios. Incluso si no emplearamos los servicios de un CDN, nuestro entorno de alojamiento aún se simplificaría drásticamente en comparación con el escenario mencionado anteriormente. Cuando el proceso de acceder al contenido y los datos y luego rellenar los templates de página se desacopla de las peticiones de estas páginas, significa que las demandas de estas partes de la infraestructur no influyen en el cantidad de visitantes al sitio. Grandes partes de la infraestructura tradicional no necesitan escalarse o quizás no tienen la necesidad de existir.

El JAMstack reduce _drásticamente_ los costos financieros de construcción y mantenimiento de aplicaciones y sitios web.

### **Eficiencia del Equipo**

El tamaño y la complejidad de la arquitectura de un proyecto es directamente proporcional a la candidad de personas y el rango de habilidades (_skills_) requiridas para operarlo. Una arquitectura simplificada con menos servidores requieren menos personas y mucho menos especialización.

Las tareas complejas de DevOps se eliminan en gran medida de los projectos con entornos mucho más simples. Lo que antes eran procedimientos largos, costosos y críticos - como proporcionar nuevos entornos y configurarlos para replicarse fielmente - son reemplazados por el mantenimiento los entornos de desarrollo locales (requeridos con un enfoque tradicional, de todos modos) y el pipeline de despliegue para un servicio de hosting estático productivo o CDN.

Este cambio coloca mucho más poder y control en manos de los desarrolladores, quienes poseen un conjunto cada vez más extenso de habilidades de desarrollo web. Esto reduce los costos de personal en un projecto de desarrollo web (mediante una redicida demanda de algunas de las habilidades más exóticas e historicamente costosas) e incrementa la productividad de los desarrolladores empleados. Al tener conocimientos de una gran parte del stack y menos límites disciplinarios que cruzar, el proceso*** mental del proyecto de cada desarrollador puede ser más completo y, como resultado, cada individuo puede tener mucha más confianza en sus acciones y ser más productivo.

Esto también reduce los límites para la innovación y la iteración.


### **El Precio de la Innovación**

Cuando hacemos cambios en un sitio, queremos estar seguros de los efectos que nuestros cambios podrían tener en el resto del sistema.

El JAMstack toma las ventajas de las APIs y un arquitectura de servicios bien definida con capas de interfaz establecidas, moviendonos a un sistema que adopta el mantra de "piezas pequeñas, unidas libremente" (_"small pieces, loosely joined"_). Este modelo de acoplamiento libre entre diferentes partes de la arquitectura técnica de un sitio reduce las barreras de cambiar con el tiempo. Esto puede ser liberador cuando se trata de tomar desiciones técnicas de diseño porque es menos probable que estemos bloqueados por un proveedor o servicio tercerizado, dado que tenemos límites y responsabilidades bien definidasen todo el sitio.

Esto también otorga a los equipos de desarrollo la libertad para refactorizar y desarrollar las partes particulares del sitio que controlan, seguros sabiendo de que mientras respeten la estructura de las interfaces entre las diferentes partes del sitio, no comprometerán el proyecto más grande.



<!-- ## Escalado -->
<!-- ## Rendimiento -->
<!-- ## Seguridad -->
<!-- ## Por el Desarrollador; Por el Proyecto; Por la Victoria -->
