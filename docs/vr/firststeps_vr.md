# Primeros pasos con VR en Godot

Una vez instalado y configurado el entorno, vamos a proceder a trabajar con nuestra primera escena de VR en Godot. Para ello, vamos a crear una nueva escena y configurarla para que sea compatible con VR. Añadimos en primer lugar un Node3D que será nuestro nodo raíz, y lo renombraremos a "Main". Este nodo será el punto de partida para nuestra escena de VR.

Vamos a añadir los siguientes Nodos a nuestra escena, como hijos del nodo "Main":

* **ARVROrigin**: Este nodo es el punto de origen para la realidad virtual. Es el nodo raíz de nuestra escena de VR y se encargará de manejar la posición y orientación del usuario en el espacio virtual.

* **ARVRCamera**: Este nodo es la cámara que se utilizará para renderizar la escena en VR. Se debe colocar como hijo del nodo ARVROrigin para que siga la posición y orientación del usuario.

* 2 **ARVRController**: Estos nodos representan los controladores de VR que el usuario utilizará para interactuar con la escena. Se deben colocar como hijos del nodo ARVROrigin para que sigan la posición y orientación del usuario.

Ahora configuraremos los controladores; estableciendo la propiedad **tracker** a "left_hand" para el primer controlador y "right_hand" para el segundo controlador. Esto permitirá que los controladores sigan la posición y orientación de las manos del usuario en el espacio virtual.

Ahora, estableceremos la posición de la cámara para que esté a una altura adecuada para la experiencia de VR. Para ello, seleccionaremos el nodo ARVRCamera y estableceremos su posición en el eje Y a 1.6 metros, que es una altura promedio para la vista de un usuario en VR.

Y por otro lado, estableceremos la posición de los controladores para que estén a una altura adecuada para la experiencia de VR. Para ello, seleccionaremos cada uno de los nodos ARVRController y estableceremos su posición de cada uno de los controladores a:

* Controlador izquierdo: (-0.5, 1.0, -0.5)
* Controlador derecho: (0.5, 1.0, -0.5)

Esto colocará los controladores a una altura adecuada para la experiencia de VR y permitirá que el usuario interactúe con la escena de manera natural.

Y por último, añadiremos un nodo **DirectionalLight** a nuestra escena para iluminarla. Este nodo se encargará de proporcionar iluminación a la escena y mejorar la apariencia visual de los objetos en VR.

### Añadir Script de configuración de VR

Ahora, añadiremos un script al nodo "Main" para configurar el entorno de VR. Este script se encargará de inicializar el sistema de VR y asegurarse de que la experiencia de VR se configure correctamente al iniciar la escena. El código del script será el siguiente:

```gdscript
extends Node3D

var xr_interface: XRInterface

func _ready():
	xr_interface = XRServer.find_interface("OpenXR")
	if xr_interface and xr_interface.is_initialized():
		print("OpenXR initialized successfully")

		# Turn off v-sync!
		DisplayServer.window_set_vsync_mode(DisplayServer.VSYNC_DISABLED)

		# Change our main viewport to output to the HMD
		get_viewport().use_xr = true
	else:
		print("OpenXR not initialized, please check if your headset is connected")
```

Una vez hecho esto, ya podemos guardar nuestra escena y probarla en nuestro dispositivo VR para ver cómo se ve y cómo se siente la experiencia de realidad virtual en Godot. Recuerda que para probarlo necesitarás tener tu dispositivo VR configurado y conectado a tu ordenador, y asegurarte de que las opciones de VR estén habilitadas en tu proyecto de Godot.