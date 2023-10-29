# # LAMP en dos niveles
### Creamos los sh de arpivisonamiento de las dos maquinas virtuales
#### Script para MySQL
![](FOTOS/1.png)
#### Script para Apache2
![](FOTOS/2.png)
### Una vez creados los scripts, configuraremos el Vagrantfile agregando ambas maquinas y aplicando el aprovisionamiento
![](FOTOS/3.png)
### Una vez configurado todo, ponemos **vagrant up** y se empezaran a levantar ambas maquinas. Para comprobar que no han habido errores al iniciar las maquinas con el comando **vagrant status** podemos ver el estado de estas.
![](FOTOS/4.png)
![](FOTOS/5.png)

# Configuracion MySQL
### Lo primero que hay que hacer es entrar en el directorio */etc/mysql/mariadb.conf.d* y ahí modificar el fichero *50-server.cnf*.
![](FOTOS/6.png)
### En este fichero cambiaremos la *bind-address* y pondremos la ip de nuestra maquina sql.
![](FOTOS/7.png)
### Ahora entramos a mysql como root y creamos un usuario con la ip de la maquina apache y le daremos todos los permisos en la base de datos que deseemos.
![](FOTOS/10.png)
### En el home de esta maquina clonaremos el repositorio de git para poder descargar la base de datos.
![](FOTOS/9.png)

# Configuracion APACHE
### Creamos una carpeta en */var/www* y le cambiamos el propietario con **chown**. Despues clonamos el repositorio de github con **git clone** y el enlace del repositorio que queremos usar.
![](FOTOS/11.png)
### Con sudo nano a el nuevo archivo de configuración ponemos la ruta de la carpeta en */var/www*.
![](FOTOS/12.png)
### Ahora habilitamos el fichero de configuración con **a2ensite**. 
![](FOTOS/13.png)
### Lo siguiente es entrar en la carpeta creada en */var/www* y editar el fichero config.php.
![](FOTOS/14.png)
### En este fichero donde pone localhost ponemos la ip de la maquina de sql y cambiamos los datos de user y password.
![](FOTOS/15.png)
### Ahora si ponemos la dirección de la maquina de apache en Google saldrá la pagina del LAMP.
![](FOTOS/16.png)
