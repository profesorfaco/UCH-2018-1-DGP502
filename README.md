Seminario Gráfica Computacional I 2018, Primer Semestre → Clase 2 → Viernes 23 de marzo

# Seminario Gráfica Computacional I (v.2018)
### Visualización de datos

**La [clase recién pasada](https://github.com/profesorfaco/dgp502_1/) se presentó el curso e inmediatamente pusimos manos a la obra**: vimos cómo se puede [programar](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics) la visualización de datos en un mapa, mediante consultas a [JSON](https://www.json.org/json-es.html) y una biblioteca de JavaScript: [Leaflet](http://leafletjs.com/).

#### Algunos apuntes:

[JSON](https://www.json.org/json-es.html) (JavaScript Object Notation), que es un formato ligero de intercambio de datos. Debido a su amplia adopción como alternativa a [XML](https://es.wikipedia.org/wiki/Extensible_Markup_Language) (eXtensible Markup Language), se considera un formato de lenguaje independiente. Muchos datos son compartidos en JSON. Un par de ejemplos sencillos: [Number of People in Space](http://api.open-notify.org/astros.json), [Current Location of the International Space Station](http://api.open-notify.org/iss-now.json), [SWAPI - The Star Wars API](https://swapi.co/api/people/1/?format=json).

[GeoJSON](http://geojson.org/) es un derivado de JSON, ampliamente utilizado en aplicaciones de cartografía en entornos web al permitir el intercambio de datos de manera rápida, ligera y sencilla. A diferencia de de otros estándares [SIG](https://es.wikipedia.org/wiki/Sistema_de_informaci%C3%B3n_geogr%C3%A1fica), no está desarrollado y mantenido por una organización oficial, sino que es mantenido por una comunidad de desarrolladores en Internet.

Tanto JSON como GeoJSON pueden consultarse con [diversos lenguajes de programación](https://www.taniarascia.com/how-to-use-json-data-with-php-or-javascript/). En nuestro caso, que trabajamos con JavaScript,  escribimos:

```var request = new XMLHttpRequest();
request.open('GET', 'URI', true);
request.onload = function () {
	var data = JSON.parse(this.response);
	//acá es donde trabajamos.
}
request.send();
```

Lo que hacemos con este script es asignar a la **var**iable **data** el resultado de analizar el JSON o GeoJSON en una [URI](https://es.wikipedia.org/wiki/Identificador_de_recursos_uniforme), de manera que, en lo que sigue, se pueda consultar a la **var**iable **data** como se consulta a cualquier [objeto en javascript](https://www.w3schools.com/js/js_objects.asp).

En caso no tengas claro a qué nos referimos con **var**iable, podrías necesitar información básica sobre JavaScript. Para obtener esa información, se recomienda consultar: [JavaScript.com](https://www.javascript.com/learn/javascript/strings), [JavaScript for Beginner](http://xahlee.info/js/js_basics_index.html), [JavaScript Tutorial](https://www.w3schools.com/js/).

#### Bootstrap

Si la [clase recién pasada](https://github.com/profesorfaco/dgp502_1/) pudimos meternos directamente a examinar JavaScript, fue porque pudimos saltarnos las complicaciones de definir una estructura (HTML) y su correspondiente presentación (CSS), porque nos aprovechamos de [Bootstrap](https://getbootstrap.com/), un kit de herramientas de código abierto para la implementación de diseño "[responsive](https://es.wikipedia.org/wiki/Dise%C3%B1o_web_adaptable)" y "[mobile-first](https://en.ryte.com/wiki/Mobile_First)" de sitios y aplicaciones web.

Hay distintas maneras para comenzar a trabajar con Boostrap. Un grupo de opciones parten en su [descarga](https://getbootstrap.com/docs/4.0/getting-started/download/), pero una opción mucho más rápida es Bootstrap[CDN](https://es.wikipedia.org/wiki/Red_de_entrega_de_contenidos). Para usar esta última opción, el documento HTML debe verse, inicialmente, de la siguiente manera: 

```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <!-- CSS de BootstrapCDN  -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
    <title>Hola mundo!</title>
  </head>
  <body>
    <h1>Hola mundo!</h1>
    <!-- JS de BootstrapCDN -->    
    <!-- primero jQuery, luego Popper.js, después Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
  </body>
</html>
```

Luego, confiando en la red de entrega de contenidos (Bootstrap[CDN](https://es.wikipedia.org/wiki/Red_de_entrega_de_contenidos)), podemos comenzar a utilizar la grilla de 12 columnas (`col-…`) dentro de la cada fila (`row`) dentro de un contenedor (`container` o `container-fluid`):

```
<div class="container">
	<div class="row">
		<div class="col-12">Ancho completo</div>
		<div class="col-6">Mitad de 12</div>
		<div class="col-6">Mitad de 12</div>		
	</div>
</div>
```

Entre las recién referidas, la clase más interesante es la de columnas (`class="col-…"`), en tanto ofrece varias opciones que  permiten indicar "cuántas columnas se toman" según el ancho del contenedor en la pantalla donde se visualiza el documento HTML. Las opciones se explican en [Grid System](https://getbootstrap.com/docs/4.0/layout/grid/#grid-options).

> En la clase de hoy vamos a retomar el ejercicio de la clase anterior, para hacer ajustes en la programación (JavaScript) y también en estructura (HTML) y presentación (CSS) de las páginas. Antes de terminar la clase, cada estudiante tiene que publicar su trabajo en [GitHub Pages](https://www.youtube.com/watch?v=bFVtrlyH-kc&feature=youtu.be). Lo que se publique será evaluado con nota (1,0 a 7,0).

- - - - - 

[Avanzar a la siguiente clase](https://github.com/profesorfaco/dgp502_3)
