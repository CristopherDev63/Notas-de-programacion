### ✅ **Cómo pensar en un proyecto desde cero**

Imagina que tu idea es _"Crear un sistema de copias de seguridad profesional"_. El flujo sería:

#### **1. Define el problema y objetivo**

- Problema: _Los usuarios no tienen una forma sencilla de automatizar copias de seguridad personalizadas._
    
- Objetivo: _Desarrollar una herramienta que haga copias automáticas, configurables, comprimidas y seguras._
    

#### **2. Lista los requisitos (funcionales y no funcionales)**

- **Funcionales**:
    
    - Seleccionar carpeta origen y destino.
        
    - Programar copias (diarias, semanales).
        
    - Comprimir en ZIP.
        
    - Mostrar logs.
        
    - Recuperar copias.
        
- **No funcionales**:
    
    - Compatible con Windows/Linux/Mac.
        
    - Interfaz CLI fácil de usar.
        

#### **3. Define las características (mínimas vs. extras)**

- **MVP (mínimo viable)**: Copia manual con ZIP y logs.
    
- **Extras**: Interfaz gráfica, notificaciones, integración con la nube.
    

#### **4. Haz un diagrama rápido** (Arquitectura)

- **Módulo 1:** Gestión de rutas y validación.
    
- **Módulo 2:** Lógica de copia y compresión.
    
- **Módulo 3:** CLI con `argparse`.
    
- **Módulo 4:** Logs y reportes.
    

#### **5. Planifica en tareas pequeñas**

Ejemplo en orden:

-  Crear función para listar directorios.
    
-  Crear función para copiar y comprimir.
    
-  Añadir argumentos con `argparse`.
    
-  Implementar logs.
    
-  Probar en Linux y Windows.
    

#### **6. Define entregables**

- Script funcional.
    
- README con instrucciones.
    
- Opcional: ejecutable (.exe o .app).