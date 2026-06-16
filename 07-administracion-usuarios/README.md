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
