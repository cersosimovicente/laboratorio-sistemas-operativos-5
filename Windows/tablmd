| Comando (CMD)                          | Comando (PowerShell)                                                       | Descripción                                         |
|----------------------------------------|----------------------------------------------------------------------------|-----------------------------------------------------|
| `mkdir NombreDirectorio`              | `New-Item -ItemType Directory -Path NombreDirectorio`                      | Crea un nuevo directorio.                           |
| `cd Ruta`                             | `cd Ruta`                                                                  | Cambia al directorio especificado.                  |
| `echo "Texto" > archivo.txt`          | `Set-Content -Path archivo.txt -Value "Texto"`                             | Escribe texto en un archivo.                        |
| `copy archivo1.txt archivo2.txt`      | `Copy-Item -Path archivo1.txt -Destination archivo2.txt`                   | Copia un archivo en la misma ubicación o en otra.   |
| `move CarpetaOrigen CarpetaDestino`  | `Move-Item -Path CarpetaOrigen -Destination CarpetaDestino`               | Mueve una carpeta a otra ubicación.                 |
| `type archivo.txt`                    | `Get-Content -Path archivo.txt`                                            | Muestra el contenido de un archivo.                 |
| `xcopy /E /I CarpetaOrigen CarpetaDestino` | `Copy-Item -Path CarpetaOrigen -Destination CarpetaDestino -Recurse`   | Copia toda una estructura de directorios.           |
| `rd /S /Q Carpeta`                    | `Remove-Item -Path Carpeta -Recurse -Force`                                | Borra una carpeta y su contenido.                   |
| `ls -alrt`                            | `Get-ChildItem -Force \| Sort-Object LastWriteTime`                        | Lista archivos incluyendo ocultos, ordenados por fecha. |
