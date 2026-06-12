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






