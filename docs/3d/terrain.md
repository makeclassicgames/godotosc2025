# Terreno

Vamos a comenzar a crear un pequeño suelo para nuestro juego. Para ello, utilizaremos un nodo ```StaticBody3D``` como base para nuestro terreno, ya que este tipo de nodo es ideal para objetos que no necesitan moverse pero sí interactuar con la física del juego.

Creamos la siguiente lista de nodos para crear nuestro terreno:

1. Creamos un nodo ```StaticBody3D``` y lo nombramos "Ground". Haciendo click derecho en el nodo raíz de nuestra escena y pulsando la opción "Add Child Node", buscamos "StaticBody3D" y lo seleccionamos. Luego, renombramos el nodo a "Ground" para identificarlo fácilmente como nuestro terreno.
2. Añadiremos un nodo hijo de tipo ```CollisionShape3D``` para definir la forma de colisión del terreno. Para esto, seleccionamos el nodo "Ground", hacemos clic en "Add Child Node" y buscamos "CollisionShape3D". Luego, asignamos una forma de colisión adecuada, como un ```BoxShape3D```, para representar el suelo.
3. También añadiremos un nodo hijo de tipo ```MeshInstance3D``` para darle una apariencia visual al terreno. Para esto, seleccionamos el nodo "Ground", hacemos clic en "Add Child Node" y buscamos "MeshInstance3D".
4. Por último, asignamos una malla adecuada, como un ```BoxMesh```, para representar el suelo visualmente. Que añadiremos desde el inspector de propiedades del nodo `MeshInstance3D` en la sección de "Mesh". Hacemos clic en el botón de edición junto a la malla asignada y seleccionamos `BoxMesh` para darle una apariencia visual al terreno.


Después de esto la estructura de nuestro nodo "Ground" debería verse así:

```
Ground (StaticBody3D)
├── CollisionShape3D (BoxShape3D)
└── MeshInstance3D (BoxMesh)
```

Ahora vamos a ajustar el tamaño de la forma de colisión y de la malla para que se adapte a lo que necesitamos. Comenzaremos por la fora de colisión.

1. Seleccionamos el nodo "CollisionShape3D" y en el panel de propiedades, buscamos la sección de "Shape". Allí, hacemos clic en el botón de edición (el icono de lápiz) junto a la forma de colisión asignada (en este caso, el ```BoxShape3D```). Esto abrirá una ventana donde podemos ajustar las dimensiones de la forma de colisión. Establecemos un tamaño adecuado para nuestro terreno, por ejemplo, 100 unidades para el eje X, 10 unidades para el eje Z y 1 unidad para el eje Y. Esto nos dará un terreno plano y amplio para trabajar.
2. Para el nodo "MeshInstance3D", seleccionamos el nodo y en el panel de propiedades, buscamos la sección de "Mesh". Allí, hacemos clic en el botón de edición junto a la malla asignada (en este caso, el ```BoxMesh```). Esto abrirá una ventana donde podemos ajustar las dimensiones de la malla para que coincida con la forma de colisión. Establecemos las mismas dimensiones que para la forma de colisión (100 unidades para el eje X, 10 unidades para el eje Z y 1 unidad para el eje Y) para asegurarnos de que la apariencia visual del terreno coincida con su forma de colisión.


Una vez hecho esto, ya podremos ver nuestro terreno en la escena. Podemos movernos por el espacio 3D para observar cómo se ve desde diferentes ángulos y asegurarnos de que todo esté correctamente alineado. Además, podemos ajustar la posición del nodo "Ground" para colocarlo en el lugar deseado dentro de nuestra escena.

![Ground](../img/terrain3d.png)