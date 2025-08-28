## ✅ 1. **`Counter`** [[8. Counter - El Rey del conteo]]

- **Qué es:** Un contador de elementos en un iterable.
    
- **Por qué importa:** Es la forma más rápida y clara de contar frecuencias, algo que se usa en problemas clásicos como:
    
    - **Anagramas**
        
    - **Conteo de caracteres o palabras**
        
    - **Algoritmos de búsqueda**

**Ejemplo:**

`from collections import Counter  texto = "abracadabra" contador = Counter(texto) print(contador)  # {'a': 5, 'b': 2, 'r': 2, 'c': 1, 'd': 1}`

---

## ✅ 2. **`defaultdict`**

- **Qué es:** Un diccionario que **no lanza error si la clave no existe**, asigna un valor por defecto.
    
- **Por qué importa:** Evita escribir `if key not in dict:` en bucles, útil para:
    
    - **Agrupar datos**
        
    - **Contadores personalizados**
        
    - **Grafos (listas de adyacencia)**
        

**Ejemplo:**

`from collections import defaultdict  grafo = defaultdict(list) grafo['A'].append('B') grafo['A'].append('C') print(grafo)  # {'A': ['B', 'C']}`

---

## ✅ 3. **`deque`**

- **Qué es:** Una **doble cola**, más eficiente que `list` para insertar y quitar en los extremos.
    
- **Por qué importa:** Se usa en:
    
    - **BFS (Breadth-First Search)**
        
    - **Sliding Window**
        
    - **Colas y pilas**
        

**Ejemplo:**

`from collections import deque  cola = deque([1, 2, 3]) cola.append(4)       # Añade al final cola.appendleft(0)   # Añade al inicio cola.pop()           # Quita del final cola.popleft()       # Quita del inicio`

---

## ✅ 4. **`namedtuple`**

- **Qué es:** Una tupla con **nombres para los campos**.
    
- **Por qué importa:** Te ayuda a crear estructuras ligeras y legibles sin usar clases completas, como:
    
    - **Puntos en un plano**
        
    - **Estados en algoritmos**
        
    - **Datos inmutables**
        

**Ejemplo:**

`from collections import namedtuple  Punto = namedtuple('Punto', ['x', 'y']) p = Punto(2, 3) print(p.x, p.y)  # 2 3`

---

## ✅ 5. **`OrderedDict`** (menos importante en Python 3.7+, porque dict ya mantiene orden)

- **Qué es:** Diccionario que mantiene el orden de inserción (antes de que dict lo hiciera).
    
- **Útil para:** Algunos algoritmos que requieren orden estable.
    

---

### 🔥 Prioridad para algoritmos:

1. `deque` → para colas, pilas y BFS.
    
2. `Counter` → para conteo eficiente (frecuencias, histogramas).
    
3. `defaultdict` → para grafos y agrupaciones dinámicas.
    
4. `namedtuple` → para estructuras inmutables.
    
5. `OrderedDict` → opcional.