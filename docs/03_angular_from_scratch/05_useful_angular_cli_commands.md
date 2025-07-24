---
sidebar_position: 5
---

# Comando útiles de Angular CLI

La **Angular CLI (Command Line Interface)** es una herramienta oficial que permite **crear, desarrollar, construir y mantener** proyectos Angular de forma eficiente y estandarizada.

Proporciona comandos para:

- Generar componentes, servicios, rutas, módulos
- Ejecutar la aplicación localmente
- Realizar pruebas unitarias o end-to-end
- Compilar el proyecto para producción
- Añadir soporte a SSR, PWA, Tailwind, entre otros

:::warning

Angular CLI **requiere tener instalado Node.js** y se accede a través del comando `ng`.

:::

## Comando más comunes

### `ng new`

```bash
ng new nombre-proyecto
```

Crea un nuevo proyecto Angular. Adicional, tiene algunas banderas útiles

```bash
ng new frontend --standalone --routing --style=scss
```

|Opción|Descripción|
|--|--|
|`--standalone`|Usa componentes sin `NgModule`|
|`--routing`|Incluye configuración de rutas|
|`--style`|Formato de estilos: css, scss, sass, less|

### `ng serve`

```bash
ng serve
```

Levanta un servidor local (`http://localhost:4200`) para desarrollo con recarga en caliente (Hot Module Replacement). Tiene algunas opciones adicionales:

|Opción|Descripción|
|--|--|
|`--port 4500`|Cambia el puerto|
|`--open`|Abre el navegador automáticamente|
|`--configuration=production`|Sirve en modo producción|

### `ng generate` o `ng g`

Permite generar código base para estructuras Angular.

```bash
ng generate component students/student-list
ng generate service services/student
ng generate directive shared/highlight
ng generate pipe shared/date-format
```

Angular nos brinda algunos atajos para simplificar los comandos:

|Atajo|Genera...|
|--|--|
|`c`|componente|
|`s`|servicio|
|`d`|directiva|
|`p`|pipe|
|`m`|módulo|
|`i`|interceptor|
|`g`|guardia|

### `ng build`

```bash
ng build
```

Compila la aplicación para producción (por defecto genera en `dist/`). Algunas banderas útiles son:

|Opción|Descripción|
|--|--|
|`--configuration=production`|Modo optimizado para producción|
|`--watch`|Recompila automáticamente al guardar|
|`--base-href /ruta/`|Cambia la ruta base del build|

### `ng lint`

```bash
ng lint
```

Analiza el código fuente y verifica que cumple con las reglas de estilo y buenas prácticas definidas en `eslint`. Puedes personalizar `eslintrc.json` para reglas específicas.

### `ng add`

```bash
ng add @angular/material
ng add @angular/pwa
ng add @angular/ssr
```

Agrega librerías oficiales o compatibles, configurándolas automáticamente. Muy útil para añadir soporte a Material Design, SSR, PWA o Tailwind.

### `ng deploy`

```bash
ng deploy
```

Despliega la app en servicios como Firebase, GitHub Pages o Netlify (requiere configuración previa).

### `ng e2e`

```bash
ng e2e
```

Ejecuta pruebas end-to-end (automatizadas en navegador) usando herramientas como Cypress o Protractor. Es necesario una configuración adicional ya que no se instala por defecto.

### `ng analytics`

```bash
ng analytics enable
ng analytics disable
```

Activa o desactiva la recopilación de datos de uso anónimos para el equipo Angular.

## Comandos avanzados, pero menos conocidos

|Comando|Uso|
|--|--|
|`ng update`|Actualiza Angular a una nueva versión|
|`ng config`|Modifica configuración de `angular.json` desde CLI|
|`ng doc`|Abre la documentación oficial de Angular|
|`ng extract-i18n`|Extrae archivos de internacionalización (i18n)|
|`ng completion`|Habilita autocompletado en terminal (bash/zsh)|

## Buenas prácticas con Angular CLI

- Usa `ng generate` para mantener consistencia en nombres y carpetas
- Personaliza los comandos con `--dry-run` para ver los cambios antes de aplicar
- Integra el CLI con `npm scripts` en el `package.json` para facilitar comandos recurrentes
- No edites manualmente `angular.json` salvo que sea necesario
- Aprovecha la posibilidad de usar **Vite** (en Angular 20) para builds más rápidos

## Referencias

- Angular Team. (2024). [Angular CLI Documentation.](https://angular.dev/cli)
- Angular Team. (2024). [ng generate options.](https://angular.dev/cli/generate)
- Gajic, D. (2023). [CLI Tips for Productive Angular Development.](https://blog.angular.io)
- Netanel Basal. (2022). [Advanced Angular CLI Usage.](https://netbasal.com)
