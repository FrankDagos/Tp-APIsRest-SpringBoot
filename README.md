# API REST de Gestión de Productos - Programación III

Este proyecto es el Trabajo Práctico Integrador para la materia Programación III de la Tecnicatura Universitaria en Programación de la UTN.

El objetivo es desarrollar una API REST completa y profesional para la gestión de productos, aplicando arquitectura en capas, validaciones, manejo de errores, persistencia con Spring Data JPA y documentación con Swagger/OpenAPI.

### Nombre: `Franco D'Agostino`
### Legajo: `47761`

---

## 🛠️ Tecnologías Utilizadas

* **Java 17**
* **Spring Boot 3.x**
* **Spring Web:** Para la creación de controladores REST.
* **Spring Data JPA:** Para la persistencia de datos y operaciones CRUD.
* **H2 Database:** Base de datos en memoria para desarrollo y pruebas.
* **Validation:** Para validaciones de DTOs con anotaciones (`@Valid`).
* **Lombok:** Para reducir código repetitivo (getters, setters, etc.).
* **Springdoc-OpenAPI (Swagger):** Para la documentación interactiva de la API.
* **Maven:** Como gestor de dependencias y proyecto.

---

## 🚀 Instalación y Ejecución

1.  **Clonar el repositorio:**
    ```bash
    git clone https://github.com/FrankDagos/Tp-APIsRest-SpringBoot.git
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

## 🌐 Acceso a Herramientas

Una vez que la aplicación esté en ejecución, puedes acceder a:

* **Documentación Swagger UI:** `http://localhost:8080/swagger-ui/index.html`
* **Consola H2 (Base de Datos):** `http://localhost:8080/h2-console`
    * **Importante:** Asegúrate de usar la URL JDBC correcta al conectar: `jdbc:h2:mem:productosdb`
    * **Usuario:** `sa`
    * **Contraseña:** `[la que hayas configurado en application.properties, o déjalo vacío si no pusiste]`

---

## Endpoints de la API

| Método | Ruta | Descripción |
| :--- | :--- | :--- |
| `GET` | `/api/productos` | Listar todos los productos. |
| `GET` | `/api/productos/{id}` | Obtener un producto por su ID. |
| `GET` | `/api/productos/categoria/{categoria}` | Filtrar productos por categoría. |
| `POST` | `/api/productos` | Crear un nuevo producto. |
| `PUT` | `/api/productos/{id}` | Actualizar un producto completo por ID. |
| `PATCH` | `/api/productos/{id}/stock` | Actualizar solo el stock de un producto por ID. |
| `DELETE` | `/api/productos/{id}` | Eliminar un producto por ID. |

---

## 📸 Pruebas Realizadas (Capturas de Swagger y H2)

A continuación, se presentan las capturas de pantalla de las pruebas realizadas con Swagger UI y la consola H2, como se solicita en el TP.

### 1. Prueba POST Exitosa (201 Created)

Se crea un nuevo producto ("Mouse Inalámbrico") y la API responde con un código 201 y el objeto creado.

![Prueba POST exitosa](capturas/post-exitoso.png)

### 2. Prueba GET (Listado de Productos 200 OK)

Se listan todos los productos de la base de datos.

![Prueba GET de todos los productos](capturas/get-todos.png)

### 3. Error de Validación 400 (POST)

Se intenta crear un producto con el campo `nombre` vacío. La API responde correctamente con un error 400 y el mensaje de validación "El nombre no puede estar vacío".

![Error de Validación 400](capturas/error-400.png)

### 4. Error 404 No Encontrado (GET por ID)

Se intenta obtener un producto con un `id` que no existe (ej. 999). La API responde con 404 y el mensaje "Producto no encontrado con ID: 999".

![Error 404 No Encontrado](capturas/error-404.png)

### 5. Consola H2 (Datos Persistidos)

Captura de la tabla `PRODUCTO` en la consola H2, mostrando los datos persistidos después de las operaciones de creación, actualización y eliminación.

![Tabla H2 con datos](capturas/h2-tabla.png)

### 6. Otras Pruebas de Endpoints

Para validar el funcionamiento completo de la API, se incluyen pruebas adicionales:

**GET por Categoría (200 OK)**
![GET por Categoría](capturas/get-categoria.png)

**PUT - Actualización Completa (200 OK)**
![PUT Actualización](capturas/put-producto.png)

**PATCH - Actualización de Stock (200 OK)**
![PATCH Stock](capturas/patch-stock.png)

**DELETE - Eliminación de Producto (204 No Content)**
![DELETE Producto](capturas/delete-producto.png)

---

## 💡 Conclusiones

`La verdad, este TP fue muy completo. Me sirvió para conectar todos los temas que vimos: armar la API con Spring Boot , separarla en capas (controlador, servicio y repositorio) y usar DTOs para no exponer directamente el modelo de la base de datos.





Al principio, configurar las validaciones y el manejo de errores global  fue un desafío, pero una vez que funcionó, vi lo mucho que limpia el código en los controladores. Poder probar todo al final con Swagger hizo que viera el valor de documentar la API, ya que facilita muchísimo las pruebas  y deja claro cómo usarla. Siento que ahora entiendo mucho mejor cómo se construye una API profesional de punta a punta`
