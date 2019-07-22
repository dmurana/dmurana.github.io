---
layout: post
title: ¿Por qué usar un generador de contenido estático?
categories: [desarrollo]
tags: [web]
permalink: /usar-generador-contenido-estatico/
---

Para crear un blog existen varias plataformas y herramientas, quizá la más común sea el CMS (Sistema de Gestión de Contenidos) [Wordpress](https://wordpress.org) el cual estaba usando hasta hace muy poco. Tenía mi propia instalación de Wordpress alojada en el hosting que ofrece [TresDe](http://tresde.org) y funcionaba muy bien, no tengo quejas sobre él. Wordpress es software libre, posee mucha documentación, temas y plugins, y puede adaptarse a necesidades muy variadas; para funcionar solamente necesita un servidor web con PHP y una base de datos MySQL o MariaDB, que para mi blog no necesita ser demasiado grande.

Pero también existen los generadores de  contenidos estáticos, son una excelente alternativa a los CMS, permiten  disponer de sitios web más simples, rápidos y seguros. Si bien pienso  que no son aptos para todos los sitios cada vez más se posicionan como  herramientas a tener en cuenta al momento de crear y mantener un blog.  La diferencia principal de cualquier generador de contenido estático  respecto a un CMS como Worpdress es evidente, las páginas son estáticas:  HTML + CSS + JS.

#### ¿Por qué?

Primeramente, mi decisión fue motivada por aprender, inicialmente pensé usar [Hugo](https://gohugo.io/) para aprender algo de [Go](https://golang.org/), luego terminé migrando a [Pelican](https://blog.getpelican.com/) que está escrito en [Python](https://www.python.org/).  Usar un generador como Pelican es una experiencia muy distinta a  Wordpress, el ambiente para generar el sitio lo tengo preparado en mis  PCs y sincronizado vía Nextcloud, escribo las publicaciones en archivos  con lenguaje Markdown, una vez escrita una nueva publicación vuelvo a  generar el sitio y hago un commit al repositorio de GitHub para que se  actualice este sitio (que está montado sobre GitHub Pages). Muy distinto  a abrir la interfaz de administración de Wordpress, instalar  actualizaciones de sistema, temas y plugins o escribir publicaciones con  el editor web integrado, ¿verdad?

#### Ventajas

 Más allá de la posibilidad de aprender, *jugar* con Python y git, hay algunas ventajas destacables en usar un generador de sitios estáticos:

- Las  páginas se generan una sola vez, se suben al servidor y están listas  para servirse. No es necesario generarlas en cada acceso, por lo que **el sitio carga más rápido**.
- Puedo **prescindir de funciones innecesarias**, el core de Pelican (y en general de cualquier generador) es muy simple, luego añado los plugins que necesito.
- **Ahorro en alojamiento web / hosting**, el sistema en general es más liviano, no requiere PHP o base de datos y el consumo de ancho de banda es menor.
- Existen sitios como GitHub, GitLab o Netlify que nos permiten alojar un sitio de forma gratuita y con soporte SSL.
- **Es más seguro**. No hay código o bases de datos en el lado del servidor, solamente páginas estáticas.
- **Requiere menos mantenimiento**,  las actualizaciones se realizan en el ambiente local, y no actualizar  periódicamente implica menos riesgos de seguridad que con un CMS.
- **Versionado mediante git**, el control de versiones se realiza automáticamente con cada *commit*.
- En caso de error es más simple volver atrás, se vuelve a generar y/o cargar el contenido estático en el servidor.
- **Puedo escribir en Markdown con mi editor preferido**, que en Wordpress también podía pero no directamente.
- **La estructura del generador y los temas suele ser simple**, si se conoce el lenguaje es fácil realizar modificaciones.
- Tengo  la carpeta del proyecto sincronizada y respaldada de forma automática,  no necesito exportar bases de datos ni nada similar.

Por  supuesto no todos son ventajas, es difícil realizar sitios complejos o  con funcionalidades avanzadas debido a las limitaciones del contenido  estático, además de necesitar algunos conocimientos de programación,  manejo de git o línea de comandos. Pero aunque no tengas estos  conocimientos, te invito a tomar contacto con el tema y probar alguno de  los muchos generadores de contenidos estáticos, verás que son  herramientas geniales.
