---
id: 94
title: Usando docker sin sudo en ubuntu
date: 2015-06-17T08:34:24+00:00
author: Mr. bug
layout: post
guid: http://nomorepointers.com/?p=94
permalink: /docker-sin-sudo-ubuntu/
audiourl:
  - 
videourl:
  - 
categories:
  - Desarrollo
tags:
  - debian
  - docker
  - instalar
  - install
  - sudo
  - ubuntu
---
<img class="alignleft size-full wp-image-100" src="http://nomorepointers.com/wp-content/uploads/2015/06/docker.png" alt="docker" width="400" height="331" />Puede que al instalar docker por primera vez hayas necesitado lanzar los comandos con sudo.  Esto se debe a que el demonio de docker corre siempre como usuario root, y se enlaza a un socket unix, por lo tanto ese socket es solo accesible para el usuario root. Sin embargo, desde la versión 0.5.3, docker da privilegios sobre ese socket al grupo de usuarios &#8220;docker&#8221;, por lo que con añadir nuestro usuario habitual a ese grupo, sería suficiente. A continuación os pongo al completo el proceso de instalación de docker, incluyendo la linea donde añadimos nuestro user a ese grupo:

<pre>$ curl -sSL https://get.docker.io/ubuntu/ | sudo sh
$ sudo usermod -a -G docker $USER
$ sudo service docker restart
$ logout
</pre>

La línea mágica es la segunda, y la última lo que hace es desloguear al usuario para que se apliquen los cambios del grupo sobre nuestro user.