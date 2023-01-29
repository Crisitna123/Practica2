# Partimos de una imagen de Ubuntu
FROM ubuntu:latest
# Nos posicionamos en el directorio raíz
WORKDIR /
# Hace un update y configura el tzdata automáticamente y por defecto 
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt install -y tzdata
# Instala apache 
RUN apt-get install -y apache2 
# Instala php
RUN apt-get install -y php 
# Instala dependencias necesarias de apache para que funcione php
RUN apt-get install -y libapache2-mod-php 
RUN apt-get install -y apache2-utils
# Instala git
RUN apt-get install -y git
# Crea una carpeta
RUN mkdir php
# Nos posicionamos en la carpeta que acabamos de crear
WORKDIR /php
# Descarga el repositorio de git
RUN git clone https://github.com/Crisitna123/proyectoPHP.git
# Copia el repositorio en la carpeta indicada
RUN cp -r /php/proyectoPHP/ /var/www/html/
# Exponemos el puerto 80
EXPOSE 80
# Inicia el servidor apache
CMD ["/usr/sbin/apache2ctl","-D","FOREGROUND"]


