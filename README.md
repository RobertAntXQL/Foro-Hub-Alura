 ForoHub

**ForoHub** es una API REST desarrollada con Spring Framework para gestionar un foro de discusión. Los usuarios pueden crear, leer, actualizar y eliminar tópicos (CRUD). La API está diseñada siguiendo las mejores prácticas del modelo REST, e incluye validaciones, autenticación/autorización y una base de datos relacional para la persistencia de la información.

Características

- 📝 Crear un nuevo tópico
- 📖 Mostrar todos los tópicos creados
- 🔍 Mostrar un tópico específico
- ✏️ Actualizar un tópico
- 🗑️ Eliminar un tópico
- ✔️ Validaciones de las reglas de negocio
- 🔒 Autenticación y autorización de usuarios

Tecnologías Utilizadas

- **Java 11**
- **Spring Boot**
- **Spring Data JPA**
- **Spring Security**
- **Hibernate**
- **H2 Database** (para desarrollo y pruebas)
- **MySQL** (para producción)
- **Maven**

Instalación y Ejecución

### Prerrequisitos

- JDK 11 o superior
- Maven
- MySQL (para entorno de producción)

### Configuración

1. **Clonar el repositorio**:
    ```bash
    git clone https://github.com/tu-usuario/ForoHub.git
    cd ForoHub
    ```

2. **Configurar la base de datos**:

    - **Desarrollo y pruebas**: La aplicación está configurada para usar H2 Database por defecto.
    - **Producción**: Actualiza las configuraciones en `src/main/resources/application.properties` con las credenciales de tu base de datos MySQL.

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/forohub
    spring.datasource.username=tu-usuario
    spring.datasource.password=tu-contraseña
    spring.jpa.hibernate.ddl-auto=update
    ```

3. **Construir y ejecutar la aplicación**:

    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

## 📚 Uso de la API

### Endpoints

- **Crear un nuevo tópico**
    ```http
    POST /api/topics
    ```
    - Cuerpo de la petición (JSON):
        ```json
        {
            "titulo": "Título del Tópico",
            "mensaje": "Contenido del Tópico",
            "autorId": 1
        }
        ```

- **Mostrar todos los tópicos**
    ```http
    GET /api/topics
    ```

- **Mostrar un tópico específico**
    ```http
    GET /api/topics/{id}
    ```

- **Actualizar un tópico**
    ```http
    PUT /api/topics/{id}
    ```
    - Cuerpo de la petición (JSON):
        ```json
        {
            "titulo": "Nuevo Título del Tópico",
            "mensaje": "Nuevo Contenido del Tópico"
        }
        ```

- **Eliminar un tópico**
    ```http
    DELETE /api/topics/{id}
    ```

Autenticación y Autorización

La API usa **Spring Security** para la autenticación y autorización. Los usuarios deben autenticarse para acceder a los endpoints. 

Validaciones

- Todos los campos son obligatorios al crear o actualizar un tópico.
- Los mensajes de error se devuelven en caso de fallos en las validaciones.

 Contribuir

1. Haz un fork del proyecto.
2. Crea una nueva rama (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz un commit (`git commit -m 'Agregar nueva funcionalidad'`).
4. Sube los cambios a tu fork (`git push origin feature/nueva-funcionalidad`).
5. Abre un Pull Request.

Licencia

Este proyecto está licenciado bajo la **Licencia MIT**. Consulta el archivo `LICENSE` para obtener más detalles.
