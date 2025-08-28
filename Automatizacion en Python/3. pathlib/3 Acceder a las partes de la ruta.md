# 1. Saber el nombre de nuestro archivo o directorio `name`
Es `.name` es una constante o propiedad que nos puede devolver el nombre del archivo o directorio. Esta propiedad es lo equivalente de `os` a `basename()` o la expresión `path.splitex` de la misma librería.
## Sintaxis
``` python
from pathlib import Path 

p = Path("directorio/archivo.txt")
print(p.name) # Salida: archivo.txt
```
### Detalles importantes:
- `p.name`: Solo el último componente de la ruta (archivo o carpeta).
---
# 2. Saber la el nombre de archivo sin extensión 
Existe una forma de saber el nombre solo sin la extensión de un archivo. Esto se hace con la propiedad o constante solo devuelva el nombre nada más.
## Sintaxis
``` python
print(p.stem) # Salida: archivo
```

---
# 3. Saber la extensión de un archivo sin nombre
Para solo saber la extensión debemos de usar al constante o propiedad `p.suffix` que nos dará la extensión con el punto que comienza.
``` python
print(p.suffix) # salida: .tar
```
Esta función solo devuelve una sola extensión en caso de que tenga dos `tar.gz` -> `.gz`. **Pero en caso de queramos mostrar todas las extensiones se usa la función `suffixes`**:
``` python
print(p.suffixes) # salida: ['.tar', '.gz']
```
En caso de nuestro archivo no tenga extensión, devolverá una cadena de texto vacía.

---
# Saber el directorio padre de nuestra ruta 
Para que nosotros podamos saber el último directorio o el directorio padre se usa la operación `Path` `parent`. Hay que entender que cuando en la ruta **hau un archivo, ese devolverá los directorios padres**. Mientras que si **es una ruta de puras directorios, devolverá la ruta padre, ignorando la ultima ruta.**
## Sintaxis
```python
# Ruta de archivo 
p = Path("archivo/documento/text.txt")
print(p.parent) # Salida: archivo/documento

# Ruta de directorios
p = Path("archivo/documento/imagenes/fotos")
print(p.parent) # Salida: archvio/documento/imagenes
```