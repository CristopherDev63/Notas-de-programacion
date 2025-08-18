# `os.isdir()`

Es una función parecida a `os.path.exists` o `os.path.isfile()` que básicamente lo que hace es saber de la existencia de un directorio nada más (no archivos ni rutas, solo directorios).

## ⛳ Sintaxis

```python
os.path.isdir(ruta)
```

- **Retorna**:
    - `True`: Si la ruta existe y es un directorio.
    - `False`: Si no existe, es un archivo, o no es un directorio.

## 🔍 Por ejemplo

```python
import os 

directorio = "documentos"

if os.path.isdir(directorio):
    print(f"El directorio {directorio} si existe")
else:
    print(f"El directorio {directorio} no existe")
```

*Tratamos de saber que si el directorio “documentos” existe.*

## ❓¿Por qué es útil en la automatización?

1. **Validar rutas antes de operar:**
    - Evita errores al intentar crear un directorio que ya existe.
    - Previene operaciones inválidas (como tratar de leer una carpetas como archivo).
2. **Filtrar directorios en operaciones masivas:**
    - Al listar un directorio, separa subcarpetas de archivos.
3. **Garantizar estructuras de proyectos:**
    - Verifica si existen carpetas esenciales (como `data/` o `logs/`) antes de ejecutar un script.

---

# `os.path.split()`

Es una función que nos ayuda dividir una ruta de un archivo o directorio en dos partes. *Básicamente la versión contraría de `os.path.join`*:

1. **El directorio padre** (todo lo que va antes del último separador `/` o `\`).
2. **El nombre base** (el archivo o carpeta final)

## ⛳ Sintaxis

```python
directorio, nombre_base = os.path.split(ruta)
```

En automático, la función devuelve dos resultados en las que se almacenan en las dos variables ya antes declaradas.

## 🔍 Ejemplos:

### 1️⃣ Ejemplo 1: Ruta de un archivo

```python
import os 

ruta = "documentos/informes/octubre/informe1.txt"

ruta_sola, archivo = os.path.split(ruta)

print(ruta_sola)
print(archivo)
```

### 2️⃣ Ejemplo 2: Ruta de un directorio:

```python
import os

ruta_comleta = "documentos/informes/octubre"

ruta_completa_final, directorio = os.path.split(ruta_comleta)
```

## ❓¿Por qué es útil en la automatización?

1. **Extraer nombres bases sin la necesidad de manipular cadenas de texto.**
2. **Obtener el directorio padre** para poderlo usar a nuestro antojo.
3. **Trabajar con rutas dinámicas** en scripts multiplataforma.

---

# `os.path.basename(path)`

Es una función que sirve para obtener el texto del directorio con su extensión ignorando la ruta padre de este. También puede servir para saber el nombre de la última carpeta, ignorando la ruta padre.

## ⛳ Sintaxis

```python
import os

ruta = "documentos/programas/main.exe"

print(os.path.basename(ruta)) # Imprime "main.exe"
```

*Como podemos ver separa la ruta y el nombre del archivo con su extensión que es `main.exe` que se imprime en la pantalla.*

En caso de una última carpeta:

```python
ruta = "informes/cuatrimestre/octubre"

print(os.path.basename(ruta)) # Imprime "octubre"
```

## ❓¿Por qué es útil en la automatización?

1. **Extraer nombres de archivos** para procesarlos individualmente. 
2. **Renombrar archivos** sin afectar su ubicación original.
3. **Logging** **o reportes**: Mostrar solo el nombre del archivo en mensaje.

---

# `os.path.split(path)`

Es una función que solo divide la ruta en dos partes:

- **Head(cabeza)**: Todo lo que va antes del último separador(`\` o `/`)
- **Tail(cola):** El último componente de la ruta (archivo o carpeta)

## ⛳ Sintaxis básica

```python
head, tail = os.path.split(ruta)
```

---
# Resumen
 **1. Verificar directorios con `os.path.isdir()`**
- **Propósito**: Confirma si una ruta es un **directorio**.
- **Ejemplo**:
    ```python
    if os.path.isdir("carpeta"):
        print("Es una carpeta válida.")
    ```
- **Usos clave**:
    - Filtrar carpetas en operaciones masivas (ej.: `os.listdir()`).
    - Validar estructuras de proyectos (ej.: asegurar que existe `data/`).
---
**2. Dividir rutas con `os.path.split()`**
- **Propósito**: Separa una ruta en dos partes:
    - **Head**: Directorio padre.
    - **Tail**: Nombre del archivo/carpeta final.
- **Ejemplo**:
    ```python
    dir_padre, archivo = os.path.split("ruta/archivo.txt")  # dir_padre="ruta", archivo="archivo.txt"
    ```
- **Usos clave**:
    - Extraer nombres de archivos sin manipulación manual de strings.
    - Obtener rutas padre para crear estructuras dinámicas.
---
 **3. Obtener nombre base con `os.path.basename()`**
- **Propósito**: Extrae el último componente de una ruta (archivo o carpeta).
- **Ejemplo**:
    ```python
    nombre = os.path.basename("ruta/archivo.txt")  # "archivo.txt"
    ```
- **Usos clave**:
    - Renombrar archivos sin modificar su ubicación.
    - Logging simplificado (mostrar solo nombres de archivos).