# iaw-practica-17

# 1 Práctica 17: Balanceo de carga con HAProxy
En esta práctica vamos a modificar los archivos docker-compose.yml que hemos creado en las prácticas 15 y 16, y vamos a incluir un nuevo contenedor Docker con HAProxy para balancear la carga de los contenedores que ejecutan la aplicación web.

Posteriormente deberá realizar la implantación de ambos sitios web en Amazon Web Services (AWS) haciendo uso de contenedores Docker y de la herramienta Docker Compose.

### Abrir los puetos
+ 80
+ 8080
+ 1936
+ 3306

### Añadimos a nustro docker-compose (#documentamos los puestos en apache):
* A continuación se muestra un fragmento de un archivo docker-compose.yml que incluye un servicio de balanceo de carga con HAProxy que nos puede servir de ejemplo:
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/3.PNG "imagen")
    
### inciamos el docker compose:
docker-compose up --sacale apache=(numero de instancias que queramos)
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/compose.PNG "imagen")
### inciamos con :1936
usuario:stats
contraseña:stats
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/1.PNG "imagen")
### tendremos toda la informacion general 
![imagen](https://github.com/jesus2307/iaw-practica-17/blob/main/imagen/captura3.PNG "imagen")
