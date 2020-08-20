# Prueba 2do Bimestre
Asignatura: Servicios sobre redess\
Facultad: ESFOT
2020-A

### Integrantes
- Jonathan Pizarra
- Edison Jumbo

### Instrucciones 

1. Puede utilizar Kitematic para evidenciar que su imagen está siendo contenida
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/postgres_docker.png)
2. Puede utilizar el enlace que está al final para interactuar con la aplicación
3. Puede instalar cualquier imágen que se necesite por medio de Kitematic
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/mariadb_docker.png)


### PostgresSQL
1. Ejecutamos: `docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres` Este comando permite correr el programa en el puerto 5432:5432. Con el nombre yourContainerName. 
    ![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c1.png)
    
2. Para verificar que el contenedor de postgreSQL esta corriedo se debe ingresar el comando: `docker ps` 
 ![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c2.png)

3. Para poder conectarse con el contenedor es necesario ingresar el ID del contenedor: `docker exec -it [ID contenedor] bash`
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c3.png)

4. Configuración del cliente de PostgreSQL, descargamos el cliente pgAdmin: https://www.pgadmin.org/
Crear un nuevo servidor con cualquier nombre, en este caso lo llamaremos prueba.
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c4.png)
5. En la opción CONNECTION, debemos ingresar la IP del equipo local y la contraseña se debe ser cualquiera.
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c5.png))

6.  Se deben parar los servicios de postgresql por medio de este comando.
    `docker stop [ID contenedor]`
    
    Luego, creamos un nuevo contenedor para la base de datos postgreSQL. 
    `docker rm [ID contenedor]`

    Finalmente agregamos el nuevo servidor con las configuraciones ingresadas. 
    `docker run --name [ID contenedor] -e POSTGRES_PASSWORD=[password ingresada] -d postgres`

### MaríaDB
1. Primero de todo vamos a ver qué serie de imágenes tenemos disponibles. De la siguiente manera:
    `docker search mariadb`
    Nos aparecerán unas cuantas. Nosotros utilizaremos la última versión oficial, llamada “mariadb:latest”

2. Utilizamos el comando `docker pull mariadb:latest` para adquirir la imagen en us ultima versión

3. Para crear el contenedor utilizando la imagen, primero de todo utilizaremos el parámetro “inspect” para que nos muestre los puertos que utiliza la imagen: `docker inspect b1fe0881b739 | grep –i tcp`
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c6.png)

    En windows el equivalete  a "grep" es "findstr"
    ![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_7.png)
5. Para crear el contenedor vamos a especificar varias cosas, la primera, especificaremos la clave de superusuario utilizando -e MYSQL_ROOT_PASSWORD=nuestra-pass; además le vamos a asignar un nombre utilizando --name mariadbtst , de la siguiente manera:
`docker run -dti -p 33306:3306 --name mariadbtst -e MYSQL_ROOT_PASSWORD=contrasea b1fe0881b739`
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_8.png)

6. Una vez creado ya lo podemos ver en funcionamiento:
`docker run -dti -p  --name mariadbtst -e MYSQL_ROOT_PASSWORD=mariadb b28df07deb6c`


### ServidorWeb:
1. Lo primero que haremos ponernos en red, esto lo haremos mediante Hamachi!
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c9.png)

2. Lo segundo será establecer la conexión:
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker10.png)

3. Ahora crearemos un Script para que pueda tomar los datos desde la base, es decir sean consumidos, en nuestro caso lo haremos con PHP, y le daremos algunos estilos.
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c10.png)

### CLIENTE:
1. Utilizamos Nrock para generar una url y que de ese modo el cliente final pueda acceder a nuestro servicio
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c11.png)
    Utilizando*
![](https://raw.githubusercontent.com/EdisonStalin/pruebaB2_Servicios/master/Prueba_B2/assets/docker_c12.png)

    Puedes acceder a nuestra aplicación desde: http://b2d611b9506a.ngrok.io/APP_JSON/

Eso ha sido todo :)
Muchas gracias! 
Asignatura: Tópcios Especiales\
Facultad: ESFOT

2020-A
