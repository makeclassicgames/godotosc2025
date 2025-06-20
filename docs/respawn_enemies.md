# Respawn Enemigos

Vamos a hacer que aparezcan enemigos en nuestro juego; para ello entra en juego los llamados ```Timers```.
## Timer en Godot

Un **Timer** en Godot es un nodo que permite ejecutar acciones después de un intervalo de tiempo determinado o de forma repetitiva a intervalos regulares. Es útil para programar eventos temporizados, como retrasos, animaciones, enfriamientos de habilidades, o cualquier lógica que requiera esperar un tiempo específico antes de ejecutarse. El Timer puede configurarse para que se repita automáticamente o se detenga tras una sola ejecución, y emite señales como `timeout` cuando el tiempo ha transcurrido.

En la escena prinicpal, añadimos anteriormente un Timer; que podemos configurar con la siguiente configuración:

* AutoStart: ```true```.
* Wait Time: ```1.5s```.

Para ello, seleccionaremos la escena ```main``` y seleccionamos el nodo ```timer```; mostrando las propiedades en el inspector de la derecha.

## Señales

Una vez hemos añadido y configurado el nodo Timer, podemos utilizar las señales correspondientes. Godot se basa mucho en la utilización de señales que son eventos que permiten intercambiar información entre nodos a través de estas llamadas.

Para ver las señales de un nodo, podemos usar en el inspector, la pestaña ```nodo``` que aparecerá la lista de señales disponibles para establecer una función para recibir la información de dicha señal.

Vamos a usar el nodo ```Timer``` dentro de la escena ```main``` y hacer doble click en la señal timeout. Nos aparecerá un dialogo confirmando la nueva función.

La función tendrá el siguiente código:

```gdscript
func _on_enemy_timer_timeout() -> void:
	var enemy = enemy_scene.instantiate()
	enemy.position = Vector2(randf()*640,-50)
	enemy.add_to_group("enemy")
	add_child(enemy)
```

Sin embargo, si ejecutamos este script nos dará un error diciendo que no existe ```enemy_scene```; eso es por que tenemos que añadir una ```packet_scene```.

Añadiremos el siguiente código justo antes de crear la función:

```gdscript
@export var enemy_scene: PackedScene

```

Esto nos permitirá usar el editor para añadir una escena en el inspector. Para ello hacemos click en el botón de la derecha y seleccionamos ```enemy.tscn```.

Una vez hecho esto ya podremos ejecutar el juego y ver como los enemigos aparecen.