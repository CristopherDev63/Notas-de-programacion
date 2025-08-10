La función “`lambada`” es una función que se puede encontrar en Python, Javascript, C++ y otros lenguajes de programación. 

Se le puede considerar como una función anónima (sin nombre) y compacta. 

# ⛳ Sintaxis

```python
lambda paramétros : expresion
```

Se ejecuta la expresión y devuelve el resultado.

# Ejemplos

- Agregue 10 al argumento `a` y devuelva el resultado:
    - En vez que hagamos toda una función que gasta lineas
    
    ```python
    def funcion(mensaje):
    	return mensaje == "hola mundo"
    
    print(funcion("hola mundo"))
    ```
    
    - Podemos usar la función lambda:
    
    ```python
    funcion = lambda mensaje : mensaje == "hola mundo"
    
    print(funcion("hola mundo"))
    ```
    

Esta forma de escribir funciones simples nos ayuda demasiado en el tema de estética y compresión de código.

Aveces `lambda` no recibe parámetros y se pueda quedar sin ningún argumento:

```python
import os 

limpiar_pantalla = lambda : os.system("clear")

limpiar_pantalla()
```

---

Otra cosa que podemos hacer es el poder de hacer funciones que nos pide valores más de dos veces.

Por ejemplo:

```python
>>> def mensaje(a):
...     return lambda n : a + n
... mensaje_uno = mensaje("hola ")
... print(mensaje_uno("mundo"))
... 
hola mundo
```

---
# Resumen
Las funciones de python Lambda, son funciones especiales para crear simples funciones de una sola línea sin gastar muchas líneas de código.
## Sintaxis
```python
funcion = lambda parametros... : retorno y acción de la función
```
## Ejemplo
```python
contrasena_secreta = lambda contraseña : contraseña == "soda stereo"
respuesta = input("Dame la contraseña secreta por favor: ")

print(f"La contraseña secreta esta {"correcta" if contrasena_secreta(respuesta) else "incorrecta"}")
```