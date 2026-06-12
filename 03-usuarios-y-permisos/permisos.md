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

## Comandos ejecutados

```bash
mkdir ~/oracle_lab
cd ~/oracle_lab

mkdir backups
mkdir scripts
mkdir software

sudo apt install tree -y
```

## Resultado

```text
.
├── backups
├── scripts
└── software

4 directories, 0 files
```

## Evidencia

<img width="1600" height="832" alt="image" src="https://github.com/user-attachments/assets/a1dddd5f-0fd1-4240-8669-6e2709815e3e" />

# Usuarios y permisos Linux

## Creación de usuario

Comando:

```bash
sudo useradd usuario_dba

sudo groupadd dba

chmod 600 datos1.txt
chmod 755 datos2.txt

<img width="921" height="578" alt="image" src="https://github.com/user-attachments/assets/85311c21-f954-41eb-a01b-4b61925b066f" />
<img width="871" height="119" alt="image" src="https://github.com/user-attachments/assets/4f28163c-321e-43fd-b565-0c124759b7bb" />
<img width="878" height="406" alt="image" src="https://github.com/user-attachments/assets/7e525081-5b24-4709-a469-2f26a164c5bc" />
<img width="921" height="171" alt="image" src="https://github.com/user-attachments/assets/161cdfc7-f8ec-4e1b-b016-ec66e65af6f2" />
<img width="921" height="423" alt="image" src="https://github.com/user-attachments/assets/b763d24a-05d5-4b55-b68b-2cb6adf13011" />







