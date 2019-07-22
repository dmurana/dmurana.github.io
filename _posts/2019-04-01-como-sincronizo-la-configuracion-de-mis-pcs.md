---
layout: post
title: Cómo sincronizo la configuración de mis PCs
categories: [utilidades]
tags: [scripts, gnulinux]
permalink: /como-sincronizo-la-configuracion-de-mis-pcs/
---

Somos muchos los que poseemos al menos dos computadoras y las usamos en nuestro día a día. En mi caso se trata de la computadora de escritorio que tengo en casa y una [portátil ThinkPad X230]() que uso en la oficina y en movilidad. Cuando esto ocurre es posible que nos interese mantener sincronizados archivos, atajos de teclado, configuraciones de aplicaciones o inclusive habrá quien sincronice el fondo de pantalla.

En mi caso, en ambas computadoras uso GNU/Linux y **para sincronizar archivos entre ellas uso Nextcloud**, una configuración bastante simple que no vale la pena mencionar. Lo que sí pretendo mencionar es cómo sincronizo la configuración de varias de las aplicaciones que necesito usar en ambas computadoras.

Cuando abrimos por primera vez una aplicaciónen GNU/Linux, o cuando realizamos cambios en su configuración, estas suelen guardar **carpetas y archivos de configuración ocultos** en nuestra carpeta personal (*/home*). Estos archivos se ocultan anteponiendo un punto en su nombre, lo que les da el nombre de *dotfiles*.

Para la mayoría de las aplicaciones basta con copiar estos archivos de una computadora a otra para obtener exactamente la misma configuración. Por lo que en un primer momento intenté crear enlaces simbólicos de sus archivos de configuración a una carpeta sincronizada con Nextcloud, pero me encontré con que algunas aplicaciones no cargan correctamente si se usan enlaces simbólicos para todos sus dotfiles, por lo que continué buscando una solución y encontré Mackup.

**[Mackup](https://github.com/lra/mackup) es una herramienta cuya función es mantener sincronizadas aplicaciones en GNU/Linux y MacOS**. Está escrita en Python, es muy ligera y fácil de configurar, y se integra a la perfección con mi sincronización de archivos vía Nextcloud. He de decir que no hace nada mágico, también crea enlaces simbólicos para lograr su objetivo, pero trae una lista bastante extensa de aplicaciones y conoce qué dotfiles enlazar para cada una; además me ofrece la posibilidad de gestionar todo esto desde un único archivo de configuración.

**En el repositorio de GitHub se encuentra una lista completa de los proveedores de almacenamiento y aplicaciones que soporta** de forma predeterminada. Además, es posible agregar aplicaciones definiendo la ubicación de sus dotfiles y sincronizarlo con cualquier carpeta local (que posteriormente sincronicemos mediante alguna herramienta de terceros).

## Instalar y configurar Mackup

Para instalar Mackup vamos a necesitar PIP, específicamente la versión para Python 3 (con PIP en Python2 me dio error en alguna ocasión). Si no lo tenemos instalado, en Debian y derivados se puede instalar con el comando `sudo apt install python3-pip`  y para instalar Mackup usamos `pip install --upgrade mackup` .

Demás está decir que esto hay que hacerlo en todas las computadoras que querramos sincronizar.

Antes de comenzar a usarlo, como en mi caso uso Nextcloud (no integrado oficialmente), en ambas computadoras creé el archivo *.mackup.cfg* en mi carpeta personal especificando en dónde se sincronizarán los dotfiles:

``` 
[storage]
engine = file_system
path = /home/damian/Proyectos/config
```

También podemos agregar aquí aplicaciones a ignorar en la sincronización, ya que de forma predeterminada intentará sincronizar todas las aplicaciones soportadas. En mi caso agregué LibreOffice y Pidgin, quedando así el archivo:

```
[storage]
engine = file_system
path = /home/damian/Proyectos/config

[applications_to_ignore]
libreoffice
pidgin
```

Por supuesto, esta carpeta la tengo sincronizada con Nextcloud.

## Sincronizando dotfiles con Mackup

Con lo anterior configurado, podemos correr el siguiente comando en una de las computadoras para que realice la copia de las configuraciones a la carpeta sincronizada:

`mackup backup`

Y en la otra correr el comando para restaurar las configuraciones:

`mackup restore`

Con esto ya tenemos la misma configuración de las aplicaciones en ambas computadoras.

Aunque esto no es suficiente para mantener las aplicaciones sincronizadas. Antes de abrir una aplicación en una de las computadoras debemos ejecutar el comando restore para traer la configuración más reciente y una vez cerrada la aplicación ejecutar el comando backup para sincronizar eventuales cambios. Sobre esto hay mucha literatura, existen quienes lo hacen al inicio y cierre de sesión, quienes lo programan con cron, ejecutan estos comandos a mano, etc. En mi caso opté por hacerlo con zsh.

Me explico:

* Nunca utilizo ambas computadoras al mismo tiempo (lo que podría ocasionar sobreescrituras no deseadas en los dotfiles).
* En ambas uso como shell zsh.
* Ambas inician Nextcloud en segundo plano al iniciar sesión.
*  En mi flujo de trabajo en ambas computadoras suelo abrir al menos una ventana de terminal al encenderlas y la cierro al apagarlas.

Esto me permite mantener las configuraciones sincronizadas **agregando los comandos antes mencionados al inicio y cierre de sesión de zsh**.

En el archivo .zlogin (comandos al inciar zsh) de mi carpeta personal agregué ```mackup restore ```y en el archivo .zlogout (comandos al cerrar zsh) de mi carpeta personal agregué ```mackup backup``` . De este modo cuando inicio sesión se cargan las últimas configuraciones guardadas y al cerrarla se guarda la configuración existente en ese momento, quedando así sincronizadas.


