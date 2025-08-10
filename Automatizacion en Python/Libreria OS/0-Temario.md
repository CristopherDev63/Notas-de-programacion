# 0-Temario

Partes Esenciales de la Librería os para Automatización
La librería os en Python es fundamental para interactuar con el sistema operativo. Para la automatización, te sugiero enfocarte en las siguientes áreas clave:

1. Gestión de Archivos y Directorios
    - `os.getcwd()`: Obtener el directorio de trabajo actual. Esto es crucial para saber dónde estás ejecutando tus scripts. [[1-Saber Directorio actual, Cambiar de directorio,  En listar elementos]]
    - `os.chdir(path)`: Cambiar el directorio de trabajo. Te permite moverte a diferentes ubicaciones en el sistema de archivos. 
    - `os.listdir(path='.')`: Listar el contenido de un directorio. Muy útil para ver qué archivos o subdirectorios hay en una ubicación específica. [**1-Saber Directorio actual, Cambiar de directorio, En listas archivos**](https://www.notion.so/1-Saber-Directorio-actual-Cambiar-de-directorio-En-listas-archivos-22178a15854c80f1b7b7f66b0bf957e0?pvs=21)
    - `os.mkdir(path, mode=0o777)`: Crear un nuevo directorio. Esencial para organizar tus archivos de salida o crear estructuras de directorios. [**2-Creación directorios, eliminar directorios, eliminar archivos**](https://www.notion.so/2-Creaci-n-directorios-eliminar-directorios-eliminar-archivos-22178a15854c80e0bb84ff413801df01?pvs=21)
    - `os.makedirs(name, mode=0o777, exist_ok=False)`: Crear directorios recursivamente. Si necesitas crear una ruta con varios niveles de directorios, esta función lo hace por ti. [**2-Creación directorios, eliminar directorios, eliminar archivos**](https://www.notion.so/2-Creaci-n-directorios-eliminar-directorios-eliminar-archivos-22178a15854c80e0bb84ff413801df01?pvs=21)
    - `os.rmdir(path)`: Eliminar un directorio vacío. [**2-Creación directorios, eliminar directorios, eliminar archivos**](https://www.notion.so/2-Creaci-n-directorios-eliminar-directorios-eliminar-archivos-22178a15854c80e0bb84ff413801df01?pvs=21)
    - `os.remove(path) / os.unlink(path)`: Eliminar un archivo. **Visto en [**2-Creación directorios, eliminar directorios, eliminar archivos**](https://www.notion.so/2-Creaci-n-directorios-eliminar-directorios-eliminar-archivos-22178a15854c80e0bb84ff413801df01?pvs=21)**
    - `os.rename(src, dst)`: Renombrar un archivo o directorio. **Visto en [3-Renombramiento de archivos, remplazar](https://www.notion.so/3-Renombramiento-de-archivos-remplazar-23c78a15854c80f88ad4de7c3a5c228e?pvs=21).**
    - `os.replace(src, dst)`: Reemplazar un archivo o directorio. Similar a `rename`, pero maneja casos donde `dst` ya existe. **Visto en [3-Renombramiento de archivos, remplazar](https://www.notion.so/3-Renombramiento-de-archivos-remplazar-23c78a15854c80f88ad4de7c3a5c228e?pvs=21).**
    - `os.path.exists(path)`: Verificar si un archivo o directorio existe. Indispensable para evitar errores al intentar acceder a recursos inexistentes. **Visto en [4-Combinar rutas y archivos, Saber su Existencia, Saber si es un archivo](https://www.notion.so/4-Combinar-rutas-y-archivos-Saber-su-Existencia-Saber-si-es-un-archivo-24078a15854c803189c8f06678a3b288?pvs=21).**
    - `os.path.isfile(path)`: Verificar si una ruta es un archivo. **Visto en [4-Combinar rutas y archivos, Saber su Existencia, Saber si es un archivo](https://www.notion.so/4-Combinar-rutas-y-archivos-Saber-su-Existencia-Saber-si-es-un-archivo-24078a15854c803189c8f06678a3b288?pvs=21)**
    - `os.path.isdir(path)`: Verificar si una ruta es un directorio.
    - `os.path.join(path, *paths)`: Unir componentes de ruta de forma inteligente. Esto es vital para construir rutas de archivo que funcionen en diferentes sistemas operativos (Windows, Linux, macOS) sin preocuparte por las barras (\ o /). **Visto en [4-Combinar rutas y archivos, Saber su Existencia, Saber si es un archivo](https://www.notion.so/4-Combinar-rutas-y-archivos-Saber-su-Existencia-Saber-si-es-un-archivo-24078a15854c803189c8f06678a3b288?pvs=21).**
    - `os.path.split(path)`: Dividir una ruta en un par (head, tail).
    - `os.path.basename(path)`: Obtener el nombre base del archivo o el último componente de la ruta.
    - `os.path.dirname(path)`: Obtener el nombre del directorio de una ruta.
    - `os.path.getsize(path)`: Obtener el tamaño de un archivo en bytes.
    - `os.path.getmtime(path)`: Obtener la hora de la última modificación de un archivo (`timestamp`).
    - `os.path.getatime(path)`: Obtener la hora del último acceso de un archivo (`timestamp`).
2. Gestión de Rutas y Variables de Entorno
    - `os.sep`: Separador de ruta para el sistema operativo actual. Aunque `os.path.join` es preferible, conocer `os.sep` puede ser útil.
    - `os.extsep`: Separador de extensión de archivo (usualmente .).
    - `os.pardir`: Referencia al directorio padre (..).
    - `os.curdir`: Referencia al directorio actual (.).
    - `os.getenv(key, default=None)`: Obtener el valor de una variable de entorno. Esto es útil para configurar scripts con información sensible (como claves API) sin codificarla directamente.
    - `os.putenv(key, value)`: Establecer el valor de una variable de entorno.
3. Ejecución de Comandos del Sistema
    - `os.system(command)`: Ejecutar un comando shell. Útil para interactuar con programas externos o comandos del sistema operativo (como `ping`, `ipconfig`, etc.). Ten en cuenta que es menos seguro y flexible que `subprocess`.
    - `os.startfile(path)` (Solo Windows): Abrir un archivo con la aplicación asociada.
4. Información del Sistema Operativo
    - `os.name`: Nombre del sistema operativo dependiente. Por ejemplo, '`posix`' para Linux/macOS y 'nt' para Windows. Útil para ejecutar código específico para cada sistema.
    - `os.cpu_count()`: Número de CPUs en el sistema.
    - `os.getlogin()`: Nombre del usuario logueado.
5. Procesos (Nociones Básicas)
Aunque para automatización avanzada de procesos se usa más la librería `subproces`s, es bueno conocer estas funciones básicas:
    - `os.getpid()`: Obtener el ID del proceso actual.
    - `os.getppid()`: Obtener el ID del proceso padre.