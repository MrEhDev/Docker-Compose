
<div align="center">
  
  # Docker Compose files
  
  Mis archivos Docker compose y como instalarlos
  
  [![Platform](https://img.shields.io/badge/platform-Docker-blue)](https://www.docker.com/)
  [![Apache-2.0 License](https://img.shields.io/github/license/containrrr/watchtower.svg)](https://www.apache.org/licenses/LICENSE-2.0)
  [![Tip Me via PayPal](https://img.shields.io/badge/PayPal-tip%20me-blue.svg?logo=paypal&style=flat)](https://www.paypal.me/EleazarDevTech)

</div>


En este repositorio puedes encontrar mis archivos Docker-Compose junto con un archivo .env en el que puedes configurar tus variables de configuración para realizar las instalaciones de manera más sencilla.

Desde el índice podrás navegar de manera sencilla a los distintos pasos según tu necesidad.

# Indice: 

[**1. Instalación de Docker y Docker-Compose**](https://github.com/EleazarDevTech/Docker-Compose/blob/main/README.md#instalaci%C3%B3n-de-docker)

[**2. Configuración de variables de entorno**](https://github.com/EleazarDevTech/Docker-Compose/blob/main/README.md#configuraci%C3%B3n-de-variables-de-entorno)
**O** 
[**Configuración de archivos docker-compose**](https://github.com/EleazarDevTech/Docker-Compose/blob/main/README.md#configuraci%C3%B3n-de-datos-en-el-archivo-docker-compose)

[**3. Levantar Docker**](https://github.com/EleazarDevTech/Docker-Compose/blob/main/README.md#uso-de-docker-compose)

---
---
## Listado de dockers añadidos:
- [**DeCONZ**](https://github.com/deconz-community/deconz-docker): Controla una red ZigBee mediante una interfaz serial USB Conbee.
- [**Duckdns**](https://github.com/linuxserver/docker-duckdns): Servicio gratuito que apuntará un DNS (subdominio de duckdns.org) a una IP de su elección.
- [**Duplicati**](https://github.com/duplicati/duplicati): Almacena copias de seguridad cifradas de forma segura en servicios de almacenamiento en la nube.
- [**Fail2ban**](https://docs.linuxserver.io/images/docker-fail2ban/): Servicio para prohibir hosts que causan múltiples errores de autenticación.
- [**Ha-Dockermon**](https://github.com/philhawthorne/ha-dockermon): Servicio simple que comprueba el estado de un contenedor.Docker y devuelve una respuesta RESTful
- [**Home Assistant**](https://github.com/home-assistant/core): Sistema domotico de código abierto que prioriza el control local y la privacidad.
- [**Jackett**](https://hub.docker.com/r/linuxserver/jackett): Proxy indexador que admite un rango amplio de rastreadores públicos y privados para Sonarr y Radarr.
- [**JDownloader 2**](https://github.com/jlesage/docker-jdownloader-2): Herramienta de gestión de descargas gratuita y de código abierto.
- [**MariaDB**](https://hub.docker.com/r/linuxserver/mariadb): Uno de los servidores de bases de datos más populares.
- [**Minidlna**](https://github.com/crocandr/docker-minidlna): Servidor ligero de DLNA.
- [**NextCloud**](https://github.com/nextcloud/docker): Accede y comparte tus archivos, calendarios, contactos, correo y más desde cualquier dispositivo.
- [**Pi-Hole**](https://github.com/pi-hole/docker-pi-hole): Bloqueo de anuncios en toda la red
- [**Plex**](https://docs.linuxserver.io/images/docker-plex/): Organiza multimedia y los transmite a televisores y dispositivos móviles.
- [**Radarr**](https://docs.linuxserver.io/images/docker-radarr): Gestor de colecciones de películas para servicios torrent.
- [**Ring-Mqtt**](https://github.com/tsightler/ring-mqtt): Crea un puente entre estos dispositivos Ring y un agente MQTT local.
- [**Sonarr**](https://github.com/hotio/sonarr): Gestor de colecciones de series para servicios torrent.
- [**Transmission**](https://hub.docker.com/r/linuxserver/transmission): Cliente de BitTorrent rápido, sencillo y gratuito.
- [**VS Code**](https://docs.linuxserver.io/images/docker-code-server/): Completo ejecutándose en un servidor remoto, accesible a través del navegador.
- [**Watchtower**](https://github.com/containrrr/watchtower): proceso para automatizar las actualizaciones de imágenes base del contenedor Docker.


---
---
## Requisitos previos

Antes de comenzar, asegúrate de tener Docker y Docker Compose instalados en tu sistema.

### Instalación de Docker

1. **Actualizar el sistema:**

   ```bash
   sudo apt-get update
   ```

2. **Instalar los paquetes necesarios:**

   ```bash
   sudo apt-get install \
       ca-certificates \
       curl \
       gnupg \
       lsb-release
   ```

3. **Añadir la clave GPG de Docker:**

   ```bash
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
   ```

4. **Añadir el repositorio de Docker:**

   ```bash
   echo \
     "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

5. **Instalar Docker:**

   ```bash
   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io
   ```

6. **Verificar la instalación:**

   ```bash
   sudo docker --version
   ```

### Instalación de Docker Compose

1. **Descargar la última versión de Docker Compose:**

   ```bash
   sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   ```

2. **Aplicar permisos ejecutables:**

   ```bash
   sudo chmod +x /usr/local/bin/docker-compose
   ```

3. **Verificar la instalación:**

   ```bash
   docker-compose --version
   ```

# Docker y Docker-Compose instalados

El repositorio cuenta con un archivo de variables `env.templates` con el que puedes configurar los archivos docker-compose de manera global. Si quieres saber como hacerlo

## Configuración de datos en el archivo docker-compose

* Puedes copiar el archivo docker-compose.yml en tu maquina

* Modificar las variables de entorno por tus datos

 Ejemplo:
>  TZ=${DOCKER_TZ}
: Cambialo a :
> TZ=Europe/Madrid

* Y por último crea el docker con ```docker-compose up -d```

###  Configuración de variables de entorno

Este proyecto utiliza un archivo `.env.templates` para almacenar las variables de entorno. Antes de ejecutar Docker Compose, es importante que revises y edites este archivo con tus datos y según tus necesidades.

1. **Abrir el archivo `.env.templates` en un editor de texto:**

   `$ nano .env`

2. **Modificar las variables según sea necesario:**

   - `DOCKER_TZ`=TuZonaHoraria
   - `DOCKER_PATH_BACKUPS`=TuCarpetaDeBackup
   - `DOCKER_PATCH`=TuCarpetaDocker

   

### Exportar las variables de entorno

Una vez modificados los datos necesarios, asegurate de guardarlo como `.env` y utiliza el script `export-env.sh` para exportar las variables de entorno.

1. **Ejecutar el script `$. ./export-env.sh`**

   Este script cargará todas las variables de entorno definidas en el archivo `.env`.

## Uso de Docker Compose

Una vez que Docker y Docker Compose estén instalados y las variables de entorno configuradas, puedes iniciar los servicios definidos en el archivo `docker-compose.yml`.

1. **Colocate en la carpeta donde has copiado el archivo docker-compose**
    ```
    $ cd /nombre_de_la_carpeta
    ```
2. **Iniciar los contenedores en segundo plano:**

   ```
   $ docker-compose up -d
   ```

3. **Verificar que los contenedores estén corriendo:**

   ```
   $ docker-compose ps
   ```

## Contribuciones

Si deseas contribuir a este proyecto, siéntete libre de abrir un *pull request* o crear un *issue* para discutir posibles mejoras o problemas.

## Licencia

Este proyecto está bajo la Licencia Apache 2.0. Consulta el archivo `LICENSE` para más detalles.
