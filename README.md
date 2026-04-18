# 📌 Proyecto Microservicios - Plataforma GamerShop

## 📖 Descripción del Proyecto

El presente proyecto consiste en el desarrollo de una plataforma de ventas de productos gamer y cultura friki, implementada bajo una arquitectura de microservicios utilizando Spring Boot.

El sistema permite gestionar usuarios, productos, pedidos, pagos y otras funcionalidades, mediante servicios independientes que se comunican entre sí a través de APIs REST.

---

## 🎯 Objetivo

Diseñar e implementar una arquitectura distribuida basada en microservicios que permita:

* Separación de responsabilidades
* Comunicación entre servicios
* Persistencia independiente
* Implementación de reglas de negocio
* Manejo de errores y validaciones

---

## 🧱 Arquitectura del Sistema

El sistema está compuesto por **10 microservicios independientes**, cada uno con responsabilidad específica:

| Microservicio         | Responsabilidad           |
| --------------------- | ------------------------- |
| MS1 - Usuarios        | Gestión de usuarios       |
| MS2 - . . . . . .     | Responsabilidad ms2       |
| MS3 - . . . . .       | Responsabilidad ms3       |
| MS4 - . . . . .       | Responsabilidad ms4       |
| MS5 - . . . . .       | Responsabilidad ms5       |
| MS6 - . . . . .       | Responsabilidad ms6       |
| MS7 - . . . . .       | Responsabilidad ms7       |
| MS8 - . . . . .       | Responsabilidad ms8       |
| MS9 - . . . . .       | Responsabilidad ms9       |
| MS10 - . . . . .      | Responsabilidad ms10      |

---

## 🗄️ Persistencia de Datos 

* Cada microservicio posee su propia base de datos.
* No se comparten tablas entre servicios.
* Se mantiene la integridad referencial dentro de cada servicio.
* Se utiliza **MySQL** como motor de base de datos.

---

## 🧩 Estructura de Microservicios (Patrón CSR)

Cada microservicio implementa el patrón:

* **Controller** → Manejo de endpoints REST
* **Service** → Lógica de negocio
* **Repository** → Acceso a datos (JpaRepository)
* **Model (Entity)** → Representación de datos

---

## 🔄 Operaciones CRUD

Cada microservicio implementa operaciones CRUD completas sobre sus entidades principales:

Ejemplo:

### MS1 - Usuarios

* POST /usuarios → Crear usuario
* GET /usuarios → Obtener usuarios
* PUT /usuarios/{id} → Actualizar usuario
* DELETE /usuarios/{id} → Eliminar usuario

### MS3 - Catálogo

* GET /productos
* GET /productos/{id}
* GET /productos?categoria=

---

## ⚙️ Reglas de Negocio

El sistema implementa reglas de negocio relevantes, tales como:

* Validación de existencia de usuario antes de crear pedido
* Verificación de stock antes de confirmar compra
* Bloqueo de compra si el stock es insuficiente
* Cálculo de total de pedido

---

## ✅ Validaciones

Se implementan validaciones utilizando **Bean Validation (JSR 380)**:

* Campos obligatorios (@NotNull, @NotBlank)
* Validación de formato (correo, longitud, etc.)
* Validación de datos en los controladores mediante DTOs

---

## ⚠️ Manejo de Excepciones

* Uso de `@ControllerAdvice` para manejo global
* Respuestas con `ResponseEntity`
* Códigos HTTP adecuados:

  * 200 OK
  * 201 CREATED
  * 400 BAD REQUEST
  * 404 NOT FOUND

---
## 📡 Comunicación entre Microservicios

Los microservicios se comunican mediante:

* **REST APIs**
* Uso de **WebClient o Feign Client**

Ejemplo de flujo (Solo ejemplo):

1. Pedido consulta inventario
2. Inventario valida stock
3. Pedido solicita pago
4. Pago responde estado

---

## 📑 Endpoints REST

* Uso de rutas semánticas
* Métodos HTTP correctos (GET, POST, PUT, DELETE)
* Respuestas en formato JSON
* Uso de parámetros y request body estructurados

---

## 🧾 Logs

Se implementan logs mediante **SLF4J** para:

* Registro de operaciones
* Seguimiento de errores
* Trazabilidad del sistema

---

## 🧪 Pruebas

Se realizan pruebas de endpoints mediante:

* Postman

---

## 🛠️ Tecnologías Utilizadas

* Java 21+
* Spring Boot
* Spring Data JPA
* MySQL
* Maven

---

## 📂 Repositorio

El proyecto se gestiona mediante GitHub, cumpliendo con:

* Commits progresivos y descriptivos
* Trabajo colaborativo
* Organización del código por microservicio

---

## 👥 Integrantes

* Nombre 1 
* Nombre 2
* Nombre 3

---

## 🚀 Estado del Proyecto

En desarrollo – implementación de microservicios base para evaluación parcial 2.

---
