Es una función que nos permite hacer una comprobación lógica de que si un texto termina con una terminación al final sin importar el orden.

# Sintaxis
``` python
string.endswith(values, start, end)
```
## Parámetros 
- `values`: Obligatorio. Se coloca para verificar si terminal con el nombre especificado. Este devuelve un resultado booleano.
- `start`: Opcional. Se encarga de colocar en entero que específica en qué posición se iniciará la búsqueda.
- `end`: Opcional. Es parecido a `start`solo que este este se encarga de colocar un entero para especificar el final de la búsqueda.
# Ejemplos
- **Comprobar si un archivo entra en una categoría**
``` python
extensiones_archivos = [".txt", ".docs", ".xml"]
ruta = "texto.docs"

for n , ext in enumerate(extensiones_archivos):
    if ruta.endswith(ext):
        print(f"Tu archivo {ruta} pertenece a la categorias de archivos")
 
```
- **Comprobar si un texto termina con *salchichas.* al final de un texto**
``` python
texto = "Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto de relleno est√°ndar de las industrias desde el a√±o 1500, cuando un impresor (N. del T. persona que se dedica a la imprenta) desconocido us√≥ una galer√≠a de textos y los mezcl√≥ de tal manera que logr√≥ hacer un libro de textos especimesalchichas." 

if not texto.endswith("salchichas."):
    print("Lo siento, tu texto no termina con una punto")

```