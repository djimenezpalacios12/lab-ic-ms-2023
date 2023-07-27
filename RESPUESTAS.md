# Respuestas

Indica tu nombre a continuación:

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

Escribe respuestas de la etapa 1 acá

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

Se debe cambiar la dependencia de servicio, `depends_on`:

```
depends_on:
  - db
```
