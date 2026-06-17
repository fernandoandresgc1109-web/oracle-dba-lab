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
