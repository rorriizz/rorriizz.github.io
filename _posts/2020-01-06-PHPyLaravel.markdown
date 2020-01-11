---
layout: post
title:  "PHP y Laravel"
date:   2020-01-06 21:00:00 +0200
description: Se detiene el servicio de Leap Motion
---

comando para ver que versión de php se tiene:
php -v

composer es el manejador de dependencias de php, donde podremos permitir instarlas paquetes y componentes como es el framework de Laravel

comando para
composer update

antes de codear, irnos ala carpeta donde se encuentre el proyecto code/proyecto

Laravel utilizan un patron de diseño llamadao front Controller donde solo hay un punto de entrada, en caso de Laravel es: index.php

todas las peticiones llegan a index.php


Para manejar las rutas nos vamos a la carpeta routes y en el archivo web.php


Laravel va analizando las routes en orden de aparición

Expresiones regulares** es necesario revisarlo en php
->where('id', '[0-9]+')

Dentro de las rutas podemos tener parametros obligatorios y opcionales, poe ejemplo.
Route::get('/saludo/{name}/{nickname?}', function($name, $nickname=null){
  return "Bienvenido {$name}, tu apodo es {$nickname}"
});


Para probar usamos el comando
vendor/bin/phpunit
y se puede definir un alias para que sea más rápida la ejecución

alias t=vendor/bin/phpunit



Para levantar el servicio es con:
php artisan serve
Y ahi viene el servidor donde correra la página web


Laravel tiene helpers que nos ayudan con la seguridad de nuestra pagina por ejemplo la función e()
Que nos permite hacer una excepción al código injectado, y todo lo convierte a texto plano. esta funcion se utiliza con datos dinamicos que vengan de la base de datos.




Laravel tiene su propio sistema de plantillas, Blade. aquí se cambia un poco la estructura, por ejemplo las variables se meten entre llaves, así que en lugar de tener:
<?= e($title) ?>
se tiene:
{{$title}}

o en lugar de
<?php foreach ($users as $user):?>
se tiene
@foreach ($users as $user)


Blade nos protege automáticamente de ataques.



Se pueden utilizar condicionales inversos
como es en lugar de:
@if (! empty($users))
usar unless:
unless(empty($users))

Laravel tiene diferentes directivas como:
@endunless
@empty
@forelse
cada directiva de control se debe de cerrar
@endempty
@endunless
@endforelse


Blade es una manera elegante de envolver php, hay muchas formas de acomodarlo.

-----
Integrando Bootstrap a Laravel
