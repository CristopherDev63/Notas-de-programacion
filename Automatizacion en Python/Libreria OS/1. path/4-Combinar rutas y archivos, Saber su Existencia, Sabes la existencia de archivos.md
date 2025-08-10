# `os.path.join()`

Es una función que nos ayuda combinar rutas relativas o absolutas, con un el nombre de un archivo, básicamente combinarlas para alguna función. **También puedes combinar varios parámetros, tanto rutas, directorios y archivos**.

## 🪙 Sintaxis

```python
ruta = "documentos/informes"
archivo = "texto.txt"
ruta_completa = os.path.join(ruta, archivo)
```

Salida:

```bash
documentos/informes/texto.txt
```

Con rutas, directorios y archivos:

```python
ruta_nueva = os.path.join("documentos/informes", "imagenes", "imagen1.jpg")
```

Salida:

```bash
documentos/informes/imagenes/imagen1.jpg
```

## ❓¿Por qué es útil para la automatización?

- **Multiplataforma**: Usa automáticamente el separado correcto(`/` o `\`) según el sistema operativo.
- **Manejo de Rutas Dinámicas:** Permite combinar partes de rutas (ej: directorios, nombres de archivos) si preocuparse por separadores duplicados o faltantes.
- **Legibilidad**: Organiza rutas de forma clara y mantenible, especialmente en proyectos con estructuras de directorios complejas.
- **Robustez**: Evita errores al concatenar cadenas de texto manualmente.
- Genera rutas para leer/escribir archivos en scripts de automatización.
- Moverse entre directorios de manera programática.
- Crear estructuras de carpetas dinámicas (ej: backups con fechas).

---

# `os.path.exists()`

Esta función sirve para saber o verificar si una ruta (archivo, directorio o enlace simbólico) existe en sistema archivos. Como parámetros recibir una ruta absoluta o relativa a verificar. Y como valor de retorno un resultado booleano (`True` si la ruta existe, `False` Si no existe o si hay errores de permisos)

## ⛳ Sintaxis

- **Verificar la existencia de un archivo:**
    
    ```python
    import os
    
    archivo = "hola_mundo.txt"
    
    if os.path.exists(archivo):
        print(f"El erchivo {archivo} si existe")
    else:
        print(f"El archivo {archivo} no existe")
    ```
    
- **Verificar existencia de un directorio:**
    
    ```python
    import os
    
    directorio = "imagenes/fotos_favoritas"
    
    if os.path.exists(directorio):
        print(f"El directorio {directorio} si existe")
    else:
        print(f"El directorio {directorio} no existe")
    ```
    
- **Antes de operaciones críticas** (evitar errores):
    
    ```python
    import os
    
    if os.path.exists("hola_mundo.txt"):
        with open("hola_mundo.txt", "r") as a:
            print(a.read())
    else:
        print("El archivo no existe")
    ```
    

## ❓¿Pará que es útil?

1. **Evita Errores Críticos**. Por ejemplo si un script intenta abrir un archivo que no existe, Python lanzará un error (`FileNotFoundError`).
2. **Control de flujo inteligente**. Permite tomar decisiones basadas en la disponibilidad de archivos/directorios.
3. **Validación de Entradas.** En un scripts que reciben rutas dinámicas (ej: desde usuarios o APIs), asegura que la ruta es válida antes de operar con ella.
4. **Optimización de Recursos**. Evita procesamiento innecesario. Por ejemplo, no intentar copiar un archivo si ya existe en el destino. 
5. **Robustez Multiplataforma.** Funciona igual en Windows, Linux y macOS, crucial para scripts que se ejecutan en distintos entornos.

---

# `os.path.isfile(path)`

Es una función **que nos permite saber de la existencia de un archivo** (no de un directorio, enlace simbólico, etc.**)**. Como primer parámetro solo recibe el nombre del archivo a comprobar su existencia.

## ⛳ Sintaxis

```python
import os

archivo = "hola_mundo.txt"

if os.path.isfile(archivo):
	print("Este archivo ya esta creado")
else:
	print("Este archivo no esta creado")
```

## 🔍 Ejemplo

```python
import os

ruta_archivo = "documentos"
archivo = "archivo.txt"

if not os.path.exists(ruta_archivo):
    os.mkdir(ruta_archivo) # Se crea el directorio
   
os.chdir(ruta_archivo) # Nos vemos dentro de directorios

def saber_existencia_archivo():
    if os.path.isfile(archivo):
        print("Ya esta creado, no es necesario crear otro")
    else:
        print("No estaba creado, ya fue creado uno nuevo")
        with open(archivo, "w") as a:
         a.write("Hola mundo")

if __name__ == "__main__":
   saber_existencia_archivo()
```

## ❓¿Por qué es útil en la automatización?

1. **Validación precisa de archivos**. Asegura que una ruta sea **exclusivamente de un archivo**, excluyendo enlaces simbólicos, directorios o dispositivos. Esto ayuda a controlar los errores (como por ejemplo leer directorios en vez de un archivo) 
2. **Prevención de fallos.** En un scripts que procesa datos (ETL, backups, análisis), garantiza que los análisis sean hacia archivos validos, para prevenir errores como `IsADirectoryError`.
3. **Filtrado preciso**: Nos puede ayudar en el tema de solo manejar archivos sin la necesidad de manipular directorios o rutas como confusión.
4. **Robustez multiplataforma:** Funciona en cualquier tipo de sistema operativo (MacOS, Linux y windows), sin depender de formatos como de ruta específicos (`\` vs `/`).

## 🆚 Diferencias entre `isfile` y `exists`

- `exists`: Verifica si una ruta existe (sin importa que si una ruta, directorio, archivo, etc.).
- `isfile`: Es más estricto y solo comprueba la existencia de un archivo regular.
---
# Resumen
1. **Combinar rutas con** `os.path.join()`**
	- **Propósito**: Une rutas de forma multiplataforma (usa `/` o `\` automáticamente).
	- **Ejemplo**:
	    ```python
	    ruta = os.path.join("carpeta", "subcarpeta", "archivo.txt")  # "carpeta/subcarpeta/archivo.txt"
	    ```
	- **Usos clave**:
	    - Evitar errores al concatenar strings manualmente.
	    - Crear rutas dinámicas para scripts multiplataforma.
2. **Verificar existencia con** `os.path.exists()`**
	- **Propósito**: Verifica si una ruta (archivo/directorio/enlace) existe.
	- **Ejemplo**:
	    ```python
	    if os.path.exists("ruta/archivo.txt"):
	        print("La ruta existe.")
	    ```
	- **Usos clave**:
	    - Validar rutas antes de operar (evitar `FileNotFoundError`).
	    - Controlar flujos de ejecución (ej.: crear carpetas solo si no existen).
3. **Distinguir archivos con** `os.path.isfile()`**
	- **Propósito**: Confirma si una ruta es un **archivo regular** (no directorio).
	- **Ejemplo**:
	    ```python
	    if os.path.isfile("documento.txt"):
	        print("Es un archivo válido.")
	    ```
	- **Diferencia con `exists`**:
	    - `exists`: Cualquier tipo de ruta.
	    - `isfile`: Solo archivos regulares.