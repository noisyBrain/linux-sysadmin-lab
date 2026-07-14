# Día 4 — Auditoría de permisos

## Contexto

Durante una revisión interna se detectó que algunos desarrolladores pueden acceder a archivos que no deberían.

Infraestructura debe realizar una auditoría rápida.

---

## Objetivos del día

- Identificar permisos incorrectos.
- Revisar ownership.
- Validar grupos.

---

## Tareas

| Tarea | Objetivo | Dificultad | Tiempo |
| --- | --- | --- | --- |
| Inspeccionar permisos de directorios críticos | Detectar configuraciones riesgosas | 3/5 | 20 min |
| Identificar archivos cuyo owner no coincide con el esperado | Detectar inconsistencias | 4/5 | 20 min |
| Revisar pertenencia a grupos | Comprender acceso compartido | 4/5 | 20 min |
| Corregir estructura de ownership definida por el equipo | Alinear seguridad | 4/5 | 25 min |
| Documentar hallazgos y correcciones realizadas | Trazabilidad | 3/5 | 20 min |

---

## Checkpoint

- [ ]  Revisé owners
- [ ]  Revisé grupos
- [ ]  Detecté permisos sospechosos
- [ ]  Realicé correcciones necesarias
- [ ]  Documenté cambios

---

## Qué deberías aprender

### Habilidades adquiridas

- Lectura de permisos
- Gestión de ownership
- Comprensión básica de control de acceso

### Comandos utilizados

- chmod
- chown
- ls
- find

### Errores comunes

- Cambiar permisos sin verificar impacto
- Confundir owner y group
- Aplicar permisos excesivos

### Buenas prácticas

- Mínimo privilegio
- Documentar cambios
- Verificar después de modificar