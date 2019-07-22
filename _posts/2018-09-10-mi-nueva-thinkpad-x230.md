```
---
layout: post
title: Mi nueva Thinkpad X230
categories: [hardware, miscelánea]
tags: [personal]
---
```

Hace poco tiempo y de forma algo inesperada se murió la computadora portátil que me acompañó por casi 6 años, por lo que de pronto me vi en la búsqueda de un reemplazo, condicionado por la necesidad de disponer de un equipo rápidamente y con un presupuesto bastante bajo. Como les ocurrirá a muchos, para mi no es algo trivial adquirir un dispositivo que me acompañará día a día y suelo dedicar bastante tiempo en investigar previo a tomar una decisión. La idea de esta publicación es contarles parte de este proceso y mi experiencia con la [Lenovo ThinkPad X230](https://www.lenovo.com/us/en/laptops/thinkpad/x-series/x230/) que adquirí.

### Consideraciones

Llevaba  algún tiempo mirando el mercado de las computadoras portátiles de  segunda mano, comprar ciertos dispositivos recertificados por el  fabricante me parece una excelente opción para adquirir buen hardware a  precio conveniente y de paso colaborar un poco con el medio ambiente. En  estas búsquedas que realizaba cada tanto siempre aparecía la línea  ThinkPad de Lenovo (antes IBM), supongo que por tratarse de dispositivos  que envejecen muy bien.

La mayor parte de la oferta de Thinkpads  en estas condiciones eran euqipos de la línea T, las cuales son algo más  pesadas que mi vieja portátil, con pantallas de 14" y especificaciones  técnicas levemente mejores. Pero tenía claro que **quería un equipo más liviano**:  si bien gran parte de mi día transcurre en la oficina este año he  pasado bastante tiempo en movilidad y cargar con un equipo de casi 2  kilos en la espalda se vuelve un problema. No me importa si el  dispositivo es ultrafino o con un diseño moderno, simplemente busco que  no sea demasiado pesado pero me ofrezca una pantalla donde pueda  trabajar sin complicaciones.

Otro punto importante es que buscaba un equipo **que pudiera ampliar fácilmente**,  de ser posible reutilizar la memoria RAM y dispositivos de  almacenamiento (SSD y SSHD) que tenía y quizás disponer de alguna  batería extra para garantizar autonomía en movilidad.

Por lo  demás, no necesitaba más capacidad de procesamiento que la que ya usaba,  ni una pantalla FullHD o una tarjeta gráfica para mover grandes cargas  de trabajo. La mayor parte de mi tiempo en la PC transcurre navegando en  internet, conectado a servidores remotos o editando correos y  documentos. Claro, también me interesa poder ejecutar contenedores y  máquinas virtuales cuando lo necesito, por lo que el mínimo de memoria  RAM lo establecí en 8 GB y como extras necesarios están los puertos USB  3.0 y Ethernet Gigabit para cubrir mis necesidades de transferencia de  datos.

Con estas consideraciones en mente, estuve buscando  opciones locales y en ecommerce extranjeros, mirando equipos nuevos y  recertificados, y muchos análisis de portátiles en la blogosfera y  YouTube. He de decir que encontré algunas opciones interesantes en Dell y  HP, en algún caso con FreeDOS que es una opción interesante para  ahorrar el pago de una licencia de Windows que no usaría. Pero no me  convencía totalmente la relación calidad-precio o las capacidades de  expansión de estos equipos.

### Eligiendo ThinkPads

Si bien  estaba ignorando en mis búsquedas las ThinkPad T420 y T430 que aparecían  por ser equipos pesados, cuando comencé a considerarlos en mis  búsquedas aparecieron algunas ofertas de ThinkPad X220 a un precio menor  a 300 USD que llamaron mi atención. Las ThinkPad X220 ofrecen esa  construcción tan distintiva de la marca, una pantalla de 12.5", traen  procesadores Intel Core de 2da o 3ra generación, batería intercambiable,  un máximo de 8GB de RAM (que modificación de BIOS mediante se eleva a  16GB), la mayoría de los modelos traen solamente USB 2.0 pero se puede  agregar algún puerto USB 3.0 mediante el slot ExpressCard, podía agregar  mi disco SSD en su puerto mSATA interno y el SSHD como sustituto del  disco SATA3 incluído, y como todas las ThinkPads incluyen el trackpoint,  un dispositivo que a mi personalmente me parece genial.

Cuando me  había decidido a adquirir una ThinkPad X220 de segunda mano en una  tienda en concreto, me enteré que allí vendían ThinkPads X230 y no X220,  había sido un error al publicar el artículo en la plataforma de  ecommerce. ¡Genial! La X230 siendo de una generación más nueva cambiaba  el teclado por uno de tipo isla con retroiluminación, como procesador un  Intel Core i5 vPro de 3ra gen., soporte nativo para 16GB de RAM y 2  puertos USB 3.0. **Me compré esa**.

### Mi ThinkPad X230

![Mi ThinkPad X230](assets/mi_thinkpad_x230.jpg)

Adquirí mi *nueva* computadora portátil por menos de 300 dólares en un estado muy bueno,  el único detalle estético es una marca en una esquina no apreciable a  simple vista, la duración de la batería se aproxima a las 2 horas con  una carga completa y de las especificaciones técnicas no tengo mucho que  agregar, le agregué un módulo de RAM para obtener 8GB en total, le  cambié el SSD de 160GB por un SSHD de 500+8GB (para la partición /home) y  le agregué un SSD de 32GB (para el sistema operativo), funciona de  maravillas para los usos comentados.

Como la tarjeta inalámbrica que trae necesita un firmware no libre no quise perder tiempo en mantener la instalación de [Parábola GNU/Linux](https://www.parabola.nu/) -la distribución que estaba usando hasta el momento- así que le instalé Arch y previa lectura de los [comentarios en su wiki](https://wiki.archlinux.org/index.php/Lenovo_ThinkPad_X230) en  poco más de una hora la tenía funcionando y con el sistema configurado a  mi gusto. En algún momento sustituiré la tarjeta de red inalámbrica por  alguna compatible con software libre y le cambiaré el firmware UEFI por  [Coreboot](https://www.coreboot.org/Board:lenovo/x230), en ese entonces posiblemente convertiré la instalación de Arch en Parábola.

También  tengo pensado adquirir una batería de 9 celdas y quizás un segundo  cargador, los originales se encuentran en Amazon por aproximadamente  60USD y 15USD respectivamente.

#### Lo que me gusta

- **Portabilidad:**  es pequeño y ligero, puedo guardarlo dentro de mi mochila y cargarlo en  mi espalda cuando lo necesito. Tiene el tamaño de un libro mediano y  pesa áprox 1.4kg.
- **Construcción:** el equipo se  siente muy sólido, con plásticos de calidad y metal en las bisagras que  unen la base con la pantalla. Además posee ranuras para filtrado de  líquidos en el teclado y otros mecanismos comunes en ThinkPad como  sensores para detener el disco duro ante caídas.
- **TrackPoint:** es el *joystick* rojo  tan distintivo de estos equipos, una vez acostumbrado a usarlo como  control para el puntero no hay vuelta atrás, su uso ofrece una agilidad  incomparable.
- **Capacidad de expansión:** todavía  puedo ampliar la RAM, cambiar el disco duro por un SSD de mayor tamaño,  reemplazar la tarjeta de red inalámbrica o el disco mSATA por un módem  3G, agregar una tarjeta en el slot ExpressCard, utilizar baterías  intercambiables de gran capacidad, extender los puertos con un dock o  inclusive cambiar el procesador.
- **Precio:** un equipo de gama alta y gran portabilidad de hace 6 años, totalmente válido para mi uso y por menos de 300 dólares.

#### Lo que no me gusta

- **Resolución:**  no es que sea peor que otras, pero los 1366x768 me resultan algo  incómodos luego de acostumbrarme a resoluciones mayores, aunque en 12.5"  no se ven tan mal.
- **Trackpad:** es demasiado  pequeño y termina en una curva en la parte inferior, no tiene una  usabilidad muy cuidada. Afortunadamente se puede prescindir de él  gracias al TrackPoint.
- **Sonido integrado:** tanto  los parlantes como el micrófono son de muy baja calidad, en mi  experiencia no son aptos para la reproducción multimedia ni para  realizar llamadas de voz. Como dispongo de auriculares la mayor parte  del tiempo no me supone un problema mayor, pero si piensan usar el  equipo para videollamadas habitualmente esto es un problema.

Habiendo  dicho todo esto, recomiendo la ThinkPad X230 aún siendo un equipo con  varios años, es una excelente opción para quienes buscan portabilidad y  un dispositivo robusto sin un excesivo poder de cómputo. En este rango  de precios creo que es la mejor opción.