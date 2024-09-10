# Gen_Evol_Bohe
Códigos para Genómica Evolutiva

# Codigo 1:
```r
mkdir genomas;
grep ">" genomas.fasta;
ls;
```
```r
# Entrar a la página
https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit
#Descargar en la linea de comandos
wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/3.1.1/sratoolkit.3.1.1-ubuntu64.tar.gz -O stk.tar.gz
# Dar todos los permisos de edición
chmod 777 stk.tar.gz
# Descomprimir un archivo tar.gz
tar -vxzf sratoolkit.3.0.10-ubuntu64.tar.gz
tar -vxzf stk.tar.gz
# Export to bin
export PATH=$PATH:$PWD/sratoolkit.3.0.10-ubuntu64/bin
#cambiar según la versión instalada
export PATH=$PATH:$PWD/sratoolkit.3.1.1-ubuntu64/bin 
#
prefetch -h 

```
