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
```sh
chown :grupo archivo.txt
```
### 2.2.3 Cambiar Propietario y Grupo Simultáneamente
```sh
chown usuario:grupo archivo.txt
```
## 3. Práctica guiada
## 3. Creación de Archivos y Directorios

### 3.1 Creación de Archivos y Directorios
Crear un nuevo directorio y varios archivos dentro de él.
```sh
# Crear un nuevo directorio
mkdir nombre_del_directorio

# Cambiar al nuevo directorio
cd nombre_del_directorio

# Crear varios archivos dentro del nuevo directorio
touch archivo1 archivo2 archivo3
```
### 3.2 Modificación de Permisos y Propietarios
Cambia los permisos de `archivo1.txt` a `rw-r--r--`.
```sh
chmod 644 archivo1.txt
```
Cambia los permisos de archivo2.txt a rwxr-x---.
```sh
chmod 750 archivo2.txt
```
Cambia el propietario de archivo3.txt a otro usuario (ej. usuario2).
```sh
sudo chown usuario2 archivo3.txt
```
Cambia el grupo de archivo3.txt a otro grupo (ej. grupo2).
```sh
sudo chown :grupo2 archivo3.txt
```




