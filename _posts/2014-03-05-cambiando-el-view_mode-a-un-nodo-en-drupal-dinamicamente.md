---
id: 16
title: Cambiando el view_mode a un nodo en drupal dinámicamente
date: 2014-03-05T13:19:31+00:00
author: Mr. bug
layout: post
guid: http://nomorepointers.com/?p=16
permalink: /cambiando-el-view_mode-a-un-nodo-en-drupal-dinamicamente/
categories:
  - Drupal
tags:
  - custom render
  - drupal
  - hooks
  - view_mode
---
Para cambiar el modo de visualización de un nodo en drupal 7, a partir de la versión 7.17 tenemos disponible el hook hook\_entity\_view\_mode\_alter. Este hook se dispara cuando se va a renderizar una entidad, y ahí podemos determinar si, según el contexto en el que estemos, queremos alterar el valor view\_mode o no. Como ejemplo, en la siguiente función nosotros estamos detectando un valor pasado por $\_GET para sacar un nodo de tipo &#8220;page&#8221; de un modo u otro:

<pre>function MYMODULE_entity_view_mode_alter(&$view_mode, $context){
  $query = drupal_get_query_parameters();
  if ($context['entity_type'] == 'node'
    && $context['entity']->type == 'page'
    && isset($query['get_param'])) {
    $view_mode = 'my_custom_view_mode';
  }
}
</pre>