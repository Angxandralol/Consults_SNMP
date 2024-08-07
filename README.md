# Consultas SNMP
Crea consultas SNMP a distintos equipos de la red. 

## Objetivo
Este proyecto tiene como finalidad poder ejecutar múltiples consultas SNMP para obtener los resultados en archivos JSON para su utilidad. 

### Advertencias
Los archivos `snmp.sh` y `ping.sh` tiene los comandos básicos para su ejecución. Es necesario su verificar que los comandos por defecto funcionen en el equipo, en caso contrario, puede especificar el comando correcto cambiando la variable `COMMAND` del archivo necesario. 

## Requerimientos
Se requiere un archivo `elements.csv` que contenga todas las IPs y comunidades a consultar. 
```
ip, comunidad, ip, comunidad, ...
```

## Funcionamiento
```bash
bash consults_snmp.sh [cantidad_de_consultas] [parte_de_consultas]
```
**Cantidad de consultas:** Este script puede ejecutar una cantidad determinada de consultas diferente a la cantidad de elementos (IP y Comunidad) que se suministre. 
<br>
**Parte de Consultas:** Si se require ejecutar varias consultas en paralelo, se debe especificar la parte de la división que se va a obtener. 

#### Ejemplo
Si se tiene un total de 50 elementos, se pudiera realizar dos consultas en paralelo. Así la primera parte de la consulta obtendrá los primeros 25 elementos, y la segunda parte de la consulta los 25 últimos. 
```bash
bash consults_snmp.sh 25 1 
bash consults_snmp.sh 25 2
```
## Consulta global
Si se requiere consultar todo en una sola consulta:
```bash
bash consults_snmp.sh [total_de_elements] 1
```
