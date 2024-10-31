# Laboratorio 4: Implementación de Shaders en OpenGL

## Descripción del Proyecto

Este laboratorio se centra en la creación de shaders personalizados utilizando **OpenGL** en **Python** para implementar efectos visuales en tiempo real. Los shaders diseñados incluyen transformaciones simples, efectos de color, y animaciones en los objetos renderizados en una escena 3D. Para este proyecto se utilizan varias técnicas de shaders, incluyendo la manipulación de vértices y colores para obtener efectos visuales únicos y dinámicos, usando **GLSL** (OpenGL Shading Language).

## Características

- **Shaders Implementados**: Incluye shaders de pulsación, escaneo, animación de vértices y degradado.
- **Transformaciones de Vértices**: Escalado, rotación y animación de vértices para efectos visuales.
- **Manipulación de Color**: Creación de efectos de color en función del tiempo y de la posición en el espacio.
- **Interactividad**: Uso de teclas para alternar entre los diferentes modos de renderizado (relleno y alambre).
- **Cámara**: Configuración de una cámara controlable para navegar por la escena.

## Instalación

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/TuRepositorio/Laboratorio4-Shaders.git
   ```

2. Instalar las dependencias necesarias:
   ```bash
   pip install pygame PyOpenGL PyGLM
   ```

3. Ejecutar el proyecto:
   ```bash
   python RendererOpenGL.py
   ```

## Estructura del Proyecto

- **buffer.py**: Gestiona los buffers de vértices y atributos para su uso en OpenGL.
- **camera.py**: Implementación de la cámara, permitiendo su movimiento y configuración en la escena.
- **gl.py**: Motor de renderizado principal, que controla los objetos de la escena, shaders y modos de visualización.
- **model.py**: Carga y configura modelos OBJ, aplicando texturas y transformaciones.
- **obj.py**: Cargador de archivos OBJ para cargar modelos 3D en la escena.
- **RendererOpenGL.py**: Archivo principal para configurar la ventana y ejecutar el ciclo de renderizado.
- **shaders.py**: Contiene los shaders GLSL para efectos visuales de animación y color.

## Uso

Para alternar entre shaders, edita `RendererOpenGL.py` y ajusta la función `SetShaders` para cargar el shader deseado. A continuación, algunos ejemplos de shaders disponibles:

### Ejemplo de uso del Shader de Pulsación:
```python
from shaders import pulsating_vertex_shader, pulsating_fragment_shader
rend.SetShaders(pulsating_vertex_shader, pulsating_fragment_shader)
```

### Ejemplo de uso del Shader de Escaneo:
```python
from shaders import scan_vertex_shader, scan_fragment_shader
rend.SetShaders(scan_vertex_shader, scan_fragment_shader)
```

### Alternar entre modos de visualización
Presiona **1** para activar el modo de relleno y **2** para el modo de alambre en la escena renderizada.

## Shaders Implementados

### Shader de Pulsación
Este shader produce un efecto de pulsación, expandiendo y contrayendo el objeto en función del tiempo y cambiando su color entre dos tonos (por ejemplo, azul y amarillo). Utiliza una función de seno para animar el tamaño del objeto, creando una "respiración" visual.

### Shader de Escaneo
Genera una franja de luz que se mueve verticalmente en el objeto, simulando un efecto de escaneo. Esta franja de luz cambia en función de la posición en el eje Y y del tiempo, iluminando temporalmente diferentes áreas del objeto.

### Shader de Degradado Vertical
Este shader usa la posición vertical del objeto para interpolar su color entre dos tonos, logrando un efecto de degradado suave desde la base hasta la parte superior del objeto.

### Shader de Animación de Vértices
Aplica un movimiento ondulatorio a los vértices de los objetos, creando un efecto de superficie animada como si el objeto estuviera hecho de agua o estuviera siendo distorsionado por ondas.

## Capturas de Pantalla

Captura de pantalla del efecto de pulsación y escaneo en la escena:

![Captura de pantalla 2024-10-30 180723](https://github.com/user-attachments/assets/db6543e4-94e0-4c84-82d0-2f7380b8c4b4)

## Contribuciones

Las contribuciones son bienvenidas. Si tienes sugerencias, encuentras un error o deseas agregar un shader, por favor abre un "issue" o envía un "pull request".