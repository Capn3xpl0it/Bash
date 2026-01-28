# Comandos Bash - Comandos Básicos

## Contenido
0. __[Comandos básicos](#0-comandos-básicos)__
1. __[`ls`](#1-listar-el-contenido-del-directorio-ls)__
2. __[`cd`](#2-cambiar-directorio-cd)__
3. __[`pwd`](#3-mostrar-directorio-de-trabajo-actual-pwd)__
4. __[`echo`](#4-visualización-de-texto-echo)__
5. __[`cat`](#5-concatenar-y-mostrar-contenido-de-archivos-cat)__
6. __[`cp`](#6-copiar-archivos-y-directorios-cp)__
7. __[`mv`](#7-mover-o-renombrar-archivos-mv)__
8. __[`rm`](#8-eliminar-archivos-o-directorios-rm)__
9. __[`touch`](#9-cambiar-marcas-de-tiempo-de-archivo-touch)__
10. __[`mkdir`](#10-crear-directorios-mkdir)__
11. __[`man`](#11-manual-de-usuario-man)__
12. __[`alias`](#12-crear-atajos-para-comandos-largos-alias)__

# 0. Comandos básicos
Los comandos Bash son la forma en que interactúas con el sistema operativo y realizas tareas.

| Comando | Función                                       |
| ------- | --------------------------------------------- |
| `ls`    | Muestra el contenido del directorio           |
| `cd`    | Cambia el directorio actual                   |
| `pwd`   | Muestra el directorio de trabajo actual       |
| `echo`  | Muestra una línea de texto                    |
| `cat`   | Concatenar y mostrar contenido de archivos    |
| `cp`    | Copiar archivos y directorios                 |
| `mv`    | Mover o renombrar archivos                    |
| `rm`    | Eliminar archivos o carpetas                  |
| `touch` | Crear un archivo vacío o actualizar su tiempo |
| `mkdir` | Crear una nueva carpeta                       |
| `man`   | Muestra el manual de usuario del comando      |
| `alias` | Crear atajps para comandos largos             |

---

# 1. Listar el contenido del directorio (`ls`)

## Usando el comando `ls`

El comando `ls` se utiliza para listar el contenido de un directorio.<br>
El comando `ls` puede mostrar archivos, directorios e información sobre ellos.<br>

### Uso básico

Para ver qué hay en la carpeta actual, usa `ls`

```bash
    ┌──(kali㉿Kali)-[~]
    └─$ ls
    ejemplo.txt reporte.csv scripts
```

### Opciones

El comando `ls` ofrece varias opciones para personalizar su resultado.<br>

| Opción | Función                                                |
| ------ | ------------------------------------------------------ |
| `-l`   | Formato de lista larga                                 |
| `-a`   | Incluir archivos ocultos                               |
| `-h`   | Tamaños legibles por humanos                           |
| `-t`   | Ordenar por fecha de modificación                      |
| `-r`   | Orden inverso                                          |
| `-R`   | Listar subdirectorios de forma recursiva               |
| `-S`   | Ordenar por tamaño de archivo                          |
| `-1`   | Listar un archivo por línea                            |
| `-d`   | Listar directorios en sí, no su contenido              |
| `-F`   | Añadir indicador (`*` `/` `=` `@` `\|`) a las entradas |

---
# 2. Cambiar directorio (`cd`)

## Usando el comando `cd`

El comando `cd` se utiliza para cambiar el directorio de trabajo actual en el terminal.

### Uso básico

Para cambiar a un directorio específico utiliza: `cd nombre_directorio`

```bash
    ┌──(kali㉿Kali)-[~]
    └─$ cd scripts

    ┌──(kali㉿Kali)-[~/scripts]
    └─$ 
```

### Opciones

El comando `cd` soporta varias opciones útiles para navegar entre directorios:

| Opción  | Función                        |
| ------- | ------------------------------ |
| `cd ..` | Sube un nivel de directorio    |
| `cd ~`  | Cambia al directorio principal |
| `cd -`  | Cambia al directorio anterior  |
| `cd /`  | Cambia al directorio raíz      |

---
# 3. Mostrar directorio de trabajo actual (`pwd`)

## Usando el comando `pwd`

El comando `pwd` te muestra la ruta completa de la carpeta en la que estás actualmente.

### Uso básico

Para ver la ruta completa de la carpeta actual, solo tienes que escribir `pwd`:

```bash
    ┌──(kali㉿Kali)-[~/scripts]
    └─$ pwd
    /home/kali/scripts
```

### Opciones

El comando `pwd` soporta varias opciones para personalizar su salida:

| Opción   | Función                                        |
| -------- | ---------------------------------------------- |
| `pwd -L` | Mostrar el directorio lógico de trabajo actual |
| `pwd -P` | Mostrar el directorio físico de trabajo actual |

---
# 4. Visualización de texto (`echo`)

## Usando el comando `echo`

El comando `echo` se utiliza para mostrar una línea de texto o el valor de una variable en el terminal.

### Uso básico
Para mostrar un sencillo mensaje, use: `echo "mensaje"`.

```bash
    ┌──(kali㉿Kali)-[~]
    └─$ echo "¡Hola, mundo!"
    ¡Hola, mundo!
```

### Opciones

El comando `echo` tiene varias opciones para personalizar su salida:

| Opción    | Función                                                       |
| --------- | ------------------------------------------------------------- |
| `echo -n` | No añadir salto de línea al final                             |
| `echo -e` | Permitir caracteres especiales como `\n` para saltos de línea |
| `echo E`  | No permitir caracteres especiales (por defecto)               |

---
# 5. Concatenar y mostrar contenido de archivos (`cat`)

## Usando el comando `cat`

El comando `cat` se utiliza para mostrar el contenido de los archivos en el terminal.<br>
También puedes usarlo para combinar varios archivos en uno solo.

### Uso básico

Para mostrar el contenido de un archivo, utilice: `cat archivo`

```bash
    ┌──(kali㉿Kali)-[~]
    └─$ cat hola.txt
    ¡Hola, mundo!
```

### Opciones
El comando `cat` tiene varias opciones para personalizar su salida:

| Opción   | Función                                                                 |
| -------- | ----------------------------------------------------------------------- |
| `cat -n` | Añadir números a cada línea                                             |
| `cat -b` | Añadir números solo a líneas con texto                                  |
| `cat -s` | Eliminar líneas vacías                                                  |
| `cat -v` | Mostrar caracteres no imprimibles (excepto tabulaciones y fin de línea) |

---
# 6. Copiar archivos y directorios (`cp`)

## Usando el comando `cp`

El comando `cp` se utiliza para copiar archivos y directorios de una ubicación a otra.<br>
Es como hacer un duplicado de tu archivo o carpeta.

### Uso básico

Para copiar un archivo, utiliza `cp archivo_origen archivo_destino`

```bash
    ┌──(kali㉿Kali)-[~]
    └─$ cp hola.txt hola_copia.txt
```

### Opciones

El comando `cp` tiene varias opciones para cambiar su funcionamiento:

| Opción  | Función                                                      |
| ------- | ------------------------------------------------------------ |
| `cp -r` | Copiar todos los archivos y carpetas dentro de un directorio |
| `cp -i` | Preguntar antes de reemplazar archivos                       |
| `cp -u` | Copiar solo si el origen es más reciente                     |
| `cp -v` | Modo verboso, mostrar archivos copiándose                    |

---
# 7. Mover o renombrar archivos (`mv`)

## Usando el comando `mv`
El comando `mv` se utiliza para mover o renombrar archivos y directorios.<br>

### Uso básico
Para mover un archivo, utiliza `mv archivo_origen directorio_destino`.<br>
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ mv hola.txt ~/scripts/
```
Para renombrar un archivo, utiliza `mv nombre_original nombre_nuevo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ mv hola.txt hola_mundo.txt
```

### Opciones
El comando `mv` tiene varias opciones para personalizar su comportamiento:

| Opción  | Función                                   |
| ------- | ----------------------------------------- |
| `mv -i` | Preguntar antes de reemplazar archivos    |
| `mv -u` | Mover solo si el origen es más reciente   |
| `mv -v` | Modo verboso, mostrar archivos moviéndose |

---
# 8. Eliminar archivos o directorios (`rm`)

## Usando el comando `rm`

El comando `rm` se utiliza para eliminar archivos o directorios.

### Uso básico

Para eliminar un archivo, utiliza `rm archivo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ rm hola.txt
```

### Opciones

El comando `rm` tiene opciones para cambiar su funcionamiento:

| Opción  | Función                                               |
| ------- | ----------------------------------------------------- |
| `rm -r` | Eliminar una carpeta y todo lo que hay dentro de ella |
| `rm -i` | Preguntar antes de eliminar cada archivo              |
| `rm -f` | Forzar la eliminación sin preguntar                   |
| `rm -v` | Modo verboso, mostrar archivos eliminados             |

---
# 9. Cambiar marcas de tiempo de archivo (`touch`)

## Usando el comando `touch`

El comando `touch` se usa para cambiar las marcas de tiempo de los archivos o crear un archivo vacío si no existe.<br>
A menudo se usa para crear archivos provisionales o actualizar marcas de tiempo para sistemas de compilación.

### Uso básico
Para actualizar los tiempos de acceso y modificación de un archivo, utilize `touch archivo`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ touch hola.txt
```

### Opciones

El comando `touch` tiene opciones para cambiar su funcionamiento:

| Opción     | Función                                                    |
| ---------- | ---------------------------------------------------------- |
| `touch -a` | Actualizar cuándo fue leído el archivo por última vez      |
| `touch -m` | Actualizar cuándo fue modificado el archivo por última vez |
| `touch -t` | Establecer la marca de tiempo a una hora específica        |
| `touch -c` | No crear ningún archivo                                    |

---
# 10. Crear directorios (`mkdir`)

## Usando el comando `mkdir`

El comando `mkdir` se utiliza para crear nuevos directorios.

### Uso básico

Para crear un nuevo directorio, utiliza `mkdir directorio`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ mkdir nuevo_directorio
```

### Opciones

El comando `mkdir` tiene varias opciones para personalizar su comportamiento:

| Opción     | Función                                        |
| ---------- | ---------------------------------------------- |
| `mkdir -p` | Crear directorios padre según sea necesario    |
| `mkdir -v` | Mostrar un mensaje para cada directorio creado |
| `mkdir -m` | Establecer modo de archivos (permisos)         |

---
# 11. Manual de usuario (`man`)

## Usando el comando `man`

El comando `man` se utiliza para mostrar el manual de usuario de cualquier comando que pueda ejecutarse en el terminal.

### Sintaxis

La sintaxis básica del comando `man` es `man <comando>`.

### Usos comunes

El comando `man` se usa comúnmente para:

+ Aprender sobre las opciones y el uso de comandos
+ Entender la sintaxis de los comandos
+ Acceder a documentación detallada para la resolución de problemas

---
# 12. Crear atajos para comandos largos (`alias`)

## Creación de `alias`

Para crear un alias, usa la sintaxis `alias nombre='comando'`, donde `nombre` es el acceso directo que quieres usar y `comando` es el comando completo que quieres ejecutar.

#### Ejemplo: Lista
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ alias ll='ls -la'
```
#### Ejemplo: Git Status
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ alias gs='git status'
```

### Gestión de alias

Para ver todos los alias actuales, usa el comando `alias` sin argumentos.
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ alias
    alias ll='ls -la'
    alias gs='git status'
```

### Eliminar un alias

Para eliminar un `alias` usa `unalias nombre`
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ unalias gs
```

### Creación de alias permanentes
Para que un alias sea permanente, añádelo a tu archivo de `~/.bashrc` o `~/.bash_profile`

### Ejemplo: Añadir alias permanente

#### Abrir editor
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ nano ~/.bashrc
```
#### Añadir Alias
```bash
    alias ll='ls -la'
```
#### Guardar y aplicar
```bash
    ┌──(kali㉿Kali)-[~]
    └─$ source ~/.bashrc
```