# Gen_Evol_Bohe
Códigos para Genómica Evolutiva

# Codigo 1:
```r
mkdir genomas;
grep ">" genomas.fasta;
ls;
```
# Clase 2:
```r
# Paso 01:Entrar a la página
https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit
# Paso 02:Descargar en la linea de comandos el archivo sratoolkit.3.1.1-ubuntu64.tar.gz desde el servidor de NCBI y lo guarda como stk.tar.gz
wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/3.1.1/sratoolkit.3.1.1-ubuntu64.tar.gz -O stk.tar.gz
# Paso 03: Dar todos los permisos de edición al archivo descargado, para que sea accesible por todos (lectura, escritura y ejecución).
chmod 777 stk.tar.gz
# Paso 04: Descomprimir el archivo tar.gz, usando tar con opciones para extraer (x), mostrar los archivos que se están extrayendo (v), descomprimir (z), y especificar el archivo (f).
tar -vxzf stk.tar.gz
# Paso 05: Configurar el PATH,  añade la ruta sratoolkit.3.1.1-ubuntu64/bin al PATH, permitiendo que los ejecutables en esa carpeta se puedan usar desde cualquier lugar en la línea de comandos
export PATH=$PATH:$PWD/sratoolkit.3.1.1-ubuntu64/bin 
# Paso 06: Descargar datos especificados en el archivo sra_accessions_1.txt, limitando el tamaño de cada archivo a 50 GB. 
prefetch --max-size 50G --option-file sra_accessions_1.txt ;
# Paso 07: Mover todos los archivos .sra desde subdirectorios al directorio actual
mv */*.sra .
# Paso 08:  Se usa fasterq-dump para convertir los archivos .sra en archivos .fastq. La opción --split-files divide los archivos de salida en archivos separados por lectura (R1 y R2).
fasterq-dump --split-files *.sra
# Paso 09: Comprimir todos los archivos .fastq generados usando gzip
gzip *fastq
# Paso 10: Cambiar los permisos de todos los archivos en el directorio actual para que sean accesibles para todos (lectura, escritura y ejecución).
chmod 777 *
# Paso 11: Analisis de Calidad usando fastqc en todos los archivos .fastq.gz, utilizando hasta 15 hilos para el procesamiento
fastqc -t 15 *.fastq.gz
```
