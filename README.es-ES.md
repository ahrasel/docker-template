

# Aplicación Web con Docker Compose

Este repositorio contiene una configuración de Docker Compose para un stack de aplicación web que consiste en PHP, MySQL, Nginx, PHPMyAdmin y caché Redis. Proporciona un entorno de desarrollo local para su aplicación web.

## Tabla de contenidos

- [Introducción](#introduction)
- [Requisitos previos](#prerequisites)
- [Comenzando](#getting-started)
  - [Configuración](#configuration)
- [Uso](#usage)
- [Servicios de Docker Compose](#docker-compose-services)
- [Personalización](#customization)
- [Licencia](#license)

## Introducción

Este proyecto simplifica la configuración de un entorno de desarrollo local para su aplicación web utilizando Docker Compose. Incluye los siguientes servicios:

- Servicio de PHP con PHP-FPM.
- Servicio de base de datos MySQL.
- Servidor web Nginx.
- PHPMyAdmin para la gestión de la base de datos.
- Servicio de caché Redis.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Comenzando

Para comenzar con este proyecto, siga estos pasos:

1. Clone este repositorio en su máquina local:

   ```bash
   git clone https://github.com/ahrasel/docker-template.git
   ```

2. Navegue al directorio del proyecto y añada esos archivos a su proyecto:

   ```bash
   cd your-repo
   ```

3. Cree un archivo `.env` en la raíz del proyecto y configure las variables de entorno:

   ```dotenv
   DOCKER_APP_PORT=8080
   DOCKER_APP_SSL_PORT=443
   DOCKER_DB_PORT=3306
   DOCKER_PHPMYADMIN_PORT=8081
   DOCKER_REDIS_PORT=6379
   ```

   Reemplace los valores con los puertos que desea utilizar.

4. Inicie los servicios de Docker Compose:

   ```bash
   docker-compose up -d
   ```

### Configuración

Puede personalizar el proyecto actualizando las variables de entorno en el archivo `.env` o modificando la configuración de Docker Compose en `docker-compose.yml`. Consulte la sección [Personalización](#customization) para más detalles.

## Uso

Una vez que los servicios estén ejecutándose, puede acceder a su aplicación web en `http://localhost:8080` (o el puerto que especificó) en su navegador web. PHPMyAdmin está disponible en `http://localhost:8081`.

## Servicios de Docker Compose

Este proyecto define los siguientes servicios de Docker Compose:

### myapp (Servicio de PHP)

- **Descripción:** Servicio de PHP para su aplicación web.
- **Puertos expuestos:** Ninguno.
- **Configuración:** Variables de entorno para configuraciones de PHP e información de usuario.

### myapp_db (Servicio de MySQL)

- **Descripción:** Servicio de base de datos MySQL.
- **Puertos expuestos:** Puerto 3306 (personalizar en `.env`).
- **Configuración:** Variables de entorno para credenciales y configuraciones de la base de datos.

### myapp_nginx (Servicio de Nginx)

- **Descripción:** Servicio de servidor web Nginx.
- **Puertos expuestos:** Puerto 80 (HTTP) y 443 (HTTPS) (personalizar en `.env`).
- **Configuración:** Monta archivos de configuración de Nginx y certificados SSL.

### myapp_phpmyadmin (Servicio de PHPMyAdmin)

- **Descripción:** Servicio de PHPMyAdmin para gestionar la base de datos MySQL.
- **Puertos expuestos:** Puerto 8081 (personalizar en `.env`).
- **Configuración:** Variables de entorno para conectarse a la base de datos.

### myapp_redis_cache (Servicio de Caché Redis)

- **Descripción:** Servicio de caché Redis.
- **Puertos expuestos:** Puerto 6379 (personalizar en `.env`).
- **Configuración:** Configura Redis con una contraseña y un volumen de datos.

## Personalización

Puede personalizar el proyecto de las siguientes maneras:

- Actualice las variables de entorno en el archivo `.env` para cambiar la configuración de puertos, credenciales de base de datos y otras opciones de configuración.
- Modifique la configuración de Docker Compose en `docker-compose.yml` para agregar o personalizar servicios.

## Licencia

Este proyecto está licenciado bajo la LICENCIA MIT - consulte el archivo [LICENSE.md](LICENSE.md) para más detalles.
