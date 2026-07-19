# Día 2 — Organización de documentación y backups

## Contexto

El equipo de desarrollo envió documentación dispersa y copias de seguridad antiguas.

Necesitan una estructura organizada para poder trabajar.

---

## Objetivos del día

- Reorganizar información.
- Mover archivos a ubicaciones adecuadas.
- Mantener una estructura consistente.

---

## Tareas

| Tarea | Objetivo | Dificultad | Tiempo |
| --- | --- | --- | --- |
| Crear árbol de directorios para documentación, backups y archivos temporales | Estandarizar almacenamiento | 2/5 | 20 min |
| Copiar documentación a la nueva estructura | Preservar originales | 2/5 | 15 min |
| Reubicar backups antiguos | Mejorar organización | 2/5 | 20 min |
| Renombrar archivos siguiendo una convención definida por el equipo | Normalizar nomenclatura | 2/5 | 20 min |
| Verificar que todos los archivos estén en la ubicación correcta | Evitar pérdidas | 3/5 | 20 min |

---

## Checkpoint

- [X]  Creé la estructura requerida
- [X]  Copié archivos correctamente
- [X]  Moví archivos sin perder información
- [X]  Renombré siguiendo el estándar
- [X]  Verifiqué resultados

---

## Qué deberías aprender

### Habilidades adquiridas

- Organización de información
- Gestión de archivos
- Validación de cambios

### Comandos utilizados

- cp
- mv
- ls
- tree

### Errores comunes

- Sobrescribir archivos accidentalmente
- Mover archivos a rutas equivocadas
- Trabajar sin verificar resultados

### Buenas prácticas

- Verificar antes y después de cada movimiento
- Mantener convenciones de nombres
- Evitar estructuras caóticas

---

## Estado actual del servidor

El servidor fue preparado para simular un entorno de trabajo con documentación y respaldos heredados.

Estado inicial:

- Existen los directorios `Downloads`, `Desktop`, `old_docs` y `workspace` dentro del HOME del usuario `sysadmin`.
- La documentación y los archivos de respaldo se encuentran distribuidos entre `Downloads` y `old_docs`.
- `workspace` contiene archivos de trabajo que no forman parte de la documentación heredada.
- Se instaló la utilidad `tree` para facilitar la visualización de la estructura de directorios.
- El sistema se encuentra actualizado mediante `apt update` y `apt upgrade`.

<img width="889" height="572" alt="tree-dia2" src="https://github.com/user-attachments/assets/652c765b-b5dd-415b-aedc-d4bc2ae53e7f" />
