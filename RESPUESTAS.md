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

-   Ya que la funcion del docker-compose es adminitrar multiples contenedores, se puede observar que dentro de este existe un servicio llamado `movies-api`. este servicio buscar dentro de movies-api un archivo dockerfile para la imagen.

¿Qué crees que hace el atributo context debajo de build (está en la linea 6 del archivo docker-compose.yml)?

-   Buscara dentro del directorio en `context` un archivo Dockerfile para construir una imagen del contenedor.

## ETAPA 4

Compara los archivos `Dockerfile` de `movies-api` y `movies-front`.

Compara el atributo `build` del servicio `movies-api` con el de `movies-front`.

-   ¿Cuál es la diferencia?
    -   Lo mas evidente que el archivo dockerfile de movies-api posee 2 etapas (build y deploy) además de usar imagenes diferentes. en particular, movies-api crea ademas un empaquetamiendo en una imagen mas ligera.
-   ¿Qué pasa si los dejas iguales?
    -   Hablando en resultados finales, ambas configuraciones crean imagenes capaz de ejecutar una aplicacion en su respectiva tecnología, manteniedo por supuesto los archivos por separados en sus respectivos contextos para crear ambas imágenes.
