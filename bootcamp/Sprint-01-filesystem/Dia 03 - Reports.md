# Reporte Día 3

## Resumen
Durante la jornada de hoy, se trabajó sobre la estructura de los logs, tanto del sistema como de aplicaciones. Se buscó mejorar y
optimizar la investigación con distintos comandos y sus combinaciones posibles, además de conocer datos claves que sirven a la hora
de buscar errores a nivel de sistema en Linux.

## Desarrollo
Como primera medida, al desconocer en absoluto el formato de los logs del sistema o las aplicaciones, se comenzó a investigar sobre
la estructura de los mismos con comandos simples. Por ejemplo: se ejecutó `cat` junto con `less` mendiante un `pipe` sobre los distintos ficheros que se encuentran en la
ruta `/opt/labcorp/app/logs/` para poder visualizar las primeras y últimas líneas de los archivos y verificar la estructura de los mismos.

Investigando comandos recomendados para el ejercicio, la metodología anterior se reemplazó por `head` y por `tail`, comandos que realizan lo mismo
sin necesidad de ejecutar un `pipe`.

Se detectó, por ejemplo, que el archivo `application.log`, respeta la siguiente estructura:
|date|type|ID|process type?|
|----|----|--|-------------|
|2026-07-18 00:00:01|INFO|[ReqID-00001]|User request processed in 11 ms|

Luego de revisar algunas cuantas líneas desplazándose por el documento, no se encontraron datos distintos del de más arriba.

Se siguió investigando sobre los demás logs de la misma manera con el mismo resultado.

Finalmente, no se encontró a mano información relevante en los demás logs ubicados en las rutas de `/opt/labcorp/auth` y `/opt/labcorp/reports`.

Se avanzó consultando documentación sobre comandos y combinaciones posibles para hacer más fácil la investigación y diagnóstico.

Como conclusión sobre el ejericio, 


## Problemas encontrados
El primero problema que se presentó está relacionado al desconocimiento del formato de los logs tanto de las aplicaciones como de
los workers, aplicaciones, etc. junto con el desconocimiento de la eficientización de las herramientas de bash.

Por ejemplo, a la hora de buscar un error o un alerta en los logs, se probó primero con `cat /opt/labcorp/app/application.log | grep 'warn'`
o también  `cat /opt/labcorp/app/application.log | grep 'error'`. Esto obligaba a hacer un `grep` por cada archivo, resultando tedioso
y poco eficiente la búsqueda de errores dentro de los logs.

## Troubleshooting
Con una mínima investigación internet (sólo buscando "logs structure in linux") apareció la primer pista: se debe buscar como "WARN" 9en
mayúsculas en los logs.

Dado que se conocía previamente que `grep` se utiliza para buscar texto dentro de los archivos sumado a un poco de lectura sobre el manual
de la utilidad, se intentó realizar una búsqueda case-**insensitive**. Con el primer resultado positivo, se investigó cómo hacer la búsqueda
más eficiente, evitando ir archivo por archivo ejecutando `cat` junto con `grep`.

Pensando de manera lógica, se buscó hacer un `for loop` escrito en bash para la ubicación `/opt/labcorp/`, de todos los archivos dentro, correr
el comando `grep` con una búsqueda case-insensitive. El resultado final de esto, fue:
```bash
for file in $(find .); do
  grep -IH 'warn' "$i"
done
```

Luego de un poco más de investigación sobre la mejora de la búsqueda, en documentación de internet se halló que se puede hacer una búsqueda eficiente
con `find` y `grep` sin un for loop. Se llegó al siguiente resultado:
```bash
find . -type f -exec grep -iH 'warn' {} +
```

## Lecciones aprendidas

...

## Evidencias

...
