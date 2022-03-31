# Visuales en servidores 

Premisa: texturas generadas con Hydra en un servidor.
Hydra como un elemento de otro marco
Hydra como el marco de trabajo principal 

## HTML, Javascript y estructura de archivos 

Experiencia previa con Javascript, P5, Processing 

Buenas/malas prácticas, en todo caso la estructura de p5 es una opción 

## P5.js

Este modo se ajusta para el dibujo 2d. Tiene la ventaja de que es posible ejecutarlo en el editor de p5
Posibles problemas: variables que ya existen 

Cuestiones generales: setup y draw, sistema de coordenadas, colores, variables

Primero agregar:

`<script src="https://unpkg.com/hydra-synth"></script>`

Y:

`<canvas id="myCanvas" width="400px" height="400px"></canvas>`

Una nueva instancia de Hydra

`var hydra = new Hydra({
  canvas: document.getElementById("myCanvas")
})`

Seleccionarlo y ocultarlo para quue no se empalmen

`hc = select("#myCanvas")`

`hc.hide()`

Creamos un espacio para guardar la imagen

`pg = createGraphics(width, height)`

Y usamos en algún lugar de la memoria
  
`pg.image(hc, 0, 0);`

Podemos obtener la información de los pixeles y pasarla a un círculo

`fill(pg.get(x, y))`

`ellipse(x, y, 5);`

## Three.js 

Este modo se ajusta para entornos 3d. Puede ejecutarse en algo como codepen

Si todo sale bien, podemos subir los archivos a un servidor 

[Fundamentals](https://threejs.org/manual/#en/fundamentals) 

Cargar la librería

`<script src="https://unpkg.com/hydra-synth"></script>`

Y agregar el canvas

`<canvas id="myCanvas" width="400px" height="400px"></canvas>`


Luego seguir el [tutorial](https://threejs.org/docs/index.html#manual/en/introduction/Creating-a-scene) para armar elementos iniciales de una escena

Una vez que ya hay una escena:

`
var hydra = new Hydra({
    canvas: document.getElementById("myCanvas"),
    detectAudio: false
})
`

`const elCanvas = document.getElementById( 'myCanvas');`

`elCanvas.style.display = 'none';`

Pasamos el canvas como una nueva textura

`const tex = new THREE.CanvasTexture(elCanvas);`

Y agregar dentro de los materiales:

`map: tex`

## Montaje en github

Nuevo proyecto y subir archivos

Activar github pages

Esperar unos minutos 