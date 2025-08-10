# `os.mkdir(path, mode=0o777)` y `os.makedirs()`

Es una función que nos permite crear un nuevo directorio (carpeta) en tu sistema de archivos.

## ¿Cómo funciona?

La función `os.mkdir()` toma dos argumentos principales:

- `path`(obligatorio): Es una cadena de texto que especifica la **ruta del directorio que deseas crear**: Puede ser:
    - Una **ruta absoluta**: La ruta completa de la raíz del sistema.
    - Una **ruta relativa**: La ruta en relación con el directorio.
- `mode` (opcional, por defecto `0o777`): Esta argumento o parámetro es para establecer los permisos de directorio:
    - `0o777`: Este es el valor por defecto y significa que el propietario, el grupo y otros usuarios tienen permisos completos (lectura, escritura y ejecución). En la mayoría de los casos, especialmente en Windows, no necesitarás modificar este valor a menos que estés trabajando en un entorno Linux/MacOS donde la gestión de permisos es más estricta y crucial para la seguridad.
    - **Ejemplos comunes** en sistemas Unix/Linux:
        - `0o755`: Propietario con permisos completos, grupo y otros solos con lectura y ejecución.
        - `0o700`: Solo el propietario tiene permisos completos, nadie más.
    - **Notas importantes en Windows**: En Windows, el argumento `mode` es ignorado en gran medida y los permisos se gestionan de forma diferente (a través de ACLs). Sin embargo, la función sigue requiriéndolo, por lo que usar el valor por defecto `0o777` es lo habitual y no causará problemas.

---

## Ejemplo:

```bash
import os

sub_carpeta = "imagenes"

if not os.path.exists(sub_carpeta):
    os.mkdir(sub_carpeta)

os.chdir(sub_carpeta)
print(f"estamos en {os.getcwd()}")
```

1. Como podemos ver, primero se asigna el nombre en una variable, que también actuara como ruta relativa para crear nuestro directorio.
2. Después se hace una comprobación con una sentencia lógica con el fin de saber si existen el directorio para no remplazarlo que cree otra copia usando la función `not.path.exists(<carpeta>)` .
    1. En caso de que no, usamos nuestra función para crear nuestro directorio `os.mkdir(<carpeta>)` .
3. Lo siguiente es que nos metemos dentro del subdirectorio usando `os.chdir()` 
4. Imprimimos nuestra dirección para comprobar que estamos dentro de nuestro directorio comprobado.

## ¿Para qué sirve en la automatización?

1. **Organizar la salida:** Si tu script de automatización genera reportes, logs, imágenes o cualquier tipo de archivo, es común querer guardarlos en una carpeta específica para mantener el orden.
2. **Crear entornos de trabajo:** Puedes configurar estructuras de directorios para proyectos nuevos, donde carpeta tiene un propósito definido (por ejemplo, `data`, `scripts`, `output`, `logs`)
3. **Preparar ubicaciones temporales**: Antes de descargar o procesar archivos, puede crear carpetas temporales donde se almacenarán los datos intermedios.
4. **Generación de copias de seguridad**: Crear una nueva carpeta con la fecha actual para almacenar copias se seguridad. 

## Diferencias clave con `makedirs()`:

Es crucial entender que `os.mkdir()` **Solo puede crear el último directorio en la ruta especificada.** Si alguno de los directorios padres en la ruta no existe, `os.mkdir()` lanzara un `FileNotFoundError`.

Resumiéndolo mejor `os.mkdir()` crea una directorio solo una vez asegurando que su directorio padre exista. Mientras que `os.makedirs()` se encarga de crear toda una jerarquía completa.

---

# `os.rmdir(path)`

Esta función de la librería OS nos permite el poder de eliminar directorios existentes. Sin embargo, tiene una restricción muy importante **solo pueda eliminar directorios que estén completamente vacíos.**

## ¿Cómo funciona?

La función `os.rmdir()` toma un único argumento: `path`.

- `path`: Esta es una cadena de texto que especifica la **ruta que deseas eliminar** que puede ser una ruta absoluta o relativa.

## ¿Para qué se puede usar en la automatización?

1. **Limpieza de directorios temporales vacíos:** Si tu script crea carpetas temporales para almacenar archivos intermedios y, una vez que esos archivos se han procesado o movida, la carpeta queda vacía.
2. **Mantenimiento de estructura de directorios:** En escenarios donde se crean y eliminan directorios forma controlada y se garantiza que estén vacíos antes de la eliminación. 

---

# `os.remove(path) / os.unlink(path)`

Ambas funciones sirven para **eliminar un archivo (file)** del sistema de archivos. Son el equivalente a mover un archivo a la papelera.

## ¿Por qué dos nombres para la misma cosa?

La razón por la que existen `os.remove()` y `os.unlink()` es histórica y se relaciona con el origen de los sistemas operativos Unix.

- `unlink()`: Es el nombre tradicional de la llamada al sistema POSIX (un estándar de sistemas operativos Unix) para eliminar un archivo.
- `remove()`: Es un nombre más intuitivo y más alineado con el estándar C `removes()`, que también se usa para eliminar archivos.

## ¿Cómo funciona?

Pues solo recibe un parámetro, que es una ruta relativa o absoluta.

## Por ejemplo:

Tenemos esta serie de archivos dentro de nuestro directorio actual:

```bash
documento.txt        eliminar_archivos.py imagene.png          tablas.cvc           textos.txt          tablas.cvc           textos.txt
```

Y queremos hacer un script para eliminarlas, para eso esta:

```bash
import os

lista_archivos = os.listdir(path=".") # Primero se visualizan los archivos 
print(lista_archivos)

for i in lista_archivos:
    os.rmdir(i)
```

1. Lo que pasa primero es que en lista todo los archivos de nuestro directorio actual en una variable
2. Después hacemos un bucle en la que cada vuelva de cada elemento `i` vamos a eliminarlo para eliminar todo los archivos de nuestro directorio actual.

## Para que funcionaria de automatización

1. **Limpieza de archivos temporales:** Si tú script genera archivos intermedios que ya nos necesarios después de un procesamiento, puede eliminarlo.
2. **Archivos de log antiguos:** Para purgar logs que han alcanzado una cierta antigüedad o tamaño.

---
# Resumen
- **`os.mkdir(path)`**:
    - Crea un **único directorio**. Si los directorios padres no existen, lanza un error.
    - Ejemplo:
        ```python
        if not os.path.exists("nueva_carpeta"):
            os.mkdir("nueva_carpeta")
        ```
- **`os.makedirs(path)`**:
    - Crea **toda la jerarquía de directorios** (padres incluidos).
    - Ejemplo:
        ```python
        os.makedirs("ruta/con/subcarpetas")  # Crea todas las carpetas necesarias
        ```
- **`os.rmdir(path)`**:
    - Elimina un **directorio vacío**. Si no está vacío, lanza error.
    - Ejemplo:
        ```python
        os.rmdir("carpeta_vacia")
        ```
- **`os.remove(path)` / `os.unlink(path)`**:
    - Elimina **archivos** (no directorios).
    - Ejemplo:
        ```python
        os.remove("archivo.txt")  # Elimina el archivo
        ```
        