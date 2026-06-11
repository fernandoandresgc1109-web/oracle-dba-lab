# Usuarios y permisos en Linux

## Objetivo

Aprender a identificar usuarios, grupos y permisos en Linux.

## Comandos utilizados

### Ver información del usuario

```bash
id
```

### Ver grupos del usuario

```bash
groups
```

### Ver permisos de archivos

```bash
ls -l
```

### Cambiar permisos

```bash
chmod 600 notas.txt
```

### Verificar permisos

```bash
ls -l notas.txt
```

## Resultados obtenidos

Se verificó que el usuario `dbaadmin` pertenece al grupo `sudo`, lo que permite ejecutar tareas administrativas.

También se practicó la modificación de permisos mediante `chmod`.

## Evidencias

<img width="1292" height="803" alt="image" src="https://github.com/user-attachments/assets/af41b0e8-e701-4e97-9875-b8c42df48097" />


# Usuarios y permisos Linux

## Creación de grupos

```bash
sudo groupadd dba
```

## Creación de usuarios

```bash
sudo useradd usuario_prueba
sudo passwd usuario_prueba
```

## Verificación

```bash
id usuario_prueba
groups usuario_prueba
```

## Cambio de propietario

```bash
sudo chown usuario_prueba:dba respaldo.bkp
```

## Resultado

Se creó un usuario de prueba, se asignó a un grupo administrativo y se modificó la propiedad de un archivo mediante chown.
<img width="805" height="728" alt="image" src="https://github.com/user-attachments/assets/9164ff27-1be1-4556-b97b-e2ae867335d3" />

