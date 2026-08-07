# Auditoría de documentación

## Parte A - Revisión de tu backlog de historias de usuario

### Paso 1

Recupera tu entregable del ejercicio pre-S4

### Paso 2 Contrástalo con lo que sabes ahora

- ¿Siguen teniendo sentido las historias tal como las generaste? ¿El alcance sigue ceñido al MVP del PRD, o se coló alguna que la IA "inventó" fuera de scope?
Sí se había colado una historia con una pantalla de bienvenida, no especificada en el MVP.

- ¿Hay historias cuyos criterios de aceptación ahora ves incompletos o poco verificables?

La historia 17 el AC3

```markdown
- Historia 17: Eliminación o marcado de evento al completar/borrar tarea
3. Given archivo una tarea con evento asociado *(asumido: `archived` se trata igual que completar/borrar a efectos de sincronización; el PRD no lo distingue)*, When la archivo, Then el evento se actualiza de forma consistente con ese comportamiento.
```

Está en la sección de `Notas / ambigüedades abiertas`. El texto `el evento se actualiza de forma consistente con ese comportamiento` que se va a hacer exactamente, cuando lo correcto es que se marque como `archived`.

- ¿Hay historias que han cambiado de naturaleza desde entonces? (porque descubriste una dependencia, porque la spec evolucionó, porque entiendes mejor el dominio).
No, hasta el momento no.

- ¿Hay historias nuevas que no aparecieron cuando lo generaste y que ahora sí deberían estar?
No, tampoco.

- Al contrastar con el backlog que el mentor construyó en el directo de S4 sobre Linear: ¿qué priorizaste distinto tú? ¿Quién acertó y por qué?
Más que el backlog, me llamo la atención las secciones de los prompt que comento, que yo no tenia o bien estaban muy pobres:

Las secciones son muy buenas, que a continuación te los describo:

```markdown
### Formato del output

Formato de output esperado (ejemplo, no lo copies literal, es sólo estructural)

---

Epica: [Nombre del módulo]
Historia N: [título corto de la historia]

Como [rol], quiero [acción], para [beneficio].

Criterios de aceptación:
Dado [contexto], cuando [acción], entonces [resultado esperado].
Dado [contexto], cuando [acción], entonces [resultado esperado].
Dado [contexto], cuando [acción], entonces [resultado esperado].

(repetir por cada story, agrupadas por épica)

### Seccion de supuestos

Supuestos y ambigüedades
 - [Lista de puntos del PRD que quedaron ambiguos o a decisión del equipo, y cómo los interpretaste o por qué no generaste una story para ellos.]

### La amplitud de la seccion de restricciones

Restricciones

Debes cumplir estrictamente las siguientes reglas:

- Analizar exclusivamente la información contenida en el PRD.
- No agregar funcionalidades, mejoras o ideas que no estén explícitamente definidas en el documento.
- No ampliar el alcance del MVP.
- No proponer funcionalidades "Nice to Have".
- No generar épicas futuras ni funcionalidades para versiones posteriores.
- Respetar completamente el stack tecnológico definido en el PRD.
- No realizar estimaciones de tiempo.
- No realizar estimaciones de esfuerzo (Story Points, T-Shirt Sizes, etc.).
- No incluir tareas técnicas ni subtareas de desarrollo.
- No proponer soluciones técnicas que contradigan el PRD.

Si existe alguna ambigüedad en el PRD, debes asumir siempre la interpretación más conservadora para mantener el alcance del MVP.

### La seccion de Calidad esperada

Calidad esperada

Todos los criterios de aceptación deben cumplir con el modelo INVEST:

- Independent (Independiente)
- Negotiable (Negociable)
- Valuable (Valiosa)
- Estimable (Estimable)
- Small (Pequeña)
- Testable (Comprobable)

Las historias de usuario también deben ser:

- Atómicas.
- No duplicadas.
- Claras.
- Sin ambigüedades.
- Orientadas al usuario.
- Funcionalmente completas.
- Priorizadas para la construcción del MVP.

### La seccion de Orden esperado

Orden esperado

Organiza las historias de usuario siguiendo un flujo lógico de construcción del producto, por ejemplo:

1. Autenticación
2. Gestión de usuarios
3. Configuración inicial
4. Funcionalidad principal
5. Administración
6. Reportes
7. Configuración
8. Integraciones
9. Notificaciones
10. Cierre del flujo del MVP

El orden debe facilitar el desarrollo incremental del producto.

### La seccion de Validación final

Validación final

Antes de finalizar, verifica que:

- Todas las funcionalidades del MVP estén cubiertas.
- No existan User Stories duplicadas.
- Ninguna User Story esté fuera del alcance del PRD.
- Todas las historias tengan valor para el usuario.
- Todos los criterios de aceptación sean verificables.
- No existan referencias a funcionalidades futuras.
- Se respete completamente el stack tecnológico definido en el PRD.
- La salida esté completamente escrita en español.

```

Secciones la verdad muy buenas y enriquecen el resultado del backlog.

### Paso 3 Anota los ajustes

- Ajuste 1
Seccion: `Historia 17`
Ajuste: Cambiar la redacción de la AC3 por: 
        - Dada una tarea tiene un evento asociado, When marco la tarea como `archived`, Then el evento se marca como archivado.
Motivo: Porque es consistente con el comportamiento de `completed`.

- Ajuste 2
Seccion: `Notas / ambigüedades abiertas`
Ajuste: En la Nota de **Orden por defecto del listado** hace referencia a la Historia 12, pero debe ser la 11
Motivo: Porque se eliminó una historia (la de la página de bienvenida)

- Ajuste 3
Seccion: `Notas / ambigüedades abiertas`
Ajuste: Eliminar la Nota de **Comportamiento exacto al completar una tarea (3.5):**
Motivo: Porque la AC2 dice `Then el evento se marca como completado`

- Ajuste 4
Seccion: `Notas / ambigüedades abiertas`
Ajuste: Eliminar la nota de *Tratamiento de tareas archivadas frente a sincronización (3.5):*
Motivo: Por el primer ajuste que se hizo.


## Parte B - Auditoría de documentación del proyecto

### Paso 4  Decide el formato del artefacto de auditoría

Tabla en Markdown con columnas (tipo de documentación, estado, observación, ubicación)

### Paso 5 - Audita cada tipo de documentación


| No | Tipo | Estado | Observación | Ubicación |
|---|---|---|---|---|
| 1 | `README` | Completa | El README raíz cubre el arranque de extremo a extremo: requisitos (Node 24+), instalación de dependencias, copia de `.env`, `generate:key`, migraciones y `npm run dev` para backend **y** frontend, más una tabla de endpoints. `backend/README.md` complementa con la estructura de carpetas y las convenciones del backend. El frontend no tiene README propio, pero el arranque ya queda cubierto desde el raíz. Falta indicar versión exacta probada de Node más allá de "24+" y no hay sección de troubleshooting. | `README.md` (raíz), `backend/README.md` |
| 2 | `Descripción de la arquitectura` | Parcial | No existe un documento dedicado que explique componentes y cómo se relacionan en tiempo de ejecución (flujo auth, cómo habla el frontend con la API, etc.). Lo que hay es un árbol de carpetas en el README raíz y una sección "Estructura" en `backend/README.md` (solo lista de directorios, sin explicar relaciones). `docs/README.md` reconoce explícitamente que "ADRs y diagramas de arquitectura se añaden en sesiones posteriores" — está identificado como pendiente. No hay diagrama C4 pese a que `docs/README.md` lo anuncia como parte del PRD. | Disperso: `README.md` (raíz), `backend/README.md`, `docs/README.md` |
| 3 | `Documentación de la API` | Parcial | El README raíz trae una tabla de endpoints (método, ruta, auth, descripción) que cubre todo lo implementado y es suficiente para no tener que leer `start/routes.ts`. Pero no es una spec real: no documenta shape de request/response, códigos de error (401/404/422) ni ejemplos de payload. Para integrarse de verdad contra la API todavía haría falta leer los controllers o las specs de OpenSpec. | `README.md` (raíz), sección "Endpoints del backend" |
| 4 | `TSDoc/JSDoc` | Parcial | Los controllers (`health`, `users`, `new_accounts`, `access_tokens`, `profiles`) tienen un comentario breve y consistente por método (ruta + una línea de descripción), igual que el transformer y los validators. Pero no son TSDoc reales (sin `@param`/`@returns`/errores documentados) y el modelo `User` (`app/models/user.ts`) no tiene ningún comentario, pese a ser la pieza con más reglas implícitas (auth finder, access tokens, columnas ocultas). | `backend/app/controllers/*.ts`, `backend/app/transformers/user_transformer.ts`, `backend/app/validators/auth.ts`; sin cobertura en `backend/app/models/user.ts` |
| 5 | `ADRs` | Inexistente | No hay carpeta ni archivos de ADRs en ningún sitio del repo. Las decisiones técnicas relevantes (por qué SQLite, por qué access tokens y no sesiones, por qué scrypt) no están justificadas por escrito en ningún documento; solo se pueden inferir del código y del PRD §5 (que es informativo, no una decisión razonada). | No existe |
| 6 | `Guía operacional` | Inexistente | No hay instrucciones de despliegue a ningún entorno, no hay pipeline de CI/CD (`.github/` no existe), no hay Dockerfile ni docker-compose, y no hay runbooks o troubleshooting para incidencias típicas. El README solo cubre arranque en local para desarrollo. | No existe |
| 7 | `Convenciones` | Completa | `CLAUDE.md` en el raíz documenta stack, comandos, convenciones de backend (lógica en controllers, validación con VineJS, salida vía transformers, subpath imports, rutas bajo `/api/v1`) y una lista explícita de "No hacer". Está reforzado y es coherente con `backend/README.md` y con el bloque `context` de `openspec/config.yaml`. | `CLAUDE.md` (raíz), reforzado en `backend/README.md` y `openspec/config.yaml` |
| 8 | `Especificación OpenSpec` | Parcial | Hay dos specs (`authentication`, `users`) bien escritas con requirements y scenarios en formato WHEN/THEN/AND. La spec de `authentication` está 100% sincronizada con el código (register, login, logout, profile implementados tal cual se describen). La spec de `users`, en cambio, documenta `GET /api/v1/users/active` (requirement "Listado de usuarios activos") que **no existe en el código**: `users_controller.ts` solo implementa `index` y `show`, y no hay ruta `/users/active` en `start/routes.ts` — solo un comentario indicando que se implementará en directo. Es una divergencia real spec↔código que cualquiera que confíe ciegamente en la spec detectaría tarde. | `openspec/specs/authentication/spec.md` (en sync), `openspec/specs/users/spec.md` (diverge de `backend/app/controllers/users_controller.ts` y `backend/start/routes.ts`) |

### Paso 6 - Top 3

- Carencias y fortalezas

1. **La spec de OpenSpec de `users` describe un endpoint (`GET /api/v1/users/active`) que no existe en el código.** Es la carencia más peligrosa porque no es una simple ausencia de documentación: es documentación que activamente miente. Cualquiera que planifique trabajo o integre contra la API confiando en la spec se lleva una sorpresa. Es justo el tipo de divergencia que rompe la confianza en "la spec como fuente de verdad".
2. **No hay guía operacional ni ADRs.** El proyecto no tiene forma de desplegarse fuera de local (sin CI/CD, sin Dockerfile, sin runbooks) y las decisiones técnicas de fondo (SQLite, access tokens, scrypt) no están justificadas por escrito. Para un repo que se usa como base de referencia de un máster, esto deja a cualquiera que lo extienda sin criterio documentado de "por qué así y no de otra forma".
3. **No hay descripción de arquitectura real ni diagrama C4**, pese a que `docs/README.md` lo anuncia como parte del plan. Lo que existe son árboles de carpetas, que describen dónde vive el código, no cómo se relacionan los componentes en ejecución (auth flow, frontend↔backend, etc.). Esto complica el onboarding de alguien que necesite entender el sistema sin leer todo el código.

- Cosas que ya están bien

1. **El README raíz permite arrancar el proyecto de cero sin preguntar a nadie**: requisitos, instalación, `.env`, `generate:key`, migraciones y arranque de backend y frontend están cubiertos con comandos copiables y en orden correcto.
2. **La spec de `authentication` está perfectamente sincronizada con el código.** Registro, login, logout y perfil coinciden exactamente entre lo que dice la spec (incluyendo status codes y forma de la respuesta) y lo que hace el controller. Es el ejemplo a seguir para el resto de specs.
3. **Las convenciones del proyecto están bien centralizadas y son coherentes entre documentos.** `CLAUDE.md`, `backend/README.md` y `openspec/config.yaml` dicen lo mismo (lógica en controllers, validación VineJS, transformers, subpath imports), sin contradicciones entre sí — nada que "romper" en la sesión.

### Paso 7 - Exploración rápida de tres formatos de documentación

- Diagrama C4
Presenta una vista panorámica (el mapa completo) e ir haciendo "zoom in"

- ADR
Muestran el porqué, la justificación y las consecuencias de cada decisión tecnológica.

- Especificación OpenAPI
Muestra los parámetros, solicitudes y las respuestas de cada punto final.