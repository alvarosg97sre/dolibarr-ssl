Proyecto Dolibarr con Docker, Nginx y Certbot
=============================================

Este repositorio contiene la configuración y documentación necesaria para desplegar Dolibarr, un sistema de gestión empresarial, usando Docker. Se utiliza Nginx como servidor web y proxy inverso, y Certbot para la generación y manejo de certificados SSL.

Contenido
---------

-   `docker-compose.yml`: Archivo de configuración de Docker Compose para definir y ejecutar los servicios de Dolibarr, MariaDB, Nginx y Certbot.
-   `nginx.conf`: Archivo de configuración para Nginx, configurado para actuar como un proxy inverso y manejar SSL.

Componentes
-----------

-   Dolibarr: Aplicación de gestión empresarial.
-   MariaDB: Sistema de gestión de base de datos.
-   Nginx: Servidor web y proxy inverso.
-   Certbot: Herramienta para la generación de certificados SSL de Let's Encrypt.

Configuración y Despliegue
--------------------------

### Paso 1: Preparación

-   Instalar Docker y Docker Compose en el servidor.
-   Clonar este repositorio en el servidor.

### Paso 2: Docker Compose

-   Ejecutar `docker-compose up` para iniciar todos los servicios definidos en `docker-compose.yml`.

### Paso 3: Verificación

-   Verificar que todos los servicios estén ejecutándose correctamente mediante `docker ps`.

Problemas y Soluciones
----------------------

### Conflicto de Puertos y Configuración de Nginx

-   Se ajustó `docker-compose.yml` para exponer únicamente los puertos de Nginx.
-   Configuración de Nginx para redirigir el tráfico a Dolibarr y manejar los desafíos de Certbot.

### Generación de Certificados SSL

-   Modificación temporal de Nginx para escuchar solo en el puerto 80 y permitir que Certbot genere certificados SSL.
-   Reconfiguración de Nginx para HTTPS una vez obtenidos los certificados.

Uso y Acceso
------------

-   Dolibarr: Accesible a través de `https://dolibarr.orsatecsl.es` (o tu dominio específico), con Nginx actuando como proxy inverso.
-   Nginx y Certbot: Manejan las solicitudes y la renovación automática de certificados SSL.
