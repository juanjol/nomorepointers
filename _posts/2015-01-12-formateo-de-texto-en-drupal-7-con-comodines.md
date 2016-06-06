---
id: 56
title: Formateo de texto en drupal 7 con comodines
date: 2015-01-12T11:38:07+00:00
author: Mr. bug
layout: post
guid: http://nomorepointers.com/?p=56
permalink: /formateo-de-texto-en-drupal-7-con-comodines/
audiourl:
  - 
videourl:
  - 
categories:
  - Drupal
tags:
  - comodines
  - drupal
  - drupal 7
  - format_string
  - t
---
En drupal, cuando usamos formateo de cadenas o traducciones (format_string, t, etc&#8230;)  tenemos la posibilidad de pasar un segundo parámetro a estas funciones con un array con comodines de la siguiente manera:
  
`t('@total available positions', array('@total' =>; $totalPos));`
  
&nbsp;

Estos parámetros pueden ir prefijados con @, % o !, cada uno de estos prefijos interpreta de una forma distinta el valor que estamos pasando, de la siguiente manera:

  * **@variable**:  Se quita todo el HTML que pueda contener el valor usando [check_plain](https://api.drupal.org/api/drupal/includes%21bootstrap.inc/function/check_plain/7 "Encodes special characters in a plain-text string for display as HTML."){.local}().
  * **%variable**: Igual que @ solo que además le aplica la función [drupal_placeholder](https://api.drupal.org/api/drupal/includes%21bootstrap.inc/function/drupal_placeholder/7 "Formats text for emphasized display in a placeholder inside a sentence."){.local}(), que rodea el texto con el tag <em> para enfatizarlo.
  * **!variable**:  Inserta el valor tal cual llega. Puede ser arriesgado usarlo si no sabemos qué puede contener el valor. Es conveniente formatear el valor previamente para que sea compatible con HTML. Es muy recomendable pasar este valor previamente por [filter_xss](https://api.drupal.org/api/drupal/includes%21common.inc/function/filter_xss/7 "Filters HTML to prevent cross-site-scripting (XSS) vulnerabilities."){.local}().

&nbsp;