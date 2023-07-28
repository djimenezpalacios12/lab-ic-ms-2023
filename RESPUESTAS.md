# Respuestas

Indica tu nombre a continuación:

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

Escribe respuestas de la etapa 1 acá

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?

-   Los archivos con el prefijo `create` crean las tablas
-   Los archivos con el prefijo `add` agregan datos a las tablas.

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?

-   `flyway`

¿Cuál es el comando que se ejecuta en el servicio declarado?

-   `-locations=filesystem:/flyway/sql -connectRetries=60 migrate`

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

Se debe cambiar la dependencia de servicio, `depends_on`:

```
depends_on:
  - db
```

## ETAPA 3

Revisa el archivo `movies-api/Dockerfile`.

¿Qué te llama la atención?

-   Hay una etapa de building (compilacion) y despliegue (deployment). Cada una corresponde a una imagen distinta.

Revisa el archivo `docker-compose.yml`.

¿Cómo se relacionan el archivo `docker-compose.yml` y el archivo `movies-api/Dockerfile`?

-
