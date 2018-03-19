Seminario Gráfica Computacional I 2018, Primer Semestre → Clase 2 → Viernes 23 de marzo

# Seminario Gráfica Computacional I (v.2018)
### Visualización de datos

**La [clase recién pasada](https://github.com/profesorfaco/dgp502_1/) se presentó el curso e, inmediatamente, pusimos manos a la obra**: vimos cómo se puede [programar](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics) la visualización de datos en un mapa, mediante consultas a [JSON](https://www.json.org/json-es.html) y una biblioteca de JavaScript: [Leaflet](http://leafletjs.com/).

#### Algunos apuntes:

[JSON](https://www.json.org/json-es.html) (JavaScript Object Notation), que es un formato ligero de intercambio de datos. Debido a su amplia adopción como alternativa a [XML](https://es.wikipedia.org/wiki/Extensible_Markup_Language) (eXtensible Markup Language), se considera un formato de lenguaje independiente. Muchos datos son compartidos en JSON. Un par de ejemplos sencillos: [Number of People in Space](http://api.open-notify.org/astros.json), [Current Location of the International Space Station](http://api.open-notify.org/iss-now.json), [SWAPI - The Star Wars API](https://swapi.co/api/people/1/?format=json).

[GeoJSON](http://geojson.org/) es un derivado de JSON, ampliamente utilizado en aplicaciones de cartografía en entornos web al permitir el intercambio de datos de manera rápida, ligera y sencilla. A diferencia de de otros estándares [SIG](https://es.wikipedia.org/wiki/Sistema_de_informaci%C3%B3n_geogr%C3%A1fica), no está desarrollado y mantenido por una organización oficial, sino que es mantenido por una comunidad de desarrolladores en Internet.

Tanto JSON como GeoJSON pueden consultarse mediante [distintos lenguajes de programación](https://www.taniarascia.com/how-to-use-json-data-with-php-or-javascript/). En nuestro caso, que trabajamos con JavaScript,  escribimos:

```var request = new XMLHttpRequest();
request.open('GET', 'URI', true);
request.onload = function () {
	var data = JSON.parse(this.response);
	//acá es donde trabajamos.
}
request.send();
```

Lo que hacemos con este script es asignar a la **var**iable **data** el resultado de analizar el JSON o GeoJSON que encontramos en una [URI](https://es.wikipedia.org/wiki/Identificador_de_recursos_uniforme), de manera que, en lo que sigue, se pueda consultar a la **var**iable **data** como se consulta a cualquier [objeto en javascript](https://www.w3schools.com/js/js_objects.asp).

Para más información sobre JavaScript, se recomienda:

- [JavaScript.com](https://www.javascript.com/learn/javascript/strings)

- [Fundamentos de JavaScript](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

- [JavaScript for Beginner](http://xahlee.info/js/js_basics_index.html)

- [JavaScript Tutorial](https://www.w3schools.com/js/)
