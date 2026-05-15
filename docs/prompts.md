# Prompts del Proyecto LTI

## Prompt Inicial - 15/05/2026

**Rol**: Arquitecto de software

**Tareas a realizar**:
- Vamos a crear un sitio web con front-end y backend que servira para ir trabajando sobre el para ir aprendiendo mejores estrategias de desarrollo con IA.
- Crear la estructura basica del proyecto
- Guardar todos los prompts introducidos para poder realizar seguimiento de los mismo y la evolucion del proyecto
- Guardar en carpeta docs la estructura del proyecto cada vez que haya un cambio que afecte a este en el proyecto

**Restricciones**:
- La tecnologia de front-end sera en React junto con typescript.
- La tecnologia de backend sera Java 17. Utilizaremos maven.
- La base de datos sera Postgres

**Consideraciones**:
- Me preguntaras siempre que haya una decision de arquitectura
- Guardaremos archivos de memoria para mantener el contexto entre sesiones
- el repositorio sera multi proyecto. El backend se situara en una carpeta llamada "backend". En ella, cada funcionalidad de backend del programa tendra una carpeta dedicada donde se implementara el microservicio asociado. Los agruparemos por ambitos (usuarios, gestion de adjuntos, etc...)

---

## Decisiones de Arquitectura - 15/05/2026

### Frontend (React + TypeScript)
1. **Build tool**: Create React App
2. **UI Library**: Tailwind CSS
3. **State Management**: Context API

### Backend (Java 17 + Maven)
- **Framework**: Jakarta EE
- **Arquitectura de microservicios**: Cada microservicio será un módulo Maven separado dentro del backend
- **API**: REST API
- **Gestión**: Cada microservicio podrá ser gestionado individualmente. También dispondremos la opción de poder activarlos todos de una vez

### Base de Datos (PostgreSQL)
- **Despliegue**: Docker

### Gestión del Monorepo
- **Estructura**: Estructura simple con carpetas separadas
