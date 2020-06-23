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

