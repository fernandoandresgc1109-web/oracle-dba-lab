## Solución de error por privilegios insuficientes

Durante la creación de la tabla `CLIENTES_PRUEBA` con el usuario `ANALISTA`, se presentó un error de privilegios insuficientes.

### Problema encontrado

Al intentar crear la tabla con el usuario `ANALISTA`, Oracle no permitió ejecutar la operación porque el usuario no tenía los permisos necesarios para crear tablas o no contaba con cuota asignada sobre el tablespace correspondiente.

### Causa

El usuario `ANALISTA` tenía permiso para conectarse a la base de datos, pero aún no tenía asignado el privilegio `CREATE TABLE` ni cuota suficiente sobre el tablespace `TS_DESARROLLO`.

### Solución aplicada

Se ingresó nuevamente como usuario administrador `SYS` dentro de la PDB `XEPDB1` y se otorgaron los permisos necesarios.

### Comandos utilizados

```sql
GRANT CREATE TABLE TO ANALISTA;

ALTER USER ANALISTA 
QUOTA UNLIMITED ON TS_DESARROLLO;
```

<img width="587" height="551" alt="image" src="https://github.com/user-attachments/assets/2220d8cc-5137-4a7f-baa4-6d9f66e6c79a" />
<img width="927" height="495" alt="image" src="https://github.com/user-attachments/assets/68985f31-8b0d-4e48-aeaf-9908dc819cac" />
