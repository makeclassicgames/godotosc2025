# Movimiento 3D

En esta sección, vamos a agregar un script al jugador para controlar su movimiento en el espacio 3D. Volvemos a la escena de jugador que creamos anteriormente (`player.tscn`) y seleccionamos el nodo raíz `CharacterBody3D`. Luego, hacemos clic en el botón de "Attach Script" en la parte superior del editor para agregar un nuevo script al jugador.

Recuerda que en godot por defecto se utiliza el lenguaje de programación GDScript, que es un lenguaje de scripting específico para Godot. Sin embargo, también puedes usar otros lenguajes como C# o VisualScript si lo prefieres. Para este tutorial, usaremos GDScript.

Una vez que hayas hecho clic en "Attach Script", se abrirá una ventana donde puedes configurar el nuevo script. Asegúrate de que el lenguaje seleccionado sea GDScript y luego haz clic en "Create". Esto creará un nuevo script asociado al nodo `CharacterBody3D` del jugador.

Vamos a ver el Script a añadir, que se encargará de controlar el movimiento del jugador. El script se verá algo así:

```gdscript
extends CharacterBody3D

@export
var started:bool = false

var move_speed:float = 10.0
var jump_speed:float = 8.0 
var rotation_speed: float = 5.0 # Velocidad de giro


var gravity: float = ProjectSettings.get_setting("physics/3d/default_gravity")

@onready var mesh:MeshInstance3D = $MeshInstance3D

func _physics_process(delta: float) -> void:
	if not started:
		return
	if not is_on_floor():
		velocity.y -= gravity * delta
		mesh.rotate_z(rotation_speed*delta)
	else:
		var target_rotation = round(mesh.rotation.z / (PI/2)) * (PI/2)
		mesh.rotation.z = lerp_angle(mesh.rotation.z, target_rotation, 0.2) 
 
	# 2. Manejar Salto
	if Input.is_action_just_pressed("ui_accept") and is_on_floor():
		velocity.y = jump_speed

	# 3. Movimiento Constante en X Negativo
	# Mantenemos la velocidad actual en Y (salto/caída) y Z (por si acaso)
	velocity.x = -move_speed

	# 4. Mover el cuerpo
	move_and_slide()
```

Vamos a analizar este script paso a paso para entender cómo funciona:

1. **Variables Exportadas**: Tenemos una variable `started` que es un booleano exportado. Esto nos permite controlar cuándo el jugador comienza a moverse. También tenemos variables para la velocidad de movimiento, velocidad de salto, velocidad de rotación y gravedad. Las variables exportadas podemos controlarlas desde el editor, lo que es útil para ajustar los valores sin tener que modificar el código.

2. **Función _physics_process**: Esta función se llama en cada frame de física, lo que la hace ideal para manejar el movimiento del jugador. Dentro de esta función, primero verificamos si `started` es falso; si es así, simplemente retornamos y no hacemos nada. Esto nos permite controlar cuándo el jugador comienza a moverse.

3. **Gravedad y Rotación**: Si el jugador no está en el suelo, aplicamos la gravedad a su velocidad vertical y hacemos que el mesh gire alrededor del eje Z para simular un efecto de rotación mientras está en el aire. Si el jugador está en el suelo, ajustamos la rotación del mesh para que se alinee con los ángulos de 90 grados, lo que le da un aspecto más estable.

4. **Salto**: Si el jugador presiona la tecla de salto (en este caso, "ui_accept") y está en el suelo, asignamos la velocidad de salto a la velocidad vertical del jugador.

5. **Movimiento Constante**: Asignamos una velocidad constante en el eje X negativo para que el jugador se mueva hacia la izquierda de manera continua.

6. **Mover el Cuerpo**: Finalmente, llamamos a `move_and_slide()` para mover el cuerpo del jugador según la velocidad calculada. Esta función se encarga de manejar las colisiones y el deslizamiento del jugador por el escenario.

!!! Note
    Las acciones como `ui_accept` se configuran en el Input Map de Godot, donde puedes asignar teclas específicas a estas acciones. Asegúrate de que "ui_accept" esté configurada para la tecla que deseas usar para saltar (por ejemplo, la barra espaciadora).


Una vez hecho esto, vamos a nuestro juego y si ejecutamos la escena principal, veremos que el jugador no se mueve hasta que cambiemos el valor de `started` a `true`. Para hacer esto, simplemente selecciona el nodo del jugador en la escena principal, ve al panel de propiedades y cambia el valor de `started` a `true`. Esto hará que el jugador comience a moverse automáticamente hacia la izquierda y pueda saltar cuando presiones la tecla de salto.