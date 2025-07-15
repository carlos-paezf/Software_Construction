# Construcción de Software

[![wakatime](https://wakatime.com/badge/user/8ef73281-6d0a-4758-af11-fd880ca3009c/project/536829f5-61ef-43ed-8b16-078545acb1f1.svg?style=for-the-badge)](https://wakatime.com/badge/user/8ef73281-6d0a-4758-af11-fd880ca3009c/project/536829f5-61ef-43ed-8b16-078545acb1f1)

> 🌟 *El conocimiento no es útil si no se comparte.*

Este proyecto es una plataforma de documentación educativa desarrollada con [Docusaurus](https://docusaurus.io/).

## Objetivo

Brindar tanto a estudiantes cómo docentes, un recurso descentralizado, estructurado y multilingüe, que facilite el acceso a los siguientes temas:

- Módulo 1: Fundamentos y Diseño Centrado en el Usuario
  - ¿Qué es Construcción de Software?
  - Introducción al enfoque ágil y al modelo SCRUM
  - Roles de un equipo SCRUM
  - Artefactos: backlog, sprint, entregables
  - Ciclo de vida de un proyecto ágil
  - Principios de UX/UI
  - Heurísticas de usabilidad de Nielsen
  - Diseño centrado en el usuario (DCU)
  - ¿Qué es un wireframe y un mockup?
  - Uso básico de Figma o Penpot para prototipos
- Módulo 2: Arquitectura y diseño de software moderno
  - ¿Qué es arquitectura de software?
  - Estilos arquitectónicos comunes (Monolítica, SOA, Microservicios)
  - Principios de Clean Architecture
  - Capas y dependencias en Clean Architecture
  - Arquitectura modular monolítica
  - Diseño de casos de uso y entidades
- Módulo 3: Angular desde 0
  - ¿Qué es Angular y por qué usarlo?
  - Instalación de entorno Angular (Node, CLI, Vite)
  - Estructura de un proyecto Angular
  - TypeScript para Angular: tipos, interfaces, clases
  - Comando útiles de Angular CLI
  - ¿Qué es un componente? (decoradores, selector, HTML, CSS, TS)
  - Comunicación entre componentes: `@Input` y `@Output`
  - Servicios en Angular e Inyección de Dependencias
  - Routing en Angular (básico y avanzado)
  - Estilos con TailwindCSS o Angular Material
  - Formularios reactivos vs. template-driven
  - Validación de formularios (sincrónica y asincrónica)
  - Manejo de estados en formularios
- Módulo 4: NestJS y Backend moderno
  - ¿Qué es NestJS y cómo se estructura?
  - Instalación de NestJS y comandos CLI
  - Módulos, controladores y servicios
  - Uso de DTOs y pipes de validación
  - Conexión con base de datos: TypeORM o Prisma
  - CRUD básico con repositorios y entidades
  - Autenticación con Passport y JWT
  - Middleware y guards en NestJS
- Módulo 5: Integración Fullstack
  - HTTP Client en Angular: consumo de APIs
  - Servicios y promesas con `HttpClient`
  - Comunicación con el backend NestJS
  - Manejo de errores HTTP
  - Mecanismos de autenticación en frontend
  - LocalStorage, sesiones y guardias de rutas
- Módulo 6: Testing y Calidad
  - ¿Qué es testing y por qué es clave?
  - Pruebas unitarias con Jasmine/Karma (Angular)
  - Pruebas en servicios y componentes
  - Pruebas unitarias e integración en NestJS (Jest)
  - Buenas prácticas de testing (AAA, mocking)
  - Introducción a SonarQube y métricas de código
  - Configuración de ESLint y Prettier
  - Integración continua con GitHub Actions
- Módulo 7: Metodologías y gestión ágil
  - Fundamentos de metodologías ágiles
  - Artefactos: user stories, definition of done
  - Herramientas para gestión: Trello, Jira
  - Cómo planificar un sprint realista
  - Retroalimentación continua y mejora
- Módulo 8: Herramientas, despliegue y seguridad
  - Comparativa: Firebase vs Supabase vs Auth0
  - Selección de herramientas según requisitos del cliente
  - Variables de entorno y configuración segura
  - Despliegue frontend con Vercel paso a paso
  - Despliegue backend en Render o Fly.io
  - Protección de rutas y manejo de errores críticos
- Módulo 9: Validación, accesibilidad y presentación
  - Principios de accesibilidad en diseño web
  - Ajustes visuales y de experiencia
  - Preparación de pitch final
  - Memoria técnica del proyecto
  - Reflexión final sobre calidad del producto
- Módulo 10: Extras
  - Cómo versionar tu proyecto en GitHub
  - Plantillas de documentación para proyectos
  - Ejemplos de commits y mensajes semánticos
  - Glosario de términos técnicos

## Internacionalización

El portal estará disponible en 2 idiomas:

- 🇪🇸 Español (predeterminado)
- 🇺🇸 Inglés

Puedes cambiar el idioma desde el menú superior del sitio.

## Instalación local

Para trabajar en el sitio de documentación de forma local:

```bash
# Clona el repositorio
git clone https://github.com/carlos-paezf/Software_Construction.git
cd Software_Construction

# Instala las dependencias
npm install

# Inicia el servidor de desarrollo
npm run start
```

Abre <http://localhost:3000> en tu navegador.

## Estructura del proyecto

- `/docs` Contenidos originales en español
- `/i18n/en` Traducciones al inglés
- `src` Componentes y páginas personalizadas
- `/static` Archivos estáticos (imágenes, descargas, etc.)

## Contribuciones

Este proyecto está abierto a docentes o estudiantes que deseen colaborar con:

- Traducciones
- Correcciones ortográficas o técnicas
- Mejora en la organización o visualización de los contenidos

Por favor, antes de hacer un Pull Request, revisa el archivo [`CONTRIBUTING.md`](./CONTRIBUTING.md)

## Comandos útiles

|Acción|Comando|
|--|--|
|Ejecutar en modo desarrollo|`npm run start`|
|Compilar para producción|`npm run build`|
|Generar estructura para traducciones|`npm run write-translations`|

## Autor

Proyecto desarrollado por Carlos David Páez Ferreira, Ingeniero de Sistemas y Docente Universitario, como recurso de apoyo para estudiantes y colegas.

## Licencia

Este proyecto está licenciado bajo la MIT License.
