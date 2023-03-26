Seminario Gráfica Computacional I 2018, Primer Semestre → Clase 6 → Viernes 27 de abril

# Seminario Gráfica Computacional I (v.2018)

### Visualización de datos

En [la clase recién pasada](https://github.com/profesorfaco/dgp502_5/) cerramos la segunda iteración. En esta clase corresponde abrir la tercera iteración, donde revisaremos: 

- [HTML5](https://developer.mozilla.org/es/docs/HTML/HTML5), [CSS3](https://developer.mozilla.org/es/docs/Web/CSS/CSS3) y [JavaScript](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics) (con [Bootstrap](https://getbootstrap.com/))
- [SVG](https://developer.mozilla.org/es/docs/Web/SVG) y [CANVAS](https://developer.mozilla.org/es/docs/Web/Guide/HTML/Canvas_tutorial)
- [P5.js](https://p5js.org/es/)

[Canvas (en castellano, lienzo)](https://developer.mozilla.org/es/docs/Web/HTML/Canvas) se puede utilizar para dibujar gráficos a través de secuencias de comandos JavaScript: 

```
<canvas id="miCanvas" width="400" height="400" style="background:silver;"></canvas>
<script>
  var canvas = document.getElementById('miCanvas');
  var context = canvas.getContext('2d');
  var centerX = canvas.width / 2;
  var centerY = canvas.height / 2;
  var radius = 70;
  context.beginPath();
  context.arc(centerX, centerY, radius, 0, 2 * Math.PI, false);
  context.fillStyle = '#333';
  context.fill();
</script>
```

- - - - 

[Avanzar a la siguiente clase](https://github.com/profesorfaco/dgp502_7/)
