[14/05/2026-19:20]
Vas a tomar el rol de arquitecto de software.

Tareas a realizar:
- Vamos a crear un sitio web con front-end y backend que servira para ir trabajando sobre el para ir aprendiendo mejores estrategias de desarrollo con IA.
- Crear la estructura basica del proyecto
- Guardar todos los prompts introducidos para poder realizar seguimiento de los mismo y la evolucion del proyecto
- Guardar en carpeta docs la estructura del proyecto cada vez que haya un cambio que afecte a este en el proyecto

Restricciones:
- La tecnologia de front-end sera en React junto con typescript.
- La tecnologia de backend sera Java
- La base de datos sera Postgres

Consideraciones:
- Me preguntaras siempre que haya una decision de arquitectura
- Guardaremos archivos de memoria para mantener el contexto entre sesiones

[14/05/2026-19:35]
Decisiones de arquitectura actualizadas:
- Backend: Node.js + TypeScript con NestJS (cambio de Java)
- Build tool: NestJS CLI
- Versión: Node.js 18
- Frontend: Next.js + TypeScript + Tailwind CSS
- State management: Context API (inicio simple)
- Estructura: Monorepo
- Docker: Postgres y backend en contenedores

[14/05/2026-19:43]
Confirmación de arquitectura final:
- Procederemos a configurar el proyecto como monorepo con Node.js + TypeScript con NestJS

