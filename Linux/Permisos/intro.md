# Laboratorio de Permisos en Linux

## Introducción

En este laboratorio, vamos a trabajar con los permisos de archivos y directorios en Linux. Los permisos en Linux son fundamentales para la seguridad y la gestión de usuarios en el sistema.

## Requisitos

- Una distribución de Linux instalada (puede ser una máquina virtual)
- Acceso a la terminal
- Conocimientos básicos de comandos de Linux

## 1. Exploración de Permisos

### 1.1 Verificando Permisos

Para ver los permisos de un archivo o directorio, usa el comando `ls` con la opción `-l`.

```sh
ls -l
```
1.2 Descripción de los Permisos
Los permisos se dividen en tres categorías: usuario (owner), grupo y otros (others). Cada categoría puede tener permisos de lectura (r), escritura (w) y ejecución (x).

Por ejemplo, en la salida:
```sh
-rwxr-xr--
```
- **Tipo de archivo**: (en este caso, un archivo regular)
- **rwx**: Permisos del usuario (lectura, escritura y ejecución)
- **r-x**: Permisos del grupo (lectura y ejecución)
- **r--**: Permisos para otros (solo lectura)

## 2. Modificación de Permisos

### 2.1 Usando chmod
El comando `chmod` se usa para cambiar los permisos de archivos y directorios.

#### 2.1.1 Sintaxis
```sh
chmod [opciones] permisos archivo
```
#### 2.1.2 Cambiar Permisos con Notación Simbólica
Agregar permisos de ejecución para el usuario (owner):
```sh
chmod u+x archivo.txt
```
Remueve permisos de escritura para el grupo:
```sh
chmod g-w archivo.txt
```
#### 2.1.3 Cambiar Permisos con Notación Numérica
Los permisos también pueden ser representados numéricamente:

- Lectura (r) = 4
- Escritura (w) = 2
- Ejecución (x) = 1

Por ejemplo, para establecer permisos `rwxr-xr--`:
```sh
chmod 754 nombre_del_archivo
```
### 2.2 Usando chown
El comando `chown` cambia el propietario y el grupo de un archivo o directorio.

#### 2.2.1 Cambiar el Propietario
```sh
chown usuario archivo.txt
```
### 2.2.2 Cambiar el Grupo
