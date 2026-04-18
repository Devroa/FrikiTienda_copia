# 📦 Microservicio: [Nombre del Microservicio]

Ejemplo: MS1 - Usuarios

ESTA PLANTILLA ESTA SIENDO MODIFICADA PARA AYUDE A ORIENTAR LA CONSTRUCCION DE MICROSERVICIOS
---

## 📌 Descripción

Describe brevemente qué hace este microservicio.

Ejemplo:
Gestiona el registro, consulta, actualización y eliminación de usuarios del sistema.

---

## 🎯 Responsabilidad

*
*
*

---

## 🧱 Entidad Principal

### 📄 Nombre: [Ej: Usuario]

| Campo      | Tipo   | Descripción           |
| ---------- | ------ | --------------------- |
| id         | Long   | Identificador único   |
| nombre     | String | Nombre del usuario    |
| correo     | String | Email del usuario     |
| contraseña | String | Contraseña encriptada |

---

## 🔄 Operaciones CRUD

### 🟢 Crear

* Método: POST
* Endpoint: `/usuarios`
* Descripción: Crear un nuevo usuario

#### 📥 Request Body

```json id="x6kq9v"
{
  "nombre": "Juan",
  "correo": "juan@email.com",
  "contraseña": "123456"
}
```

#### 📤 Response

```json id="8n1z3p"
{
  "id": 1,
  "nombre": "Juan",
  "correo": "juan@email.com"
}
```

---

### 🔵 Obtener todos

* Método: GET
* Endpoint: `/usuarios`
* Descripción: Listar usuarios

---

### 🔵 Obtener por ID

* Método: GET
* Endpoint: `/usuarios/{id}`
* Descripción: Obtener usuario por ID

---

### 🟡 Actualizar

* Método: PUT
* Endpoint: `/usuarios/{id}`
* Descripción: Actualizar datos del usuario

---

### 🔴 Eliminar

* Método: DELETE
* Endpoint: `/usuarios/{id}`
* Descripción: Eliminar usuario

---

## ⚙️ Lógica de Negocio

* Validar que el correo no esté duplicado
* Encriptar contraseña antes de guardar
* No permitir campos vacíos

---

## ⚠️ Validaciones

* @NotBlank → nombre
* @Email → correo
* Longitud mínima contraseña

---

## 🔗 Comunicación con otros microservicios

| Microservicio | Tipo de comunicación | Descripción               |
| ------------- | -------------------- | ------------------------- |
| Auth          | REST                 | Validación de login       |
| Pedidos       | REST                 | Validar usuario existente |

---

## 🧩 Estructura del Proyecto

```id="t1j3kp"
controller/
service/
repository/
model/
dto/
exception/
```

---

## ⚠️ Manejo de Errores

| Código | Descripción           |
| ------ | --------------------- |
| 400    | Datos inválidos       |
| 404    | Usuario no encontrado |
| 500    | Error interno         |

---

## 🧾 Logs

* Creación de usuario
* Errores de validación
* Llamadas a otros servicios

---

## 🧪 Pruebas

### 📌 Ejemplo Postman

* POST /usuarios ✔
* GET /usuarios ✔

---

## 📡 Swagger

URL:

```id="m6z2xg"
http://localhost:8080/swagger-ui/index.html
```

---

## 🚀 Estado

⬜ No iniciado
⬜ En desarrollo
⬜ Completo

---

## 📌 Notas

* Este microservicio es independiente
* Tiene su propia base de datos
* No comparte lógica con otros servicios

---
## 🔍 Consultas Personalizadas (Queries)

Además de las operaciones CRUD básicas, este microservicio implementa consultas personalizadas para cubrir necesidades específicas del negocio.

---

### 📌 Método 1: [Nombre del método]

* Descripción:
* Tipo: Derivado / JPQL / Query nativa

#### 🧠 Lógica

Explica qué hace la consulta.

#### 💻 Repository

```java
// Ejemplo
List<Usuario> findByCorreoContaining(String correo);
```

#### 🌐 Endpoint asociado

* GET /usuarios/buscar?correo=

---

### 📌 Método 2: [Nombre del método]

* Descripción:
* Tipo:

#### 💻 Repository

```java
@Query("SELECT u FROM Usuario u WHERE u.nombre = :nombre")
List<Usuario> buscarPorNombre(@Param("nombre") String nombre);
```

#### 🌐 Endpoint

* GET /usuarios/nombre/{nombre}

---

### 📌 Método 3: [Nombre del método]

* Descripción:
* Tipo: Query nativa

#### 💻 Repository

```java
@Query(value = "SELECT * FROM usuarios WHERE correo LIKE %:correo%", nativeQuery = true)
List<Usuario> buscarPorCorreo(@Param("correo") String correo);
```

---

## ⚙️ Casos de Uso Implementados

* Búsqueda por nombre parcial
* Filtro por categoría
* Ordenamiento por precio
* Validación de existencia de datos

---
