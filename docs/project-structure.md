# Estructura del Proyecto LTI

## Visión General
Monorepo para proyecto de aprendizaje de estrategias de desarrollo con IA.

## Tecnologías

### Frontend
- **Framework**: Next.js 14 con TypeScript
- **Estilos**: Tailwind CSS
- **State Management**: Context API (inicio simple)
- **Puerto**: 3000

### Backend
- **Framework**: NestJS con TypeScript
- **Base de Datos**: PostgreSQL
- **ORM**: TypeORM
- **Puerto**: 3001

### Infraestructura
- **Contenerización**: Docker y Docker Compose
- **Base de Datos**: PostgreSQL 15 en Docker

## Estructura de Directorios

```
LTI-project/
├── frontend/                 # Next.js + TypeScript + Tailwind
│   ├── src/
│   │   ├── app/             # App Router
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx
│   │   │   └── globals.css
│   │   ├── components/     # Componentes React
│   │   └── lib/            # Utilidades
│   ├── package.json
│   ├── tsconfig.json
│   ├── tailwind.config.ts
│   ├── next.config.js
│   ├── postcss.config.js
│   ├── Dockerfile
│   └── .gitignore
│
├── backend/                  # NestJS + TypeScript
│   ├── src/
│   │   ├── main.ts         # Entry point
│   │   ├── app.module.ts   # Módulo principal
│   │   ├── modules/        # Módulos de funcionalidad
│   │   └── common/         # Utilidades compartidas
│   ├── package.json
│   ├── tsconfig.json
│   ├── tsconfig.build.json
│   ├── nest-cli.json
│   ├── .env.example
│   ├── Dockerfile
│   └── .gitignore
│
├── docker/                   # Configuración Docker
│   └── docker-compose.yml   # Orquestación de servicios
│
├── docs/                     # Documentación
│   ├── prompts.md          # Registro de prompts
│   └── project-structure.md # Este archivo
│
├── README.md                # Documentación principal
└── .git/                   # Control de versiones
```

## Configuración de Entorno

### Backend (.env)
```env
PORT=3001
NODE_ENV=development
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=postgres
DB_DATABASE=lti_db
```

## Scripts Disponibles

### Frontend
- `npm run dev` - Servidor de desarrollo
- `npm run build` - Build para producción
- `npm run start` - Servidor de producción
- `npm run lint` - Linting

### Backend
- `npm run start:dev` - Servidor de desarrollo con hot-reload
- `npm run build` - Build para producción
- `npm run start:prod` - Servidor de producción
- `npm run test` - Ejecutar tests
- `npm run lint` - Linting

## Docker

### Servicios
- **postgres**: Base de datos PostgreSQL 15
- **backend**: API NestJS

### Comandos
```bash
cd docker
docker-compose up -d    # Iniciar servicios
docker-compose down     # Detener servicios
docker-compose logs -f  # Ver logs
```

## Flujo de Desarrollo

1. **Frontend**: Desarrollar en `frontend/` con Next.js
2. **Backend**: Desarrollar en `backend/` con NestJS
3. **Base de Datos**: Usar Docker Compose para PostgreSQL
4. **Documentación**: Actualizar `docs/` con cambios de estructura

## Próximos Pasos

- [ ] Instalar dependencias (npm install en frontend y backend)
- [ ] Configurar módulos iniciales en backend
- [ ] Crear componentes base en frontend
- [ ] Establecer conexión entre frontend y backend
- [ ] Implementar autenticación si es necesario
