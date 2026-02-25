# Trampas (Pinchos)

En este capítulo se describen las trampas o pinchos, que son obstáculos comunes en los videojuegos. Se explicará cómo crear trampas utilizando el motor de juego Godot, en este caso serán los obstáculos que el jugador debe saltar para no perder. Para esto, se creará una nueva escena llamada `spike.tscn` que representará la trampa o pincho en el juego.

En la escena `spike.tscn`, se agregará un nodo `Area3D` como nodo raíz, que es un nodo estático que no se mueve pero puede detectar colisiones. Luego, se agregarán dos nodos hijos: un `CollisionShape3D` para definir la forma de colisión de la trampa y un `MeshInstance3D` para renderizar el modelo 3D de la trampa.

Para el caso de la `MeshInstance3D`, vamos a utilizar una forma de prisma triangular para representar el pincho.  Puedes crear esta forma usando la propiedad de `Mesh` del `MeshInstance3D` y seleccionando `New PrismMesh`. Luego, ajusta las propiedades del `PrismMesh` para obtener la forma deseada. En nuestro caso recomendamos configurar el `PrismMesh`con los siguientes valores: X e Y con 1 unidad y Z con 10 unidades. Esto creará un pincho con profundidad de 10 unidades, lo que lo hace lo suficientemente alto para que el jugador tenga que saltar sobre él.

También es importante configurar el `CollisionShape3D` para que coincida con la forma del pincho. Para esto, selecciona el nodo `CollisionShape3D` y en la propiedad `Shape`, selecciona `New CylinderShape3D`. Luego, ajusta las dimensiones del `CylinderShape3D` para que coincidan con las dimensiones del pincho. Además, en este caso hay que rotar el cilindro para que quede alineado con el pincho. Para hacer esto, selecciona el nodo `CollisionShape3D` y en la propiedad `Rotation`, ajusta los valores para rotar el cilindro 90 grados en el eje X. Esto hará que el cilindro esté alineado con el pincho y pueda detectar colisiones correctamente. Modifica las propiedades de la forma de colisión para que tenga una altura de 10 unidades y un radio de 0.5 unidades, lo que coincidirá con la forma del pincho.

![Trampa](img/trampa.png)

Ahora vamos a añadir estas trampas a la escena principal; por lo que vamos a ir creando grupos de trampas para que el jugador pueda saltar sobre ellas. Abriremos la escena principal y agregaremos un nodo3D desde el nodo principal, al que llamaremos `Traps`. Este nodo servirá como contenedor para todas las trampas que agreguemos a la escena. Luego, dentro del nodo `Traps`, vamos a agregar varias instancias de la escena `spike.tscn` para crear un grupo de trampas. Para agregar una instancia de la escena `spike.tscn`, simplemente arrastra y suelta el archivo `spike.tscn` desde el panel de archivos al nodo `Traps` en el panel de la escena. Esto creará una instancia de la trampa dentro del nodo `Traps`. Repite este proceso varias veces para agregar varias trampas a la escena. También puedes duplicar cada nodo para no arrastrar siempre; para ello acercate y pulsa <kbd>Ctrl + D</kbd> para duplicar el nodo seleccionado. Luego, ajusta la posición de cada trampa para crear un grupo de trampas que el jugador pueda saltar.

![Trampas en la escena principal](img/mainescenetraps.png)

