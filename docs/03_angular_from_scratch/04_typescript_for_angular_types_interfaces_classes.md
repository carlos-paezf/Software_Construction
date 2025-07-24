---
sidebar_position: 4
---

# TypeScript para Angular: tipos, interfaces, clases

Angular está construido sobre **TypeScript**, un superconjunto tipado de JavaScript que permite detectar errores antes de ejecutar el código, definir estructuras formales de datos, y aplicar principios de programación orientada a objetos (OOP) y funcional.

Comprender y usar adecuadamente los **tipos, interfaces y clases** en TypeScript es esencial para escribir aplicaciones Angular robustas, mantenibles y seguras.

## ¿Por qué TypeScript en Angular?

Angular requiere TypeScript porque:

- Proporciona **tipado estático** para evitar errores comunes
- Mejora la experiencia con **autocompletado** y **refactorización**
- Permite trabajar con **decoradores** (`@Component`, `@Injectable`, etc.)
- Aplica principios de **POO moderna** (clases, herencia, encapsulamiento)
- Hace posible implementar **principios SOLID** y patrones de diseño

## Tipos en TypeScript

Los tipos son la base del sistema de tipos de TypeScript. Sirven para restringir el tipo de datos que puede contener una variable o parámetro. Los tipos son útiles cuando necesitas restricciones simples, combinaciones, o unión de tipos.

### Ejemplo de tipos primitivos

```ts showLineNumbers
let username: string = 'Carlos';
let age: number = 25;
let isAdmin: boolean = false;
```

### Ejemplo de tipos compuestos

```ts showLineNumbers
let tags: string[] = ['angular', 'typescript'];
let tuple: [string, number] = ['item', 1];
let status: 'pending' | 'approved' | 'rejected' = 'approved';
```

### Ejemplo de tipos personalizados

```ts showLineNumbers
type Role = 'STUDENT' | 'TEACHER';

type UserID = number | string;
```

## Interfaces en TypeScript

Una `interface` describe la **forma de un objeto**. Es una de las herramientas más usadas en Angular, especialmente para definir contratos de datos (por ejemplo, una entidad, un DTO o una respuesta de API).

Por ejemplo:

```ts showLineNumbers
export interface Student {
  id: number;
  fullName: string;
  email: string;
  enrolled: boolean;
}

const newStudent: Student = {
  id: 1,
  fullName: 'Ana Gómez',
  email: 'ana@usta.edu.co',
  enrolled: true,
};
```

Con las interfaces podemos aplicar conceptos de POO como la herencia:

```ts showLineNumbers
interface Person {
  name: string;
  email: string;
}

interface Teacher extends Person {
  subject: string;
}
```

Las interfaces permiten aplicar polimorfismo, composición y cumplir con el principio de sustitución de Liskov (SOLID).

## Clases en TypeScript

Las clases permiten definir plantillas de objetos con lógica. Son esenciales en Angular para:

- Servicios (`@Injectable`)
- Componentes (`@Component`)
- Pipes (`@Pipe`)
- Repositorios
- Casos de uso

Por ejemplo, así se vería una clase simple:

```ts showLineNumbers
export class StudentModel {
  constructor(
    public id: number,
    public name: string,
    public enrolled: boolean
  ) {}

  toggleEnrollment(): void {
    this.enrolled = !this.enrolled;
  }
}
```

Adicional podemos hacer uso de interfaces para implementarlas en las clases:

```ts showLineNumbers
export interface Enrollable {
  toggleEnrollment(): void;
}

export class Student implements Enrollable {
  constructor(public id: number, public name: string, public enrolled: boolean) {}

  toggleEnrollment() {
    this.enrolled = !this.enrolled;
  }
}
```

## Relación entre tipos, interfaces y clases

|Concepto|Se usa para...|Puede instanciarse|Permite lógica|Extiende otros|
|--|--|--|--|--|
|`type`|Tipos simples o combinados|❌|❌|✅ (via union)|
|`interface`|Estructura de objetos o contratos |❌|❌|✅|
|`class`|Modelos de lógica + datos |✅|✅|✅|

## Aplicación de principios Clean y SOLID

- **S (Single Responsibility):** las interfaces y clases tienen una única responsabilidad (modelo, servicio, vista).
- **O (Open/Closed):** puedes extender interfaces o clases sin modificarlas.
- **L (Liskov):** puedes sustituir implementaciones concretas por interfaces.
- **I (Interface Segregation):** puedes definir pequeñas interfaces específicas.
- **D (Dependency Inversion):** Angular inyecta dependencias a través de interfaces o tokens.

## Referencias

- Microsoft. (2024). [TypeScript Handbook.](https://www.typescriptlang.org/docs/)
- Angular Team. (2024). [Angular & TypeScript Integration.](https://angular.dev/guide/typescript)
- Freeman, E., & Robson, E. (2020). Head First Object-Oriented Analysis and Design. O’Reilly.
- Brown, S. (2021). [Clean Architecture with Angular and TypeScript.](https://leanpub.com/clean-angular-architecture) Leanpub.
