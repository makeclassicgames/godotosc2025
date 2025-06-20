# Escenas

En Godot, una **escena** es una colección de nodos organizados jerárquicamente que representan una parte funcional del juego, como un personaje, un nivel, una interfaz o cualquier otro elemento. Las escenas pueden contener otras escenas, lo que permite reutilizar y organizar el proyecto de manera modular.

## ¿Cómo se utilizan las escenas?

- **Creación:** Puedes crear una nueva escena desde el editor de Godot, añadiendo nodos según las necesidades de tu juego.
- **Instanciación:** Una escena puede ser instanciada dentro de otra, permitiendo reutilizar componentes y facilitar el desarrollo.
- **Edición:** Cada escena se puede editar de forma independiente, lo que mejora la organización y el mantenimiento del proyecto.
- **Cambio de escenas:** Es posible cambiar entre escenas durante la ejecución del juego usando scripts, por ejemplo, para pasar de un menú principal a un nivel.

Las escenas son fundamentales en Godot, ya que permiten estructurar el juego de manera flexible y eficiente.

Las escenas normalmente tienen extensión _.tscn_.

## Crear una Escena

Para crear una escena en Godot, sigue estos pasos:

1. Abre el editor de Godot y haz clic en **Escena > Nueva Escena** o usa el atajo `Ctrl+N`.
2. Añade nodos a la escena según lo que necesites (por ejemplo, un nodo `Node2D`, `Sprite2D`, `Control`, etc.).
3. Organiza los nodos en la jerarquía arrastrándolos y configurando sus propiedades.
4. Guarda la escena con **Escena > Guardar Escena** o `Ctrl+S`, eligiendo un nombre descriptivo y una ubicación en tu proyecto.

> **Consejo:** Es recomendable guardar cada escena en una carpeta específica (por ejemplo, `scenes/`) para mantener el proyecto organizado.