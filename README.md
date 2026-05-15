# LTI Project

Proyecto de aprendizaje para practicar estrategias de desarrollo con IA.

## Stack Tecnológico

### Frontend
- **Framework**: Next.js 16.2.6 con TypeScript
- **Estilos**: Tailwind CSS
- **State Management**: Context API (inicio simple)
- **Puerto**: 3000

### Backend
- **Framework**: NestJS 10.0.0 con TypeScript
- **Base de Datos**: PostgreSQL
- **ORM**: TypeORM
- **Puerto**: 3001

### Infraestructura
- **Contenerización**: Docker + Docker Compose
- **Backend**: Ejecuta en container Docker en WSL (Windows Subsystem for Linux)

## Requisitos Previos

- Node.js 18+
- npm o yarn
- Docker Desktop con WSL2 habilitado
- Git

## Instalación

### 1. Clonar el repositorio
```bash
git clone https://github.com/Shackpack/LTI-project.git
cd LTI-project
```

### 2. Instalar dependencias del Frontend
```bash
cd frontend
npm install
```

### 3. Instalar dependencias del Backend
```bash
cd ../backend
npm install
```

## Ejecución

### Frontend (Desarrollo)

El frontend se ejecuta localmente en Windows:

```bash
cd frontend
npm run dev
```

Acceder en: http://localhost:3000

### Backend (Docker en WSL)

El backend se ejecuta en un container Docker en WSL:

```bash
# Asegurarse de que Docker Desktop esté corriendo con WSL2
cd docker
docker-compose up -d
```

Esto iniciará:
- PostgreSQL en puerto 5432
- Backend NestJS en puerto 3001

**Comandos útiles:**
```bash
# Ver logs
docker-compose logs -f

# Detener servicios
docker-compose down

# Reiniciar servicios
docker-compose restart
```

## Scripts Disponibles

### Frontend
- `npm run dev` - Servidor de desarrollo con hot-reload
- `npm run build` - Build para producción
- `npm start` - Servidor de producción (requiere build previo)
- `npm run lint` - Linting del código

### Backend
- `npm run start:dev` - Servidor de desarrollo con hot-reload (local)
- `npm run build` - Build para producción
- `npm run start:prod` - Servidor de producción
- `npm run test` - Ejecutar tests
- `npm run lint` - Linting del código

## Configuración

### Backend (.env)
Crear archivo `.env` en `backend/` basado en `.env.example`:

```env
PORT=3001
NODE_ENV=development
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=postgres
DB_DATABASE=lti_db
```

**Nota**: Cuando se ejecuta con Docker Compose, las variables de entorno se configuran automáticamente en `docker/docker-compose.yml`.

## Estructura del Proyecto

```
LTI-project/
├── frontend/          # Next.js + TypeScript + Tailwind
├── backend/           # NestJS + TypeScript
├── docker/            # Configuración Docker Compose
├── docs/              # Documentación y registro de prompts
└── README.md
```

## Flujo de Desarrollo Típico

1. **Iniciar PostgreSQL y Backend (Docker en WSL)**:
   ```bash
   cd docker
   docker-compose up -d
   ```

2. **Iniciar Frontend (Local)**:
   ```bash
   cd frontend
   npm run dev
   ```

3. **Desarrollar**: 
   - Frontend en `frontend/`
   - Backend en `backend/`

4. **Detener servicios al terminar**:
   ```bash
   cd docker
   docker-compose down
   ```

## Documentación

- [Estructura del Proyecto](docs/project-structure.md)
- [Registro de Prompts](docs/prompts.md)

## Notas Importantes

- El backend está configurado para ejecutarse en Docker con WSL2 para mejor compatibilidad con PostgreSQL
- El frontend se ejecuta localmente para desarrollo más rápido
- Evitar usar `npm audit fix --force` ya que puede causar conflictos de dependencias
- Para producción, ambos servicios pueden ejecutarse en Docker