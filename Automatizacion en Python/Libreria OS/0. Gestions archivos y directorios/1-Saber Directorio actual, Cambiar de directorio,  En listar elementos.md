# `os.getcwd()`

Es una función super útil de la librería `os` de Python que nos permite saber en qué **directorio actual** está trabajando tu script.

## ¿Como se usa?

Simplemente la llamas y te devolverá una cadena (un `string`) con la ruta completa del directorio actual.

```python
import os

# guardar la ruta en un variable
directorio_actual = os.getcwd()

print(directorio_actual)

```

---

## ¿Para qué es útil en la automatización?

1. **Saber dónde estás parado**: Antes de manipular archivos o carpetas, es crucial saber dónde se está ejecutando tu script.
2. **Construir rutas absolutas**: A menudo, querrás crear o acceder archivos en relación con la ubicación de tu script.
3. **Depuración**: Si tu script no encuentra un archivo que esperas que encuentre, la función antes mencionada es una de las primeras cosas que puedes usar para verificar si el script está buscando en el lugar correcto.

---

# `os.chdir(path)`

Es una función para moverse a un directorio dentro de una subcarpeta

## ¿Como funciona?

Esta función solo toma un solo argumento que es `path` que es una cadena texto que representa la ruta al directorio al que quieres moverte o cambiar.

- Puede ser una **ruta absoluta**: La ruta completa desde la raíz del sistema de archivos `/home/usuario/documentos` en Linux/macOS, o `C:\\Users\\TuUsuario\\Documentos` en Windows.
- O puede ser una ruta **relativa**: que solo es el directorio de trabajo actual de tu script (ej., `mi_subcarpeta`, `otra_carpeta`)

### Ejemplo:

```python
import os # importamos la libreria

sub_carpeta = "imagenes" # Guardamos el nombre de la carpeta

if not os.path.exists(sub_carpeta): # Se verifica si la carpeta "images" existe con os.path.exists()
	os.makedirs(sub_carpeta) # Con la función makedirs sirve para crear directorios y colocamos el nombre de nuestra subcarpeta

os.chdir(subcarpeta) # Ahora con la función aprendemos
print(f"estamos en el directorio: {os.getwcd}")

```

Vamos a explicar lo que hicimos aquí:

1. Primero importamos la librería os.
2. Hacemos una variable llamada `sub_carpeta` en donde guardaremos el nombre de nuestro directorio y también actuara como ruta de directorio relativa.
3. Hacemos un comprobación lógica usando la función de la librería os que nos deja usar una función llamada `os.path.exists` que sirve para saber si existe un directorio.
4. Si devuelve un valor falso nuestra comprobación lógica, haremos que este cree una directorio nuevo usando la función de os llamada `makedirs()` que nos deja crear un directorio recibiendo el parámetro de una ruta, y como el `subcarpeta` actuara también como nombre y ruta relativa.
5. Después se va a mover por la carpeta `imagenes` ya creada por la sentencia lógica anterior usando la función vistas en esta sección usando a función `os.chdir()` que va a necesitar un parámetro como ruta, que se va a usar la variable `sub_carpeta` que ya mencionamos como dos veces, actuara como nombre de directorio o ruta relativa.
6. Y por último vamos imprimir nuestra ruta actual con el proposito de comprobar qué estamos dentro de la ruta `imagenes`.
Salida de consola:

```bash
cristopherrobledo in ~/Documents/programacion/apredizaje/pythonOs λ python3 practica2.py
estamos en /Users/cristopherrobledo/Documents/programacion/apredizaje/pythonOs/imagenes

```

---

## ¿Para qué es útil en la automatización?

1. **Consistencia de rutas**: Cuando tu script necesita operar sobre muchos archivos que están dispersos en una estructura de directorios. En lugar de construir rutas absolutas complejas para cada archivo, puedes `chdir` al directorio que contiene y luego usar rutas relativas simples.
2. **Procesamiento por lotes**: Si tienes un script que procesa un grupo de archivos en una carpeta, puedes `chdir` esa carpeta, procesar los archivos, y luego `chdir` a la siguiente carpeta, y así sucesivamente.

---

# `os.listdir(path=".")`

Es una función que nos permite **obtener una lista de todos los archivos y carpetas (subdirectorios) que se encuentran directamente dentro de un directorio específico.**

## ¿Cómo funciona?

La clave está en el argumento `path`:

- `path`: Es la ruta del directorio cuyo contenido quieres listar.
    - Si no especificas un `path`, o si usas `"."`(un punto), `os.listdir()` listará el contenido del **directorio de trabajo actual** de tu script. Este es el comportamiento por defecto y el más común cuando ves `os.listdir(path=".")`.
    - Si proporcionas una ruta diferente (ya sea absoluto cómo `/home/usuario/documento)` o relativa cómo `mi_subcarpeta`), listará el contenido de ese directorio especifico.

## Por ejemplo:

```python
import os

contenido_actual = os.listdir(path=".")

for n, elemento in enumerate(contenido_actual):
    print(f"{n} {elemento}")

```

Salida de consola:

```bash
cristopherrobledo in ~/Documents/programacion/apredizaje/pythonOs λ python3 practica3.py
1 practica3.py
2 practica2.py
3 imagenes
4 practica1.py

```

---

# Para que sirve en la automatización?

1. **Explorar directorios**: Es el primero paso para saber qué archivos o subcarpetas tienes en lugar determinado.
2. **Procesar archivos por lotes**: Si necesitas, por ejemplo, leer todos los archivos `.txt` de una carpeta, primero listarías el contenido con la función vista y luego filtrarías los archivos `.txt`.
3. **Verificar la existencia de archivos/carpetas**: Aunque `os.path.exists()` es más directo, puedes usar `os.listdir()` para ver si un nombre específico aparece en una lista.

---
# Resumen
1. **`os.getcwd()`**
    - **Función**: Obtiene la ruta del directorio actual donde se ejecuta el script.
    - **Uso**:
        ```python
        import os
        print(os.getcwd())  # Ejemplo: "/ruta/actual"
        ```
    - **Utilidad**: Verificar ubicación, construir rutas absolutas y depurar errores de archivos.
2. **`os.chdir(path)`**
    - **Función**: Cambia el directorio de trabajo a la ruta especificada (absoluta o relativa).
    - **Uso**:
        ```python
        os.chdir("subcarpeta")  # Cambia a "subcarpeta"
        ```
    - **Utilidad**: Mantener consistencia en rutas y procesar archivos en lotes dentro de directorios específicos.
3. **`os.listdir(path=".")`**
    - **Función**: Lista archivos y subcarpetas en un directorio (por defecto, el actual).
    - **Uso**:
        ```python
        
        for archivo in os.listdir():  # Lista el contenido actual
            print(archivo)
        ```
    - **Utilidad**: Explorar directorios, procesar archivos por lotes (ej., filtrar `.txt`) y verificar existencia de elementos.jjkk