# Ganar la Partida (fin)

Para acabar nuestro juego, vamos a implementar una condición de victoria. Para esto, vamos a crear un nuevo nodo que representará el objetivo que el jugador debe alcanzar para ganar la partida.

En primer lugar, vamos a añadir una nueva escena llamada `end.tscn` que representará el objetivo de la partida. Para crear esta escena, sigue estos pasos:

1. Haz clic derecho en el panel de archivos y selecciona "New Scene".
2. En la nueva escena, agrega un nodo `Node3D` como nodo raíz.
3. Renombra el nodo raíz a "End" o cualquier nombre que prefieras.
4. Ahora vamos a añadir 3 `StaticBody3D` como hijos del nodo raíz. Estos nodos representarán el objetivo que el jugador debe alcanzar para ganar la partida. 
5. Para cada `StaticBody3D`, añade un nodo hijo de tipo `CollisionShape3D` para definir la forma de colisión del objetivo. Puedes usar una forma de colisión de tipo caja para representar el objetivo.
6. También añade un nodo hijo de tipo `MeshInstance3D` para darle una apariencia visual al objetivo. Puedes usar una forma de malla de tipo caja para representar el objetivo visualmente
7. Mueve y escala cada uno de los `StaticBody3D` para crear un objetivo que el jugador pueda alcanzar. Por ejemplo, puedes colocar los `StaticBody3D` en diferentes posiciones dentro de la escena para que el jugador tenga que moverse por el escenario para alcanzarlos.

Puedes ver una previsualización de cómo se ve el objetivo en la siguiente imagen:

![Objetivo](../img/objetivo.png)

Además la jerarquía de la escena `end.tscn` debería verse así:

```
End (Node3D)
├── StaticBody3D
│   ├── CollisionShape3D (BoxShape3D)
│   └── MeshInstance3D (BoxMesh)
├── StaticBody3D
│   ├── CollisionShape3D (BoxShape3D)
│   └── MeshInstance3D (BoxMesh)
└── StaticBody3D
    ├── CollisionShape3D (BoxShape3D)
    └── MeshInstance3D (BoxMesh)
``` 

Ahora que tenemos nuestro objetivo creado, vamos a agregarlo a la escena principal. Para esto, simplemente arrastra y suelta el archivo `end.tscn` desde el panel de archivos al panel de la escena principal. Esto creará una instancia del objetivo en la escena principal.