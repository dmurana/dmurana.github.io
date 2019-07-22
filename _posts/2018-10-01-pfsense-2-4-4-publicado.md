---
layout: post
title: Publicado pfSense 2.4.4 con interesantes novedades
categories: [redes]
tags: [pfsense]
permalink: /pfsense-2-4-4-publicado/
---

Desde el 24 de septiembre tenemos disponible la versión 2.4.4 de [pfSense](https://www.pfsense.org/),  la distribución FreeBSD que nos proporciona un completo firewall/router  libre sobre la cual ya he comentado. pfSense es una excelente solución  para firewall y UTM corporativos, basada en FreeBSD, el firewall pf y  muchos proyectos de sofware libre.

![/img](/img/pfsense.png)

Soy  usuario y administrador de pfSense desde su versión 2.1, pero recuerdo  pocos saltos de versión con novedades tan interesantes a simple vista.  Esta versión además de inclir parches de seguridad, nuevas  características y mejoras en estabilidad y soporte de hardware trae como  novedad el hecho de que **el contenido gold que antes se obtenía por suscripción ahora pasa a ser gratuito**.

A partir de pfSense 2.4.4 están disponibles de forma gratuita las siguientes características de la suscripción *pfSense Gold:*

- **AutoConfigBackup:**  la funcionalidad de respaldo de configuración en la nube, que además  estará integrada en el sistema dejando de ser un pauqete opcional.
- **Hangouts mensuales:** han  sido disponibilizados públicamente en YouTube y [el sitio de  Netgate](https://www.netgate.com/resources/videos/), y a partir de ahora  todos los nuevos Hangouts estarán disponibles mediante YouTube Live.
- **El libro oficial de pfSense:** un excelente material para aprender más de este sistema. Lo podemos obtener [aquí](https://www.netgate.com/docs/pfsense/book/).

Además de estos complementos, algunas mejoras destacables incluyen:

- Actualización del sistema base a FreeBSD 11.2-RELEASE-p3.
- Actualización de PHP a la versión 7.2.
- Túneles IPSec enrutados o Virtual Tunnel Interfaces (VTI).
- Grupos de puertas de enlaces predeterminadas (*default gateway group*) que nos permitirán obtener alta disponibilidad en el ruteo predeterminado, mejorando la característica *default gateway switching* que ya existía.
- DNS sobre TLS en DNS Resolver (unbound).
- Portal  cautivo rediseñado y con autenticación mejorada (pudiéndo usarse los  proveedores de autenticación integrados en el sistema, esto es: LDAP,  RADIUS y usuarios locales).

Y por supuesto, varias correciones y parches de seguridad que podemos conocer en las [notas de la versión](https://www.netgate.com/docs/pfsense/releases/2-4-4-new-features-and-changes.html).

Si  estamos ejecutando pfSense 2.3 o 2.4 podremos actualizar desde la  interfaz de actualización del sistema sin mayores inconvenientes, aunque  no está demás realizar un respaldo de la configuración previamente.

También  aprovecho para recordarles a quienes estén usando pfSense 2.3.x que el  31 de octubre de 2018 finaliza el soporte para esta rama y junto con  ella el soporte a procesadores de 32 bits y las instalaciones de tipo  NanoBSD. Para más información visitar [pfSense® Release 2.3.x EOL Reminder](https://www.netgate.com/blog/pfsense-release-2-3-x-eol-reminder.html).
