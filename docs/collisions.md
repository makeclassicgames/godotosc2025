# Colisiones

Para acabar, ya solo queda ver las colisiones; las colisiones en un juego es cuando 2 o más objetos interactuan por estar dentro del mismo espacio.

Como has podido ver, hemos creado durante este taller, una serie de áreas para poder marcar la superficie de colisión.

En este apartado, vamos a ver como utilizar estas superficies.

## Areas

Como hemos podido ver en apartados anteriores, hemos utilizado señales; por lo que de igual forma, vamos a utilizar las señales dentro de un nodo.

Vamos a utilizar la escena ```Bullet``` y seleccionaremos el nodo principal ```Area2D```; veremos en el inspector que hay una señal llamada ```area_entered``` esta señal se lanza al entrar un objeto o un area dentro del area designada. 

Al hacer doble click, podremos crear una nueva función llamada ```_on_area_entered```; que añadiremos el siguiente código:

```gdscript
func _on_area_entered(area: Area2D) -> void:
	if area.is_in_group("enemy"):
		queue_free()
		area.queue_free()
```

Una vez terminado esto, ya podremos ver nuestro juego funcionando.

Espero que hayas disfrutado de este taller y te invito a continuar aprendiendo.