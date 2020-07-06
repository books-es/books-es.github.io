---
layout: default
permalink: /jamstack/introduction
---
# Introducción

Hace unos pocos años atras, una gran ráfaga de avances han fortalecido la web, como plataforma de contenido y aplicación. Los navegadores son mucho más poderosos. JavaScript ha madurado. WebAssembly está en el orizonte. Ciertamente, se siente como el comienzo de un nuevo capítulo para la web. Probablemente lo sientas como cuando presenciaste la explosión de los nuevos _frameworks frontend_ y los servicios basados en API.

Si bien lo que es técnicamente posible en el navegador ha avanzado mucho, también lo han hecho las expectativas de inmediatez de resultados. Los videso deben reproducirse inmediatamente. Las aplicaciones de navegador deben ejecutarse más rápido que sus contrapartes en escritorio. Los usuarios han incrementado el uso del telefonia móvil e incrementado su impaciencia - todos estamos hartos de páginas lentas y expresamos nuestro enojo hacia ellas volviendo hacia atras -. (Google también parece estar perdiendo la paciencia, y ahora tiene en cuenta la rapidez del sitio en sus famosos algoritmos de rankeo.)

En general, este libro abarca enfoques nuevos y modernos para la construcción de sitios web que se ejecutan tan rápido como sea posible. Más concretamente, este libro le muestra como ejecutar cualquier propiedad web, desde sitios simples hasta aplicaciones complejas, sobre una _Content Delivery Network (CDN)_ global y sin un solo servidor web. Lo introduciremos al JAMstack: un nuevo enfoque poderoso para desplegar sitios y aplicaciones rápidos y altamente escalables que no requieren de la infraestructura frontend tradicional. Si siente que la entrega de sitios web deberia ser más sobre el arte de _markup_ y JavaScript que la administración y configuración de servidor, ha encontrado su libro.

Y si alguna vez se ha enfrentado con algún sistema o framework monolítico - luchando con hosting, implementando cambios, seguridad y escalado - ya comprende por qué el JAMstack se está volviendo tan popular. Es uno de esos cambios poco comunes en el paisaje que lleva a un aumento de productividad para los desarrolladores _y_ un gran aumento en el rendimiento para los usuarios. El JAMstack ayuda a hacer una web más segura, estable y eficiente, y a la vez más divertida para crear y desarrollar.

Bajo este nuevo enfoque, no hay "entorno de servidor" - al menos no en el sentido tradicional -. En su lugar, HTML es pre-renderizado en archivos estáticos, los sitios son entregados desde un CDN global y las tareas que antes se procesaban y gestionaban dentro del servidor, ahora se ejecutan a través de APIs y microservicios.

Sabemos que los desarroladores web experimentados podrian mirar algo nuevo con un poco de escepticismo. Ciertamente, han habido gran número de otras nuevas ideas sobre como construir la web antes. Por casi tres decadas, la comunidad de desarrolladores ha explorado formas de hacer que la web sea más fácil y rápidod e desarrollar, más poderosa, más eficiente y más segura.

A veces, sin embargo, el esfuerzo parece haber intercambiado un objetivo por otro. Wordpress, por ejemplo, se convirtió en una revolución para facilitar la creación de contenido para el autor - pero cualquiera que haya escalado un sitio Wordpress de alto tráfico sabe que también trae consigo un juego completo de nuevos desafios en rendimiento y seguriedad -. Cambiar la simplicidad de archivos HTML por contenido basado en base de datos significa enfrentar las amenzas reales que los sitios podrian enfrentarse a medida que se popularizan o son bulneradas cuando nadie las observa de cerca.

Y transformar dinámicamente el contenido HTML - cada vez que se requiere - toma algunos ciclos de computo. Para mitigar toda la sobrecarga, muchos _stacks_ web introdujeron esquemas de caché complejos e inteligentes en casi todos los niveles, desde la base de datos hacia arriba. Pero esta complejidad a menudo ha hecho que el procesos de desarrollo se sienta engorroso y frágil. Puede ser difícil realizar cualquier trabajo en un sitio cuando no puede ejecutarlo y probarlo en su propio computador (Confía en nosotros, lo sabemos).

Todos estos desafíos ha llevado a la comunidad de desarrolladores a comenzar a explorar el JAMstack como una refactorización moderna de la forma en que se desarrolla y entregan sitios web. Y como cualquier buena refactorización, encontrará que, al mismo tiempo, avanza y simplifica la pila.

Siendo nosotros mismos desarrolladores web, los autores de este libro están más entusiasmados con el JAMstack que con cualquier otra tendencia emergente desde hace bastante tiempo. Esto se debe a que resuelve de manera única todos los problemas comunes - experiencia de desarrollo, rendimiento y seguridad -, todos a la vez y todos sin que uno comprometa al otro. Para nosotros, se siente como el futuro lógico de la plataforma.

Simplemente tiene sentido.

El desarrollador Jonathan Prozzi lo dice mejor en Twitter: "My viaje de aprendizaje hacia #JAMstack ha revivido mi interes y pasión por la tecnología web." Creemos que el JAMstack puede hacer mucho para reavivar también su propio entusiasmo, y estamos ansiosos de darte la bienvenida a la creciente comunidad de parcticantes del JAMstack. Encontrarás que el desarrollo web se ha vuelto divertido y sin miedos de nuevo.

## El JAM en JAMstack

El JAMstack trae JavaScript, APIs y markup, los tres componentes núcleo usados para crear sitios que son rápidos y altamente dinámicos. Los sitios JAMstack estan bien preparados para satisfacer los requerimientos demandados de la web móvil de hoy (donde los tiempos de carga son urgentes y la calidad del ancho de banda nunca puede garantizarse).

Deberiamos hacer una pausa para decir lo que el JAMstack no es: no es una tecnología específica en si misma; no está manejado por una gran compañia; no hay ningún organizmo normalizador que lo controle o defina.

En cambio, el JAMstack es un movimiento, una colección comunitaria de flujos de trabajo y buenas prácticas que resultan en sitios web de alta velocidad sobre los que es un placer trabajar.

Mientras se sumerge, encontrará algunas pautas comunes asi como tambien muchas alternativas, incluyendo su elección del lenguaje. JavaScript se denomina específicamente como el lenguaje del navegador, pero podrá usar mucho o poco JavaScript, según lo requiera su proyecto. Muchos sitios JAMstack también usan Python, Go o Ruby para la creación de _templates_ y la lógica. Mucho software de código abierto ha surgido para ayudarle a crear sitios JAMstack y pasamos algo de tiempo en este libro repasando algunas de las alternativas más populares.

No todo sobre el JAMstack es una idea nueva, pero solo recientemente hemos tenido la tecnología requerida para hacer posible el enfoque, especialmente en el borde de la red y en el navegador. Esta primera sección del libro debería darle una comprensión funcional del JAMstack, por qué es importante un nuevo desarrollo y como razonar al respecto.

## Un flujo de trabajo para productividad y rendimiento

Por naturaleza, los sitios JAMstack son los siguientes:

- Flexible y globalmente distribuido para tráfico intenso.
- Centrado en un desarrollo amigable, flujo de trabajo basado en Git.
- Diseño modular, consumiendo otros servicios a través de APIs.
- Prefabricado y optimizado antes de ser entregado.

Es este último punto el que merece atención especial. Piense por un momento sobre el enfoque más común hoy en día para servir contenido web: por cada petición hecha a un sitio web, los datos se extraen de una base de datos, renderizando de nuevo un template, procesado en HTML, y finalmente enviado a través de la red (y tal vez incluso un oceano) al navegador que lo solicitó.

Cuando los servidores web construyen una página por cada petición, se comienza a acumular mucho trabajo en el lugar equivocado en el momento equivocado. Después de todo, una regla general para maximizar el rendimiento es realizar la menor cantidad de pasos posibles. ¿No debería producirce un nuevo HTML sólo cuando cambian los datos o el contenido, y no cada vez que se realiza una petición?

Así es exactamente como funciona el JAMstack. Aquí está lo que sucede bajo el flujo de trabajo del JAMstack:

1. La fuente del sitio es un repositorio alojado que almacena el contenido y el codigo como archivos editables.
2. Cada vez que se realiza un cambio, se lanza un proceso de construcción que pre-renderiza el sitio, creando el HTML final a partir de templates, contenido y datos.
3. Los activos preparados y renderizados se publican globalmente sobre un CDN, poniendolos a dispocisión de los usuarios finales tan cerca como sea posible.

Este enfoque elimina grandes cantidades de servidores y latencia de red. Dada la eficiencia y simplicidad de entregar contenido pre-renderizado directamente desde un CDN, no sorprende que sitios JAMstack tiendan a obtener los puntajes más altos en pruebas de velocidad como la de Google Light - el contenido distribuido globalmente no es completamente nuevo, pero la velocidad con la que puede actualizar los archivos del CDN directamente desde un repositorio _es_ nuevo -. No más las temidas demoras, esperando que la caché del CDN caduque - ahora podemos construir sitios altamente distribuidos en el borde de la red y eliminar la necesidad de cualquier tipo de servidores frontend para procesar cada solicitud -.

## Control de Versiones y Despliegues Atómicos

En JAMstack, es posible y común que el contenido del sitio, las publicaciones de blog y todo lo demás, viva en un repositorio Git junto al código y los templates. Esto significa que no se requiere una base de datos de contenido, haciendo que los sitios JAMstack sean más fáciles de configurar, correr, desplegar, ramificar y modificar.

Y en este mundo centrado en el control de versiones de JAMstack, cada despliegue del sitio es _atómico_, haciendo trivial el _rollback_ a cualquier estado, en cualquier momento, por cualquir motivo. Ya no son necesarios escenarios de entornos complejos, ya que la vista previa y los cambios de prueba emplean el sistema de ramificación integrado en el corazón de Git. Con un flujo de trabajo para realizar cambios más rápidos, simples y seguros, la mayoria de los sitios JAMstack están lejos de ser "estáticos" y como mucho se actualizan tan a menudo como sus contrapartes más complejas, a veces cientos de veces al día.

## Contribuyendo al JAMstack

Cuando se imagina un flujo de trabajo JAMstack, probablemente se imagine haciendo cambios de código en un editor y luego ejecutando un comando para construir el sitio y desplegarlo en producción. Un poco del desarrollo en JAMstack sucede exactamente de esta manera, especialmente al principio.

Pero para la mayoria de los sitios JAMstack, los contribuyentes no son sólo desarrolladores. Las nuevas actualizaciones del sitio también son lanzadas por los autores de contenido que utilizan un CMS , asi como por acciones automatizadas, tal como se esperaría de cualquier sitio web moderno.

En lugar de producirse localmente, el proceso de compilación ahora se ejecuta sobre un servidor alojado en la nube. Suba un cambio a GitHub (o cualquier otro servicio de repositorio) y se lanza automaticamente una nueva compilación en servidores de propósito general, enviando el resultado final directamente al CDN. Es una forma increiblemente adictiva de desarrollar, y le mostramos como hacerlo funcionar. Pero, ¿qué pasa con los autores que no son desarrolladores y podrían no familiarizarse con Git? El JAMstack ha generado una nueva generación inteligente de herramientas de autoria que se ven y funcionan como un Sistema de Gestión de Contenidos (_CMS Content Management System_) normal, pero que en realidad verifica los cambios en el control de versiones detrás de escenas. De esta manera, todos los participantes en el mismo flujo de trabajo, disfrutan de la seguridad, ramificación y rollbacks del software de control de versiones moderno - incluso si no son concientes de lo que está sucediendo -. Es una buena mejora sobre el contenido que requiere una base de datos que necesita administrar y versionar el mismo por separado.

También puede aportar cambios en el sitio de una tercera manera: mediante programación, a través de la automatización. Por ejemplo, puede ejecutar un script diario que incorpora los últimos articulos de prensa y menciones de Twitter en la página de inicio. O captar lo que sucede en un sitio JAMstack de _Smashing Magazine_: cada vez que un usuario comenta sobre un artículo, una simple función publica el comentario en el repositorio del sitio y lanza una nueva compilación (siempre que el comentario supere una cierta moderación).

¿Comienza a ver el poder de este flujo de trabajo? Los desarrolladores, los autores de contenido y los procesos automatizados están guardando una historia viva del sitio directamente en el mismo lugar - el repositorio - que actua como una fuente de verdad. Incluso si el sitio se actualiza cientos de veces o más, cada estado se conserva. Y, lo más importante, el sitio se mantiene rápido y _responsive_, dado que cada página se construye y optimiza antes de ser entregada.

## APIs para procesamiento y personalización

Sin embargo, se necesita más que HTML: las aplicaciones web necesitan realizar trabajo y tener estado. Tradicionalmente, se requerian servidores web para almacenar una sesión de usuario y permitir a la aplicacion hacer cosas como recordar artículos en un carrito de compras o mejorar la experiencia de pago.

En el JAMstack, estas experiencias personalizadas se realizan utilizando JavaScript para hacer llamadas a APIs que envian y reciven datos. La mayoria de las APIs utilizadas son servicios tercerizados. _Stripe_, por ejemplo, es un servicio popular para procesar pagos. _Algolia_ es un API popular para potenciar búsquedas. (Sus autores tienen un profundo amor por casi toda la tecnología, pero nunca volverían a manejar pagos de forma manual ni ejecutar clusteres de búsqueda en Apache Solr.)

Otras APIs pueden ser funciones personalizadas de forma exclusiva para cada aplicación. En lugar de un _framework_ monolítico y complejo que administra todo, los sitios pueden diseñarse al rededor de microservicios: funciones simples que ejecutan tareas específicas, ejecutándose una sola vez cuando se solicitan y luego terminan de forma limpia. Es un enfoque muy escalable sobre el que es fácil razonar.

Pero sin servidores para almacenar sesiones de usuario, ¿cómo hacemos para conectar todas estas llamadas discretas a la API? ¿Cómo hacemos para manejar autenticación e identificación? Para gestionar cuentas de usuario, una aplicación JAMstack a menudo creará un token ID de seguridad almacenado en el navegador. (Este tipo de token se denomina _JavaScript Web Token_, o _JWT_). Luego, se pasa la identidad con cada llamada a la API para que los servicios reconozcan al usuario. Cubriremos este tema con mayor detalle más adelante, pero lo introduciomos aquí para ayudarlo a entender el poder de la plataforma. Los sitios JAMstack pueden hacer mucho más que servir contenido simple, y muchas son aplicaciones costosas con todas las caracteristicas que esperaría, como _ecommerce_ (comercio electrónico), _membership_ (membresía) y _rich personalization_ (personalización).

Los sitios estáticos pueden ser, pues, estáticos, pero encontrará que los sitios JAMstack son cualquier cosa menos estáticos. De hecho, encontrará markup pre-renderizado para _UI_ (_User Interface_ - interfaz de usuario -) web combinado con APIs y microservicios para ser una de las plataformas más rápidas y eficientes disponibles para aplicaciones web avanzadas.

## Produciendo todo junto: Un caso de estudio de _Smashing Magazine_

_Smashing Magazine_ ha sido uno presencia constante en el desarrollo web por más de una decada, brindando un sitio web de gran popularidad y publicando contenido de alta calidad sobre temas como desarrollo frontend, diseño, experiencia de usuario y rendimiento web.

A finales de 2017, _Smashing Magazine_ reescribió y rediseñó completamente su sitio para cambiar de un sistema basado en varias aplicaciones monolíticas tradicionales a el JAMstack. La sección final del libro muestra como resolver desafíos como ecommerce, gestión de contenido, comentarios, subscripciones y el trabajo con un proyecto JAMstack a escala.

## ¿Listo? Hora de comenzar con nuestra sesión JAM

La mejor forma de aprender el JAMstack es sumergiendose en él. El JAMstack utiliza habilidades que ya posee, pero aplica tus convenciones sobre cómo se ejecutan los sitios web y qué es posible sin servidores. Le sugerimos que traiga la mente abierta y el mismo sentido de aventura que lo llevó a explorar el desarrollo web la primera vez. Nunca ha habido un mejor momento para ser un desarrollador web - liberarnos de la administración de sitios web está trayendo de vuelta el foco a la creación de contenido e interfaces que lo hacen atrayentes -.
