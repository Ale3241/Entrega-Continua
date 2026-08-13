# Entrega Continua - Hola Mundo

Aplicación web sencilla desarrollada con **Python y Flask**, utilizando **Docker** para crear y ejecutar la aplicación dentro de un contenedor.

## Descripción del proyecto

El objetivo de esta práctica es demostrar un flujo básico de **Entrega Continua (Continuous Delivery)** utilizando una aplicación web, Docker, Docker Hub, GitHub Actions y Render.

La aplicación muestra el mensaje:

**Hola Mundo desde Docker!**

## Tecnologías utilizadas

* Python 3.12
* Flask
* Docker
* Docker Hub
* GitHub
* GitHub Actions
* Render

## Estructura del proyecto

```text
Entrega-Continua/
├── app.py
├── requirements.txt
├── Dockerfile
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
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

## Docker

El proyecto utiliza un `Dockerfile` para crear una imagen basada en Python.

### Crear la imagen

```bash
docker build -t entregacontinua .
```

### Ejecutar el contenedor

```bash
docker run -p 5000:5000 entregacontinua
```

Después se puede abrir en el navegador:

```text
http://localhost:5000
```

## Docker Hub

La imagen de la aplicación está publicada en Docker Hub:

```text
alex3241/entregacontinua
```

### URL de la imagen

https://hub.docker.com/r/alex3241/entregacontinua

## GitHub Actions

El proyecto utiliza **GitHub Actions** para automatizar el proceso de Entrega Continua.

Cada vez que se realiza un `push` a la rama `main`, GitHub Actions ejecuta automáticamente los siguientes pasos:

1. Descarga el código del repositorio.
2. Inicia sesión en Docker Hub utilizando Secrets.
3. Construye la imagen Docker.
4. Publica la imagen en Docker Hub.
5. Ejecuta el despliegue de la aplicación en Render.

### Flujo de trabajo

```text
GitHub
   ↓
GitHub Actions
   ↓
Construcción de imagen Docker
   ↓
Docker Hub
   ↓
Render
   ↓
Aplicación desplegada
```

## Secrets

Para proteger las credenciales se utilizan Secrets de GitHub:

```text
DOCKER_USERNAME
DOCKER_PASSWORD
RENDER_DEPLOY_HOOK_URL
```

Las credenciales no se almacenan directamente dentro del código del proyecto.

## Aplicación en producción

🚀 **Aplicación:** https://entregacontinua.onrender.com

## Resultado

La aplicación puede ejecutarse mediante Docker y muestra:

```text
Hola Mundo desde Docker!
```

El proceso de GitHub Actions permite automatizar la publicación de la imagen y el despliegue de la aplicación.

## Autor

Alex
