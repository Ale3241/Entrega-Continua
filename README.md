# Entrega Continua - Hola Mundo

Aplicación web sencilla desarrollada con **Python y Flask**, utilizando **Docker** para crear y ejecutar la aplicación dentro de un contenedor.

## Descripción del proyecto

El objetivo de esta práctica es demostrar un flujo básico de **Entrega Continua (Continuous Delivery)** utilizando una aplicación web, Docker y Docker Hub.

La aplicación muestra el mensaje:

**Hola Mundo desde Docker!**

## Tecnologías utilizadas

- Python 3.12
- Flask
- Docker
- Docker Hub

## Estructura del proyecto

```text
EntregaContinua/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
```

## Aplicación

La aplicación está desarrollada con Flask y utiliza el puerto **5000**.

Para ejecutarla directamente con Python:

```bash
python app.py
```

Luego se puede acceder desde:

```text
http://localhost:5000
```

## Dockerfile

El proyecto utiliza un `Dockerfile` para crear una imagen de Docker basada en Python.

El contenedor instala las dependencias necesarias y ejecuta la aplicación Flask.

## Crear la imagen Docker

Desde la carpeta del proyecto se ejecuta:

```bash
docker build -t entregacontinua .
```

## Ejecutar el contenedor

Para ejecutar la aplicación dentro de Docker:

```bash
docker run -p 5000:5000 entregacontinua
```

Después se puede abrir en el navegador:

```text
http://localhost:5000
```

## Docker Hub

La imagen de Docker será publicada en Docker Hub utilizando el nombre:

```text
TU_USUARIO/entregacontinua
```

Para asignar el nombre a la imagen:

```bash
docker tag entregacontinua TU_USUARIO/entregacontinua
```

Para iniciar sesión en Docker Hub:

```bash
docker login
```

Para subir la imagen:

```bash
docker push TU_USUARIO/entregacontinua
```

### URL de la imagen

Después de publicar la imagen, la URL será:

```text
https://hub.docker.com/r/TU_USUARIO/entregacontinua
```

> **Nota:** Reemplazar `TU_USUARIO` por el nombre real de usuario de Docker Hub.

## Resultado

Al ejecutar el contenedor y acceder a `http://localhost:5000`, la aplicación muestra:

```text
Hola Mundo desde Docker!
```

## Autor

Alex
