# Día 3 — Investigación de logs

## Contexto

Un desarrollador informa que algunos procesos fallaron durante el fin de semana.

Infraestructura necesita revisar registros para identificar evidencias.

---

## Objetivos del día

- Localizar logs relevantes.
- Filtrar información útil.
- Reducir ruido.

---

## Tareas

| Tarea | Objetivo | Dificultad | Tiempo |
| --- | --- | --- | --- |
| Localizar archivos de logs relacionados con una aplicación | Identificar fuentes de información | 3/5 | 20 min |
| Examinar archivos grandes sin abrirlos completos | Analizar eficientemente | 3/5 | 20 min |
| Encontrar líneas que contengan errores específicos | Investigar incidentes | 3/5 | 25 min |
| Obtener únicamente las últimas entradas relevantes | Enfocarse en eventos recientes | 3/5 | 20 min |
| Crear un archivo con resultados filtrados | Compartir hallazgos | 3/5 | 20 min |

---

## Checkpoint

- [ ]  Encontré los logs correctos
- [ ]  Filtré información relevante
- [ ]  Revisé únicamente las secciones necesarias
- [ ]  Generé un resumen técnico
- [ ]  Guardé resultados en un archivo separado

---

## Qué deberías aprender

### Habilidades adquiridas

- Investigación básica
- Lectura eficiente de logs
- Filtrado de información

### Comandos utilizados

- less
- head
- tail
- grep
- find
- wc

### Errores comunes

- Leer archivos completos innecesariamente
- Buscar sin filtrar
- Analizar logs equivocados

### Buenas prácticas

- Filtrar antes de leer
- Documentar evidencia
- Conservar resultados