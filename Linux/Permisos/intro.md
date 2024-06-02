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
