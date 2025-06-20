# Disparos

Ya queda poco para terminar nuestro juego; vamos a añadir la capacidad de disparar a nuestro jugador. Pero en primer lugar, vamos a crear la escena ```bullet.tscn``` que contendrá lo necesario para un disparo del jugador.

1. **Crear el Nodo Principal**

    - Haz clic derecho en el panel de nodos y selecciona **Añadir Nodo**.
    - Busca y selecciona `Area2D` como nodo principal de la escena.

2. **Añadir un Sprite2D como Hijo**

    - Selecciona el nodo `Area2D`.
    - Haz clic en **Añadir Hijo** y elige `Sprite2D`.
    - En el inspector, asigna la textura `bullet.png` al Sprite2D.

3. **Añadir un CollisionShape2D como Hijo**

    - Selecciona el nodo `Area2D`.
    - Haz clic en **Añadir Hijo** y elige `CollisionShape2D`.
    - En el inspector, selecciona una forma adecuada (por ejemplo, `CircleShape2D`) y ajústala al tamaño de la bala.

El árbol de nodos debería verse así:

```
Area2D
├── Sprite2D (textura: bullet.png)
└── CollisionShape2D
```

## Script

Vamos a crear el Script asociado al ```Area2D```. Para que la bala se borre cuando llegue al borde superior.

El Script contendrá el siguiente código inicialmente:

```gdscript

extends Area2D

@export var speed= 500

func _process(delta: float) -> void:
	position.y -= speed * delta
	if position.y < -10:
		queue_free()
```


## Disparo

Por último, vamos a crear un disparo cuando pulsemos espacio, desde el propio jugador. Por ello, vamos a volver a la escena ```player```; para ampliar la función ```_process```.

En primer lugar, vamos a añadir debajo de la velocidad, una nueva propiedad que será una packet_scene; esta escena nos va a permitir crear disparos en tiempo de ejecución.

```gdscript
@export var speed = 300
@export var bullet_scene: PackedScene
```

!!! note
    Recuerda solo añadir la última línea del anterior fragmento.

Una vez añadida la propiedad, en el editor estableceremos la propiedad ```bullet_scene``` a la escena ```bullet.tscn```.

Por último, en el script de player, ampliamos la función ```_process``` con el siguiente fragmento:

```gdscript

	if Input.is_action_just_pressed("ui_accept"):
		var bullet = bullet_scene.instantiate()
		bullet.position = position
		bullet.add_to_group("bullet")
		get_parent().add_child(bullet)
```

Si todo ha ido bien, el script de ```player``` debería quedar así:

```gdscript
extends CharacterBody2D

@export var speed = 300
@export var bullet_scene: PackedScene

func  _process(delta: float) -> void:
	var dir = Vector2.ZERO
	if Input.is_action_pressed("ui_right"):
		dir.x+=1
	if Input.is_action_pressed("ui_left"):
		dir.x -=1
	if Input.is_action_pressed("ui_up"):
		dir.y-=1
	if Input.is_action_pressed("ui_down"):
		dir.y +=1
		
	velocity = dir.normalized()* speed
	move_and_slide()
	
	if Input.is_action_just_pressed("ui_accept"):
		var bullet = bullet_scene.instantiate()
		bullet.position = position
		bullet.add_to_group("bullet")
		get_parent().add_child(bullet)
```