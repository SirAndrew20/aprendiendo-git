# Curso de Git y GitHub

### Flujo del git al gitHub

para poder pasar a craquear codigo git tenemos que pasar la carpeta o el directorio lo asemos usando el comando **git add .** para añadir todos los archivos _git add_ mas el nombre del **archivo** solo se agregara ese.

ahora para oficializar un cambio, es decir dejar un registro en el repositorio colocamos el comando **git commit -m "Mensaje descriptivo del cambio"** y finalmente para mandarlo al remoto al gitHub usamos el comando **git push**

Si queremos extraer un archivo modificado de gitHub usamos el comando **git pull**

nota: Cuando es primera vez tenemos que colocar los siguiente: **git remote add origin https://github.com/usuario/repositorio.git** para añadirlo y
la primera vez que vinculamos el repositorio remoto con el local
**git push -u origin main**.

despues solo colocamos git add y gid push

## Solicitar ayuda

Desde la Terminal:

Colocamos:

git el nombre del comando y -h,

Desde la red:

Colocamos git help nombre del comando


## Crear Archivo gitignore

Para ello creamos un archivo con **touch** y luego colocamos el comando **.gitignore**. En este archivo se va a especificar cuales van a ser los documentos o tipos de archivos que seran ignorados

## Ignorar Archivos
debemos colocar dentro de gitignore los siguinetes comandos:

para ignorar archivo:

archivo.ext

para ignorar carpeta carpeta:

_/archivo_desde_raiz.ext_

ignorar todos los archivos que terminen en .log:

_\*.log_

excepto production.log:

_!production.log_

ignorar los archivos terminados en .txt dentro de la carpeta doc,
pero no en sus subcarpetas:

_doc/*.txt_

ignorar todos los archivos terminados en .txt dentro de la carpeta doc
y también en sus subcarpetas:

_doc/**/*.txt_

## Solicitar ayuda

Desde la Terminal:

Colocamos:

git el nombre del comando y -h,

Desde la red:

Colocamos git help nombre del comando

## Ignorar Archivos
