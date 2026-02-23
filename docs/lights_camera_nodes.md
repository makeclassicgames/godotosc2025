# Luces, Cámara y Nodos

En esta sección, aprenderás sobre los diferentes tipos de luces, cámaras y nodos que puedes usar en tus escenas 3D en Godot. Cubriremos cómo configurar y manipular estos elementos para crear escenas atractivas y funcionales.

## Luces

En Godot, hay varios tipos de luces que puedes usar para iluminar tus escenas 3D. Los tipos de luces incluyen:

- **DirectionalLight3D**: Simula la luz del sol, iluminando toda la escena desde una dirección específica.
- **OmniLight3D**: Emite luz en todas las direcciones desde un punto específico, similar a una bombilla.
- **SpotLight3D**: Emite luz en un cono desde un punto específico, ideal para simular linternas o focos.
- **AreaLight3D**: Emite luz desde una superficie, útil para simular luces de techo o paneles luminosos.

## Cámaras

La cámara es esencial para mostrar tu escena 3D. Sin camara, no puede visualizarse tu escena ni interactuar con el juego. En Godot, puedes usar el nodo ``Camera3D`` para configurar la vista de tu escena. Puedes ajustar parámetros como el campo de visión, la distancia de recorte y la proyección para lograr el efecto deseado.

Existen diferentes tipos de cámaras, como la ``Camera3D`` que es la cámara estándar para escenas 3D.

Obviamente, para esta sección, usaremos la cámara 3D para mostrar nuestras escenas 3D. Puedes manipular la cámara para crear diferentes perspectivas y efectos visuales en tu juego.

## Nodos

En Godot, los nodos son los bloques de construcción básicos de tus escenas. Para trabajar con gráficos 3D, es importante entender los diferentes tipos de nodos que puedes usar. Algunos nodos comunes para escenas 3D incluyen:

- **MeshInstance3D**: Para representar modelos 3D.
- **Light3D**: Para agregar iluminación a tu escena.
- **Camera3D**: Para configurar la vista de tu escena.

Es importante mencionar que los nodos en Godot pueden contener otros nodos, lo que te permite organizar tu escena de manera eficiente. Por ejemplo, puedes tener un nodo raíz que contenga varios nodos de objetos 3D, luces y cámaras.

Cada nodo puede tener diferentes funcionalidades y propiedades, lo que te permite personalizar tu escena según tus necesidades. Puedes agregar scripts a los nodos para controlar su comportamiento y crear interactividad en tu juego.