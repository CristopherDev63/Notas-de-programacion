### **MÓDULO 1: FUNDAMENTOS PARA AUTOMATIZACIÓN**

1. **Variables y Entorno**
    
    - Declaración y uso de variables [[2. Declaración variables locales]]
        
    - Variables de entorno (`PATH`, `HOME`, `USER`) 
        
    - Exportación para scripts hijos
        
2. **Argumentos y Parámetros**
    
    - `$1`, `$2`, ..., `$9` (argumentos)
        
    - `$#` (número de argumentos)
        
    - `$@` y `$*` (todos los argumentos)
        
3. **Salidas y Estados de Salida**
    
    - `exit codes` (`0` = éxito, `1-255` = error)
        
    - `$?` (capturar exit code del último comando)
        

---

### **MÓDULO 2: ESTRUCTURAS DE CONTROL**

1. **Condicionales**
    
    - `if-then-else` (con `[ ]` o `[[ ]]`)
        
    - Operadores: `-f` (archivo), `-d` (directorio), `-z` (cadena vacía)
        
    - Comparaciones: `=`, `!=`, `-eq`, `-lt`, `-gt`
        
2. **Bucles**
    
    - `for in` (iterar sobre listas o archivos)
        
    - `while` y `until` (ejecutar mientras se cumpla condición)
        
    - `break` y `continue`
        
3. **Case/Esac**
    
    - Estructura `case` para múltiples opciones
        

---

### **MÓDULO 3: MANEJO DE ARCHIVOS Y DIRECTORIOS**

1. **Operaciones Básicas**
    
    - Crear, mover, copiar, eliminar (`mkdir`, `mv`, `cp`, `rm`)
        
    - Verificar existencia (`test -f archivo`)
        
2. **Búsqueda y Filtrado**
    
    - `find` (búsqueda por nombre, tipo, tamaño, fecha)
        
    - `grep` (filtrado por contenido)
        
    - `xargs` (ejecutar comandos con resultados de búsqueda)
        
3. **Process Substitution y Pipes**
    
    - `|` (pipe para redirigir salida)
        
    - `>` (sobrescribir archivo), `>>` (append)
        
    - `$(comando)` (capturar salida de comando)
        

---

### **MÓDULO 4: HERRAMIENTAS ESENCIALES**

1. **awk**
    
    - Extracción de columnas (`awk '{print $1}'`)
        
    - Filtrar lineas por patrón o condición
        
2. **sed**
    
    - Reemplazo de texto (`sed 's/old/new/g'`)
        
    - Eliminar lineas o imprimir por número
        
3. **cut, sort, uniq, wc**
    
    - Manipulación de texto/conteo de lineas
        

---

### **MÓDULO 5: FUNCIONES Y MODULARIZACIÓN**

1. **Funciones**
    
    - Definición y llamada
        
    - Pasar argumentos a funciones
        
    - Retornar valores (usando `echo` o exit codes)
        
2. **Scripts Modulares**
    
    - Importar funciones desde otros scripts (`source`)
        
    - Scripts reutilizables
        

---

### **MÓDULO 6: PROGRAMACIÓN DEFENSIVA**

1. **Manejo de Errores**
    
    - `set -e` (terminar en error)
        
    - `set -u` (detectar variables no definidas)
        
    - `trap` (capturar señales y errores)
        
2. **Logging**
    
    - Redirigir `stdout` y `stderr` a archivos
        
    - Timestamps en logs (`date +"%Y-%m-%d %H:%M:%S"`)
        

---

### **MÓDULO 7: AUTOMATIZACIÓN PRÁCTICA**

1. **Backups**
    
    - Compresión (`tar`, `zip`)
        
    - Copia incremental con `rsync`
        
2. **Monitoreo**
    
    - Verificar uso de disco (`df`), memoria (`free`), procesos (`ps`)
        
    - Alertas por email (`mail` o `curl` a API)
        
3. **Programación de Tareas**
		    
    - `cron` y `anacron` (ejecución automática)