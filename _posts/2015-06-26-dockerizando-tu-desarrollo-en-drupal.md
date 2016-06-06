---
id: 103
title: Dockerizando tu desarrollo en drupal
date: 2015-06-26T11:58:12+00:00
author: Mr. bug
layout: post
guid: http://nomorepointers.com/?p=103
permalink: /dockerizando-tu-desarrollo-en-drupal/
audiourl:
  - 
videourl:
  - 
categories:
  - Desarrollo
  - docker
  - Drupal
tags:
  - apache
  - docker
  - drupal
  - github
  - lamp
  - mailhog
  - mysql
  - pimpmylog
  - ssmtp
  - vagrant
---
<img class="alignright wp-image-105" src="http://nomorepointers.com/wp-content/uploads/2015/06/dock.png" alt="Developer" width="320" height="320" />Estos días he decidido dedicar un poquito de tiempo a probar docker y aprender un poco sobre el. Como sobre todo trabajo con Drupal, gracias a <a title="Patxangas" href="http://twitter.com/patxangas" target="_blank">@patxangas</a> he aterrizado en un repo de <a title="Carlos Reig" href="https://twitter.com/unstatu" target="_blank">@unstatu</a>:

<a title="Carlos Reig - Drupal7 docker" href="https://github.com/carlosreig/drupal7-docker" target="_blank">https://github.com/carlosreig/drupal7-docker</a>

Como todo esto para mi es experimental decidí hacerle un fork y empezar a toquitear y añadir funcionalidades a esa &#8220;pila docker&#8221;. Los resultados los podéis ir viendo aquí:

<a title="Enfuse - Docker Drupal LAMP" href="https://github.com/enfuse/docker-drupal-lamp" target="_blank">https://github.com/enfuse/docker-drupal-lamp</a>

Podéis ver que he añadido un docker con <a title="Mailhog" href="https://github.com/mailhog/MailHog" target="_blank">mailhog</a> (me resulta muy útil para capturar los emails que genere el drupal), y he modificado el docker de apache para que se instale también <a title="Pimp My Log" href="http://pimpmylog.com/" target="_blank">pimpmylog</a> para poder ver los logs fácilmente.

Aún tengo muchas pruebas que hacer e ideas pendientes, ¡pero estoy abierto a que me deis las vuestras!

&nbsp;

&nbsp;