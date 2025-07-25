---
sidebar_position: 11
---

# Estilos con TailwindCSS o Angular Material

Angular proporciona un sistema robusto para el manejo de estilos (CSS/SCSS encapsulado por componente). Sin embargo, al construir aplicaciones reales necesitamos **acelerar el diseño** y mantener **consistencia visual**.

Para ello se suelen usar **frameworks utilitarios o de componentes** como:

- **TailwindCSS:** Framework de utilidades CSS.
- **Angular Material:** Librería oficial de componentes UI para Angular.

Ambos pueden **convivir** según las necesidades del proyecto.

## TailwindCSS

### ¿Qué es TailwindCSS?

- Es un **framework de utilidades** CSS que permite diseñar interfaces directamente desde las clases en el HTML.
- Genera **clases predefinidas** como `flex`, `p-4`, `bg-blue-500`, etc., que se componen entre sí.
- Ideal para **personalización rápida** y estilos modernos.

### Instalación Tailwind

```bash
npm install -D tailwindcss @tailwindcss/postcss postcss autoprefixer --force
npx tailwindcss init
```

Crea y configura el archivo `.postcssrc.json` en la raíz de tu proyecto y añade el plugin `@tailwindcss/postcss`:

```json
{
  "plugins": {
    "@tailwindcss/postcss": {}
  }
}
```

Agregar a `styles.scss`:

```scss
@import "tailwindcss";
```

### Ejemplo de uso Tailwind

```html
<div class="flex items-center justify-center h-screen bg-gray-100">
  <button class="px-4 py-2 text-white bg-blue-600 rounded hover:bg-blue-700">
    Guardar
  </button>
</div>
```

### Ventajas Tailwind

- Alta **velocidad de prototipado**.
- Tamaño de CSS optimizado (purge automático).
- Fácil de combinar con componentes Angular.

### Limitaciones Tailwind

- Clases largas en el HTML (aunque se puede usar `@apply` en SCSS).
- No incluye componentes listos, hay que componerlos.

## Angular Material

### ¿Qué es Angular Material?

- Es la librería oficial de **componentes UI de Angular**, basada en las Material Design Guidelines de Google.
- Ofrece **componentes listos** y accesibles (botones, menús, tablas, formularios, etc.).
- Altamente integrado con Angular y su sistema de theming.

### Instalación Angular Material

```bash
ng add @angular/material
```

Angular CLI configurará automáticamente estilos globales y temas.

### Ejemplo de uso Angular Material

```ts
import { Component } from '@angular/core';
import { MatButtonModule } from '@angular/material/button';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [MatButtonModule],
  template: `
    <button mat-raised-button color="primary">Guardar</button>
  `
})
export class App {}
```

### Theming (temas de colores)

`angular.json` incluye un tema por defecto (indigo/pink). Puedes personalizarlo en `styles.scss`:

```scss
@use '@angular/material' as mat;

$custom-theme: mat.define-light-theme((
  color: (
    primary: mat.define-palette(mat.$indigo-palette),
    accent: mat.define-palette(mat.$pink-palette)
  )
));

@include mat.all-component-themes($custom-theme);
```

## Comparativa rápida

|Característica|TailwindCSS|Angular Material|
|--|--|--|
|Tipo|Utilidades CSS|Componentes UI completos|
|Componentes listos|No|Sí (botones, tablas, diálogos, etc.)|
|Personalización|Muy alta (desde utilidades)|Alta (via theming y CSS)|
|Curva de aprendizaje|Baja|Media|
|Integración Angular|Indirecta (HTML y SCSS)|Total (standalone components y directivas)|

## ¿Usar uno, el otro o ambos?

1. **TailwindCSS** es ideal para:
   - Diseños personalizados
   - Prototipado rápido
   - Aplicaciones con estilos únicos
2. **Angular Material** es ideal para:
   - Aplicaciones empresariales
   - Diseño consistente basado en Material Design
   - Necesidad de componentes listos y accesibles
3. **Usar ambos** es válido:
   - Angular Material para la base de componentes
   - TailwindCSS para personalización y ajustes rápidos

## Buenas prácticas

- Mantén un **diseño consistente**: define paleta de colores y tipografía.
- Si usas Angular Material, aprovecha el sistema de **temas globales**.
- Con Tailwind, utiliza `@apply` en SCSS para simplificar clases largas.
- Evita duplicar librerías de componentes que cumplan la misma función.

## Referencias

- Angular Team. (2024). [Angular Material Documentation](https://material.angular.io). Angular.dev.
- Tailwind Labs. (2024). [TailwindCSS Documentation](https://tailwindcss.com).
- Tailwind Labs. (2024). [Install Tailwind CSS with Angular](https://tailwindcss.com/docs/installation/framework-guides/angular).
- Brown, S. (2023). Design Systems in Angular. Leanpub.
- Google Developers. (2023). [Material Design Guidelines](https://m3.material.io).
