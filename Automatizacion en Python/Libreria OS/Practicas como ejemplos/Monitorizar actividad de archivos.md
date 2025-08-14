Es un script automatizado que nos ayuda saber los ultimos accesos de hace 7 días de una lista de archivos.

---
# Explicación del código 
Primero se importa dos librerías o herramientas que nos ayudaran en estoy que es  `os` y `time` que nos ayudaran a usar leer archivos y saber comparar el tiempo de segundos. Y agregamos la herramienta más importante `datetime` que nos ayudara en el tema de formatear la fecha y hacerla visualmente mas entendible.
```python
import os, time
from datetime import datetime
```
código completo:
``` python
import os, time
from datetime import datetime

def archivos_recientes(directorio, dias=7):
    limite = time.time() - dias * 24 * 3600
    for archivo in os.listdir(directorio):
        ruta = os.path.join(directorio, archivo)
        if os.path.getatime(ruta) > limite:
            print(f"{archivo}: Accedido el {datetime.fromtimestamp(os.path.getatime(ruta))}")

if __name__ == "__main__":
    archivos_recientes(directorio="practicas")
```

### Explicación paso a paso
1. Se crea una una función que tendrán dos elementos de entrada cuando la llamemos:
	 - `directorio`: Es la ruta de los archivos a leer.
	 - `dias`: El limite de archivos a leer.
2. Se define una variable llamada `limite` que esta se encarga de restar los segundos restados con los días, las cantidad de horas en un día y los segundos de una hora en sí.
3. Un bucle lee cada archivos de la ruta `directorio` en la que leerá cada archivos haciendo un comparación lógica dentro:
	- Si un archivo que se lee el tiempo usando `getatime` se lleva es mayor a la variable `limite` establecido, esta imprimirá un mensaje de que el archivo a sido accesado tal fecha y hora.
	- En caso de que no se visualice el archivo se debe por que no esta dentro del limite establecido dentro de la variable `limite`.