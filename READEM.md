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

y para agregatr esa rama al remoto colocamos git push -u origin nombre de la ramahtml

## Fusionar ramas

Une dos ramas. Para hacer una fusión necesitamos:

Situarnos en la rama que se quedará con el contenido fusionado.
Fusionar.
Cuando se fusionan ramas se pueden dar 2 resultados diferentes:

Fast-Forward: La fusión se hace automática, no hay conflictos por resolver.

Manual Merge: La fusión hay que hacerla manual, para resolver conflictos de duplicación de contenido. Esto implica modificar el documento en cuestion y borrar el contenido que no queremos que se quede o agregar contenido que queremos que se quede

- nos cambiamos a la rama principal que quedará de la fusión

**git checkout rama-principal**

- ejecutamos el comando merge con la rama secundaria a fusionar

**git merge rama-secundaria**

## Cambios al Commit

Puede que nos pase que se nos haya olvidado escribir unas lineas de codigo y eso implica hacer otro _commit_ para guardarlo, pero nosotros podemos hacer cambios al ultimo _commit_. para ello tenemos estos codigos.

- sin editar el mensaje del último commit

**git commit --amend --no-edit** : Se usa para no editar el mensaje

- editando el mensaje del último commit

git commit --amend -m "nuevo mensaje para el último commit" : Se usa para agregar un nuevo mensaje

- eliminar el último commit

**git reset --hard HEAD~1** Para eliinar el ultimo commit

- **git log**: Nos permite ver los cambios que hemos hecho en el commit, si queremos seguir viendo mas commit modificados le precionamos _enter_ y si queremos salirnos de esa lista escribimos **q**, esto nos permitira obtener el **id** para movernos al commit que queramos.

y si queremos ver todos los cambios en una sola linea colocamos el comando **git log --oneline**

- **git checkout id-commit** : Nos permite movernos al commit con el id especificado

Nota: Hay que tener cuidado de hacer siempre push, por que podriamos dañar un archivo

## Registro del Historial

Accedemos a el por medio del comando **git log**, que nos permite conocer todo el historial de un proyecto, con la información de la fecha, el autor y id de cada cambio.

diferentes comandos Log:

git log

- git log --oneline : muestra en una sola línea por cambio

- git log > commits.txt : guarda el log en la ruta y archivo que especifiquemos 

- git log --pretty=format:"%h - %an, %ar : %s" : muestra el historial con el formato que indicamos

- git log -n : cambiamos la n por cualquier número entero y mostrará los n cambios recientes

- git log --after="2019-07-07 00:00:00" : muestra los cambios realizados después de la fecha especificada

- git log --before="2019-07-08 00:00:00": muestra los cambios realizados antes de la fecha especificada

- git log --after="2019-07-07 00:00:00" --before="2019-07-08 00:00:00" : muestra los cambios realizados en el rango de fecha especificado

- git log --oneline --graph --all : muestra una gráfica del historial de cambios, rama y fusiones
muestra todo el registro de acciones del log incluyendo inserciones, cambios, eliminaciones, fusiones, etc.

- git reflog

- git diff: diferencias entre el Working Directory y el Staging Area

## Reseteo del Historial

Podemos eliminar el historial de cambios del proyecto hacia adelante con respecto de un punto de referencia.

nos muestra el listado de archivos nuevos (untracked), borrados o editados
git status

* borra HEAD
git reset --soft

* borra HEAD y Staging
git reset --mixed

* borra todo: HEAD, Staging y Working Directory
git reset --hard

* deshace todos los cambios después del commit indicado, preservando los cambios localmente

git reset id-commit

* desecha todo el historial y regresa al commit especificado

git reset --hard id-commit

## Resetear un repositorio

Si en algún momento tienes la necesidad de resetear el historial de cambios de un repositorio para que quede como si lo acabarás de crear ejecuta esta serie de comandos:

cd carpeta-repositorio
mv .git/config ~/saved_git_config
rm -rf .git
git init
git branch -M main
git add .
git commit -m "Commit inicial"
mv ~/saved_git_config .git/config
git push --force origin main

## Remotos