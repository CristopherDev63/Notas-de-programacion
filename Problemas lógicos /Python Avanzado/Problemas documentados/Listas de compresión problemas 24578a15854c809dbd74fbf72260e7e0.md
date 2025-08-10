# Listas de compresión problemas

# 🟢 Nivel básico

1. **Cuadrados**
    1. **Enunciado:** Dada una lista de números `[1, 2, 3, 4, 5]` crea una nueva lista  con los cuadrados de cada número.
    2. **Código resuelto:**
        
        ```python
        >>> lista = [n ** 2 for n in [1, 2, 3, 4, 5]]
        >>> print(lista)
        [1, 4, 9, 16, 25]
        ```
        
    3. **Explicación**: Básicamente lo que tuve que hacer fue primero hacer una lista de compresión, dentro de esta tuve que hacer un bucle que vaya reguardando cada valor de la lista en la variable `n`, después de esto guardaba esa variable con una elevación de dos (ósea cuadrados). Y por último imprimimos en pantalla.
2. **Pares**
    1. **Enunciados:** Filtra los números pares de la lista **`[10, 15, 20, 25, 30, 35]`**.
    2. **Código:** 
        
        ```python
        >>> lista = [n for n in [10, 15, 20, 25, 30, 35] if n % 2 == 0]
        >>> print(lista)
        [10, 20, 30]
        ```
        
    3. **Explicación:** Primero por cada vuelva del bucle en la lista, se hace guarda cada valor de la lista dentro de `n` y esta hace un comprobación lógica que si **`n` residuo de 2, si da 0 hace que el valor `n`** se guarda en la lista.
3. **Longitud de palabras** 
    1. **Enunciado:** Dada la lista **`["hola", "mundo", "python"]`**, genera una lista con las longitudes de cada palabra.
    2. **Código:**
        
        ```python
        >>> lista = [len(l) for l in ["hola", "mundo", "python"]]
        >>> print(lista)
        [4, 5, 6]
        ```
        
    3. **Explicación:** Básicamente lo que pasa es que cada vuelta iteramos con `l` hace que guarde en forma de lista el numero de longitud de cada palabra.

---

# 🟡 Nivel intermedio

1. **Divisibles por 3 y 5**:
    - **Enunciado:** De la lista **`[15, 30, 45, 10, 12, 60]`**, extrae los números divisibles **tanto por 3 como por 5**.
    - **Código:**
        
        ```python
        >>> lista = [n for n in [15, 30, 45, 10, 12, 60] if n/5 == n//5 and n/3 == n//3]
        >>> print(lista)
        [15, 30, 45, 60]
        ```
        
    - Explicación:
        1. Primero hace un iteración `n` y después hace una comparación lógica usando la siguiente lógica:
            1. **Si (15 % 5 → 5) igual que (15 // 5 → 5) Y (15 % 3 → 3) igual que (15 // 3 → 3) → Cierto**
            2. **Si (30 % 5 → 5) igual que (30 // 5 → 5) Y (30 % 3 → 3) igual que (30 // 3 → 3) → Cierto**
            3. **Si (45 % 5 → 5) igual que (45 // 5 → 5) Y (145 % 3 → 3) igual que (15 // 3 → 3) → Cierto**
            4. **Si (60 % 5 → 5) igual que (60 // 5 → 5) Y (60 % 3 → 3) igual que (60 // 3 → 3) → Cierto**
            5. *Todo los de más da Falso.*
2. **Lista de tuplas:**
    - **Enunciado:** Combina las listas **`["a", "b", "c"]`** y **`[1, 2, 3]`** para obtener **`[("a", 1), ("b", 2), ("c", 3)]`**.
    - **Código:**
        
        ```python
        >>> lista_letras = ["a", "b", "c"]
        >>> lista_numeros = [1, 2, 3]
        >>> diccionario = list(zip(lista_letras, lista_numeros))
        >>> print(diccionario)
        [('a', 1), ('b', 2), ('c', 3)]
        ```