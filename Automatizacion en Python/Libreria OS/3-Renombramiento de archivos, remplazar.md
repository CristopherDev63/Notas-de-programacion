# `os.raname`

Es una función que nos ayuda a **renombrar archivos o directorios** y también puede moverlo a otra ubicación si la ruta de destino (`dst`) es diferente a la de origen (`src`).

## 🚏Parámetros

- `src` (*source*): Ruta actual del archivo o directorio que quieres renombrar/mover.
- `dst` (*destination*): Nueva ruta o nombre.

---

## 🎳Funciones

1. **Renombrar un archivo en el mismo directorio:**
    
    Cambiar el nombre del archivo sin moverlo. Por ejemplo cambiar el nombre de una carpeta 
    
    ```python
    os.raname("documentos", "docu")
    # el directorio "documentos" sera cambiando a "docu"
    ```
    
2. **Mover un directorio a otro** 
    
    Dijéramos que tenemos una `carpeta1` y `carpeta2`, y queremos mover `carpeta1` dentro de `carpeta2`.
    
    ```python
    os.rename("carpeta1", "carpeta2")
    ```
    

## ⚠️Posibles errores  y notas importantes

- `FileNotFoundError`: Si `src` no existe.
- `FileExistsError`: Si `dst` ya existe (en sistemas como Linux, no en Windows).
- `PermissionError`: Si no tienes permisos a modificar archivos.

### 🟩 Solución a errores comunes

- **Verifica si las rutas existen:**
    
    ```python
    if os.path.exists("docu"):
        os.rename("docu", "documentos")
    ```
    
    *En caso de que exista `docu` cambiarlo al nombre `documentos`.*
    
- **Sobreescribir en Windows:**
    
    En Windows, si `dst` existe, `os.rename` fallará. Usa `os.replace()` para sobreescribir.
    

### 🔍Ejemplo usando los excepciones

```python
import os 

# Renombrar achivo o directorio
try:
	os.rename("archivo.txt", "archivo_de_cris.txt")
except FileNotFoundError:
	print("El archivo origen no existe")
except PermissionError:
	print("No tienes permisos para modificar el archivo")
```

## 🎶Notas importantes

- **Entre sistemas operativos:**
    - En **Linux/macOS**, `dst` no puede existir (debes borrarlo primero).
    - En **Windows** `os.rename` fallará si `dst` existe, pero `os.replace()` funciona.
- **Rutas absolutas/relativas:**
    
    Usa `os.path.abspath()` para evitar problemas con rutas relativas.
    

---

## ⁉️¿Por qué es importante para la automatización?

1. **Organización automática de archivos**. Por Ejemplo: Renombrar archivos descargados o generados para mantener un orden consistente. 
2. **Procesamiento Batch de archivos.** Por ejemplo: renombrar archivos después de procesarlos.
3. **Renombrar/mover archivos masivamente** sin intervención manual, ahorrando horas de trabajo.
4. **Estandarizar nombres** (eliminar espacios, corregir formatos, agregar prefijos/sufijos).

---

# `os.replace()`

Es una función muy parecida a `rename` pero con diferentes en el manejo de archivos existentes.

## ⁉️¿Qué hace `os.replace()`?

- **Renombra o mueve** un archivo o directorio.
- **Sobreescribe el archivo destino** ya existe (a diferencia de `os.rename()`, que falla en Windows si el destino existe).
- Es ideal para operaciones de actualización segura de archivos.

## 🐊 Sintaxis básica

```python
import os
os.replace(src, dst)
```

- `src`: Ruta del archivo/directorio origen.
- `dst`: Ruta del archivo/directorio destino.

---

## 🔍 Ejemplo

- **Cambio de nombre**
    
    ```python
    import os 
    
    archivo_origen = "archivo_antiguo.txt"
    archivo_nuevo = "archivo_nuevo.txt"
    
    with open (archivo_origen, "w") as a:
        a.write("Hola mundo")
    
    os.replace(archivo_origen, archivo_nuevo)
    ```
    
- **Mover un archivo a otra carpeta**
    
    ```python
    import os
    
    # Crear directorio de destino si no existe
    os.makedirs("backup", exist_ok=True)
    
    # Mover archivo a la carpeta "backup" (sobreescribe si ya existe)
    os.replace("nuevo_nombre.txt", "backup/nuevo_nombre.txt") 
    ```
---
# Resumen
- **`os.rename(src, dst)`**:
    - Renombra o mueve archivos/directorios. **Falla si `dst` existe** (excepto en Windows).
    - Ejemplo:
        ```python
        
        os.rename("viejo.txt", "nuevo.txt")  # Renombra
        os.rename("carpeta1", "carpeta2")    # Mueve/renombra
        ```
- **`os.replace(src, dst)`**:
    - Similar a `rename`, pero **sobreescribe `dst` si existe** (ideal para Windows).
    - Ejemplo:
	    ```python
        os.replace("temp.txt", "backup/temp.txt")  # Mueve y sobrescribe
        ```
