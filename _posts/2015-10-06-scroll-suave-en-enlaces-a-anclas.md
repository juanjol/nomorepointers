---
id: 115
title: Scroll suave en enlaces a anclas
date: 2015-10-06T10:23:55+00:00
author: Mr. bug
layout: post
guid: http://www.nomorepointers.com/?p=115
permalink: /scroll-suave-en-enlaces-a-anclas/
audiourl:
  - 
videourl:
  - 
categories:
  - Sin categoría
---
Para conseguir hacer un scroll suave al hacer click en un ancla no es necesario instalar plugins extra a jquery. Con este simple snippet es suficiente:

<pre>$('a.smoothscroll').click(function(){
 $('html, body').animate({
 scrollTop: $( $.attr(this, 'href') ).offset().top
 }, 500);
 return false;
 });</pre>

Con esto, todos los enlaces a anclas a los que añadamos el class smoothscroll, harán un desplazamiento suave. Podemos ajustar la velocidad cambiando el valor 500 por otro mayor o menor (es la duración de la animación).