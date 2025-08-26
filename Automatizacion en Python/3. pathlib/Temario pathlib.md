## **Módulo 2: Operaciones Básicas de Rutas**

- `Path()` - Crear objetos de ruta
    
- `/` operator - Unir rutas de forma segura
    
- `name`, `stem`, `suffix` - Partes del path
    
- `parent`, `parents` - Directorios padres
    
- `absolute()`, `resolve()` - Rutas absolutas
    

## **Módulo 3: Verificación y Propiedades**

- `exists()` - Verificar existencia
    
- `is_file()`, `is_dir()` - Tipo de elemento
    
- `stat()` - Metadatos del archivo
    
- `owner()`, `group()` - Propiedad y permisos
    

## **Módulo 4: Navegación y Búsqueda**

- `iterdir()` - Listar contenido del directorio
    
- `glob()` - Búsqueda con patrones
    
- `rglob()` - Búsqueda recursiva
    
- `match()` - Verificar patrones en nombres
    

## **Módulo 5: Manipulación de Archivos y Directorios**

- `mkdir()` - Crear directorios (con `parents` y `exist_ok`)
    
- `touch()` - Crear archivos vacíos
    
- `rename()`, `replace()` - Renombrar y mover
    
- `unlink()` - Eliminar archivos
    
- `rmdir()` - Eliminar directorios vacíos
    

## **Módulo 6: Lectura y Escritura**

- `read_text()`, `write_text()` - Manejo de texto
    
- `read_bytes()`, `write_bytes()` - Manejo de binarios
    
- `open()` - Abrir archivos (context manager)
    

## **Módulo 7: Casos Prácticos de Automatización**

- Organización automática de descargas
    
- Limpieza de archivos temporales
    
- Backup de proyectos
    
- Procesamiento por lotes de archivos
    
- Monitoreo de cambios en directorios
    

## **Módulo 8: Integración con Otras Librerías**

- `shutil` + `pathlib` - Operaciones de archivos
    
- `glob` + `pathlib` - Búsquedas avanzadas
    
- `datetime` + `pathlib` - Archivos por fecha
    

## **Módulo 9: Mejores Prácticas y Performance**

- Path objects vs strings
    
- Métodos eficientes para muchos archivos
    
- Manejo de errores y excepciones
    
- Patrones comunes en automatización