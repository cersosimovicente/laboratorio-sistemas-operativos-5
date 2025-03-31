# Práctica: Gestión de Ficheros en CMD y PowerShell

## 1. Crear la estructura de directorios

Desde el directorio de usuario, ejecuta los siguientes comandos:

### **CMD:**
```cmd
mkdir PracticaWindows\PrimeraParte\Seccion1
mkdir PracticaWindows\PrimeraParte\Seccion2
mkdir PracticaWindows\SegundaParte
```

### **PowerShell:**
```powershell
New-Item -ItemType Directory -Path PracticaWindows\PrimeraParte\Seccion1
New-Item -ItemType Directory -Path PracticaWindows\PrimeraParte\Seccion2
New-Item -ItemType Directory -Path PracticaWindows\SegundaParte
```

## 2. Crear y editar archivos en Seccion1

### **CMD:**
```cmd
cd PracticaWindows\PrimeraParte\Seccion1
echo Este es el contenido del fichero 1 > fichero1.txt
copy fichero1.txt fichero2.txt
echo Este es el contenido del fichero 2 > fichero2.txt
```

### **PowerShell:**
```powershell
Set-Content -Path PracticaWindows\PrimeraParte\Seccion1\fichero1.txt -Value "Este es el contenido del fichero 1"
Copy-Item -Path PracticaWindows\PrimeraParte\Seccion1\fichero1.txt -Destination PracticaWindows\PrimeraParte\Seccion1\fichero2.txt
Set-Content -Path PracticaWindows\PrimeraParte\Seccion1\fichero2.txt -Value "Este es el contenido del fichero 2"
```

## 3. Crear archivos en Seccion2 sin cambiar de directorio

### **CMD:**
```cmd
copy fichero1.txt ..\Seccion2\fichero3.txt
copy fichero2.txt ..\Seccion2\fichero4.txt
echo Este es el contenido del fichero 3 > ..\Seccion2\fichero3.txt
echo Este es el contenido del fichero 4 > ..\Seccion2\fichero4.txt
```

### **PowerShell:**
```powershell
Copy-Item -Path fichero1.txt -Destination ..\Seccion2\fichero3.txt
Copy-Item -Path fichero2.txt -Destination ..\Seccion2\fichero4.txt
Set-Content -Path ..\Seccion2\fichero3.txt -Value "Este es el contenido del fichero 3"
Set-Content -Path ..\Seccion2\fichero4.txt -Value "Este es el contenido del fichero 4"
```

## 4. Cambio de directorio a SegundaParte y crear duplicado

### **CMD:**
```cmd
cd ..\..\SegundaParte
copy ..\PrimeraParte\Seccion1\fichero1.txt duplicado.txt
echo Este es el contenido del duplicado > duplicado.txt
```

### **PowerShell:**
```powershell
cd ..\..\SegundaParte
Copy-Item -Path ..\PrimeraParte\Seccion1\fichero1.txt -Destination duplicado.txt
Set-Content -Path duplicado.txt -Value "Este es el contenido del duplicado"
```

## 5. Mover Seccion2 a nivel superior con nuevo nombre

### **CMD:**
```cmd
move ..\PrimeraParte\Seccion2 ..\TerceraParte
```

### **PowerShell:**
```powershell
Move-Item -Path ..\PrimeraParte\Seccion2 -Destination ..\TerceraParte
```

## 6. Mostrar contenido de todos los archivos con un único comando

### **CMD:**
```cmd
type ..\PrimeraParte\Seccion1\fichero1.txt ..\PrimeraParte\Seccion1\fichero2.txt ..\TerceraParte\fichero3.txt ..\TerceraParte\fichero4.txt duplicado.txt
```

### **PowerShell:**
```powershell
Get-Content -Path ..\PrimeraParte\Seccion1\fichero1.txt, ..\PrimeraParte\Seccion1\fichero2.txt, ..\TerceraParte\fichero3.txt, ..\TerceraParte\fichero4.txt, duplicado.txt
```

## 7. Duplicar todo el árbol de ficheros

### **CMD:**
```cmd
xcopy /E /I PracticaWindows PracticaWindows_Backup
```

### **PowerShell:**
```powershell
Copy-Item -Path PracticaWindows -Destination PracticaWindows_Backup -Recurse
```

## 8. Borrar el duplicado con un solo comando

### **CMD:**
```cmd
rd /S /Q PracticaWindows_Backup
```

### **PowerShell:**
```powershell
Remove-Item -Path PracticaWindows_Backup -Recurse -Force
```

## 9. Listar archivos con opciones en PracticaWindows

### **CMD:**
```cmd
cd PracticaWindows
ls -alrt
```

### **PowerShell:**
```powershell
cd PracticaWindows
Get-ChildItem -Force | Sort-Object LastWriteTime
```

## Tabla de comandos utilizados

| Comando (CMD)                        | Comando (PowerShell)                         | Descripción |
|---------------------------------------|---------------------------------------------|-------------|
| `mkdir NombreDirectorio`              | `New-Item -ItemType Directory -Path NombreDirectorio` | Crea un nuevo directorio. |
| `cd Ruta`                             | `cd Ruta`                                  | Cambia al directorio especificado. |
| `echo "Texto" > archivo.txt`          | `Set-Content -Path archivo.txt -Value "Texto"` | Escribe texto en un archivo. |
| `copy archivo1.txt archivo2.txt`      | `Copy-Item -Path archivo1.txt -Destination archivo2.txt` | Copia un archivo en la misma ubicación o en otra. |
| `move CarpetaOrigen CarpetaDestino`   | `Move-Item -Path CarpetaOrigen -Destination CarpetaDestino` | Mueve una carpeta a otra ubicación. |
| `type archivo.txt`                    | `Get-Content -Path archivo.txt`            | Muestra el contenido de un archivo. |
| `xcopy /E /I CarpetaOrigen CarpetaDestino` | `Copy-Item -Path CarpetaOrigen -Destination CarpetaDestino -Recurse` | Copia toda una estructura de directorios. |
| `rd /S /Q Carpeta`                    | `Remove-Item -Path Carpeta -Recurse -Force` | Borra una carpeta y su contenido. |
| `ls -alrt`                             | `Get-ChildItem -Force ` | ` Sort-Object LastWriteTime` | Lista los archivos con detalles ordenados por fecha. |

