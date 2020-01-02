## Información que cura sobre Vue JS

### Prototipado instantaneo

VueCLI permite un rápido prototipado de componentes, sin necesidad de generar un proyecto completo [Prototipado instantaneo](https://cli.vuejs.org/guide/prototyping.html)

Ejecuta los prototipos de ejemplo dentro de cada carpeta con el comando `$ vue serve App.vue`, por default la herramienta escucha en el puerto 8080.

- Algunos ejemplos utilizan [pug](https://pugjs.org/api/getting-started.html), de ser necesario instala los paquetes necesarion

```
$ yarn add pug pug-plain-loader
```

### Funciones de renderizado

VueJS recomienda utilizar plantillas, pero hay algunos casos en los que es necesario utilizar todo el poder prográmatico que ofrece javascript, ahi en donde entran en acción las funciones de renderizado.

### Componentes controlados

Los componentes controlados son utiles cuando se requiere abstraer la lógica interna de un componente para que este pueda ser aprovechado 