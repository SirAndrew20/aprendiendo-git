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

_doc/\*.txt_

ignorar todos los archivos terminados en .txt dentro de la carpeta doc
y también en sus subcarpetas:

_doc/\**/*.txt_

## Clonar Repositorio

para ello colocamos el comando git clone u la url del repositorio ejemplo:

**git clone https://github.com/usuario/repositorio.git**

## Ramas 

Nos permite aislar una nueva funcionalidad en nuestro código que después podremos añadir a la versión principal, es como si fueran pequeñas realidades simultaneas de nuestros proyectos, esto nos permite poder realizar figure. para ello escribimos los siguientes comandos

**crear rama**

_git branch nombre-rama_

 **cambiar de rama:**

_git checkout nombre-rama_

**para crear y cambiar de Rama de una vez**
_git checkout -b nombre de la rama_

**crear una rama y cambiarte a ella**

_git checkout -b crea esa rama_

 **eliminar rama**

_git branch -d nombre-rama_

**eliminar ramas remotas**

_git push origin --delete nombre-rama_

**eliminar rama (forzado)**

_git branch -D nombre-rama_

 **listar todas las ramas del repositorio**

_git branch_

 **lista ramas no fusionadas a la rama actual**

_git branch --no-merged_

 **lista ramas fusionadas a la rama actual**

_git branch --merged_

 **rebasar ramas:**

_git checkout rama-secundaria_

_git rebase rama-principal_

y para agregatr esa rama al remoto colocamos git push -u origin nombre de la rama