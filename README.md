# iaw-practica-17

# 1 Práctica 17: Balanceo de carga con HAProxy
En esta práctica vamos a modificar los archivos docker-compose.yml que hemos creado en las prácticas 15 y 16, y vamos a incluir un nuevo contenedor Docker con HAProxy para balancear la carga de los contenedores que ejecutan la aplicación web.

Posteriormente deberá realizar la implantación de ambos sitios web en Amazon Web Services (AWS) haciendo uso de contenedores Docker y de la herramienta Docker Compose.

### Abrir los puetos
80
8080
1936
3306

### Añadimos a nustro docker-compose (#documentamos los puestos en apache):
###### services:
######  lb:
######    image: dockercloud/haproxy
######    ports:
######      - 80:80
######      - 1936:1936
######    links:
######      - apache
######    volumes:
######      - /var/run/docker.sock:/var/run/docker.sock
######    networks:
######      - frontend-network
    
### inciamos el docker compose:
docker-compose up --sacale apache=(numero de instancias que queramos)
### inciamos con :1936
usuario:stats
contraseña:stats
