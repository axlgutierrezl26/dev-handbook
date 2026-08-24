
1. Se realiza la descarga de una imagen postgres , desde la pagina docker hub <br>
```https://hub.docker.com/_/postgres/tags```<br>
```docker pull postgres:latest```
2. Verificar las variables de entorno en la siguiente documentacion
```https://hub.docker.com/_/postgres```
3. Crear una instancia (contenedor) de PostgreSQL basada en la imagen oficial.<br>
El servidor PostgreSQL escucha en el puerto 5432 dentro del contenedor, pero como ese puerto no ha sido publicado (-p), solo es accesible desde la red interna de Docker.
```docker container run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres```<br>

Ejemplo : El puerto 5432 del contenedor no está publicado hacia el host. Por ello, no es posible acceder a 
PostgreSQL desde localhost:5432.<br>

CONTAINER ID   IMAGE      COMMAND                  CREATED         STATUS         PORTS      NAMES
ddb29cad71b9   postgres   "docker-entrypoint.s…"   8 seconds ago   Up 7 seconds   5432/tcp   some-postgres

4. Utilizar la instancia en tu maquina , -dp <br>
-d : detached -> El contenedor sigue ejecutando en segundo plano , se sigue ejecutando el contenedor aunque la teminal quede libre<br>
-p: publish (publicar puerto) -> Sintaxis : -p <puerto_host>:<puerto_contenedor> <br>
```docker container run --name some-postgres -p 5432:5432 -e POSTGRES_PASSWORD=mysecretpassword -d postgres```<br>

Ejemplo : el puerto muestro localhost:5432<br>
CONTAINER ID   IMAGE      COMMAND                  CREATED             STATUS             PORTS                                         NAMES
45d5918d1d39   postgres   "docker-entrypoint.s…"   About an hour ago   Up About an hour   0.0.0.0:5432->5432/tcp, [::]:5432->5432/tcp   some-postgres

###
1. Aparecen todos los contenedores
```docker ps -a``` && ```docker container ls -a```<br>
Comando para solo mostrar los contenedores activos
```docker ps``` && ```docker container ls```
2. Eliminacion del contenedor
```docker container rm -f containerID```<br>
docker container : vas a trabajar con el contenedor <br>
rm: eliminar el contenedor <br>
-f (--force) : forzar eliminacion e incluso si el contenedor esta en ejecucion (internamente docker realiza un ```docker stop```) <br>
code: es el nombre (o el ID) del contenedor que quieres eliminar. (containerID: puede ser el ID o el nombre del contenedor.)

###

1. Crear una base de datos en postgres
```docker container run --name postgres-sale -p 5432:5432 -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin -e POSTGRES_DB=crud_api_sale -d postgres```<br>


