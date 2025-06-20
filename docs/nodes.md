# Nodos

# Nodo en Godot

Un **Nodo** en Godot es la unidad fundamental de la estructura de una escena. Cada nodo representa un objeto con una funcionalidad específica, como puede ser mostrar gráficos, reproducir sonidos, manejar lógica de juego, detectar colisiones, entre otros. Los nodos se organizan jerárquicamente en un árbol de nodos, donde cada nodo puede tener uno o varios nodos hijos, permitiendo así la composición y reutilización de funcionalidades.

## Características principales de un Nodo:

- **Jerarquía:** Los nodos pueden anidarse unos dentro de otros, formando una estructura de árbol. Esto permite que los nodos hijos hereden transformaciones y comportamientos de sus nodos padres.
- **Escenas:** Una escena en Godot es, en esencia, un árbol de nodos. Las escenas pueden ser instanciadas y reutilizadas en otras escenas, facilitando la modularidad y organización del proyecto.
- **Tipos de nodos:** Godot proporciona una amplia variedad de nodos predefinidos, como `Node2D` para objetos en 2D, `Spatial` para objetos en 3D, `Control` para interfaces de usuario, entre otros.
- **Ciclo de vida:** Los nodos tienen métodos especiales como `_ready()`, `_process()`, y `_physics_process()` que permiten ejecutar código en momentos específicos del ciclo de vida del nodo.
- **Propiedades y señales:** Los nodos pueden tener propiedades configurables y emitir señales para comunicar eventos a otros nodos.

En resumen, los nodos son los bloques de construcción esenciales en Godot, permitiendo crear desde simples objetos hasta complejas estructuras de juego mediante su combinación y organización jerárquica.