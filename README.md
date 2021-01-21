# Auditoría de seguridad con WPScan

Realización de auditoría de seguridad con WPScan.

## Instalando Docker

Se puede instalar la utilidad para comprobar la seguridad de nuestro sitio Wordpress, pero en este caso vamos a utilizar un contenedor docker.

Si no tenemos Docker instalado, lo podemos instalar con el siguiente comando:

>apt install docker

Cuando se descargue, cada vez que lo queramos utilizar deberá de ser con el comando sudo, para evitar esto, tenemos que meter al usuario en el grupo de usuarios de Docker, esto se hace con el comando que hay a continuación:

>sudo usermod -aG docker $USER

Después de esto, tenemos que habilitar el servicio docker para que se arranque cada vez que iniciemos el sistema, para ello ejecutamos este comando:

>sudo systemctl enable docker

Ahora reiniciamos la máquina haciendo un reboot y podremos empezar a utilizar docker.

## Contenedor Docker con WPScan

Ahora tenemos que poner en funcionamiento el contenedor que tiene WPScan, si no tenemos la imagen, podemos mirar la página de [dockerhub](https://hub.docker.com), en donde tendremos todo lo relacionado con este [contenedor](https://hub.docker.com/r/wpscanteam/wpscan/).

Para descargar la imagen hacemos un pull:

>docker pull wpscanteam/wpscan

Y a continuación lo ponemos en marcha:

## Utilizando WPScan

Para utilizar la herramienta lo haremos de la siguiente forma, pondremos en funcionamiento el contenedor junto con la tarea que queramos que realice, es decir, así:

>docker run -it --rm wpscanteam/wpscan --url http://Ip

Donde IP será la dirección IP o DNS donde se encuentra alojado nuestro sitio Wordpress.
De esta forma haremos un escaneo completo de nuestro sitio Wordpress, aquí se muestran un par de capturas del resultado obgtenido al escanear mi sitio Wordpress:

![Esta es una imagen de ejemplo](/capturas/Demostracion_1.PNG)