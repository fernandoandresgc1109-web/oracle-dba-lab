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
