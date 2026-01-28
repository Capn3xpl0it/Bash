# Comandos Bash - Procesamiento de texto

## Contenido

1. __[`grep`](#1-buscar-texto-mediante-patrones-grep)__
2. __[``]()__
3. __[``]()__
4. __[``]()__
5. __[``]()__
6. __[``]()__
7. __[``]()__

---
# 1. Buscar texto mediante patrones (`grep`)

El comando `grep` se utiliza para buscar patrones de texto dentro de archivos.

## Uso básico

Para buscar un patrón en un archivo, usa `grep 'patrón' archivo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ grep 'mundo' hola.txt
    ¡Hola, mundo!
```

### Opciones
El comando `grep` tiene opciones para cambiar su funcionamiento:

| Opción    | Función                                                            |
| --------- | ------------------------------------------------------------------ |
| `grep -i` | Búsqueda ignorando las diferencias de mayúsculas o minúsculas      |
| `grep -r` | Buscar en todos los archivos de un directorio y sus subdirectorios |
| `grep -v` | Encontrar líneas que no coincidan con el patrón                    |

### Uso con regEx

Las expresiones regulares permiten buscar patrones complejos.<br>
Por ejemplo, `grep '^[A-Za-z] archivo.txt`  encuentra líneas que empiezan por una letra.

---
# 2. Escaneo y procesamiento de patrones del lenguaje (`awk`)

El comando `awk` se utiliza para el escaneo y procesamiento de patrones del lenguaje. Es útil para manejar archivos de texto y se utiliza para la extracción de datos y la elaboración de informes.

## Uso básico

El comando `awk` es potente para el procesamiento de texto. Por ejemplo, puedes usarlo para extraer campos específicos de un archivo o realizar cálculos.
```CSV
    id,Created,Amount,Currency,Description,Customer
    1,2024-11-01,100,USD,Payment,John Doe
    2,2024-11-02,200,EUR,Refund,Jane Smith
    3,2024-11-03,150,USD,Purchase,Emily Davis
    4,2024-11-04,175,GBP,Subscription,Michael Brown
```
Para imprimir la primera columna de un archivo, usa `awk -F"," '{print $1}' archivo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ awk -F"," '{print $1}' datos.csv
    # Output:
    # id
    # 1
    # 2
    # 3
    # 4
```

### Opciones

El comando `awk` tiene opciones para cambiar su funcionamiento.

| Opción   | Función                                        |
| -------- | ---------------------------------------------- |
| `awk -F` | Establecer el separador de los datos           |
| `awk -v` | Establecer una variable para usar en el script |

---
# 3. Editor de flujo (`sed`)

El comando `sed` es un editor de flujo usado para realizar transformaciones básicas de texto en un flujo de entrada. Es una herramienta poderosa para hacer ediciones rápidas en archivos o flujos de datos. 

## Uso básico

Para reemplazar la primera aparición de un patrón en un archivo, usa `sed 's/original/nuevo' archivo` 
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ sed 's/Mundo/Bash' hola.txt
    ¡Hola, Bash!
```

### Opciones

El comando `sed` tiene opciones para cambiar su funcionamiento:

| Opción   | Función                                                               |
| -------- | --------------------------------------------------------------------- |
| `sed -i` | Editar archivos directamente sin necesidad de guardarlos por separado |
| `sed -e` | Añadir el script a los comandos a ejecutar                            |
| `sed -n` | No imprime líneas automáticamente                                     |
| `sed -r` | Utilizar expresiones regulares extendidas                             |
| `sed -f` | Añadir un script a partir de un archivo                               |
| `sed -l` | Especificar la longitud de la línea para el comando `l`               |

---
# 4. Eliminar secciones de líneas (`cut`)

El comando `cut` se utiliza para eliminar secciones de cada línea de un archivo. Es una herramienta útil para extraer campos específicos de datos de un archivo o flujo de salida.

##### Archivo _datos.txt_
```CSV
Kai 	Refsnes	30,Norway
Robin	Smith	25,Denmark
Sienna	Davis	40,Germany
```

## Uso básico

Para extraer el primer campo de un archivo, use `cut -f1 archivo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ cut -f1 datos.txt
```
Por defecto, `cut` usa una tabulación como delimitador.

### Opciones

El comando `cut` tiene opciones para cambiar su funcionamiento:

| Opción             | Función                                            |
| ------------------ | -------------------------------------------------- |
| `cut -d`           | Elegir el delimitador de los campos                |
| `cut -f`           | Seleccionar campos específicos a mostrar           |
| `cut --complement` | Mostrar todos los campos excepto los seleccionados |

--- 
# 5. Ordenar líneas de texto de un archivo (`sort`)

El comando `sort` se utiliza para ordenar líneas de archivos de texto. Es una herramienta útil para organizar datos en archivos.

## Uso básico

Para ordenar un archivo, utiliza `sort archivo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ sort colores.txt
    Amarillo
    Café
    Dorado
    Fucsia
    Rojo
```

### Opciones

El comando `sort` tiene opciones para cambiar su funcionamiento:

| Opción    | Función                             |
| --------- | ----------------------------------- |
| `sort -r` | Erden inverso                       |
| `sort -n` | Orden numérico                      |
| `sort -k` | Ordenar una columna específica      |
| `sort -u` | Eliminar líneas duplicadas          |
| `sort -t` | Especificar el delimitador de campo |

---
# 6. Mostrar la última parte de un archivo (`tail`)

El comando `tail` se utiliza para mostrar la última parte de los archivos. Es especialmente útil para ver el final de archivos de registro o cualquier archivo que se esté actualizando en tiempo real.

## Sintaxis

La sintaxis básica del comando `tail` es `tail <opción> <archivo>`

### Opciones

El comando `tail` tiene varias opciones para personalizar su comportamiento:

| Opción             | Función                                                                         |
| ------------------ | ------------------------------------------------------------------------------- |
| `tail -n <número>` | Muestra las últimas líneas \<numeradas> del archivo                             |
| `tail -f`          | Sigue el archivo a medida que crece, útil para monitorizar archivos de registro |
| `tail -c <número>` | Muestra los últimos <número> bytes del archivo                                  |
| `tail --pid=<pid>` | Terminar después de que finaliza el proceso con el PID proporcionado            |
| `tail --retry`     | Sigue intentando abrir un archivo aunque sea inaccesible                        |

---
# 7. Mostrar el inicio de un archivo (`head`)

El comando `head` se utiliza para mostrar la primera parte de los archivos. Es especialmente útil para previsualizar el inicio de un archivo y así entender su estructura.

## Uso básico

El comando `head` muestra por defecto las primeras 10 líneas de un archivo.
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ head log.txt
    línea 01
    línea 02
    línea 03
    línea 04
    línea 05
    línea 06
    línea 07
    línea 08
    línea 09
    línea 10
```

### Opciones

El comando tiene dos opciones para personalizar su comportamiento:

| Opción             | Función                                           |
| ------------------ | ------------------------------------------------- |
| `head -n <número>` | Muestra las primeras \<número> líneas del archivo |
| `head -c <número>` | Muestra los primeros \<número> bytes del archivo  |