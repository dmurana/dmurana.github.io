---
layout: post
title: Gestionar notas con Joplin
categories: [utilidades]
tags: [gnulinux, productividad]
permalink: /como-gestiono-mis-notas-joplin/
---

[Joplin](https://joplin.cozic.net/)  es una aplicación libre y multiplataforma para gestionar notas que  incorporé hace poco más de un año a mi flujo de trabajo. Antes había  usado Evernote, Google Keep, Tomboy, etc. con más o menos éxito, pero he  de decir que no terminé de adaptarme a ningún software libre de los que  probé, y los privativos que además implicaban guardar mi información en  servidores de terceros los descarté. Hasta que llegó Joplin mi gestión  de notas fue bastante errática y sin rumbo.

En Joplin las notas se pueden tomar en texto plano o en [formato Markdown](https://en.wikipedia.org/wiki/Markdown),  pudiendo también agregar adjuntos y listas. La estructura de  organización principal consiste en libretas que pueden almacenar notas u  otras libretas, y además a las notas podemos agregarles etiquetas para  facilitar la clasificación. Así de símple; abrimos la libreta,  escribimos un título, apuntamos, agregamos algún adjunto, una o dos  etiquetas y listo. Luego podremos ver las notas formateadas, ordenarlas  según varios criterios y buscar entre ellas usando el buscador integrado  (que por tratarse de archivos casi en texto plano funciona muy rápido).

Así se ve la interfaz principal:

![Joplin](/img/joplin_interfaz_principal.jpg)

#### Algunas características destacables

- Escritura en formato Markdown
- Estructura de libretas y etiquetas
- Permite importar notas desde Evernote (algo que nunca usé, pero habrá a quien le es útil)
- Sincronización con Nextcloud, Dropbox, OneDrive, WebDAV o sistema de archivos remotos
- Multiplataforma: aplicación para Windows, GNU/Linux, macOS, Android e iOS
- Web Clipper para guardar páginas y capturas de pantalla directamente desde *Firefox* o *Chrome*
- Cifrado punto-a-punto

#### Instalación en GNU/Linux

Para  GNU/Linux se distribuye en formato AppImage, lo que debería permitir  que con el siguiente comando lo instalemos en cualquier distribución:

```
wget -O -https://raw.githubusercontent.com/laurent22/joplin/master/Joplin_install_and_update.sh | bash
```

En mi caso me ha funcionado en Debian, Ubuntu, Trisquel, ArchLinux y Parabola.

#### Sincronización con Nextcloud

Para configurar la sincronización con Nextcloud he creado una carpeta llamada *Notas* en la raíz del almacenamiento de mi usuario en Nextcloud.

Luego  para configurarlo en Joplin es necesario disponer de la URL WebDAV que  podemos obtener en la app Archivos de Nextcloud con un clic en el ícono  de Configuración en la esquina inferior izquierda:

![Joplin](/img/joplin_sync_nextcloud.jpg)

 Al final de esta URL le agregaremos el nombre de la carpeta, quedando `https://SERVIDOR/remote.php/webdav/CARPETA_DE_NOTAS` .

Con esta información, en Joplin iremos al menú *Herramientas -> Opciones generales* y completaremos las opciones de sincronización:

![Joplin](/img/joplin_sync_config.jpg)

Y  con esto tenemos resuelta la sincronización de las notas, bastará con  usar la misma configuración en las aplicaciones móviles y otros  escritorios.

Como extra, por tratarse de archivos en texto plano que se almacenan localmente, además de tener mis notas sincronizadas también las tengo respaldadas al respaldar los archivos de mi PC.

