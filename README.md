# Marcela González Arias

Backend developer y software engineer en Chile. En GitHub publico mi trabajo como **@Margoar**.

Me interesa la parte del backend que no se ve en una demo: qué pasa cuando dos requests compiten por el mismo recurso, dónde vive cada responsabilidad y cómo comprobar que el sistema hace lo que dice que hace.

## En qué estoy trabajando

Mi foco reciente es **.NET 8 con Redis**. En [dotnet-redis-inventory-demo](https://github.com/margoar/dotnet-redis-inventory-demo) construí una API de inventario para practicar tres mecanismos concretos:

- **Cache-Aside con TTL** para leer y repoblar el stock.
- **Reserva atómica con un script Lua**, para que nada se intercale entre validar y descontar.
- **Distributed lock** con `SET NX`, token de ownership y liberación segura.

Los tests de integración corren contra un Redis real. Uno de ellos lanza 20 reservas simultáneas sobre un stock de 10 y verifica que se acepten exactamente 10.

## Proyectos

| Proyecto | Problema | Stack |
| --- | --- | --- |
| [dotnet-redis-inventory-demo](https://github.com/margoar/dotnet-redis-inventory-demo) | Stock consistente bajo concurrencia | C#, ASP.NET Core, Redis, xUnit |
| [ejercicio-arbol-filogenetico](https://github.com/margoar/ejercicio-arbol-filogenetico) | Construir un árbol a partir de IDs jerárquicos (`1.2.3`) y recorrer subárboles | C#, .NET 8 |
| [pacientes](https://github.com/margoar/pacientes) | Aplicación web de gestión de pacientes con login y exportación a Excel | Java, Servlets, JSP, JDBC, MySQL |
| [PC-MUNDO](https://github.com/margoar/PC-MUNDO) | Modelado orientado a objetos de órdenes de computadores y periféricos | Python |
| [PAGINARESTAURANT](https://github.com/margoar/PAGINARESTAURANT) | Sitio responsive sin frameworks ni dependencias | HTML, CSS, JavaScript |

## Stack

**Principal:** C# · .NET 8 · ASP.NET Core · Redis (StackExchange.Redis, Lua)  
**Testing:** xUnit · pruebas de integración  
**También he trabajado con:** Java (Servlets, JSP, JDBC, Maven) · MySQL · Python · HTML, CSS y JavaScript  
**Herramientas:** Git · Docker para entornos locales

## Explorando ahora

- Concurrencia y consistencia con Redis: operaciones atómicas, locks distribuidos y expiración.
- Arquitectura en capas en .NET, con Domain, Application, Infrastructure y API separados y dependencias hacia adentro.
- Desarrollo asistido por IA generativa, que practiqué construyendo el sitio de PAGINARESTAURANT.

## Cómo trabajo

- **Separo responsabilidades antes de escribir lógica.** Dominio, aplicación e infraestructura van en capas distintas, incluso en ejercicios pequeños.
- **Pruebo lo que puede fallar.** Concurrencia, TTL y locks se verifican contra un Redis real, no solo con dobles de prueba.
- **Documento también lo que falta.** Mis README indican qué pieza todavía no se usa o qué va a fallar en otro sistema operativo.
