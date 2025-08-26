### 🎯 **Temario Esencial de Bash/Shell para Automatización**
#### **Módulo 1: Fundamentos Críticos (Lo que usarás todos los días)**
1. **Shebang y permisos:** `#!/bin/bash`, `chmod +x script.sh`
2. **Variables:** Declarar (`VAR="valor"`), usar (`$VAR`), variables de entorno (`$HOME`, `$PATH`)
3. **Argumentos de script:** `$1`, `$2`, `$@`, `$#`
4. **Salida de comandos:**
    - **Redirección:** `>` (sobrescribir), `>>` (añadir)
    - **Pipes (`|`)**: Conectar el output de un comando al input de otro. Ej: `cat file.txt | grep "error"`

#### **Módulo 2: Flujo de Control (El cerebro de la automatización)**
1. **Condicionales (`if`/`else`):**
    - Sintaxis: `if [ condicion ]; then ... fi`
    - Tests esenciales: `-f` (archivo existe?), `-d` (directorio existe?), `-z` (cadena vacía?)
2. **Loops (`for`, `while`):**
    - `for i in $(cat list.txt); do ... done` (iterar sobre una lista)
    - `for file in *.txt; do ... done` (iterar sobre archivos)
    - `while read line; do ... done < file.txt` (leer un archivo línea por línea)

#### **Módulo 3: Procesamiento de Texto (Tu navaja suiza)**
1. **`grep`:** Buscar patrones. Flags: `-i` (ignore case), `-v` (invert match), `-E` (regex extendida)
2. **`awk` (Lo mínimo vital):** Extraer columnas. Ej: `awk '{print $1}' file.txt` (imprime la 1ra columna)
3. **`sed` (Lo mínimo vital):** Reemplazar texto. Ej: `sed 's/foo/bar/g' file.txt` (cambia "foo" por "bar" globalmente)
4. **`cut`:** Extraer secciones de cada línea. Ej: `cut -d',' -f2 data.csv` (corta por coma, 2da field)

#### **Módulo 4: Funciones y Robustez (Scripts de nivel profesional)**
1. **Funciones:** Agrupar código reutilizable.
    ```bash
    function log_message() {
        echo "$(date): $1" >> script.log
    }
    log_message "Starting process..."
    ```
2. **Manejo de errores:**
    - `set -e` (hace que el script falle inmediatamente si cualquier comando falla)
    - `exit codes`: Verificar si un comando anterior tuvo éxito (`$? -eq 0`)

#### **Módulo 5: Automatización y Programación (Integración con Python)**
1. **Programación de scripts (`cron`):**
    - `crontab -e` para editar tu crontab.
    - Sintaxis básica: `* * * * * /ruta/a/tu/script.sh` (minuto, hora, día del mes, mes, día de la semana).
        
2. **Variables y comandos en la terminal:**
    - Puedes **definir variables** directamente desde la terminal y usarlas en tus scripts.
    - Ejemplo: `MAX_SIZE=1000` y luego en el script: `if [ $size -gt $MAX_SIZE ]; then ... fi`.
        
3. **Llamar scripts de Bash desde Python:**
    - Usa el módulo `subprocess` para ejecutar comandos de Bash y capturar su output.
    - Ejemplo: `result = subprocess.run(['bash', 'script.sh', 'arg1'], capture_output=True, text=True)`.

---
### 📌 **Proyectos Prácticos para Aprender (De menor a mayor complejidad)**
1. **Organizador de Descargas:** Script que mueva archivos de la carpeta `Downloads` a subcarpetas según su extensión (`PDFs`, `Images`, `Videos`).
2. **Buscador de Logs:** Script que busque un patrón (ej: "ERROR") en todos los archivos `.log` de un directorio y guarde las líneas encontradas en un reporte.
3. **Compresor de Backups:** Script que comprima todos los archivos de una carpeta que no hayan sido modificados en los últimos 30 días y los suba a un servidor remoto usando `rsync` o `scp`.
4. **Monitor de Sistema:** Script que verifique el uso de CPU y memoria y envíe un email (usando `mail` o una API) si supera un umbral.