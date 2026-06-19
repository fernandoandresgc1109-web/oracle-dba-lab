# Tablespaces y Almacenamiento

## Consulta de tablespaces existentes

En esta práctica se consultaron los tablespaces disponibles en la base de datos Oracle para identificar las áreas lógicas de almacenamiento utilizadas por el sistema y los usuarios.

### Comando utilizado

```sql
SELECT tablespace_name,
       status,
       contents
FROM dba_tablespaces
ORDER BY tablespace_name;
```

### Resultado

Se obtuvo el listado de tablespaces configurados en la base de datos, incluyendo tablespaces permanentes, temporales y de sistema.

```
```
<img width="967" height="200" alt="image" src="https://github.com/user-attachments/assets/f15201df-6499-4545-9952-78c1763d4201" />

## Consulta de datafiles

Se consultaron los archivos físicos asociados a los tablespaces de Oracle.

### Comando utilizado

```sql
SELECT file_name,
       tablespace_name,
       bytes/1024/1024 AS MB
FROM dba_data_files;
```

### Resultado

Se identificaron los archivos físicos de almacenamiento utilizados por la base de datos y el tablespace al que pertenecen.

```
```

<img width="900" height="472" alt="image" src="https://github.com/user-attachments/assets/058f0431-85ab-4a8e-bf51-c7e1b79fd930" />

## Creación de un tablespace personalizado

Se creó el tablespace `TS_DESARROLLO` para almacenar objetos de usuarios y aplicaciones de forma independiente a los tablespaces predeterminados del sistema.

### Comando utilizado

```sql
CREATE TABLESPACE TS_DESARROLLO
DATAFILE '/opt/oracle/oradata/XE/ts_desarrollo01.dbf'
SIZE 100M
AUTOEXTEND ON
NEXT 10M
MAXSIZE 500M;
```

### Resultado

El tablespace fue creado correctamente con crecimiento automático habilitado para facilitar la administración del almacenamiento.

```
```

<img width="669" height="231" alt="image" src="https://github.com/user-attachments/assets/7f30692b-5589-45c0-9bc4-af5f7e395155" />
<img width="1386" height="87" alt="image" src="https://github.com/user-attachments/assets/4726294c-cf30-4388-a76e-d4d87ace9d87" />

## Verificación del tablespace creado

Después de crear el tablespace `TS_DESARROLLO`, se verificó su existencia dentro de la base de datos.

### Comando utilizado

```sql
SELECT tablespace_name,
       status,
       contents
FROM dba_tablespaces
WHERE tablespace_name = 'TS_DESARROLLO';
```

### Resultado

El tablespace quedó registrado correctamente y disponible para almacenar objetos de usuarios.

## Verificación del datafile asociado

Se consultó el archivo físico asociado al tablespace creado.

### Comando utilizado

```sql
SELECT tablespace_name,
       file_name,
       bytes/1024/1024 AS MB
FROM dba_data_files
WHERE tablespace_name = 'TS_DESARROLLO';
```

### Resultado

Se confirmó la creación del archivo físico `ts_desarrollo01.dbf` con un tamaño inicial de 100 MB y crecimiento automático habilitado.

<img width="921" height="587" alt="image" src="https://github.com/user-attachments/assets/12b57292-0b93-4428-9f77-111de346d001" />

## Asignación de tablespace a usuario

Se configuró el tablespace `TS_DESARROLLO` como tablespace predeterminado para el usuario `ANALISTA`.

### Problema encontrado

Inicialmente se presentó el error:

```sql
ORA-00959: tablespace 'TS_DESARROLLO' does not exist
```

La causa fue que el usuario y el tablespace se encontraban en contenedores diferentes dentro de la arquitectura multitenant de Oracle.

### Solución aplicada

Se verificó el contenedor activo, se creó el tablespace en la PDB correspondiente (`XEPDB1`) y posteriormente se realizó la asignación al usuario.

### Comando utilizado

```sql
ALTER USER ANALISTA
DEFAULT TABLESPACE TS_DESARROLLO;
```

### Verificación

```sql
SELECT username,
       default_tablespace
FROM dba_users
WHERE username = 'ANALISTA';
```

### Resultado

El usuario `ANALISTA` quedó configurado correctamente para utilizar `TS_DESARROLLO` como tablespace predeterminado para la creación de sus objetos.


<img width="672" height="702" alt="image" src="https://github.com/user-attachments/assets/0cec4f43-7e9e-42b9-a3f9-ecc24d0b05b3" />
<img width="642" height="550" alt="image" src="https://github.com/user-attachments/assets/e5df07ef-4176-4b55-b9a8-49bc05f74b90" />
<img width="652" height="616" alt="image" src="https://github.com/user-attachments/assets/afbb725b-7c93-405d-9f30-fa25382cdf91" />

## Monitoreo de espacio en tablespaces

Se realizaron consultas para verificar la capacidad y el espacio disponible de los tablespaces configurados en Oracle.

### Consulta de tamaño

```sql
SELECT tablespace_name,
       ROUND(SUM(bytes)/1024/1024,2) AS MB
FROM dba_data_files
GROUP BY tablespace_name
ORDER BY tablespace_name;
```

### Consulta de espacio libre

```sql
SELECT tablespace_name,
       ROUND(SUM(bytes)/1024/1024,2) AS MB_LIBRES
FROM dba_free_space
GROUP BY tablespace_name
ORDER BY tablespace_name;
```

### Resultado

Las consultas permitieron identificar el tamaño asignado y el espacio libre disponible en cada tablespace, información fundamental para la administración y planificación del almacenamiento de la base de datos.

<img width="596" height="340" alt="image" src="https://github.com/user-attachments/assets/a6749302-6c1e-4918-8537-c8ba23248beb" />
<img width="683" height="334" alt="image" src="https://github.com/user-attachments/assets/2a978df1-414c-4ab5-bb09-4a459fa18fa2" />
<img width="608" height="258" alt="image" src="https://github.com/user-attachments/assets/2d9d89db-7363-49d6-a417-07c476901803" />



