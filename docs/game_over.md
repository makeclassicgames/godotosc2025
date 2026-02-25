# Game Over (Final de partida)

Comenzaremos con una de las partes más importantes de nuestro juego; el final de la partida. Tenemos que tener en cuenta que nuestro "juego" puede acabar la partida de dos formas: la primera es que el jugador choque con las trampas y la segunda es que el jugador alcance la meta. En ambos casos, el juego se detendrá y se mostrará un mensaje al jugador indicando el resultado de la partida.

## Game Over por choque con trampas

Como ya hemos visto, las trampas son objetos que el jugador debe evitar. Si el jugador choca con una trampa, el juego se detendrá y se mostrará un mensaje indicando que el jugador ha perdido la partida. Para implementar esto, podemos utilizar la función `game_over()` que se llamará cuando el jugador choque con una trampa.

Para ello, vamos a crear un nuevo Script que será el script principal de nuestro juego. Este script se encargará de manejar la lógica del juego, incluyendo el final de la partida. Para crear este script, seleccionamos el nodo principal de nuestra escena `main.tscn`y hacemos clic derecho sobre él, luego seleccionamos "Attach Script". Esto abrirá una ventana donde podemos configurar el script. Asegúrate de que el lenguaje seleccionado sea GDScript y luego haz clic en "Create". Esto creará un nuevo script llamado `main.gd` y lo adjuntará al nodo principal de la escena.

Adjuntamos el script que analizaremos después.

```gdscript
extends Node

signal game_over

@onready var player = $player

func _ready() -> void:
	for tramp in get_tree().get_nodes_in_group("traps"):
		tramp.connect("body_entered",_on_body_entered)


func _on_body_entered(body: Node3D) -> void:
	if body.is_in_group("player"):
		game_over.emit()

func _on_game_over() -> void:
	$player.started = false
```

Como podemos ver, en el script `main.gd` hemos definido una señal llamada `game_over` que se emitirá cuando el jugador choque con una trampa. En la función `_ready()`, conectamos la señal `body_entered` de cada trampa al método `_on_body_entered()`. Esto nos permitirá detectar cuándo el jugador choca con una trampa. En el método `_on_body_entered()`, verificamos si el cuerpo que ha entrado en la trampa es el jugador. Si es así, emitimos la señal `game_over`. Finalmente, en el método `_on_game_over()`, detenemos el movimiento del jugador estableciendo la propiedad `started` en `false`. Esto hará que el jugador deje de moverse y se detenga el juego.

### Grupos

Habrás visto que comprobamos que los objetos jugador y las trampas pertenezcan a un grupo. Esto es una propiedad muy útil a la hora de organizar nuestro juego, ya que nos permite agrupar objetos similares y realizar acciones sobre ellos de manera más sencilla. Para agregar un objeto a un grupo, selecciona el nodo del objeto en la escena y en el panel de propiedades, busca la sección "Groups". Allí puedes agregar el nombre del grupo al que deseas que pertenezca el objeto. En nuestro caso, hemos agregado el jugador al grupo "player" y las trampas al grupo "traps". Esto nos permite verificar fácilmente si un objeto pertenece a un grupo específico utilizando el método `is_in_group()`, como lo hicimos en el método `_on_body_entered()`.

![Grupos](img/groups.png)

