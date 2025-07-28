---
sidebar_position: 15
---

# Ejercicios propuestos por tema

## TypeScript para Angular: tipos, interfaces, clases

### Reto 1: Clases en acción (Angular-friendly)

*Nivel:* Medio

*Tiempo estimado de resolución:* 40 minutos

*Participantes:* Grupo de 3

*Enunciado:* Crea una clase `Product` con propiedades como `id`, `name`, `price` y un método `applyDiscount(percentage: number): number`. Luego, instánciala en un archivo y úsala para calcular precios.

*Resultado esperado:* Código de clase funcional y prueba en consola mostrando descuentos aplicados.

*Pistas o ayudas:*

- Las clases en TypeScript permiten constructores, propiedades privadas y métodos públicos. Usa modificadores de acceso (`public`, `private`, `readonly`).

## Signals

### Reto 1: Tu primer signal

*Nivel:* Básico

*Tiempo estimado de resolución:* 25 minutos

*Participantes:* Individual

*Enunciado:* Crea un componente Angular con un signal que almacene un contador. Debe:

- Mostrar el valor actual
- Incrementar y decrementar el contador con dos botones

*Resultado esperado:*

- Uso de `signal<number>(0)`
- Métodos `set`, `update` o equivalentes
- Template funcional

*Pistas o ayudas:*

- Recuerda importar signal desde `@angular/core` y actualizar el valor con `counter.update(v => v + 1)`.

### Reto 2: Signals + computed

*Nivel:* Básico

*Tiempo estimado de resolución:* 30 minutos

*Participantes:* En parejas

*Enunciado:* Crea un componente que tenga dos signals: price y quantity. Usa un computed para mostrar el total dinámico. Ejemplo:

```txt
Precio: 50
Cantidad: 2
Total: 100
```

*Resultado esperado:*

- Signal de precio y cantidad
- `computed` para el total
- Template que actualice dinámicamente el total al cambiar valores

*Pistas o ayudas:*

- Importa `computed` de `@angular/core` y recuerda que se recalcula automáticamente cuando cambian los signals dependientes.

## Comunicación entre componentes: `@Input` y `@Output`

### Reto 1: Lista dinámica con datos hacia y desde el hijo

*Nivel:* Medio

*Tiempo estimado de resolución:* 40 minutos

*Participantes:* Grupo de 3

*Enunciado:* Implementa un componente padre que tenga una lista de tareas y un componente hijo que muestre cada tarea:

- El padre envía la lista al hijo (`@Input`)
- El hijo emite un evento cuando el usuario borre una tarea (`@Output`)
- El padre actualiza la lista al recibir el evento

*Resultado esperado:*

- Comunicación en dos vías: datos bajan (`@Input`), eventos suben (`@Output`)
- Lista dinámica funcional

*Pistas o ayudas:*

- Declara en el hijo:

  ```ts showLineNumbers
  @Input() tasks: string[] = [];
  @Output() remove = new EventEmitter<number>();
  ```

- Puedes usar `input()` y `output()` para ajustarte a las versiones más recientes de Angular.

### Reto 2: Comunicación entre varios niveles

*Nivel:* Avanzado

*Tiempo estimado de resolución:* 55 minutos

*Participantes:* Grupo de 4

*Enunciado:* Crea una estructura de 3 componentes anidados: `GrandParent`, `Parent` y `Child`.

- `GrandParent` envía datos al `Child` usando `@Input` indirectamente a través del `Parent`.
- `Child` emite un evento (`@Output`) hacia el `Parent`, y este a su vez lo propaga al `GrandParent`.

*Resultado esperado:*

- Comunicación de datos descendente a través de múltiples niveles
- Eventos que se propagan hacia arriba

*Pistas o ayudas:*

- Los decoradores no funcionan de forma automática en múltiples niveles. Debes “encadenar” los @Input y @Output en cada nivel.

## Servicios en Angular e Inyección de Dependencias

### Reto 1: Interfaces + Clases + Servicios Angular

*Nivel:* Avanzado

*Tiempo estimado de resolución:* 50 minutos

*Participantes:* Grupo de 4

*Enunciado:* Crea una interfaz Task y una clase TaskService en Angular que:

- Defina un arreglo de tareas
- Permita agregar y obtener tareas
- Use tipado fuerte en todo momento

*Resultado esperado:*

- Archivo `task.interface.ts` con el contrato
- Clase `TaskService` inyectable en Angular (`@Injectable`)
- Prueba en consola desde un componente mostrando tareas cargadas

*Pistas o ayudas:*

- Recuerda cómo Angular maneja los servicios con `@Injectable` y la inyección de dependencias.

### Reto 2: Servicio con lógica de negocio

*Nivel:* Medio

*Tiempo estimado de resolución:* 40 minutos

*Participantes:* En parejas

*Enunciado:* Crea un servicio `CartService` que gestione un carrito de compras:

- Agregar productos
- Quitar productos
- Calcular el total

Usa este servicio en dos componentes: uno para mostrar productos y otro para mostrar el carrito.

*Resultado esperado:*

- Servicio inyectado en ambos componentes
- Métodos `addItem()`, `removeItem()` y `getTotal()`
- Lista de productos compartida

*Pistas o ayudas:*

- Usa `private cart: Product[] = []` dentro del servicio y expón solo lo necesario.

### Reto 3: Servicio HTTP con HttpClient

*Nivel:* Medio

*Tiempo estimado de resolución:* 45 minutos

*Participantes:* Grupo de 3

*Enunciado:* Implementa un servicio `UserService` que consulte usuarios de una API pública ([https://jsonplaceholder.typicode.com/users](https://jsonplaceholder.typicode.com/users)).

- Métodos: `getUsers()`, `getUserById(id)`
- Muestra la lista de usuarios en un componente usando el servicio

*Resultado esperado:*

- Servicio inyectado correctamente con `HttpClient`
- Llamadas asíncronas funcionales
- Template con datos renderizados

*Pistas o ayudas:*

- Recuerda importar el `HttpClientModule` en el `bootstrapApplication` de Angular 20 o en el `AppModule` si lo usas en versiones anteriores.

### Reto 4: Servicios + Signals (estado reactivo global)

*Nivel:* Avanzado

*Tiempo estimado de resolución:* 55 minutos

*Participantes:* Grupo de 4

*Enunciado:* Crea un servicio `AuthService` que use signals para manejar el estado de autenticación:

- `isAuthenticated: Signal<boolean>`
- Método `login()` y `logout()` que actualicen el estado
- Componente de login que reactive el template según el estado

*Resultado esperado:*

- Servicio inyectable con `signal` y métodos que actualicen el estado
- Componentes que reaccionen automáticamente a los cambios sin `Subject` ni `BehaviorSubject`

*Pistas o ayudas:*

- Usa `signal(false)` para inicializar el estado y `computed` o `effect` si necesitas derivar datos.

## Routing en Angular (básico y avanzado)

### Reto 1: Parámetros en la ruta

*Nivel:* Básico

*Tiempo estimado:* 30 minutos

*Participantes:* En parejas

*Enunciado:* Implementa un componente `UserDetailComponent` que reciba el **ID del usuario** por parámetro en la URL (`/users/:id`).

- Debe mostrar el ID recibido
- Si el ID no existe, mostrar un mensaje de error

*Resultado esperado:*

- Uso de `ActivatedRoute` para obtener el parámetro
- Navegación dinámica usando `routerLink` en un listado de usuarios

*Pistas o ayudas:*

- Usa `route.paramMap.subscribe(...)` o el nuevo `route.paramMap().subscribe()` si usas signals.

### Reto 2: Rutas hijas y layout común

*Nivel:* Medio

*Tiempo estimado:* 40 minutos

*Participantes:* Grupo de 3

*Enunciado:* Crea un módulo de administración con un layout (`AdminLayoutComponent`) que contenga:

- Rutas hijas: `dashboard`, `users`, `settings`
- Navbar y `<router-outlet>` compartidos en el layout

*Resultado esperado:*

- Navegación `/admin/dashboard`, `/admin/users`, `/admin/settings`
- Layout persistente mientras cambian las rutas hijas

*Pistas o ayudas:*

- Define las rutas así:

  ```ts
  {
    path: 'admin',
    component: AdminLayoutComponent,
    children: [
      { path: 'dashboard', component: DashboardComponent },
      ...
    ]
  }
  ```

### Reto 3: Lazy Loading con loadComponent

*Nivel:* Avanzado

*Tiempo estimado:* 50 minutos

*Participantes:* Grupo de 4

*Enunciado:* Configura el **lazy loading** de un componente `ReportsComponent` que solo se cargue cuando el usuario navegue a `/reports`.

*Resultado esperado:*

- Uso de `loadComponent` en lugar de `component` en la definición de la ruta
- Validación de que el bundle solo se carga al entrar a la ruta

*Pistas o ayudas:*

```ts
{
  path: 'reports',
  loadComponent: () =>
    import('./reports/reports.component').then(m => m.ReportsComponent)
}
```

### Reto 4: Guards y protección de rutas

*Nivel:* Avanzado

*Tiempo estimado:* 55 minutos

*Participantes:* Grupo de 4

*Enunciado:* Implementa un **guard** llamado `authGuard` que permita el acceso solo si el usuario está autenticado:

- Si el usuario no está autenticado, redirígelo a `/login`
- Si está autenticado, permitir acceso a `/profile`

*Resultado esperado:*

- Función guard implementada con `inject(AuthService)`
- Integración en el arreglo de rutas con `canActivate`

*Pistas o ayudas:*

```ts
export const authGuard: CanActivateFn = (route, state) => {
  const auth = inject(AuthService);
  return auth.isAuthenticated() ? true : redirectUnauthorizedToLogin();
};
```

## Validación de formularios (sincrónica y asincrónica)

### Reto 1: Validaciones básicas sincrónicas

*Nivel:* Básico

*Tiempo estimado:* 30 minutos

*Participantes:* Individual

*Enunciado:* Crea un formulario de registro con los campos nombre, email y password.

- El `nombre` es requerido.
- El `email` debe ser válido.
- El `password` debe tener al menos 8 caracteres.

*Resultado esperado:*

- Uso de `FormGroup` y validadores de Angular (`Validators.required`, `Validators.email`, `Validators.minLength`).
- Mensajes de error dinámicos en el template (`<div *ngIf="control.errors?.required">...`).

*Pistas o ayudas:*

- Usa `ReactiveFormsModule` importado en tu componente standalone y formControlName en el template.

### Reto 2: Validador personalizado de contraseñas

*Nivel:* Básico

*Tiempo estimado:* 35 minutos

*Participantes:* En parejas

*Enunciado:* Extiende el formulario anterior agregando confirmación de contraseña (`confirmPassword`) con un **validador sincrónico personalizado** que verifique que ambas coincidan.

*Resultado esperado:*

- Función validadora aplicada al `FormGroup` completo (no solo a un control).
- Mensaje de error cuando las contraseñas no coincidan.

*Pistas o ayudas:*

- Crea un validador como:

  ```ts
  export function passwordsMatch(control: AbstractControl) {
    const pass = control.get('password')?.value;
    const confirm = control.get('confirmPassword')?.value;
    return pass === confirm ? null : { passwordsMismatch: true };
  }
  ```

### Reto 3: Validación asíncrona de usuario existente

*Nivel:* Medio

*Tiempo estimado:* 45 minutos

*Participantes:* Grupo de 3

*Enunciado:* Agrega un campo `username` al formulario. Este debe validarse contra una API simulada para verificar si el usuario ya existe.

- Si el usuario existe, muestra un error.
- Si no existe, permite continuar.

*Resultado esperado:*

- Uso de validadores asíncronos con `AsyncValidatorFn`.
- Llamada a un `UserService` que devuelva un `Observable<boolean>`.

*Pistas o ayudas:*

- Usa `of()` y `delay()` de RxJS para simular la llamada HTTP:

  ```ts
  export function usernameValidator(userService: UserService): AsyncValidatorFn {
    return (control: AbstractControl) =>
      userService.checkUserExists(control.value).pipe(
        map(exists => exists ? { userExists: true } : null)
      );
  }
  ```

## Manejo de estados en formularios

### Reto 1: Observando el estado de un campo

*Nivel:* Básico

*Tiempo estimado:* 25 minutos

*Participantes:* Individual

*Enunciado:* Crea un formulario con un solo campo email y muestra en el template el estado actual de ese `FormControl`:

- `touched` / `untouched`
- `dirty` / `pristine`
- `valid` / `invalid`

*Resultado esperado:*

- Template que reaccione a los cambios en tiempo real
- Uso de `formControl.status` y propiedades directas (`control.touched`, `control.dirty`)

*Pistas o ayudas:*

- Usa `ReactiveFormsModule` y muestra los estados con `{{ emailControl.dirty }}`.

### Reto 2: Cambiando estado programáticamente

*Nivel:* Básico

*Tiempo estimado:* 30 minutos

*Participantes:* En parejas

*Enunciado:* Agrega un segundo campo `password` al formulario y botones que permitan:

- Limpiar el campo (`reset()`)
- Marcarlo como touched manualmente (`markAsTouched()`)
- Deshabilitarlo y volverlo a habilitar (`disable()` / `enable()`)

*Resultado esperado:*

- Control del estado desde el componente TS
- Template actualizado según los cambios

*Pistas o ayudas:*

- Crea métodos en el componente:

  ```ts
  disablePassword() { 
    this.form.controls['password'].disable(); 
  }
  ```

### Reto 3: Estados y UX mejorada (avance visual)

*Nivel:* Avanzado

*Tiempo estimado:* 55 minutos

*Participantes:* Grupo de 4

*Enunciado:*

Implementa un formulario de registro que muestre indicadores visuales según el estado de los campos:

- Bordes rojos para inválidos
- Bordes verdes para válidos
- Icono de “cargando” cuando el control esté `pending` por validación asíncrona
- Además, agrega un `progress bar` que muestre el porcentaje de campos completados correctamente.

*Resultado esperado:*

- Uso de `[ngClass]` y estados `control.valid`, `control.invalid`, `control.pending`
- Barra de progreso dinámica calculada en el componente

*Pistas o ayudas:*

- Itera sobre `form.controls` para contar cuántos están válidos y calcular el porcentaje.
