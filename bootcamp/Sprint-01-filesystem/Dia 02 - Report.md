# Reporte Día 2

## Resumen
Durante esta jornada se trabajó sobre información, documentación y backups desorganizados en el servidor.
Esto me permitirá aprender a **reorganizar la información**, **mover archivos a ubicaciones adecuadas** y **mantener una estructura consistente**


## Desarrollo
Como primer paso, interesa visualizar la información que se debe organizar de manera general. Para esto, se usó la utilidad `tree`, que me
permite una rápida visualización de los archivos en una ubicación elegida (en este caso, en `/home/sysadmin/`)

Una vez hecho el análisis de los archivos que existen en el servidor y qué tipo de archivos son, se creó, dentro de `workspace` un directorio
para documentación (`docs`) y un directorio para backups (`backups`).

Con el comando `cp`, se copiaron los archivos desde las distintas ubicaciones a sus destinos corresopndientes. Por ejemplo:
```bash
# Se encontraban algunos archivos de backup dentro de ~/old_docs/
# Para esto, se utilizó el comando "cp" de la siguiente manera

sysadmin@ubuntu-sv:~$ cp ./old_docs/backup* ./workspace/backups
```

## Problemas encontrados
Falta de claridad entre algunos archivos disponibles en el servidor a la hora de organizarlos. Por ejemplo, `w11.iso` y `ubuntu-server.iso`
dentro de `Desktop/` o `tmp.log` y `config.old` dentro de `old_docs`.

## Troubleshooting
Se define, respecto a los archivos problemáticos que en un caso real, se debería lograr obtener más información al respecto de los mismos.

No se logró identificar el propóstio del archivo `tmp.log` , por lo que se decidió dejarlo donde está hasta obtener más información.

En el caso de `config.old`, se debería consultar a algún responsable si ese archivo se dejó como documentación de un estado anterior
o bien es una configuración legacy que no se volverá a utilizar, pero se requiere guardar a modo de documentación o histórico.

## Lecciones aprendidas
Utilización del comando `tree` para poder visualizar en formato de árbol la estructura de carpetas.

Debido a que la TTY de Ubuntu Server (y las TTY en general) no presentan la posibilidad de "scrollear" el histórico de las entradas en consola,
se combinó el comando `tree` junto con `less` (mediante un `pipe`) para facilitar la visualización completa del árbol del directorio elegido.

Cuando se tienen archivos con nombres consecutivos o parecidos, como, por ejemplo, `documentacion1.pdf`, `documentacion2.pdf`, etc.
es de gran utilidad usar el operador "comodin" (`*`) para seleccionar todos los archivos que se sepa que tienen la misma nomenclatura
y no se desea ingrsear el comando archivo por archivo.

Asimismo, es importante aclarar que se debe estar muy seguro a la hora de usar el patrón comodín, ya que mal utilizado, puede provocar que se 
seleccionen más archivos de los esperados, aumentando el riesgo de copiar, mover o eliminar información incorrecta.


## Evidencias

...
