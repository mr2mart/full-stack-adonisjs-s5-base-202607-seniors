# Respuestas

## ¿Siguen teniendo sentido las historias tal como las generaste? ¿El alcance sigue ceñido al MVP del PRD, o se coló alguna que la IA "inventó" fuera de scope?
Si se habia colado una historia con una pantalla de bienvenida, no especificada en el MVP.

## ¿Hay historias cuyos criterios de aceptación ahora ves incompletos o poco verificables?
La historia 17 el AC3
```
### Historia 17: Eliminación o marcado de evento al completar/borrar tarea
3. Given archivo una tarea con evento asociado *(asumido: `archived` se trata igual que completar/borrar a efectos de sincronización; el PRD no lo distingue)*, When la archivo, Then el evento se actualiza de forma consistente con ese comportamiento.
```
Esta en la seccion de `Notas / ambigüedades abiertas`. El texto `el evento se actualiza de forma consistente con ese comportamiento` que se va a hacer exactamente, cuando lo correcto es que se marque como `archived`.

## ¿Hay historias que han cambiado de naturaleza desde entonces? (porque descubriste una dependencia, porque la spec evolucionó, porque entiendes mejor el dominio).
No, hasta el momento no.

## ¿Hay historias nuevas que no aparecieron cuando lo generaste y que ahora sí deberían estar?
No, tampoco.

## Al contrastar con el backlog que el mentor construyó en el directo de S4 sobre Linear: ¿qué priorizaste distinto tú? ¿Quién acertó y por qué?
Mas que el backlog, me llamo la atención las secciones de los prompt que comento, que yo no tenia o bien estaban muy pobres:

A continuación te los describo:

```
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