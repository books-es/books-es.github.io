---
layout: page
permalink: /jamstack/chapter-01
---

## **Capítulo #1**

# Los Desafíos del Desarrollo Web Moderno

En tecnología, cualquier tipo de cambio - incluso uno que es gradual o comienza con proyectos más pequeños - no se hará a la ligera. Estos cambios implican la evaluación de inversiones pasadas en infraestructura, adquisición de nuevo conocimiento y consideración seria de las retribuciones de características.

Entonces, antes de que podamos convencerte de que hay un valor en considerar el JAMstack como otro enfoque de desarrollo web, pasaremos algún tiempo investigando los enfoques más abarcativos para el desarrollo web de hoy y los desafíos que presentan. En pocas palabras, observemos primero el riesgo de golpearse con el _status quo_ antes de sumergirse en el JAMstack y los beneficios de hacer un cambio.

## Los Inconvenientes de las Arquitecturas Monolíticas

Los sitios web han sido impulsados tradicionalmente por arquitecturas monolíticas, con el frontend de la aplicación estrechamente acoplado al _backend_.

Las aplicaciones monolíticas tienen dogmatismos sobre cómo se realizan las tareas que tienen lugar en el servidor. Las opiniones que imponen han conformado como se aborda el desarrollo web y el entorno en que trabajamos ahora.

Popular y confiable como la forma _de facto_ de construir la web, estas herramientas han tenido un profundo impacto no sólo en cómo funcionarán los sitios, sino también en cúan eficiente pueden desarrollarse e incluso sobre la mentalidad de los desarrolladores.

El bloqueo creado por esto es tangible. Estas aplicaciones dictan el enfoque de muchas facetas de un proyecto de desarrollo web de formas que no siempre resultan atractivas para la comunidad de desarrollo web en general. La selección de una aplicación monolítica sobre otra, a menudo se basado en la duración de sus características. Una tendencia a seleccionar herramientas basado en que es la mejor en su clase, o la más popular en el mercado, a menudo puede pasar por alto una consideración fundamental: ¿Qué necesita realmente este proyecto?

Entonces, ¿Esto le suena familiar? ¿Ha trabajado en proyectos donde lo que debería ser simple resulta bastante complejo? ¿Quzás esta complejidad se acepta porque el proyecto es un sitio de alto perfil o está siendo trabajado por un equipo grande?

¿Encuentra realmente necesaria esta complejidad?

Al hacernos regularmente estas preguntas, hemos llegado a creer que hay un nivel de sobreingeniería presente en el desarrollo web de hoy. Esta sobreingeniería impide el uso de procesos, tecnologías y arquitecturas efectivas y comprobadas.

¿Podemos tomar medidas para mejorar esta situación? ¿Podemos atacar la flexibilidad limitada, las cuestiones de rendimiento, los desafíos de escalado y los problemas de seguridad impuestos por la arquitectura heredada?

### **Flexibilidad Limitada**

La libertad de hacer un buen trabajo - para diseñar las experiencias exactas que queremos para nuestros usuarios - está comprometida regularmente por aplicaciones monolíticas complejas.

En los últimos años, ha habido una creciente apreciación de las mejoras drásticas de rendimiento logradas por la optimización de código frontend. Sin embargo, mientras el reconocimiento del valor del fuerte desarrollo frontend ha crecido, las plataformas utilizadas por los desarrolladores a menudo no han brindado la libertad de aplicar plenamente sus habilidades frontend.

Las arquitecturas impuestas por aplicaciones monolíticas pueden debilitar nuestra capacidad para utilizar las últimas tecnologías e incluso afectan cosas como nuestro flujo de trabajo de desarrollo. Esto inhibe nuestros esfuerzos para proteger, fundamentalmente, los aspectos importantes del desarrollo de software, como una experiencia de desarrollo saludable para desbloquear el potencial de nuestros talentosos equipos de desarrollo.

### **Temas de Rendimiento**

El rendimiento del sitio web es integramente importante para el éxito del contenido entregado en internet. Existen varios estudios que concluyen que el rendimiento y la transformación están estrechamente enlazados. Uno de los estudios concluye que el retraso de un sólo segundo en el tiempo de carga puede perjudicar la transformación de un sitio de ecommerce en un 7%.

Como esto sucede, las aplicaciones monolíticas rara vez conducen a un rendimiento superior del sitio. Necesitan generar y entregar HTML cada vez que un nuevo visitante llega al sitio. Esto relentiza significativamente el tiempo de carga de la página.

Pero el rendimiento no solo se dicta por la velocidad. Debido a que las aplicaciones monolíticas son tan grandes, puede ser difícil definir límetes arquitectónicos. El código está tan interconectado que arreglar un _bug_, actualizar una librería o cambiar un framework en una parte de la aplicación, puede romper otra parte de la misma.

La caché es otra parte importante del rendimiento del sitio en general - y que es algo notoriamente difícil hacerlo bien en un sitio dinámico -. Si un sitio está construido sobre una aplicación monolítica, es posible que la misma URL pueda retornar contenido diferente dependiendo de una variedad de parámetros, incluyendo si un usuario inició sesión o si el sitio estaba ejecutando previamente una prueba dividida. Ser capaz de entregar una experiencia previsible a los usuarios finales es vital.

### **Los Desafios de Escalado**

Debido a que una arquitectura monolítica requiere que la vista de la página se genere para cada visitante, la infraestructura necesita ser escalable en anticipación al tráfico del sitio. No solo es costoso, también es difícil hacerlo bien. Los equipos terminan sobreaprovisionando su infraestructura para evitar el tiempo de inactividad o arriesgarse a un bloqueo porque no hay una separación clara entre la infraestructura requerida para producir y gestionar el sitio y la requerida para servir el sitio.

Cuando la misma aplicación que crea las vistas de página o permite a los autores gestionar contenido, también necesita escalarse para manejar los picos de tráfico, no es posible desacoplar estas piezas para escalar y proteger cada pieza de la infraestructura de acuerdo a sus necesidades.

En este escenario, las consideraciones que afectan la arquitectura técnica de un sitio sufren el estar agrupados en un sólo sistema. En ciencias de la computación, reconocemos que los costos de lectura y escritura pueden ser muy diferentes y, a pesar de todo, las aplicaciones monolíticas agrupan estas características en la misma aplicación, haciéndolos dificiles de diseñar adecuadamente.

El enfoque para diseñar un sistema que permite cientos de millones de operaciones de lectura es muy diferente al de un sistema que permite un número similar de operaciones de escritura. Entonces, ¿es prudente combinar esas capacidades en la misma infraestructura y exigir que el perfil de riesgo de una característica influya en el de otra? ¿Y es probable que estas características encuentren niveles de tráfico similares?

Hay maneras de dejar distancia entre los usuarios que visitan su sitio y la complejidad que genera y entrega ese sitio. Sin tal separación, el escalado puede ser difícil de lograr.

### **Problemas de Seguridad**

Queremos asegurarnos de que, al evaluar los motivos por los que las aplicaciones monolíticas ya no mantienen el crecimiento de la web, tenemos cuidado de no ofender a los cientos de miles de equipos de desarrollo que optaron por implementarlas. Hemos sido ese equipo. Puede ser que estes en este equipo ahora mismo. Una de las formas de hacer esto es simplemente mirando los hechos. Y cuando hablamos de seguridad, los hechos son dificiles de descartar.

De acuerdo a estimaciones recientes, Wordpress potencia el 29% de la web. Joomla y Drupal lo siguen como el segundo y tercer sistema de gestión de contenido más popular, respectivamente. Eso los convierte en el objetivo principal de mucha gente malintencionada.

La disponibilidad de estos productos como servicios alojados pude ayudar a liberarnos de algunas de las responsabilidades para asegurar la infraestructura subyacente, pero en instancias de alojamiento propio, debemos ponernos al hombro toda esa carga nosotros mismos. En cualquier caso, hay muchos vectores de ataque, y la incoporación de complementos (_plugins_) de terceros puede exponernos a riesgos adicionales y hacer que las cosas sean aun más dificiles de proteger.

Las aplicaciones monolíticas como Wordpress, Drupal y Joomla combinan todos los componentes y complementos de la arquitectura de un proyecto web en un único código base. A su vez, esto crea una área enorme por la que el malware puede penetrar. No sólo es una área de ataque extremadamente grande, también se expone cada vez que se construye el sitio ya que cualquier complemento que el sitio utilice debe ejecutarse cada vez que se carga la página para un nuevo visitante del sitio, aumentando el riesgo.

Con ese volumen de distribución, injectar malware en un único complemento puede significar una distribución masiva. Un [**ataque reciente**](https://nakedsecurity.sophos.com/2014/10/30/millions-of-drupal-websites-at-risk-from-failure-to-patch/) causó que 12 millones de sitios Drupal requieran un parche urgente.

Y hay una cosa más: en aplicaciones monolíticas, los plugins están vinculados directamentes al núcleo del framework. Debido a que son notoriamente inseguros y requieren actualizaciones frecuentes (y a menudo con errores), los complementos actualizados rápidamente corren el riesgo de romper todo el sitio. Los _manteiners_ tiene que elegir entre parches de seguridad y el riesgo de quebrar la funcionalidad del sitio.

## El Riesgo de Permanecer Igual

Tanto los desarrolladores como los encargados de tomar decisiones empresariales han reconocido los riesgos de continuar desarrollando proyectos web utilizando aplicaciones monolíticas. Pero el riesgo de cambiara menudo supera el riesgo de permanecer igual.

Para grandes compañías, la enorme inversión en arquitectura y talento se combina con el miedo de renunciar a la flexibilidad, las características y las herramientas de un ecosistema más maduro. Para las pequeñas empresas, la reconstrucción de la infraestructura web extrae recursos fuera de las iniciativas críticas de crecimiento.

Sin embargo, creemos que ha llegado el momento en el que continuar invirtiendo en el status quo es un riesgo demasiado grande de mantener. Y hay un ejército de desarrolladores que respaldan esto. Los primeros susurros llegaron como una ola de blogs personales, sitios de documentación de proyectos _open source_ (de código abierto) y proyectos con plazos como eventos y sitios de conferencias migraron al JAMstack.

Estos susurros se han vuelto más fuertes a medida que sitios más grandes con un mayor número de audiencia y más contenido también comenzaron a adoptar el JAMstack, desafiando las limitaciones previamente aceptadas mediante la entrega de comentarios, contenido de suscripción, ecommerce y más.

A medida que una mayor parte de la población mundial se conecta, es esencial que entreguemos sitios que puedan manejar enormes picos de tráfico, ejecutarse de forma rápida y predecible bajo cualquier condición de tráfico, soportar diferentes lenguajes y localizaciones, y ser accesible y utilizable en todos los dispositivos que conocemos y en muchos que no. Y, los sitios necesitan hacer todo esto mientras están seguros y protegidos de ataques maliciosos que son inherentes en una red global y abierta.

Esto suena como un trabajo para el JAMstack.
