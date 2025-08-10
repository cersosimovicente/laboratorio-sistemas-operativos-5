# PowerShell para administradores
## 1.-Gestión de usuarios y grupos.

**Gestión de usuarios**:

Get-LocalUser: muestra las cuentas de usuarios locales.

New-LocalUser: Crea una nueva cuenta de usuario local.

Set-LocalUser: Establece o modifica una propiedad de una cuenta de usuario local.

Rename-LocalUser: Renombra una cuenta de usuario local.

Disable-LocalUser: Desactiva una cuenta de usuario local.

Enable-LocalUser: Activa una cuenta de usuario local.

Remove-LocalUser: Elimina una cuenta de usuario local.


**Gestión de grupos**

Get-LocalGroup: muestra los grupos locales.

New-LocalGroup: Crea un nuevo grupo local.

Set-LocalGroup: Establece o modifica una propiedad de un grupo local.
 
Rename-LocalGroup: Renombra un grupo local.

Remove-LocalGroup: Elimina un grupo local.

Get-LocalGroupMember: Muestra los miembros de un grupo.

Add-LocalGroupMember: Agrega un miembro a un grupo.

Remove-LocalGroupMember: Elimina un miembro de un grupo local.

```powershell
#Creación de un usuario
$usuario = Read-Host "Introduce nombre de usuario"
$contra = Read-Host "Introduce contraseña" -AsSecureString
New-LocalUser $usuario -Password $contra
Add-LocalGroupMember -Group usuarios -Member $usuario
```
```powershell
#Creación de usuarios de forma masiva
$usuarios = Import-Csv -Path C:\material\usuarios.csv
foreach ($i in $usuarios) {
    $clave = ConvertTo-SecureString $i.contra -AsPlainText -Force
    New-LocalUser $i.nombre -Password $clave -AccountNeverExpires -PasswordNeverExpires
    Add-LocalGroupMember -Group usuarios -Member $i.nombre
}
```

```powershell
#Eliminación de usuarios de forma masiva
$usuarios= Import-Csv -Path C:\material\usuarios.csv
foreach ($i in $usuarios) {
    Remove-LocalUser -Name $i.nombre
}


