# API REST de Gestión de Productos - Programación III

Este proyecto es el Trabajo Práctico Integrador para la materia Programación III de la Tecnicatura Universitaria en Programación de la UTN.

[cite_start]El objetivo es desarrollar una API REST completa y profesional para la gestión de productos, aplicando arquitectura en capas, validaciones, manejo de errores, persistencia con Spring Data JPA y documentación con Swagger/OpenAPI[cite: 9, 10, 11].

### Nombre: `[Tu Nombre Aquí]`
### Legajo: `[Tu Legajo Aquí]`

---

## [cite_start]🛠️ Tecnologías Utilizadas [cite: 246]

* [cite_start]**Java 17** [cite: 27]
* [cite_start]**Spring Boot 3.x** [cite: 27]
* [cite_start]**Spring Web:** Para la creación de controladores REST. [cite: 30]
* [cite_start]**Spring Data JPA:** Para la persistencia de datos y operaciones CRUD. [cite: 31]
* [cite_start]**H2 Database:** Base de datos en memoria para desarrollo y pruebas. [cite: 32]
* [cite_start]**Validation:** Para validaciones de DTOs con anotaciones (`@Valid`). [cite: 33]
* [cite_start]**Lombok:** Para reducir código repetitivo (getters, setters, etc.). [cite: 34]
* [cite_start]**Springdoc-OpenAPI (Swagger):** Para la documentación interactiva de la API. [cite: 172]
* [cite_start]**Maven:** Como gestor de dependencias y proyecto. [cite: 27]

---

## [cite_start]🚀 Instalación y Ejecución [cite: 248]

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/](https://github.com/)[TuUsuario]/[TuRepositorio].git
    ```

2.  **Navegar al directorio:**
    ```bash
    cd productos-api
    ```

3.  **Ejecutar la aplicación:**
    * **Desde un IDE (Recomendado):** Abrir el proyecto con IntelliJ IDEA o VS Code y ejecutar la clase principal `ProductosApiApplication.java`.
    * **Desde la terminal (usando Maven):**
        ```bash
        mvn spring-boot:run
        ```

---

## [cite_start]🌐 Acceso a Herramientas [cite: 259]

Una vez que la aplicación esté en ejecución, puedes acceder a:

* **Documentación Swagger UI:** `http://localhost:8080/swagger-ui/index.html`
* **Consola H2 (Base de Datos):** `http://localhost:8080/h2-console`
    * **Importante:** Asegúrate de usar la URL JDBC correcta al conectar: `jdbc:h2:mem:productosdb`
    * **Usuario:** `sa`
    * **Contraseña:** `[la que hayas configurado en application.properties, o déjalo vacío si no pusiste]`

---

## [cite_start]Endpoints de la API [cite: 254]

| Método | Ruta | Descripción |
| :--- | :--- | :--- |
| `GET` | `/api/productos` | [cite_start]Listar todos los productos. [cite: 128] |
| `GET` | `/api/productos/{id}` | [cite_start]Obtener un producto por su ID. [cite: 134] |
| `GET` | `/api/productos/categoria/{categoria}` | [cite_start]Filtrar productos por categoría. [cite: 134] |
| `POST` | `/api/productos` | [cite_start]Crear un nuevo producto. [cite: 134] |
| `PUT` | `/api/productos/{id}` | [cite_start]Actualizar un producto completo por ID. [cite: 134] |
| `PATCH` | `/api/productos/{id}/stock` | [cite_start]Actualizar solo el stock de un producto por ID. [cite: 134] |
| `DELETE` | `/api/productos/{id}` | [cite_start]Eliminar un producto por ID. [cite: 134] |

---

## 📸 Pruebas Realizadas (Capturas de Swagger y H2)

A continuación, se presentan las capturas de pantalla de las pruebas realizadas con Swagger UI y la consola H2, como se solicita en el TP.

### [cite_start]1. Prueba POST Exitosa (201 Created) [cite: 257]

[cite_start]Se crea un nuevo producto ("Mouse Inalámbrico") y la API responde con un código 201 y el objeto creado. [cite: 1]

![Prueba POST exitosa](ruta/a/tu/post-exitoso.png)

### [cite_start]2. Prueba GET (Listado de Productos 200 OK) [cite: 257]

[cite_start]Se listan todos los productos de la base de datos. [cite: 3]

![Prueba GET de todos los productos](ruta/a/tu/get-todos.png)

### [cite_start]3. Error de Validación 400 (POST) [cite: 258]

Se intenta crear un producto con el campo `nombre` vacío. [cite_start]La API responde correctamente con un error 400 y el mensaje de validación "El nombre no puede estar vacío". [cite: 2]

![Error de Validación 400](ruta/a/tu/error-400.png)

### [cite_start]4. Error 404 No Encontrado (GET por ID) [cite: 258]

Se intenta obtener un producto con un `id` que no existe (ej. 999). [cite_start]La API responde con 404 y el mensaje "Producto no encontrado con ID: 999". [cite: 6]

![Error 404 No Encontrado](ruta/a/tu/error-404.png)

### [cite_start]5. Consola H2 (Datos Persistidos) [cite: 259]

[cite_start]Captura de la tabla `PRODUCTO` en la consola H2, mostrando los datos persistidos después de las operaciones de creación, actualización y eliminación. [cite: 10]

![Tabla H2 con datos](ruta/a/tu/h2-tabla.png)

### 6. Otras Pruebas de Endpoints

Para validar el funcionamiento completo de la API, se incluyen pruebas adicionales:

[cite_start]**GET por Categoría (200 OK)** [cite: 4]
![GET por Categoría](ruta/a/tu/get-categoria.png)

[cite_start]**PUT - Actualización Completa (200 OK)** [cite: 7]
![PUT Actualización](ruta/a/tu/put-producto.png)

[cite_start]**PATCH - Actualización de Stock (200 OK)** [cite: 8]
![PATCH Stock](ruta/a/tu/patch-stock.png)

[cite_start]**DELETE - Eliminación de Producto (204 No Content)** [cite: 9]
![DELETE Producto](ruta/a/tu/delete-producto.png)

---

## [cite_start]💡 Conclusiones [cite: 259]

`[Escribe aquí tus conclusiones personales sobre el trabajo. ¿Qué aprendiste? ¿Qué desafíos encontraste? ¿Cómo aplicaste los conceptos de la materia (arquitectura en capas, DTOs, JPA, manejo de errores)?]`

`Ejemplo:`
`Este trabajo práctico me permitió consolidar todos los conceptos de la materia. Implementar la arquitectura en capas (Controlador, Servicio, Repositorio) fue clave para mantener el código ordenado. [cite_start]El uso de DTOs [cite: 11] [cite_start]me ayudó a entender la importancia de desacoplar la API del modelo de datos y a manejar las validaciones [cite: 110] de forma limpia. [cite_start]El desafío principal fue configurar correctamente el manejo global de excepciones[cite: 157], pero una vez implementado, simplificó enormemente la lógica de los controladores. [cite_start]Finalmente, documentar con Swagger [cite: 169] demostró ser una herramienta fundamental para probar y presentar la API de forma profesional.`
