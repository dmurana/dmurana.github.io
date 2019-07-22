```
---
layout: post
title: Notificar el estado de batería en GNU/Linux
categories: [gnulinux, utilidades]
tags: [scripts]
---
```

Recientemente cambié de trabajo y con ello  también la computadora portátil que uso para trabajar. Esto implica que  además de la instalación inicial durante las primeras horas o días uno  va instalando el software necesario, configurando el sistema a gusto y  necesidad, y entendiendo las particularidades del dispositivo en  cuestión.

Pese a tener parcialmente automatizada la instalación de  paquetes con un script en bash que agrega repositorios e instala  aquellas herramientas que suelo usar siempre, otros tantos los instalo a  mano y la personalización del escritorio la hago más o menos de memoria  según lo que aprendí en [esta guía](https://www.youtube.com/watch?v=WeQIITDo-M4).

Mientras  realizaba esto charlaba con un compañero que se encontraba en la misma  tarea de instalar su nueva computadora y recordamos alguna cosa leída  sobre las buenas prácticas respecto a la carga de la batería, que en  estos dispositivos es quizá la parte que más se desgasta con el  uso. Entonces recordé que una computadora portátil que tuve la  oportunidad de usar disponía de una opción en su configuración que  permitía limitar la carga máxima de la batería al 80%, agregándole a  esto la recomendación de que la carga no baje del 20% y realizar ciclos  completos de carga y descarga cada 30 o 50 ciclos (hay mucha literatura  al respecto, estos números que menciono se basan en una aproximación a  la que arribé en una charla de oficina).

Comentado lo anterior,  surgió la idea de realizar un script para monitorear el estado de carga  de la batería y al llegar a los valores definidos emitir una alerta para  conectar o desconectar el cargador según sea el caso. Mi compañero [hizo lo suyo con PowerShell en Windows](http://blog.victorsilva.com.uy/script-para-comprobar-la-bateria/) y yo me dispuse a solucionarlo con un script bash en GNU/Linux.

Para conocer toda la información relativa a la energía en nuestra PC podemos emplear herramientas que trabajen con la «*Interfaz Avanzada* *de Configuración y Energía*»  o ACPI, un estándar que proporciona a la BIOS/UEFI y al sistema  operativo mecanismos para obtener información y gestionar la energía en  el sistema. En GNU/Linux encontramos el comando `acpi` para esto; y en particular usaremos `acpi -b`  para obtener información de la batería. Para emitir notificaciones que  se integren con las notificaciones nativas del sistema una buena opción  es utilizar el comando `notify-send` (en Debian y derivados es parte del paquete *libnotify-bin*).

Así  lo que hice fue un script con un bucle que cada 10 minutos ejecuta el  comando anteriormente mencionado y guarda el porcentaje de carga usando `grep`  en una variable y verifica el valor de la misma: si es mayor a 80%  emite una alerta, si es menor a 20% emite una alerta, y si no cumple  ninguno de estas condiciones no realiza ninguna acción.

```
#!/bin/bash
while true
do
bat_level=`acpi -b | grep -oP '[0-9]+(?=%)'`
if [ $bat_level -ge 80 ]; then
notify-send "Battery is above 80%" "Current charge: ${bat_level}%"
elif [ $bat_level -le 20 ]; then
notify-send "Battery is lower 20%" "Current charge: ${bat_level}%"
else
echo "" > /dev/null
fi
sleep 600
done
```

Basta con ejecutarlo una vez ya que los comandos `while` y `sleep`  se encargan de que se mantenga en ejecución, por lo que lo configuré  para ejecutarse al inicio de sesión y con esto ya tengo alertas para  saber cuando puedo desconectar y conectar el cargador.

En el escritorio KDE Plasma se ven así: 

![Notificación del estado de la batería](assets/battery_notify.png)