Sistema de Gestión de Tienda Friki & Gamer
Asignatura: Desarrollo FullStack 1 (DSY1103) | Proyecto Semestral
📝 Descripción
GeekStore es una plataforma basada en microservicios diseñada para la venta de productos de cultura pop, videojuegos y artículos coleccionables. El sistema permite la gestión de usuarios, catálogo dinámico, control de inventario en tiempo real y procesamiento de pedidos, utilizando una arquitectura distribuida y escalable.

🏛️ Arquitectura del Sistema
El proyecto sigue el patrón de diseño CSR (Controller-Service-Repository) en cada microservicio, asegurando una separación clara de responsabilidades:

Controller: Gestión de endpoints REST y validación de entrada con @Valid.

Service: Lógica de negocio (reglas de la tienda gamer).

Repository: Persistencia de datos mediante Spring Data JPA.

📦 Listado de Microservicios (Mínimo 10)
Para cumplir con las directrices académicas, el ecosistema se compone de:

ms-gateway (Infraestructura): Punto de entrada único. Gestiona el enrutamiento hacia todos los servicios.

ms-usuarios (Gestión de Usuarios): Registro, actualización de perfiles y roles (Admin/Cliente).

ms-catalogo (Servicio de Catálogo): Consulta de productos, filtros por categoría gamer y búsqueda por nombre.

ms-inventario (Gestión de Stock): Control de existencias, actualización de ID de productos y alertas de stock bajo.

ms-pedidos (Servicio de Órdenes): Generación de boletas y gestión del estado de la compra.

ms-carrito (Shopping Cart): Persistencia temporal de artículos seleccionados por el usuario.

ms-pagos (Payment Service): Simulación de transacciones seguras para la compra de artículos.

ms-valoraciones (Reviews): Sistema de estrellas y comentarios para productos (0-5 estrellas).

ms-notificaciones (Notifications): Envío simulado de correos de confirmación de compra y despacho.

ms-descuentos (Promo Service): Aplicación de cupones (ej: "FRIKI20") y descuentos por nivel de usuario.

🚀 Requisitos Técnicos Implementados
Comunicación Inter-Servicios: Uso de Feign Clients o WebClient para que ms-pedidos descuente stock en ms-inventario.

Validación de Datos: Implementación de @NotBlank, @Min, y @Email para asegurar la integridad de los datos.

Calidad de Software: Cobertura de pruebas unitarias mínima del 80% mediante JUnit 5 y Mockito.

Documentación: API documentada íntegramente con Swagger / OpenAPI 3.

Manejo de Excepciones: Respuestas HTTP estandarizadas mediante @ControllerAdvice.

🛠️ Instrucciones de Ejecución
Requisitos Previos
Java 21+
Spring (Spring boot-,etc)
Maven 

Base de Datos (MySQL/PostgreSQL para persistencia real)

Pasos
Configurar Base de Datos: Ajustar los archivos application.yml de cada microservicio.

Levantar Gateway: Ejecutar primero el ms-gateway en el puerto 8080 (Puertos pueden ser personalizados).

Ejecutar Microservicios: Iniciar el resto de los servicios de forma independiente (10 ms minimo).

Pruebas: Acceder a través de Postman o Swagger mediante la ruta del Gateway.

👥 Equipo de Desarrollo
Estudiante 1: [Nombre] - (Ej: ms01 , ms02, ms03)

Estudiante 2: [Nombre] - (Ej: ms04,ms05 ,ms06)

Estudiante 3: [Nombre] - (Ej: ms07 ,ms08 ,msd09)

Nota de Evaluación: Este proyecto cumple con los indicadores de logro (IE) de las evaluaciones parciales 2 y 3.
