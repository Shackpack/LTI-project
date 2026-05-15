# LTI Project

Proyecto para aprender y practicar estrategias de desarrollo con IA.

## Stack Tecnológico

### Frontend
- **Framework**: React 18 con TypeScript
- **Build Tool**: Create React App
- **Estilos**: Tailwind CSS 3.3
- **State Management**: Context API
- **Puerto**: 3000

### Backend
- **Lenguaje**: Java 17
- **Build Tool**: Maven (multi-módulo)
- **Framework**: Jakarta EE 10
- **JAX-RS**: Jersey 3.1.3
- **JPA**: Hibernate 6.3.1
- **Arquitectura**: Microservicios como módulos Maven separados

### Base de Datos
- **PostgreSQL 15** en Docker
- **Puerto**: 5432

## Estructura del Proyecto

```
LTI-project/
├── frontend/          # React + TypeScript + Tailwind CSS
├── backend/           # Java 17 + Maven multi-módulo
│   ├── shared/        # Módulo compartido (JAR)
│   ├── usuarios/      # Microservicio de usuarios (WAR)
│   └── adjuntos/      # Microservicio de adjuntos (WAR)
├── docs/              # Documentación y prompts
├── docker-compose.yml # Configuración Docker (PostgreSQL)
└── README.md
```

## Configuración Inicial

### 1. Iniciar PostgreSQL
```bash
docker-compose up -d
```

### 2. Instalar dependencias del Frontend
```bash
cd frontend
npm install
```

### 3. Compilar el Backend
```bash
cd backend
mvn clean install
```

## Ejecución

### Frontend
```bash
cd frontend
npm start
```
El frontend estará disponible en http://localhost:3000

### Backend (Microservicios)

#### Ejecutar todos los microservicios
```bash
cd backend
mvn clean install
```

#### Ejecutar microservicio individual
```bash
cd backend/usuarios
mvn jetty:run
```

```bash
cd backend/adjuntos
mvn jetty:run
```

## Documentación

- [Estructura del Proyecto](docs/project-structure.md)
- [Prompts del Proyecto](docs/prompts.md)

## Arquitectura de Microservicios

Cada microservicio es un módulo Maven independiente que puede ser:
- Desplegado individualmente
- Compilado junto con otros desde el POM principal
- Accedido vía REST API en diferentes puertos

### Módulos Actuales

1. **shared**: Módulo compartido con entidades y utilidades comunes
2. **usuarios**: Gestión de usuarios, autenticación y autorización
3. **adjuntos**: Gestión de archivos adjuntos, upload y download