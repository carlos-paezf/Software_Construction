---
sidebar_position: 07
---

# Ejercicios propuesto por tema

## Capas y dependencias en Clean Architecture

### Reto 1: Inversión de dependencias en acción

*Nivel:* Avanzado

*Tiempo estimado de resolución:* 45 minutos

*Participantes:* Grupo de 3

*Enunciado:* Implementen una funcionalidad simple (ej. “registrar usuario”) usando Clean Architecture. Asegúrense de aplicar correctamente el principio de inversión de dependencias, usando interfaces y adaptadores.

*Resultado esperado:*

- Código organizado por capas
- Interfaz definida en dominio o aplicación
- Implementación real en infraestructura
- Diagrama explicativo con flechas de dependencia

*Pistas o ayudas:*

- La **interfaz debe ser definida en el dominio o en el caso de uso**, y su implementación concreta debe quedar fuera (infraestructura). Apliquen Dependency Inversion Principle - DIP.

## Arquitectura modular monolítica

### Reto 1: Diseña tu monolito modular

*Nivel:* Medio

*Tiempo estimado de resolución:* 40 minutos

*Participantes:* En parejas

*Enunciado:* Imagina que tu equipo debe construir una app de gestión académica universitaria. Diseñen una arquitectura modular monolítica, identificando:

- Módulos funcionales (ej. `students`, `courses`, `grades`)
- Contratos entre ellos (interfaces, DTOs, servicios)
- Diagrama general con flechas de dependencia

Resultado esperado:

- Diagrama visual (puede ser dibujado o digital)
- Documento con descripción de cada módulo y sus límites

*Pistas o ayudas:*

- Un buen módulo tiene **alta cohesión** interna y bajo acoplamiento externo. Pueden usar herramientas como Lucidchart, draw.io o papel y colores.

## Diseño de casos de uso y entidades

### Reto 1: Casos de uso que colaboran

*Nivel:* Medio

*Tiempo estimado de resolución:* 40 minutos

*Participantes:* Grupo de 3

*Enunciado:* A partir de la historia: "Un profesor puede registrar calificaciones de los estudiantes solo si están inscritos en el curso." Modelen:

- Las entidades involucradas (Profesor, Estudiante, Curso, Nota)
- Al menos 2 casos de uso que colaboren (ej. Validar inscripción, Registrar nota)

*Resultado esperado:*

- Diagrama de entidades con relaciones
- Diagrama o lista de casos de uso y su interacción

*Pistas o ayudas:*

- Un caso de uso puede llamar a otro caso de uso o requerir validaciones externas. Identifica bien las reglas previas (precondiciones).
