### **Módulo 2: Operaciones Básicas de Archivos (Automatización Rápida)**

#### **2.1. Copiar Archivos (`shutil.copy`)** [[1. Copiar Archivos]]
- Copiar archivos entre directorios.
- Sobrescribir archivos existentes automáticamente.
- Ejemplo: Backup diario de un archivo de configuración.
 
#### **2.2. Copiar Directorios (`shutil.copytree`)**[[2. Copiar directorios]]
- Copiar estructuras completas de carpetas.
- Manejar duplicados y permisos.
- Ejemplo: Clonar un proyecto a un directorio de backup.

#### **2.3. Mover Archivos/Directorios (`shutil.move`)** [[3. Mover archivos y directorios]]
- Mover y renombrar en una operación.
- Ejemplo: Organizar descargas automáticamente por extensión.

---
### **Módulo 3: Eliminación Automatizada**
#### **3.1. Eliminar Directorios con Contenido (`shutil.rmtree`)**[[4. Eliminar directorios]]
- Eliminar árboles de directorios completos.
- Precaución: Eliminación recursiva irreversible.
- Ejemplo: Limpiar directorios temporales al final de un script.

#### **3.2. Comparación con `os.remove` y `os.rmdir`** [[5. Cuando usar os y shutil para eliminar]]
- ¿Cuándo usar `shutil` vs `os` para eliminar?

---
### **Módulo 4: Operaciones Avanzadas para Flujos de Trabajo**

#### **4.1. Empaquetado y Compresión** [[6. Empaquetado y compresión]]
- Crear archivos comprimidos (`shutil.make_archive`):
    - Formatos: ZIP, TAR, GZTAR.
        
- Ejemplo: Automatizar backups comprimidos mensuales.

#### **4.2. Desempaquetado**
- Extraer archivos comprimidos (`shutil.unpack_archive`).
- Ejemplo: Procesar lotes de archivos descargados.[[7. Desempaquetado]]

---
### **Módulo 5: Gestión de Metadatos y Permisos**
#### **5.1. Preservar Permisos y Metadata**
- Usar `shutil.copy2` (copia con metadata). [[1. Copiar Archivos]]
- Ejemplo: Migrar servidores manteniendo permisos.

#### **5.2. Manejo de Permisos en Copias**
- ¿Cómo afecta la automatización a los permisos en Linux/Windows?

---
### **Módulo 6: Casos Reales de Automatización**
#### **6.1. Organizador Automático de Descargas**
- Script que clasifica archivos por tipo (.pdf, .jpg, .zip) en carpetas.
#### **6.2. Sistema de Backup Automatizado**
- Backup incremental de proyectos con compresión.
#### **6.3. Limpiador de Espacio en Disco**
- Eliminar logs antiguos o archivos temporales.

---
### **Módulo 7: Mejores Prácticas y Errores Comunes**
- Validar existencia de archivos antes de operar.
- Manejo de excepciones (`FileNotFoundError`, `PermissionError`).
- Logging de operaciones para auditoría.