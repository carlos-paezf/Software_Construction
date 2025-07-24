---
sidebar_position: 2
---

# Instalación de entorno Angular (Node, CLI, Vite)

## Requisitos previos

Antes de crear una aplicación Angular moderna, es necesario tener instalado:

- **Node.js** (v18.x o superior, recomendado v20.x LTS)
- **npm**, **pnpm**, **yarn** o **bun** como gestores de paquetes
- Angular CLI (herramienta oficial para crear y gestionar proyectos Angular)

Angular 17 en adelante soporta **Vite** como motor de desarrollo alternativo al tradicional Webpack, brindando un entorno más rápido y eficiente para entornos modernos.

## Instalación de Node.js

Node.js es un entorno de ejecución para JavaScript en el servidor. Angular lo requiere para:

- Ejecutar herramientas como Angular CLI
- Instalar dependencias (`npm install`)
- Ejecutar scripts de desarrollo y testing

Existen dos formas para proceder con su instalación:

1. **Instalación directa**

   - Visita [NODE JS](https://nodejs.org)
   - Descarga la versión LTS (Long-Term Support) (recomendada)
   - Confirma la instalación:

     ```bash
     node -v
     npm -v
     ```

     Resultado esperado:

     ```bash
     node v20.x.x
     npm 9.x.x o superior
     ```

2. Usar Node Version Manager (NVM)

   ```bash
   # Linux/macOS
   curl -o- <https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh> | bash
   nvm install 20
   nvm use 20

   # Windows: usar nvm-windows desde <https://github.com/coreybutler/nvm-windows>
   ```

## Instalación del Angular CLI

El **CLI (Command Line Interface)** de Angular es una herramienta oficial para:

- Crear proyectos
- Generar componentes, servicios y módulos
- Ejecutar aplicaciones y pruebas
- Construir para producción

Su instalación global es a través del siguiente comando:

```bash
npm install -g @angular/cli
```

Confirma la instalación:

```bash
ng version
```

Deberías ver una salida como (tomaré como ejemplo mi output):

```bash
Angular CLI: 20.1.2
Node: 22.15.0
Package Manager: npm 10.9.2
OS: win32 x64
```

## Crear un nuevo proyecto Angular (CLI)

El comando básico es:

```bash
ng new nombre-de-tu-app
```

Te pedirá seleccionar opciones como:

- ¿Standalone components? → ✅ Sí (Angular 17+)
- ¿Routing? → ✅ Sí si vas a usar navegación
- ¿Estilos? → CSS / SCSS / Tailwind (según preferencia)

Podemos omitir que nos pida la opciones anteriores, pasando cada una como flag en el comando:

```bash
ng new frontend --standalone --routing --style=scss
```

Luego puedes entrar a tu proyecto y levantar el servidor de desarrollo:

```bash
cd frontend
ng serve
```

## Soporte para Vite (Angular 17+)

Desde Angular 17+, se puede usar **Vite** como motor de desarrollo. Angular 20 continúa mejorando este soporte. Vite reemplaza a Webpack, mejorando tiempos de arranque y recarga en caliente (HMR).

Para la activación experimental de Vite debes ejecutar:

```bash
ng add @angular/vite
```

Este comando:

- Instala el plugin oficial
- Configura angular.json para usar Vite
- Añade soporte para HMR

Otra opción es crear un proyecto con Vite y seleccionar la plantilla de Angular:

```bash
pnpm create vite

◇  Project name:
│   nombre-de-tu-app
│
◇  Select a framework:
│   Angular
│
◇  Select a variant:
│   Angular ↗
```

## Opciones del proyecto Angular

Cuando estás creando tu proyecto aparecerán algunas opciones que requieren de tu respuesta:

### Telemetría: Uso de datos anónimos

```bash
Would you like to share pseudonymous usage data about this project with the Angular Team
at Google under Google's Privacy Policy at https://policies.google.com/privacy. 
```

Este mensaje solicita tu permiso para que Angular recolecte datos **anónimos y no identificables** sobre cómo usas el framework. Esto ayuda a Google a mejorar Angular en función de su adopción real.

Opciones:

- **Yes**: Habilita la recolección de datos anónimos (por ejemplo, qué comandos usas, versión del CLI, etc.).
- **No**: No envía nada a Google.

Recomendación:

- **Desarrollo individual:** Puedes decir **No** si prefieres privacidad.
- **Proyectos educativos o empresariales:** Es seguro decir **Yes**, ya que la información es anónima y ayuda a mejorar Angular.

Si cambias de opinión:

```bash
ng analytics disable --global  # Desactiva
ng analytics enable --global   # Activa
```

### Zoneless

```bash
✔ Do you want to create a 'zoneless' application without zone.js (Developer Preview)?
```

Angular usa `zone.js` por defecto para detectar automáticamente cambios y actualizar la UI. En Angular 17+ puedes optar por no usarlo, y en su lugar usar signals y reactividad explícita.

- **Zoneless**: Mejor rendimiento, más predecible, menos magia oculta.
- **Con `zone.js`**: Más compatible con librerías antiguas, manejo automático de cambios.

Recomendación:

- Sí, usar Zoneless (`Yes`) si:
  - Vas a trabajar con Angular moderno (17+)
  - Usarás `signals` e `@input signals`
  - No dependes de librerías antiguas

**Zoneless** es una **tendencia actual**, alineada con el futuro de Angular.

### SSR y SSG

```bash
✔ Do you want to enable Server-Side Rendering (SSR) and Static Site Generation (SSG/Prerendering)?
```

Angular Universal permite:

- **SSR (Server-Side Rendering):** renderizar vistas en el servidor para mejorar el SEO y el rendimiento inicial.
- **SSG (Static Site Generation):** generar páginas estáticas durante el build.

Recomendación:

- **Yes** si:
  - Te interesa **SEO** (sitios públicos, blogs, dashboards).
  - Buscas **mejorar el rendimiento inicial** y **accesibilidad**.
- **No** si:
  - Tu app es puramente interna o dashboard privado.
  - Puedes añadir SSR después con:

```bash
ng add @angular/ssr
```

## Consideraciones adicionales

- Puedes usar **pnpm** como alternativa ligera a npm: `npm install -g pnpm`
- Si usas **nvm**, puedes cambiar de versión de Node fácilmente según el proyecto.
- Angular CLI también soporta `--directory`, `--inline-style`, `--inline-template` y otras banderas útiles.

## Referencias

- Angular Team. (2024). [Angular Dev Documentation.](https://angular.dev)
- Node.js Foundation. (2024). [Node.js Downloads.](https://nodejs.org)
- Angular Team. (2024). [Using Vite with Angular.](https://github.com/angular/vite-plugin-angular)
- [Angular CLI Docs.](https://angular.io/cli).
- [GitHub – nvm-sh/nvm.](https://github.com/nvm-sh/nvm)
