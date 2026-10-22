# 🏥 Aplicativo para el Registro de Historias Clínicas (Posta Médica Biovital)

Este es un proyecto académico de ingeniería desarrollado para optimizar y digitalizar la gestión integral de una posta médica de atención primaria. El sistema reemplaza los registros manuales en papel por un entorno de escritorio rápido, seguro y estructurado, implementando estructuras de datos dinámicas avanzadas hechas desde cero para demostrar un dominio sólido de la lógica de programación.

---

## 🚀 Características Clave del Sistema (Requerimientos)

### 🔹 Funcionalidades de Negocio (Módulos)
* **Autenticación Segura (Login):** Control de acceso protegido para resguardar la información del centro de salud.
* **Gestión de Pacientes y Personal Médico:** Mantenimiento completo (CRUD) de datos de pacientes, doctores y especialidades clínicas.
* **Registro de Historias Clínicas:** Clasificación avanzada de las consultas médicas organizadas por especialidad.
* **Reportes y Consultas:** Filtros en tiempo real para visualizar las atenciones diarias por médico y rangos de fechas específicos.
* **Exportación Documental:** Generación de reportes locales para descargar la historia clínica completa del paciente en formato PDF.

### 🔹 Reglas Técnicas y Arquitectura (No Funcionales)
* **Control de Acceso Basado en Roles (RBAC):** El sistema restringe vistas; por ejemplo, el personal de admisión solo gestiona pacientes y tiene bloqueado el acceso al historial clínico médico.
* **Persistencia Segura ante Fallos:** Todo el almacenamiento de datos se resuelve localmente mediante la serialización de objetos en archivos binarios (`.bin`). Utiliza un mecanismo de respaldo donde escribe primero en un archivo temporal para verificar la integridad de la información antes de sobreescribir el archivo principal.
* **Seguridad de la Información:** Cifrado de datos sensibles antes de ser almacenados en el disco local.
* **Control de Duplicidad de Interfaces:** El sistema valida activamente que no se abran múltiples instancias de la misma ventana interna (`JInternalFrame`), enfocando y trayendo al frente la interfaz que ya se encuentra activa para optimizar la memoria.

---

## 🧠 Arquitectura de Estructuras de Datos Utilizadas

Para garantizar la máxima eficiencia en memoria y tiempo de ejecución sin depender de bases de datos externas, el proyecto implementa estructuras dinámicas a medida:

1. **Árboles Binarios de Búsqueda (`ArbolHistoria`):** Implementados de forma jerárquica no lineal para la gestión del historial clínico. Utilizan algoritmos basados en el DNI del paciente para asegurar búsquedas, inserciones y ordenamientos de registros en tiempo logarítmico.
2. **Colas de Prioridad (`ColaEspecialidades`):** Utilizan el principio FIFO combinando prioridades de atención clínica para ordenar el flujo de pacientes en las salas de espera.
3. **Listas Dobles Enlazadas (`ListaPacientes`):** Estructura lineal dinámica basada en nodos con punteros bidireccionales (`ini` y `fin`) que permite una navegación y renderizado veloz de los datos en tablas visuales de pacientes.
4. **ArrayLists Estructurados (`ListaDoctores`):** Empleados para el mantenimiento dinámico de colecciones ordenadas que requieren acceso indexado rápido durante los turnos del personal médico.

---

## 💻 Requisitos y Ejecución

* **Lenguaje:** Java (JDK compatible)
* **Tecnología Visual:** Java Swing (JFrame / JInternalFrame / AWT) con diseño optimizado para resoluciones base.

Para iniciar la aplicación localmente, clona este repositorio y ejecuta la clase principal encargada de levantar el flujo del aplicativo:
```bash
src/Principal/Main.java
```
