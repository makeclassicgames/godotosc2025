# Jugador

Vamos a crear nuestro jugador; en este caso se trata de un cubo que se mueve por el escenario. para este caso, vamos a crear una nueva escena llamada `player.tscn` (Recuerda que para crear una nueva escena, debes ir a `Scene -> New Scene` o usar el atajo `Ctrl + N`), y dentro de esta escena, vamos a agregar los siguientes nodos:

```
 CharacterBody3D
 ├── CollisionShape3D
 └── MeshInstance3D
```

Como podemos ver en el esquema, el nodo raíz es un `CharacterBody3D`, que es un nodo específico para personajes que se mueven por el escenario. Este nodo nos proporciona funcionalidades como la detección de colisiones y el movimiento.

El `CollisionShape3D` es un nodo hijo del `CharacterBody3D` y se utiliza para definir la forma de colisión del jugador. En este caso, podemos usar una forma de caja para representar el cubo. Y por último, el `MeshInstance3D` es otro nodo hijo que se encarga de renderizar el modelo 3D del jugador. En este caso, podemos usar un cubo simple para representar al jugador visualmente.

![Jugador](img/jugador.png)

Con esta estructura, el jugador será capaz de moverse por el escenario y detectar colisiones con otros objetos. Sin embargo, no hemos agregado el jugador a la escena principal todavía, así que vamos a hacerlo ahora. Para agregar el jugador a la escena principal, simplemente arrastra y suelta el archivo `player.tscn` desde el panel de archivos al panel de la escena principal. Esto creará una instancia del jugador en la escena principal.

También puedes añadir el jugador haciendo click derecho en el nodo raiz y seleccionando `Instance Child Scene` y luego eligiendo `player.tscn` de la lista de escenas disponibles. Esto también creará una instancia del jugador en la escena principal.

Ahora podemos ver el jugador en la escena principal y comenzar a trabajar en su movimiento y comportamiento. En los próximos pasos, vamos a agregar un script al jugador para controlar su movimiento y hacer que responda a las entradas del teclado.

![Jugador en la escena principal](img/escenajugador.png)

## Cámara

Si pulsamos en ejecutar la escena principal, veremos que el jugador no es visible; de hecho, nada lo es. Esto se debe a que no tenemos una cámara en la escena. Para solucionar esto, vamos a agregar una cámara a la escena principal.

Para agregar una cámara, simplemente haz clic derecho en el nodo raíz de la escena principal y selecciona `Add Child Node`. Luego, busca `Camera3D` en la lista de nodos disponibles y selecciónalo. Esto agregará una cámara a la escena principal.

Moveremos la camara para poder ver el jugador. Para hacer esto, selecciona la cámara en el panel de la escena y luego usa las herramientas de transformación para moverla a una posición donde pueda ver al jugador. Por ejemplo, puedes mover la cámara hacia arriba y hacia atrás para obtener una vista clara del jugador.

Si quieres ver una previsualización de lo que la cámara está viendo, puedes seleccionar la cámara y luego hacer clic en el botón de vista previa en la parte superior del editor. Esto te mostrará una ventana con la vista desde la cámara, lo que te permitirá ajustar su posición y orientación para obtener la mejor vista del jugador.

Una vez que la camara esta situada correctamente, trata de mover en la jerarquía para que la camara sea hija del nodo del jugador. De esta forma la camara se moverá junto con el jugador, lo que es ideal para un juego en tercera persona. Para hacer esto, simplemente arrastra y suelta la cámara sobre el nodo del jugador en el panel de la escena. Esto hará que la cámara sea un hijo del jugador y se moverá junto con él.

![Vista previa de la cámara](img/vistapreviacamara.png)

Una vez visualizado correctamente, podemos pasar a mover el jugador. Esto lo veremos en la siguiente sección, donde agregaremos un script al jugador para controlar su movimiento.