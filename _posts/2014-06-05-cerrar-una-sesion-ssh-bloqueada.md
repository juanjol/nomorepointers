---
id: 25
title: Cerrar una sesión ssh bloqueada
date: 2014-06-05T16:09:17+00:00
author: Mr. bug
layout: post
guid: http://nomorepointers.com/?p=25
permalink: /cerrar-una-sesion-ssh-bloqueada/
categories:
  - Sin categoría
---
Hay ocasiones en las que las sesiones SSH **quedan bloqueadas**, ya sea por fallo en las comunicaciones o por mala configuración de la máquina a la que nos conectamos. Si estamos en entorno gráfico tenemos la posibilidad de cerrar el terminal, claro, pero a veces estamos usando multiplexadores de terminal como **byobu** (screen), **tmux**&#8230; y no queremos perder lo que tengamos en las otras ventanas, o simplemente no nos apetece cerrar y volver a abrir. Para eso existen los códigos de escape de SSH: **~.**

Efectivamente, si se te queda bloqueada la sesión, basta con introducir **~. (virgulilla y un punto)** y se cerrará la sesión. La virgulilla se suele escribir con alt+ñ o alt+4, y acto seguido basta con pulsar el punto.

No se a vosotros, pero a mi me ha ahorrado tiempo en más de una ocasión.