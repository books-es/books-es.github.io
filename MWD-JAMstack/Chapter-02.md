---
layout: page
permalink: /jamstack/chapter-02
---

## **Capítulo #2**

# Introducción al JAMstack

## ¿Qué hay en el Nombre?

El JAMstack en su núcleo simplemente es un intenti de dar un nombre a un conjunto de pŕacticas arquitectónicas extendamente utilizadas. Nos dá una palabra para comunicar una amplia gama de decisiones arquitectónicas.

Surgió en conversaciones entre personas involucradas en las comunidades alrededor de generadores de sitios estáticos, frameworks de aplicaciones de una sóla página ( _SPA - Single-Page Application -_ ), herramientas de compilación y servicios API, ya que nos dimos cuenta de gran parte de la innovación en cada una de estas categorías estaba conectada.

Toda una comunidad creció alrededor de la primera generación de generadores de sitios estáticos como Jekyll, Middleman, Metalsmith, Cactus y Roots. Jekyll encontró fama como el generador de sitios estáticos soportado nativamente por _GitHub Page_, y otras fueron desarrollados internamente por agencias o _startups_ que las convirtieron en parte esencial de su pila de sitios web. Las herramientas recuperaron la sensación de simplicidad y control de los complejos Sistemas de Gestión de Contenido ( _CMSs - Content Management Systems -_ ) basados en bases de datos que reemplazaron.

Al mismo tiempo, frameworks SPA como Vue y React comenzaron un proceso de desacoplamiento del frontend y el backend, introduciendo herramientas de compilación como Grunt, Gulp y, posteriormente, Webpacl y Babel, que propagaron la idea de un frontend independiente con su propia fuente de compilación y proceso de desarrollo. Esto trajo una arquitectura de software apropiada para el flujo de trabajo frontend y permite a los desarrolladores frontend iterar mucho más rápido en la interfaz de usuario (_UI_) y la capa de interacción.

Cuando estos enfoques para crear aplicaciones y sitios web se cruzan, un nuevo ecosistema de API comienza a emerger. Herramientas como Stripe, Disqus y Algolia realizan pagos, comentarios y busquedas directamente desde el frontend a través de servicios basados en API.

Empezó a aparecer un gran conjunto de términos para las diferentes piezas de estas nuevas arquitecturas de software: aplicaciones web progresivas, sitios estáticos, _frontend build pipelines_, aplicaciones de una sola página, proyectos web desacoplados y funciones _serverless_. Sin embargo, ninguno de ellos capturó realmente el movimiento hacia una nueva arquitectura que abarque sitios web de gestión de contenido, aplicaciones web y todos los productos híbridos interesantes entre ambos.

El JAMstack pone un nombre a todo esto.

En el entorno de desarrollo web actual, el _stack_ ha subido un nivel. Antes, soliamos hablar sobre el sistema operativo, la base de datos y el servidor web cuando describiamos nuestro stack (tal como el stack LAMP o el stack MEAN), pero con la aparición de nuevas prácticas, las restricciones arquitectónicas reales se convirtieron en las siguientes:

- **J**avaScript en el navegador como _runtime_.
- **A**PIs HTTP reutilizables en lugar de bases de datos específicas de la aplicación.
- **M**arkup (marcado) precompilado como mecanismo de entrega.

Estos componentes convierten el JAM en JAMstack. Hechemos un vistazo a cada uno de estos elementos y cómo ha evolucionado cada uno para habilitar esta nueva arquitectura.

## JavaScript

En Mayo de 1995, cuando Brendan Eich escribió el primer prototipo de JavaScript (originalmente llamado Mocha) durante una famosa juerga de codificación de 10 días, pocos podrían haber imaginado que algún día sería el lenguaje runtime más importante para la pila de aplicaciones más amplia de la historia.

Hoy, JavaScript está casi omnipresente en los navegadores. Ha crecido desde la creación inicial de Eich de un pequeño lenguaje basado en esquemas con una sintaxis similar a C, en el lenguaje interpretado de alto nivel más óptimo en el mundo. Incluye constructores avanzados para acciones asíncronas, clases flexibles y sistema modular, constructores sintácticos elegantes como asignación desestructurada y una sintaxis de objeto que se ha convertido en el formato de intercambio de datos más utilizado actualmente en la web y más allá (JSON).

Más que un lenguaje de programación independiente, JavaScript se ha convertido en el objetivo de compilación para _transpilers_ (transpiladores), que traducen variaciones de JavaScript en JavaScript vainilla ejecutable en todos los navegadores modernos, y _compilers_ (compiladores) para lenguajes nuevos o existentes como Elm, ReasonML, ClojureScript y TypeScript.

De muchas maneras JavaScript es ahora el runtime universal que Sun Microsystems soñó cuando construyó la _Java Virtual Machine_ ( _JVM_ -Máquina Virtual Java- ).

Esta "Máquina Virtual" para la web es la capa en tiempo de ejecución para el JAMstack. Es la capa a la que apuntamos cuando necesitamos crear flujos dinámicos que van por encima de la capa de aplicación y de contenido, ya sea si estamos escribiendo aplicaciones completas o sólo agregando funcionalidad adicional a un sitio basado en contenido. JavaScript es para el JAMstack lo que C fué para Unix, ya que los navegadores se han convertido en el sistema operativo de la web.

## APIs

La _World Wide Web_ es básicamente una capa de _UI_ ( _User Interface_ -interfaz de usuario- ) construida sobre un protocolo _stateless_ (sin estado) denominado _HyperText Transfer Protocol (HTTP)_. El concepto más fundamental de la web es el _Universal Resource Locator (URL)_.

Como seres humanos, estamos acostumbrados a poder escribir una URL en un navegador o seguir un enlace de un sitio web y terminar en otro sitio web. Cuando construimos sitios web y aplicaciones, siempre debemos pensar cuidadosamente sobre nuestra arquitectura y estructura URL. Pero las URLs también dan a los programas que se ejecutan en un navegador el poder de alcanzar cualquier recurso programático que haya estado expuesto en la web.

Las APIs web modernas nacieron oficialmente con la disertación de Roy Fielding, _"Architectural Styles and the Desing of Network-Based Software Architectures"_ en el año 2000. Es un trabajo seminal que definió la _Representational State Transfer (REST)_ como una arquitectura reconocible y escalable para servicios expuestos a través de HTTP.

Las primeras APIs web estaba destinadas a ser consumidas desde aplicaciones del lado del servidor. Sin emplear estrategías como proxt a través de un servidor intermediario o utilizando complementos como Flash o Java Applets (ugh!), no habia forma de que un programa que se ejecuta en un navegador estándar se comunique con cualquier API web fuera de su propio dominio.

A medida que JavaScript creció a partir de un lenguaje de _scripting_ destinado principalmente a realizar mejoras progresivas menores en la parte superior de los sitios web renderizados del lado del servidor en un entorno en tiempo de ejecución completo, surgieron nuevos estándares como _CORS_, _WebSocket_ y _PostMesagge_. Junto con otros nuevos estándares como _OAuth2_ y _JSON Web Token_ (_JWT_) para autorización y autenticación stateless, cualquier API web moderna repentinamente se volvió accesible desde cualquier cliente JavaScript que se ejecute en un navegador.

Sólo recientemente comenzamos a entender los efectos de esta enorme innovación. Es uno de los impulsores del JAMstack, asi como uno de los estilos arquitectónicos más relevantes para sitios web y aplicaciones. Repentinamente, toda la web se ha copnvertido en algo como un sistema operativo gigantesco. Ahora estamos viendo APIs expuestas para cualquier cosa - desde pagos o suscripciones sobre modelos de _machine learning_ avanzados en entornos cloud a gran escala, hasta servicios que afectan directamente el mundo físico como servicios de envio o viajes compartidos, y casi cualquier cosa que puedas imaginarte -. Piénselo, y probablemente haya una API para eso.

## _Markup_

HTML es el núcleo de la web. El _HyperText Markup Language_, conocido e interpretado por todos los navegadores, define como debería estructurarse y distribuirse el contenido. Define que recursos y activos deben cargarse para un sitio y presenta un _Document Object Model (DOM)_ que puede ser analizado, presentado y procesado por cualquier cosa, desde navegadores web estándar sobre lectores de pantalla, hasta rastreadores de motores de búsqueda, dispositivos controlados por voz y _smart watches_ (relojes inteligentes).

En los primeros días de la web, un sitio web era simplemente un directorio con archivos HTML expuestos por HTTP por un servidor web. A medida que la web evolucionó, comenzamos a movernos a un modelo en el que un programa en ejecución construiría en el servidor el HTML sobre la marcha para cada visitante, normalmente luego de consultar una base de datos.

Este era un proceso mucho más lento y complejo que servir activos estáticos, pero también era la única forma viable de trabajar sobre el hecho de que los navegadores eran simples visores de documentos en ese momento. En respuesta a cualquier interacción de usuario, ya sea un click o envio de un formulario, requería que una página HTML completamente nueva se ensamblase en el servidor. Esto era cierto tanto si creaba una función de comentarios para un blog, un almacén de ecommerce o cualquier tipo de aplicación web. Debido a esta arquitectura centrada en documentos, las experiencias web a menudo se sentían menos receptivas que las aplicaciones de escritorio.

Por supuesto, esto fue antes del surgimiento de JavaScript y la aparición de APIs web de dominio, disponibles desde el navegador. Hoy, las restricciones que conducían a arquitecturas heredadas de la web han desaparecido.

### Markup Precompilado

El markup en el JAMstack se entrega por un modelo diferente. No se entrega desde servidores web frontend tradicionales encargados de crear páginas en tiempo de ejecución.

En cambio, el enfoque JAMstack construye previamente todo el markup primero y lo entrega directamente al navegador desde un CDN. Este proceso generalmente involucra una herramienta de compilación (a veces un generador de sitios estáticos como Hugo o Gatsby; otras, una herramienta de compilación frontend como Webpack, Brunch o Parcel), donde el contenido y los _templates_ (plantillas) se combinana en HTML, los archivos fuente son transpilados o compilados en JavaScript, y los CSS se ejecutan por medio de preprocesadores o postprocesadores.

Esto crea un desacoplamiento estricto entre el frontend y cualquier API del backend. Nos permite eliminar un gran conjunto de piezas móviles de la infraestructura y el _live system_, lo que hace que sea mucho más fácil considerar el frontend y las APIs individuales involucradas de forma aislada. Cuanto más podamos _hornear, en lugar de freir (bake, not fry)_ la capa de contenido de nuestro sitio, las implementaciones, el escalado y la seguridad se volverán más simples, y mejor será el rendimiento y la experiencia de usuario final.

Esta arquitectura desacoplada es similar en muchas formas a la arquitectura de aplicaciones móviles. Cuando el _iPhone_ introdujo las aplicaciones móviles (originalmente porque las aplicaciones web tradicionales no tenian el rendimiento suficiente), simplemente no era una consideración construir un modelo en el que se recargaría la UI completa desde un servidor cada vez que el usuario realice alguna accion. En cambio, IOS introdujo un modelo en el que cada aplicación podría distribuirse a los usuarios como un paquete de aplicación con una UI declarativa, incluyendo cualquier activo necesario para comunicarse con APIs web basadas en JSON y XML desde alli.

El enfoque JAMstack es similar. El frontend es la aplicación. Es distribuido directamente al navegador desde un CDN en una red globalmente distribuida. Mediante técnicas como _service workers_, incluso podemos instalar nuestro frontend directamente en los dispositivos de los usuarios finales luego de su primera visita.

#### Microservicios y funciones serverless

Otra cosa sucedió en tándem con el comienzo de la separación de las capas de frontend y API: las arquitecturas basadas en microservicios. Los equipos de backend comenzaron a alejarse de una gran API monolítica hacia servicios mucho más pequeños con responsabilidades más definidas. Este movimiento hacia microservicios ha culminado en _Lambda_ de _Amazon Web Services (AWS)_ y el concepto de funciones _cloud_ (en la nube), por medio de funciones simples que hacen una sola cosa ynada más puede exponerse como _endpoints_ de API de microweb.

Esto ha desencadenado un importante cambio arquitectónico. Antes, una _SPA_ típica tenía solo una API mediante la cual se comunicaba. Ahora, cada SPA se comunicará normalmente con varias APIs o microservicios diferentes. A medida que la superficie de cada una de estas APIs se reduce, y estándares como OAuth y JWT permiten a los desarrolladores vincularlos, las API individuales tienden a volverse más y más reutilizables.

La cantidad de APIs completamente administradas y reutilizables disponibles como servicios administrados sólo se mantendrá en crecimiento. Ahora, comenzamos a ver los primeros almacenes de aplicaciones funcionales, ayudando a levantar la carga del mantenimiento involucrado en la ejecución de aplicaciones modernas.

## Tipos de Proyectos JAMstack

Todos los equipos de desarrollo han desplegado una gran variedad de proyectos impulsados por JAMstack, desde sitios más pequeños y _landing pages_ hasta aplicaciones web complejas, y hasta propiedades web de grandes empresas con cientos de páginas.

### Contenido HTML

Los sitios JAMstack más simples son sitios estáticos puros: un directorio con HTML y elementos de soporte (archivos JavaScript, _Cascading Style Sheets_ [_CSS_], imágenes, fuentes) y partes inmóviles; archivos en texto plano que pueden editarse directamente en un editor a elección y mantenido bajo un control de versiones.

Sin embargo, tan pronto como haya mucho más que páginas únicas, tiene sentido extraer elementos como navegadores, cabeceras, pies de página y elementos repetidos en sus propios templates y parciales. Para cualquier cosa, al menos el JavaScript más simple, puede extraer módulos desde npm y usar las características de ES6 más modernas. Después de tener una _stylesheet_ un poco más compleja, puede incorporar de antemano un proveedor automático cuando lo necesite, soporte para variables CSS en los navegadores y anidar reglas.

Un conjunto de herramientas de compilación adecuado resuelve todos estos problemas mientras mantiene la simplicidad básica de un sitio estático. Todo vive en archivos de texto en un repositorio Git, bajo control de versiones y puede manipularse con todas nuestras herramientas de desarrollo centradas en texto. Con un flujo de trabajo _continuos deployment (CD)_ moderno, plublicar es tan simple como un _push_ a Git.

### Contenido desde un CMS

Durante la mayor parte de la vida de la web, hemos dado por sentado que nuestro CMS determina nuestra plataforma de desarrollo completa y acopla el renderizado, la edición de contenido y nuestro ecosistema de plugins estrechamente ligados. Pero la llegada de _headleess CMSs_ - ya sean impulsados por API o basados en Git - significa que podemos pensar en las UIs de edición de contenido completamente separadas de los frameworks y herramientas que usamos para crear y entregar nuestos sitios web.

La gestión de contenido también puede manejarse por medio de herramientas de edición de contenido centradas en Git como Netlify CMS, Prose, Forestry o CloudCannon. O bien, puede usar la herramienta de compilación para hacer que el primer paso de la compilación sea una sincronización de contenido con una API de contenido externa como Contentful, Prismic o DatoCMS.

### Aplicaciones Web

A principios de los años 2000, Microsoft agregó discretamente una API propia para Internet Explorer denominada _XMLHttpRequest (XHR)_. Antes de que esto sucediera, la única forma en la que un navegador podía inizializar la carga de una página era navegando a una nueva URL que cargaría una página web completamente nueva desde cero.

Después de años de XHR pasando más o menos desapercibido, Jesse James Garrett de la agencia Adaptive Path escribió un artículo en Febrero de 2005 que cambiaría la web: "Ajax: Un Nuevo Enfoque para Aplicaciones Web." En el artículo, Jesse acuña el término "Ajax" y dió a los desarrolladores web una forma de comunicarse sobre los nuevos patrones que aparecieron después de que XHR se usara para obtener datos  de servidores directamente desde JavaScript - similar a cómo la terminología JAMstack ahora nos habla sobre una nueva arquitectura bajo el estandarte de una nomenclatura unificadora -.

En el mundo actual de aplicaciones web frontend por todos lados, es difícil asimilar cuán revolucionario fue pasar de confiar en actualizar páginas completas como la única forma de interactuar verdaderamente con una aplicación web hasta, de repente, tener la opción de iniciar solicitudes HTTP directamente desde JavaScript. La constatación de que las consultas Ajax podrían usarse para construir aplicaciones web sin la dependencia de cargar páginas completas cambió la forma en que pensamos la web y también impulsó el mercado de navegadore a comenzar a reinventarse fundamentalmente después de años de estancamiento basado en ES6.

Inicialmente, Ajax se usó principalmente con principios como la mejora progresiva en la que una aplicación web se construiría de forma tal que todo el estado se manejase en el servidor a través de transiciones de página completa, pero donde los navegadores con soporte JavaScript podrían mejorar las interacciones a través de actualizaciones parciales de la página.

#### Separando el frontend del backend

Los verdaderos SPA surgieron cunado el rendimiento de JavaScript se volvió lo suficientemente bueno como para que pudieramos invertir el modelo existente y manejar todas las transiciones de página directamente en el navegador sin ningún viaje de ida y vuelta dentro del servidor. La primera generación de SPAs se construyó típicamente desarrollando un frontend dentro de grandes aplicaciones monolíticas impulsadas por bases de datos, Era común trabajar sobre stacks con frontends Ember dentro de aplicaciones Rails, utilizando la canalización de activos de Rails para agrupación y minificación (incluso si este flujo era, en general, doloroso de trabajar). 

Las SPAs modernas comenzaron a separar completamente el frontend y el backend, y toda una nueva generación de herramientas de compilación frontend surgieron para que trabajar con el frontend de manera aislada sea realmente divertido - luego de la instalación inicial y los obstáculos de configuración hayan sido superados, por supuesto -. Webpack es la herramienta de compilación más utilizada por las SPAs de hoy, ofreciendo un flujo que soporta transpilación JavaScript y CSS, postprocesamiento, paquetes integrados y división de código, así como actualización del navegador en tiempo real en cada guardado.

### Propiedades Web Extensas

Cuando se trata de markup precompilado, existen restricciones obvias en términos del número de páginas que es práctico generar. El ciclo de construcción e implementación simplemente se vuelve demasiado largo para permitir un flujo de trabajo viable. Si necesita publicar una historia antes que un competidor, pero tiene un ciclo de construcción e implementación de una hora entre el momento en que presiona publicar en su CMS y el momento en que la historia cobra visibilidad, tu stack te ha decepcionado.

Para algunos tipos de publicaciones, esta es una restricción tan extricta que incluso un ciclo de construcción e implementación de unos 10 minutos trabajaría mejor en otro stack.

Sin embargo, las herramientas de compilación se han vuelto sorprendentemente rápidas y el límite de lo que pueden alcanzarse en un ciclo de construcción se reduce. Un generador de sitios estáticos como Hugo puede procesar cientos de páginas por segundo y proporcionar ciclos de construcción mucho más rápidos. Estas impresionantes mejoras en estas herramientas, junto con técnicas emergentes para abordar sitios muy grandes dividiendo cuidadosamente la generación de sitios en ramas separadas tal que solo un pequeño subconjunto de los sitios se reconstruye en cada actualización, se combinan para crear grandes resultados.

Al final, el _trade-off_ necesitará basarse en qué es más importante: el rendimiento, el tiempo de actividad y la escalabilidad, o la reducción del ciclo de publicación.

Para la mayoria de los sitios basados en contenido, siempre que se pueda programar una implementación para que se active en un momento determinado, es probable que la capacidad de ejecutar un ciclo de construcción en menos de 10 minutos no sea realmente importante. A menos que su sitio sea verdaderamente gigantesco (páginas contadas en millones en lugar de cientos), un enfoque JAMstack podría ser una opción más viable de lo que alguna vez hubiera pensado.

### Experiencias Híbidas

Es común que una compañía requiera una variedad de experiencias web: un sitio web principal, un blog, un sitio de documentación, una aplicación web, una tienda de ecommerce, etcétera. Mantener una apariencia común en todas estas aplicaciónes utilizadas solia ser extremadamente desafiante para los equipos de desarrollo. Esto es porque en las arquitecturas tradicionales, el frontend de cada aplicación está estrechamente acoplado al backend utilizado para generarlo en el servidor.

El JAMstack resuelve esto de una forma elegante y altamente escalable. Podemos construir un frontend desacoplado que abarque todas las aplicaciónes. Verá esto en acción más adelante cuando presentemos el caso de estudio de _Smashing Magazine_.

## Resumen

La lista de proyectos que no serían adecuados para una arquitectura JAMstack se está reduciendo continuamente. Las mejoras en las herramientas y la automatización, los flujos de trabajo, las mejores prácticas y el ecosistema en su conjunto está creando más posibilidades de lo que puede lograr un sitio JAMstack.

Ahora que hemos cubierto qué es el JAMstack y si es adecuado para su proyecto, es tiempo de hablar sobre lo que puede proporcionar el enfoque JAMstack.