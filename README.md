#  Room Service API

Una API RESTful **Backend-Only** desarrollada para la gestión de servicios de un hotel (habitaciones, reservas, notificaciones y usuarios). Esta aplicación implementa el patrón **Modelo-Vista-Controlador (MVC)** y la **Programación Orientada a Objetos (POO)** en PHP.

---

##  Almacenamiento de Datos (No Relacional)

Este proyecto utiliza un sistema de almacenamiento **basado en archivos JSON** en lugar de una base de datos relacional tradicional (como MySQL).

* **Persistencia:** Los datos se persisten y se manipulan mediante la lectura y escritura directa de **archivos JSON**, utilizando `json_decode` y `json_encode` de PHP.
* **Modelo:** Esto simula un enfoque **NoSQL/Documental**, donde cada entidad se almacena como un documento JSON flexible.

---

##  Stack y Arquitectura

* **Lenguaje:** PHP (con uso de POO).
* **Patrón:** Modelo-Vista-Controlador (MVC).
* **Interacción:** Todas las peticiones se realizan a través de la **Línea de Comandos (CLI)** o herramientas de prueba de API (sin Front-end).

---

## Características y Seguridad

* **Sistema de Roles:** Implementa dos tipos de usuarios con permisos definidos:
    * **Admin:** Permisos completos para gestionar todas las entidades.
    * **Usuario Convencional:** Permisos limitados a sus propias reservas, notificaciones y datos personales.
* **Validación Estricta:** Se utilizan **expresiones regulares** para la validación de formatos de entrada (emails, fechas, etc.), garantizando la integridad del dato antes de su procesamiento.

---

## Endpoints y Permisos (CRUD)

| Entidad | Funcionalidades CRUD | Permisos |
| :--- | :--- | :--- |
| **`Habitaciones`** | Crear, Listar, Actualizar, Eliminar. | Solo **Admin** |
| **`Reservas`** | Crear, Listar (propias/todas), Actualizar, Eliminar. | **Admin** (todas) / **Usuario** (propias) |
| **`Notificaciones`** | Listar (propias/todas), Marcar como leída. | **Admin** (todas) / **Usuario** (propias) |
| **`Usuarios`** | Registrar, Listar, Modificar Datos, Eliminar. | **Admin** (completo) / **Usuario** (parcial) |

