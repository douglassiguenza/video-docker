
#Correr la aplicación de manera automática

**Paso 1.
Limpiar ya sea de manera manual por medio de docker o automática por medio de la terminal cualquier rastro de contenedores, imagenes o volúmenes pasados de aplicación, esto con el fin de evitar problemas con la creación del contenedor de la aplicación

**Paso 2. Ejecutar el siguiente comando: mvn clean package -DskipTests 

**Paso 3. Para iniciar la aplicación y su entorno de ejecución, se hace uso del siguiente comando 
docker-compose up

**Paso 4.Ingresar a localhost:8080/users para verificar la conexión de la aplicación por medio de esta URL.



#Correr aplicación de forma manual

**Paso 1.
Limpiar ya sea de manera manual por medio de docker o automática por medio de la terminal cualquier rastro de contenedores, imagenes o volúmenes pasados de aplicacion, esto con el fin de evitar problemas con la creación del contenedor de la aplicación

**Paso 2. Crear la imagen, esto se hace mediante el siguiente comando
docker build -t parcial1 .

**Paso 3. Iniciar un contenedor llamado "contenedorparcial1" a partir de la imagen "parcial1", mapeando el puerto 8080 del host al puerto 8080 del contenedor.
docker run -d --name contendorparcial1 -p 8080:8080 parcial1

**Paso 4.Se Utiliza el comando docker pull para descargar la imagen más reciente de PostgreSQL desde el repositorio de Docker
docker pull postgres:latest

**Paso 5.
Inicia un contenedor de PostgreSQL llamado "basededatos", configurando una contraseña para el usuario "postgres".
docker run -d --name basededatos -p 5432:5432 -e POSTGRES_PASSWORD=postgres postgres:latest

**Paso 6.
Modificar el archivo aplication.properties especificamente en la linea spring.datasource.url=jdbc:postgresql://java_db:5432/postgres
a 
spring.datasource.url=jdbc:postgresql://localhost:5432/postgres

**Paso 7.
Ejecutar el archivo CrudApplicationTests.Java

**Paso 8.
Ingresar a localhost:8080/users para verificar la conexión de la aplicación por medio de esta URL.
