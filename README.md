# API REST - Foro de Alura

Este proyecto consiste en una API REST para un foro de discusión, desarrollado con Spring Boot. Permite gestionar usuarios, temas y publicaciones en un entorno de foro, brindando funcionalidades como la creación, edición y eliminación de entradas, así como la interacción entre usuarios.

## Requisitos
Para poder ejecutar el proyecto correctamente, asegúrate de tener instalados los siguientes programas:

- **Java 20**: Versión de Java necesaria para ejecutar la aplicación.
- **Maven 3.x**: Herramienta de gestión de proyectos y dependencias para Java.
- **MySQL**: Sistema de gestión de bases de datos relacional que se utilizará para almacenar la información del foro.


## Tecnologías Utilizadas

Este proyecto hace uso de las siguientes tecnologías:

- **Spring Boot 3.0.6**: Framework que facilita el desarrollo de aplicaciones Java, permitiendo una configuración sencilla y rápida para crear aplicaciones autónomas.
- **Spring Data JPA**: Implementación de JPA (Java Persistence API) que permite interactuar con la base de datos de forma más sencilla y con menos código, utilizando repositorios.
- **Lombok**: Biblioteca que reduce la cantidad de código repetitivo y boilerplate, generando automáticamente los métodos getters, setters, constructores, entre otros.
- **MySQL**: Base de datos relacional que se emplea para almacenar los datos del foro (usuarios, publicaciones, comentarios, etc.).

## Instalación
1. Clonar el repositorio
Primero, clona el repositorio del proyecto en tu máquina local utilizando el siguiente comando:

```bash
git clone <URL_DEL_REPOSITORIO>
```

2. Navegar al directorio del proyecto
Una vez clonado el repositorio, entra al directorio del proyecto con el siguiente comando:

```bash
cd Challenge-foro-alura
```

3. Configuración de la base de datos MySQL
Antes de ejecutar la aplicación, es necesario configurar la base de datos MySQL:

- Crea una base de datos en tu instancia de MySQL. Por ejemplo, puedes crear una base de datos llamada foro_alura.

- Actualiza las credenciales de la base de datos en el archivo src/main/resources/application.properties. Debes proporcionar la URL de conexión, el usuario y la contraseña de tu base de datos. El archivo application.properties debe quedar de la siguiente forma:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/tu_base_de_datos
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
```
Nota: Asegúrate de que MySQL esté corriendo en tu máquina local (o en la máquina donde planees ejecutar la API).

4. Compilar el proyecto con Maven
Una vez configurada la base de datos, procede a compilar el proyecto usando Maven. Ejecuta el siguiente comando en la raíz del proyecto:

```bash
./mvnw clean install
```
Este comando descargará las dependencias necesarias, compilará el proyecto y preparará el paquete para ser ejecutado.

5. Ejecutar la aplicación
Con el proyecto compilado, ahora puedes ejecutar la aplicación Spring Boot utilizando Maven. Ejecuta el siguiente comando:

```bash
./mvnw spring-boot:run
```
Este comando iniciará el servidor de la API, y podrás acceder a la API REST en la URL:

```arduino
http://localhost:8080
```

# Uso
Una vez que la aplicación esté en funcionamiento, podrás interactuar con la API REST a través de herramientas como Postman o mediante peticiones HTTP utilizando cURL. Aquí tienes un ejemplo de cómo realizar una solicitud GET para obtener información de todos los usuarios del foro:

```bash
curl -X GET http://localhost:8080/api/usuarios
```
En este caso, la URL base para todas las solicitudes será ```http://localhost:8080```, y puedes consultar los diferentes endpoints de la API para crear usuarios, temas, publicaciones y gestionar los comentarios de los usuarios.

## Ejemplos de Endpoints

- ```GET /api/usuarios``` : Obtiene todos los usuarios registrados en el foro.
- ```POST /api/usuarios``` : Crea un nuevo usuario en el foro.
- ```GET /api/temas``` : Obtiene todos los temas disponibles en el foro.
- ```POST /api/temas``` : Crea un nuevo tema en el foro.
- ```GET /api/publicaciones``` : Obtiene todas las publicaciones de un tema.
- ```POST /api/publicaciones``` : Crea una nueva publicación en un tema específico.

Para detalles sobre cómo interactuar con la API y la lista completa de endpoints disponibles, consulta la documentación de la API o utiliza herramientas como Swagger para explorar la interfaz de usuario de la API si está habilitada.

