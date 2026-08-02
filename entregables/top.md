# Carencias y fortalezas

## Top 3 carencias que más duelen

1. **La spec de OpenSpec de `users` describe un endpoint (`GET /api/v1/users/active`) que no existe en el código.** Es la carencia más peligrosa porque no es una simple ausencia de documentación: es documentación que activamente miente. Cualquiera que planifique trabajo o integre contra la API confiando en la spec se lleva una sorpresa. Es justo el tipo de divergencia que rompe la confianza en "la spec como fuente de verdad".
2. **No hay guía operacional ni ADRs.** El proyecto no tiene forma de desplegarse fuera de local (sin CI/CD, sin Dockerfile, sin runbooks) y las decisiones técnicas de fondo (SQLite, access tokens, scrypt) no están justificadas por escrito. Para un repo que se usa como base de referencia de un máster, esto deja a cualquiera que lo extienda sin criterio documentado de "por qué así y no de otra forma".
3. **No hay descripción de arquitectura real ni diagrama C4**, pese a que `docs/README.md` lo anuncia como parte del plan. Lo que existe son árboles de carpetas, que describen dónde vive el código, no cómo se relacionan los componentes en ejecución (auth flow, frontend↔backend, etc.). Esto complica el onboarding de alguien que necesite entender el sistema sin leer todo el código.

## Top 3 cosas que ya están bien

1. **El README raíz permite arrancar el proyecto de cero sin preguntar a nadie**: requisitos, instalación, `.env`, `generate:key`, migraciones y arranque de backend y frontend están cubiertos con comandos copiables y en orden correcto.
2. **La spec de `authentication` está perfectamente sincronizada con el código.** Registro, login, logout y perfil coinciden exactamente entre lo que dice la spec (incluyendo status codes y forma de la respuesta) y lo que hace el controller. Es el ejemplo a seguir para el resto de specs.
3. **Las convenciones del proyecto están bien centralizadas y son coherentes entre documentos.** `CLAUDE.md`, `backend/README.md` y `openspec/config.yaml` dicen lo mismo (lógica en controllers, validación VineJS, transformers, subpath imports), sin contradicciones entre sí — nada que "romper" en la sesión.
