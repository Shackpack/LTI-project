# Estructura del Proyecto LTI

Última actualización: 15/05/2026

## Estructura General

```
LTI-project/
├── frontend/              # Frontend React + TypeScript
│   ├── src/
│   │   ├── components/    # Componentes React
│   │   ├── contexts/      # Context API para state management
│   │   ├── services/      # Servicios API
│   │   ├── types/         # Definiciones TypeScript
│   │   ├── App.tsx        # Componente principal
│   │   ├── index.tsx      # Punto de entrada
│   │   └── index.css      # Estilos globales (Tailwind)
│   ├── public/            # Archivos estáticos
│   ├── package.json       # Dependencias frontend
│   ├── tsconfig.json      # Configuración TypeScript
│   ├── tailwind.config.js # Configuración Tailwind CSS
│   └── postcss.config.js  # Configuración PostCSS
├── backend/               # Backend Java 17 + Maven
│   ├── pom.xml           # POM principal (parent)
│   ├── shared/           # Módulo compartido
│   │   ├── pom.xml       # POM del módulo shared
│   │   └── src/main/java/com/lti/shared/
│   ├── usuarios/        # Microservicio de usuarios
│   │   ├── pom.xml       # POM del módulo usuarios
│   │   └── src/main/
│   │       ├── java/com/lti/usuarios/
│   │       ├── resources/META-INF/persistence.xml
│   │       └── webapp/WEB-INF/web.xml
│   └── adjuntos/        # Microservicio de adjuntos
│       ├── pom.xml       # POM del módulo adjuntos
│       └── src/main/
│           ├── java/com/lti/adjuntos/
│           ├── resources/META-INF/persistence.xml
│           └── webapp/WEB-INF/web.xml
├── docs/                 # Documentación
│   ├── prompts.md        # Registro de prompts
│   └── project-structure.md # Este archivo
├── docker-compose.yml    # Configuración Docker (PostgreSQL)
├── .gitignore           # Archivos ignorados por Git
└── README.md            # Documentación principal
```

## Frontend (React + TypeScript)

### Stack Tecnológico
- **Framework**: React 18
- **Lenguaje**: TypeScript 4.9
- **Build Tool**: Create React App
- **Estilos**: Tailwind CSS 3.3
- **State Management**: Context API

### Estructura de Carpetas
- `components/`: Componentes React reutilizables
- `contexts/`: Contextos para gestión de estado global
- `services/`: Servicios para comunicación con API backend
- `types/`: Definiciones de tipos TypeScript

### Configuración
- Puerto: 3000 (por defecto de Create React App)
- Comandos:
  - `npm start`: Iniciar servidor de desarrollo
  - `npm build`: Crear build de producción
  - `npm test`: Ejecutar tests

## Backend (Java 17 + Maven)

### Stack Tecnológico
- **Lenguaje**: Java 17
- **Build Tool**: Maven
- **Framework**: Jakarta EE 10
- **JAX-RS**: Jersey 3.1.3
- **JPA**: Hibernate 6.3.1
- **Base de Datos**: PostgreSQL 15

### Arquitectura de Microservicios
El backend está organizado como un proyecto Maven multi-módulo donde cada microservicio es un módulo independiente:

#### Módulos
1. **shared**: Módulo compartido con entidades y utilidades comunes
   - Packaging: JAR
   - Contiene entidades JPA compartidas
   - Utilidades comunes

2. **usuarios**: Microservicio de gestión de usuarios
   - Packaging: WAR
   - Puerto: 8081 (sugerido)
   - API REST: `/api/*`

3. **adjuntos**: Microservicio de gestión de adjuntos
   - Packaging: WAR
   - Puerto: 8082 (sugerido)
   - API REST: `/api/*`

### Gestión de Microservicios
- Cada microservicio puede ser desplegado individualmente
- Todos los microservicios pueden activarse desde el POM principal
- Cada servicio tiene su propia configuración JPA

### Configuración Maven
- Comandos:
  - `mvn clean install`: Compilar todos los módulos
  - `mvn clean package`: Crear WAR files
  - `cd backend/usuarios && mvn jetty:run`: Ejecutar microservicio usuarios
  - `cd backend/adjuntos && mvn jetty:run`: Ejecutar microservicio adjuntos

## Base de Datos (PostgreSQL)

### Configuración Docker
- **Imagen**: postgres:15
- **Puerto**: 5432
- **Base de datos**: lti_db
- **Usuario**: lti_user
- **Password**: lti_password

### Comandos Docker
- `docker-compose up -d`: Iniciar contenedor PostgreSQL
- `docker-compose down`: Detener contenedor
- `docker-compose logs postgres`: Ver logs de PostgreSQL

## Ambitos de Microservicios

Los microservicios se agrupan por ámbitos funcionales:

### Usuarios
- Gestión de usuarios
- Autenticación y autorización
- Perfiles de usuario

### Adjuntos
- Gestión de archivos adjuntos
- Upload y download de archivos
- Almacenamiento de documentos

## Próximos Ambitos (Pendientes)
- Notificaciones
- Reporting
- Auditoría
