# Primeros pasos con Godot

Veamos los primeros pasos en Godot.

## Crear un nuevo proyecto en Godot

1. **Abre Godot Engine**: Inicia la aplicación Godot en tu computadora.
2. **Haz clic en "Nuevo proyecto"**: Selecciona la opción para crear un nuevo proyecto.
3. **Asigna un nombre y una ubicación**: Escribe el nombre de tu proyecto y elige la carpeta donde se guardará.
4. **Selecciona la plantilla**: Puedes elegir una plantilla vacía o importar un proyecto existente.
5. **Selecciona un Renderizador**: Puedes elegir un renderizador dependiendo del tipo de juego y recursos que necesites.

6. **Haz clic en "Crear y editar"**: Esto abrirá el editor de Godot con tu nuevo proyecto listo para usar.

### Renderizador

Godot ofrece varios renderizadores, cada uno adaptado a diferentes necesidades y plataformas:

- **Forward+**: Es el renderizador por defecto en Godot 4. Ofrece gráficos avanzados, iluminación dinámica y efectos modernos. Recomendado para juegos de escritorio con altos requisitos visuales.
- **Mobile**: Optimizado para dispositivos móviles. Consume menos recursos y es ideal para juegos que se ejecutarán en teléfonos o tabletas.
- **Compatibility**: Pensado para hardware antiguo o sistemas con capacidades gráficas limitadas. Sacrifica calidad visual para asegurar la máxima compatibilidad.




![Listado Proyectos](/img/listado.png)

## Estructura básica del proyecto

Una vez creado el prioyecto, podemos ver la estructura básica del mismo y de como suele ordenarse:


- `project.godot`: Archivo principal de configuración del proyecto.
- `scenes/`: Carpeta recomendada para guardar tus escenas.
- `scripts/`: Carpeta recomendada para tus scripts de código.
- `assets/`: Carpeta para imágenes, sonidos y otros recursos.
