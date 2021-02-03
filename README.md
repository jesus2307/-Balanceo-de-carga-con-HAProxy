# iaw-practica-17

# 1 Práctica 17: Balanceo de carga con HAProxy
En esta práctica vamos a modificar los archivos docker-compose.yml que hemos creado en las prácticas 15 y 16, y vamos a incluir un nuevo contenedor Docker con HAProxy para balancear la carga de los contenedores que ejecutan la aplicación web.

Posteriormente deberá realizar la implantación de ambos sitios web en Amazon Web Services (AWS) haciendo uso de contenedores Docker y de la herramienta Docker Compose.

### Abrir los puetos
+ 80
+ 8080
+ 1936
+ 3306
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/Captura33.PNG "imagen")
### Añadimos a nustro docker-compose (#documentamos los puestos en apache):
* A continuación se muestra un fragmento de un archivo docker-compose.yml que incluye un servicio de balanceo de carga con HAProxy que nos puede servir de ejemplo:
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/3.PNG "imagen")
<p>&lt;1&gt; Utilizaremos la imagen <a href="https://hub.docker.com/r/dockercloud/haproxy">dockercloud/haproxy</a> que está disponible en <a href="https://hub.docker.com/">Docker Hub</a>.</p>
<p>&lt;2&gt; El puerto 80 será el puerto del servicio que queremos balancear.</p>
<p>&lt;3&gt; El puerto 1936 nos permite acceder a una página web con información estadística del balanceador.</p>
<p>&lt;4&gt; Creamos un enlace con el servicio que queremos balancear. Los enlaces permiten que los contenedores se descubran entre sí y transfieran de manera segura información sobre un contenedor a otro contenedor.</p>
<p>&lt;5&gt; Es necesario montar el socket UNIX del Docker daemon (/var/run/docker.sock) para que el contenedor <code>lb</code> pueda comunicarse con el Docker daemon y obtener información del resto de contenedores.</p>

### inciamos el docker compose:
* En el siguiente ejemplo estaríamos iniciando todos los servicios que están definidos en el archivo docker-compose.yml y para el servicio de apache estaríamos creando 4 instancias.
docker-compose up --sacale apache=4
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/compose.PNG "imagen")
### Si inciamos nuesto navegador con nustra ip aparcera nustra pila lamp
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/capturass.PNG "imagen")
### i inciamos nuesto navegador con nustra ip con :1936
usuario:stats
contraseña:stats
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/1.PNG "imagen")
### tendremos toda la informacion general 
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/captura3.PNG "imagen")
