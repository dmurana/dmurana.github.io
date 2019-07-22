---
layout: post
title: Reemplazar una cadena o texto en varios archivos
categories: [utilidades]
tags: [scripts]
permalink: /reemplazar-cadena-varios-archivos/
---

Recientemente estuve reordenando archivos y  una vez finalizado esto me encontré con la necesidad de modificar varios  de estos archivos para apuntar algunas rutas a su nueva ubicación.

Si  necesitaramos editar unos pocos archivos pequeños podríamos usar el  editor de texto de nuestro agrado para buscar y reemplazar la cadena de  texto necesaria, pero cuando hablamos de muchos archivos o muy grandes  donde la cadena aparece muchas veces esta opción de vuelve poco  práctica. Ahí es donde la terminal de GNU/Linux podrá ayudarnos,  concretamente los comando `find` y `sed` que sirven para buscar y  sustituir respectivamente.

Situándonos en el directorio que  contiene los archivos a modificar, con esta línea podremos reemplazar en  todos los casos donde exista *textooriginal* por *textonuevo*:

```
find ./ -type f -exec sed -i 's/textooriginal/textonuevo/g' {} \;
```

Y eso es todo. Son dos comandos muy simples pero de gran utilidad. También podemos usar [expresiones regulares](https://www.gnu.org/software/sed/manual/html_node/Regular-Expressions.html) con sed para realizar sustituciones más complejas.
