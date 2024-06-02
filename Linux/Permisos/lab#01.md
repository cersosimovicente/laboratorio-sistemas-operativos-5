# Actividad: Trabajando con Permisos en Linux

## Objetivo

Esta actividad tiene como objetivo que los estudiantes comprendan y practiquen la gestión de permisos en Linux, utilizando los comandos `chmod`, `chown` y `ls`.

## Instrucciones

### 1. Preparación

1. Abrí una terminal en tu distribución de Linux.
2. Crea un directorio llamado `actividad_permisos` y accede a él.

```sh
mkdir actividad_permisos
cd actividad_permisos
```
### 2. Creación de Archivos y Directorios
Dentro del directorio actividad_permisos, crea los siguientes archivos y un subdirectorio:
```sh
touch archivoA.txt archivoB.txt archivoC.txt
mkdir subdirectorio
```
### 3. Exploración de Permisos
Usa el comando ls -l para ver los permisos actuales de los archivos y directorios creados.
```sh
ls -l
```
2. Anota los permisos actuales de cada archivo y directorio en la siguiente tabla:

| **Nombre**      | **Permisos Actuales** |
|-----------------|-----------------|
| archivoA.txt	  |                 |
| archivoB.txt    |                 |
| archivoC.txt    |                 |
| subdirectorio   |                 |

### 4. Modificación de Permisos
Cambia los permisos de archivoA.txt para que el usuario tenga permisos de lectura y escritura, el grupo solo lectura y otros no tengan permisos.
```sh

```
Cambia los permisos de archivoC.txt para que el usuario tenga todos los permisos, el grupo solo lectura y otros solo ejecución.
```sh

```
Cambia los permisos del subdirectorio para que el usuario tenga todos los permisos, el grupo y otros solo tengan permisos de lectura y ejecución.
```sh

```
### 5. Verificación de Cambios
```sh
ls -l
```
Anota los nuevos permisos de cada archivo y directorio en la siguiente tabla:

| **Nombre**      | **Permisos Actuales** |
|-----------------|-----------------|
| archivoA.txt	  |                 |
| archivoB.txt    |                 |
| archivoC.txt    |                 |
| subdirectorio   |                 |

