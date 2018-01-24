# Taller 1

**Nombre:** Carlos Arredondo  
**Código:** A00274596

## Descripción
En este taller deberá consignar los pasos para:
* Instalación y configuración de CentOS7
* Instalación y configuración del servidor de Apache

## Pasos

* Recien instalado centos 7 y una vez configurado una contraseña para root, y las cuentas respectivas se procede a subir la interfaz ens33 con el comando "ifup ens33".

*  Luego, con el comando "yum install httpd -y" se instala el servidor de apache.

* Una vez instalado el servidor de apache con el comando "firewall-cmd --zone=public --add-port=80/tcp --permanent" se habilita el puerto 80

* Se crea el directorio public_html con la ruta y el comando "sudo mkdir -p /var/www/nombreDelDominio/public_html"

*Se asignan permisos de edición "chmod -R 755 /var/www"

* Dentro del directorio public_html se crea el archivo index.html y se añade codigo básico de una pagina web plana

* se crean los direccotorios sites-available y sites-enabled con los comandos
"sudo mkdir /etc/httpd/sites-available"
"sudo mkdir /etc/httpd/sites-enabled"

* en el archivo httpd.conf que se encuentra en " /etc/httpd/conf/httpd.conf" se agrega la siguiente linea: IncludeOptional sites-enabled/*.conf

* con el comando "sudo vi /etc/httpd/sites-available/nombreDelDominio.com.conf" se crea el archivo de host que contendrá la configuración básica del host.

* con el comando "ln -s /etc/httpd/sites-available/nombreDelDominio.conf /etc/httpd/sites-enabled/nombreDelDominio.conf" se habilita para que la página pueda ser consultada.

* Por último se reinicia el servidor apache
