# Administración de usuarios en Oracle XE

## Bloqueo y desbloqueo de usuario

En esta práctica se administró el estado de la cuenta `DBA_JUNIOR` dentro de la base de datos `XEPDB1`.

### Comandos utilizados

```sql
ALTER USER DBA_JUNIOR ACCOUNT LOCK;

SELECT username, account_status
FROM dba_users
WHERE username = 'DBA_JUNIOR';

ALTER USER DBA_JUNIOR ACCOUNT UNLOCK;

SELECT username, account_status
FROM dba_users
WHERE username = 'DBA_JUNIOR';

Evidencia de bloqueo y desbloqueo de usuario:
```

<img width="921" height="791" alt="image" src="https://github.com/user-attachments/assets/2ecb03a1-59d0-47b4-a67c-9bf9ba2d6440" />

## Cambio de contraseña de usuario

En esta práctica se modificó la contraseña del usuario DBA_JUNIOR mediante el comando ALTER USER.

### Comando utilizado

```sql
ALTER USER DBA_JUNIOR
IDENTIFIED BY Oracle2026;
```

<img width="808" height="100" alt="image" src="https://github.com/user-attachments/assets/2bc0413d-3d8b-48b2-bbac-21c3990c0450" />

## Creación de un rol personalizado

En esta práctica se creó el rol `ROL_DESARROLLADOR` para administrar privilegios de forma centralizada.

### Comando utilizado

```sql
CREATE ROLE ROL_DESARROLLADOR;
```

### Verificación

```sql
SELECT role
FROM dba_roles
WHERE role = 'ROL_DESARROLLADOR';
```

### Resultado

El rol fue creado correctamente y quedó disponible para asignar permisos y ser utilizado por distintos usuarios de la base de datos.

<img width="921" height="221" alt="image" src="https://github.com/user-attachments/assets/cda39987-0558-4bc0-b8ac-d003b8ddcf53" />

## Asignación de privilegios a un rol

Después de crear el rol `ROL_DESARROLLADOR`, se asignaron privilegios para permitir la conexión a la base de datos y la creación de objetos.

### Comandos utilizados

```sql
GRANT CREATE SESSION TO ROL_DESARROLLADOR;
GRANT CREATE TABLE TO ROL_DESARROLLADOR;
GRANT CREATE VIEW TO ROL_DESARROLLADOR;
```

### Verificación

```sql
SELECT grantee, privilege
FROM dba_sys_privs
WHERE grantee = 'ROL_DESARROLLADOR';
```

### Resultado

El rol `ROL_DESARROLLADOR` recibió correctamente los privilegios necesarios para conectarse a la base de datos y crear tablas y vistas.
<img width="921" height="408" alt="image" src="https://github.com/user-attachments/assets/10c2a010-3a6a-44c1-ba55-0a44ce4b1d67" />

## Asignación de rol a usuario

Después de configurar el rol `ROL_DESARROLLADOR`, este fue asignado al usuario `DBA_JUNIOR`.

### Comando utilizado

```sql
GRANT ROL_DESARROLLADOR TO DBA_JUNIOR;
```
SELECT grantee, granted_role
FROM dba_role_privs
WHERE grantee = 'DBA_JUNIOR';

<img width="921" height="391" alt="image" src="https://github.com/user-attachments/assets/3bb19db2-ddef-4efa-8d84-bc4f8ed113eb" />



