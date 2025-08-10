Las listas de compresión en Python, son un método eficaz para poder hacer listas avanzadas en una misma sola línea de código. Estos nos ayudara en el tema de practicidad y estética a nuestro código.

# Ejemplo 1:

Crear una lista con las letras de una palabra:

```python
lista = []
>>> for letra in "perro":
...     lista.append(letra)
... print(lista)
...
['p', 'e', 'r', 'r', 'o']
```

Ahora con la lista de compresión:

```python
lista = [letra for letra in "perro"]
```

# Ejemplo 2:

Crear una lista con potencias de 2 de los primeros 10 

```python
>>> lista = []
>>> for n in range(0, 11):
...     lista.append(n ** 2)
... print(lista)
... 
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

Ahora con la lista de compresión:

```python
ista = [n ** 2 for n in range(0, 11)]
>>> print(lista)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
---
# Resumen 
Las listas de compresión es una forma o método de hacer acciones de operación en tuplas, listas y hasta en diccionarios. Se pueden crear nuevas listas o acciones con esta.
## Sintaxis
```
lista = [iteracion bucle expresión]
```
## Por ejemplo una lista que vaya agregando un conteo
Imaginemos un conteo de 8 a 18:
```python
lista = [e for e in range(8, 19)]

print(lista) # Salida: [8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18]
```
