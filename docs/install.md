# Instalación de Godot

La instalación de Godot es sencilla y no requiere procesos complejos. A continuación se detallan los pasos para instalar Godot en los sistemas operativos más comunes, así como las diferencias entre las versiones estándar (GDScript) y las versiones con soporte para C# (Mono).

## Instalación en Windows

1. Ve al sitio oficial de [Godot Engine](https://godotengine.org/download/windows).
2. Descarga la versión estándar (`.zip`) o la versión con soporte Mono si necesitas C#.
3. Extrae el archivo descargado en una carpeta de tu elección.
4. Ejecuta el archivo `Godot_vX.X.X_stable_win64.exe` para iniciar el editor.


!!! info

    No es necesaria instalación adicional, pero asegúrate de tener los drivers de tu tarjeta gráfica actualizados.

---

## Instalación en macOS

1. Accede a la página de [descargas de Godot](https://godotengine.org/download/osx).
2. Descarga el archivo `.zip` correspondiente a tu sistema.
3. Extrae el contenido y mueve la aplicación `Godot.app` a la carpeta `Aplicaciones`.
4. Si macOS bloquea la ejecución, haz clic derecho en `Godot.app` y selecciona "Abrir".


!!! info
    Puede ser necesario permitir la ejecución desde "Preferencias del Sistema" > "Seguridad y privacidad".

---

## Instalación en Linux

1. Dirígete a la sección de [descargas para Linux](https://godotengine.org/download/linux).
2. Descarga el archivo ejecutable (`.x86_64`).
3. Da permisos de ejecución al archivo:
    ```bash
    chmod +x Godot_vX.X.X_stable_linux.x86_64
    ```
4. Ejecuta el archivo desde la terminal o haciendo doble clic.

### Instalación usando Flatpak (opcional)

```bash
flatpak install flathub org.godotengine.Godot
flatpak run org.godotengine.Godot
```

### Requisitos adicionales

- Asegúrate de tener instalados los controladores gráficos más recientes.
- Para Mono, instala también el runtime de .NET.

