# Instalación Oracle XE

## Preparación del entorno

Se instaló Docker para ejecutar Oracle Database en contenedores.

### Comandos ejecutados

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker

# Verificación de Docker

Comando ejecutado:

```bash
docker ps
```

docker run hello-world

### Evidencia

<img width="1562" height="766" alt="image" src="https://github.com/user-attachments/assets/3ebc6cdc-03ed-4b0d-8a28-b6244d69799a" />


<img width="960" height="222" alt="image" src="https://github.com/user-attachments/assets/b70ec734-6302-46ba-941b-dade9b21705a" />
<img width="827" height="162" alt="image" src="https://github.com/user-attachments/assets/03deca63-a855-49ae-b71b-df53a19cf5b0" />
<img width="932" height="572" alt="image" src="https://github.com/user-attachments/assets/4959a94d-bce3-4f38-a4e1-1277740b2402" />
<img width="921" height="262" alt="image" src="https://github.com/user-attachments/assets/d02c3e12-2541-4ed4-bf29-c5b8b7835438" />
<img width="921" height="618" alt="image" src="https://github.com/user-attachments/assets/94a1a776-a1f6-4ddf-b02b-d9e4d7126d7c" />

# Oracle Database XE

## Objetivo

Instalar Oracle Database Express Edition utilizando Docker para practicar administración de bases de datos Oracle.

## Verificaciones previas

Comandos ejecutados:

```bash
docker --version
docker info | head -20
Resultado:

Docker 29.1.3 instalado.
Motor Docker funcionando correctamente.
Comunicación entre cliente y servidor validada.
Imagen hello-world ejecutada exitosamente.
```


<img width="921" height="326" alt="image" src="https://github.com/user-attachments/assets/877769c2-b23a-4079-ae61-14cf9ba0ad25" />

## Búsqueda de imágenes Oracle

Comando ejecutado:

```bash
docker search oracle
```

Resultado:

Se verificó la disponibilidad de imágenes Oracle en Docker Hub y se seleccionó Oracle XE 21c para el laboratorio.

<img width="996" height="565" alt="image" src="https://github.com/user-attachments/assets/d15b56c8-6ab2-4163-b4c5-7cd8b3ad4186" />

<img width="805" height="137" alt="image" src="https://github.com/user-attachments/assets/bbfca0a9-8825-45d3-b201-bd6dfcd24dff" />

<img width="921" height="461" alt="image" src="https://github.com/user-attachments/assets/ffeef657-7bf9-47db-b688-6232bcd81a88" />


<img width="921" height="213" alt="image" src="https://github.com/user-attachments/assets/4f2a9d55-af55-4e51-b08a-3d67d795ff45" />
<img width="450" height="144" alt="image" src="https://github.com/user-attachments/assets/b5692a5d-05bf-4d5a-b9cf-c8fa919d473a" />
<img width="921" height="460" alt="image" src="https://github.com/user-attachments/assets/8d9c0da6-e54e-41a7-809a-b37f64e99d57" />


Creación del usuario DBA_JUNIOR

CREATE USER DBA_JUNIOR IDENTIFIED BY Oracle123;
GRANT CONNECT, RESOURCE TO DBA_JUNIOR;

Verificación:

SELECT USERNAME
FROM DBA_USERS
WHERE USERNAME='DBA_JUNIOR';
Resultado:
DBA_JUNIOR

docker exec -it oracle-xe sqlplus dba_junior/Oracle123@XEPDB1

CREATE TABLE empleados (
    id NUMBER,
    nombre VARCHAR2(50)
);
Table created.

INSERT INTO empleados VALUES (1,'Andres');

Se ingresó nuevamente como SYSDBA y se otorgó cuota sobre el tablespace USERS:
ALTER USER DBA_JUNIOR
QUOTA UNLIMITED ON USERS;
User altered.

INSERT INTO empleados VALUES (1,'Andres');
COMMIT;
SELECT * FROM empleados;
ID  NOMBRE
1   Andres

<img width="921" height="585" alt="image" src="https://github.com/user-attachments/assets/a8b91830-84d6-41e7-a52d-7279d7d50b52" />
<img width="921" height="838" alt="image" src="https://github.com/user-attachments/assets/d15edac7-0343-4ea3-9ffd-5d17a7b351e9" />
<img width="921" height="765" alt="image" src="https://github.com/user-attachments/assets/d4b44c62-3db6-47d7-ba03-03fa609e3305" />
<img width="921" height="809" alt="image" src="https://github.com/user-attachments/assets/5e1b0ee9-40b6-4a77-8f71-2da653b410ff" />
<img width="864" height="426" alt="image" src="https://github.com/user-attachments/assets/da7816eb-93c8-4461-9bcc-c1c9df03d8d5" />












