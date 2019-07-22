```
---
layout: post
title: Mi nueva Thinkpad X230
categories: [gnulinux]
tags: [gnulinux, debian]
---
```

[**Flatpak**](https://www.flatpak.org/)  es un conjunto de herramientas de desarrollo de software y gestión de  paquetes que nos permite empaquetar aplicaciones para GNU/Linux con  todas las dependencias incluídas y ejecutarlas como procesos  aislados. Es impulsado desde hace algún tiempo por Red Hat y GNOME entre  otros, y es una alternativa a otros sistemas como Snappy (de Canonical)  o AppImage.

En el anuncio de lanzamiento de Flatpak se usó el slogan "*construye una vez, ejecuta en cualquier lugar*"  y resume bastante bien el principal beneficio, un paquete Flatpak se  empaqueta con las librerías y runtimes necesarios, haciendo que no  necesite resolver dependencias instalando paquetes desde los  repositorios de la distribución, por lo tanto se trata de paquetes que  pueden ser instalados -potencialmente- en cualquier distribución.

También  incluye otros aspectos interesantes como librerías deduplicadas para  ahorrar espacio en disco, o actualizaciones mediante *deltas estáticas*  que reducen el tamaño de descarga de las mismas (descargando solamente  los cambios). Y no menos importante, aprovecha características de  aislamiento de procesos del núcleo Linux y el servidor gráfico Wayland  para ofrecer seguridad extra al momento de ejecutar aplicaciones  mediante *sandboxing*.

Además de estas características, que  en su mayoría existen en Snap aunque implementadas de forma distinta,  me he decidido a comenzar a usar Flatpak por ser este "más abierto":  Canonical controla la distribución de paquetes permitiendo la  instalación solamente desde su repositorio oficial, y para subir  paquetes allí es necesario aceptar un acuerdo de licencia; en cambio es  posible instalar paquetes Flatpak desde repositorios comunitarios, y la  comunidad participa de forma más activa en su desarrollo.

### Instalación de Flatpak en Debian y derivados

Flatpak  actualmente está disponible en los repositorios de Debian y PureOS,  donde también encontramos los paquetes que permiten integrar  aplicaciones Flatpak en las herramientas de gestión de software GNOME  Software y KDE Discover.

En este caso vamos a instalar el paquete flatpak y la integración con GNOME Software:

```
sudo apt install flatpak gnome-software-plugin-flatpak
```

Si quisieramos la integración con Discover, el paquete es `plasma-discover-backend-flatpak` .

También podemos agregar el repositorio "oficial" de Flatpak, Flathub, con el comando:

```
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Es  importante aclarar que este repositorio contiene software libre y  software privativo, hay que prestar atención a lo que se instala o  utilizar otros que contengan solamente software libre.

### Instalado aplicaciones con Flatpak

Para  validar que el soporte para paquetería Flatpak quedó correctamente  instalado en el sistema podemos intentar instalar el editor de código  Atom desde Flathub:

```
sudo flatpak install --from https://flathub.org/repo/appstream/io.atom.Atom.flatpakref
```

Nos  pedirá confirmación respecto a instalar el paquete y mostrará el  proceso de descarga e instalación, una vez finalice debemos tener la  aplicación disponible en los lanzadores de aplicación del sistema.

Otra forma de instalar paquetes es visitar el sitio web [Flathub](https://flathub.org/) y dar clic en Install sobre las aplicaciones, esto abrirá GNOME Software o Discover para proseguir con la instalación.

![Flatpak](flatpak_apps.png)