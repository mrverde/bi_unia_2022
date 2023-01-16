# Estructura del curso

## __1) ¿Qué es GIT? ¿Para qué sirve? ¿Cómo se maneja...?__

GIT es un sistema de control de versiones. 

Un sistema de control de versiones registra los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo y permite recuperar versiones específicas y ver quien ha hecho las modificaciones, cuándo se ha modificado y recuperar los archivos fácilmente si se borran.

GIT es un sistema de control de versiones desarrollado por Linus Torvalds, el creador del sistema operativo Linux en el año 2005. Es un sistema rápido, eficiente con grandes proyectos e implemente un sistema de ramificación orientado al desarrollo no lineal.

GIT funciona tomando "una foto" de cada uno de los archivos del proyecto en un momento concreto, almacenando los archivos nuevos y dejando los antiguos si no se han modificado.

![Cómo se gestionan los cambios](/GIT/recursos/001_esquema_cambios_git.png)

Cuando se hace algún cambio GIT genera un código en formato SHA-1 en función del contenido del proyecto en ese momento, de esa manera si hay alguna modificación en el proyecto este número cambiará y podremos detectar que existen modificaciones en la versión. La apariencia de uno este código es la siguiente:

__24b9da6552252987aa493b52f8696cd6d3b00373__

### Flujo de trabajo

GIT tiene 3 estados en los que se pueden encontrar los archivos:

1) Confirmado (committed) - Significa que los datos están alamacenados de manera segura en tu base de datos local

2) Modificado (modified) - Se ha modificado un archivo pero no se ha confirmado en la base de datos 

3) Preparado (staged) - Se ha marcado el archivo modificado para que se suba en la próxima confirmación. 

![Flujo de trabajo](/GIT/recursos/002_flujo_trabajo.png)


El flujo de trabajo básico es:

1) Modificas una serie de archivos en tu directorio de trabajo.

2) Preparas los archivos, añadiéndolos a tu área de preparación.

3) Confirmas los cambios, lo que toma los archivos tal y como están en el área de preparación y almacena esa copia instantánea de manera permanente en tu directorio de Git.

Si una versión concreta de un archivo está en el directorio de Git, se considera confirmada (committed). Si ha sufrido cambios desde que se obtuvo del repositorio y ha sido añadida al área de preparación, está preparada (staged). Y si ha sufrido cambios desde que se obtuvo del repositorio, pero no se ha preparado, está modificada (modified). 


### ¿Cómo se maneja GIT?

Existen programas que aportan una interfaz visual a GIT, pero la única forma en la que podremos hacer uso de todas las opciones y posibilidades de GIT es a través de la línea de comandos.

### Instalación de GIT

#### __Linux__

En función de que usemos yum:

    $ yum install git

ó apt

    $ apt install git

#### __OSX__

Se puede descargar en la web https://git-scm.com/download/mac

#### __Windows__

Se puede descargar en la web https://git-scm.com/download/win

### Primeros pasos

En primer lugar hay que hacer una serie de pasos de configuración la primera vez que se ejecuta GIT. Esta configuración se guarda en un archivo __gitconfig__ y puede funcionar a 3 niveles: sistema (--system), usuario (--global) y repositorio. 

Lo básico es poner el nombre de usuario, el mail y el nombre de la rama por defecto. Esto se hace con los comandos:

    $ git config --global user.name "John Doe"

    $ git config --global user.email johndoe@example.com

    $ git config --global init.defaultBranch master

Para ver la configuración podemos usar el comando:

    $ git config --list

Para ver la ayuda de un comando podemos usar:

    $ git push --help

Para iniciar un repositorio en una carpeta determinada usaremos el comando

    $ git init

Este comando crea un subdirectorio denominado .git donde se guardarán todos los archivos. 

Para añadir que archivos se van a controlar y añadirse a staging se usa el comando:

    git add *

Este comando añade todos los archivos del directorio. Podremos especificar cuales de ellos en concreto queremos añadir de la siguiente forma:

    git add graficos/resumen.md

Para confirmar los cambios utilizamos el comando:

    $ git commit -m "Mi primer commit"

Lo que viene a partir de la -m es el nombre que tendrá nuestro commit.

## __3) Repositorios online: GITHub, Azure, Gitlab, Bitbucket...__

Lo interesante de los repositorios es que pueden ser subidos a diferentes plataformas de internet donde los usuarios pueden consultarlos.

De este tipo la plataforma más usada es GitHub.

![Perfil GitHub](/GIT/recursos/003_perfil_github.png)

En GitHub podemos crear repositorios, si son públicos consultarlos, subir modificaciones, issues, pull request, crear un fork, etc.

Para crear un repositorio en primer lugar nos logamos, vamos al apartado repositorio y pulsamos en el botón verde new.

![Nuevo repo](/GIT/recursos/004_nuevo_repo.png)

Nos aparecerá la pantalla de creación de repositorio

![Crear repo](/GIT/recursos/005_crear_repo.png)

En esta pantalla escogeremos el nombre del repositorio, el propietario, podremos añadir una descripción, seleccionar si es un repositorio público o privado y seleccionar si queremos añadir un archivo readme, un .gitignore y la licencia del repositorio. 

Para crear el repositorio pinchamos en el botón verde crear repositorio y nos aparecerá la pantalla de repositorio nuevo:

![Nuevo repo](/GIT/recursos/006_pagina_base_repo.png)

Aquí nos aparecen diferentes opciones básicas para crear nuestro repositorio en nuestro disco duro en función de si ya existe o no.

#### Clonar repositorio

Podemos descargarnos el repositorio yendo al mismo y pinchando en el botón verde <> Code

![Clonar repo](/GIT/recursos/007_clone_repository.png)

Ahí aparecen diferentes opciones. HTTPS y SSH son diferentes maneras de autenticación. Debemos copiar la dirección web que nos aparece y ejecutarla en consola con la instrucción clone de la siguiente forma:

    $ git clone https://github.com/mrverde/bi_unia_2022.git

## __4) VSCode - Extensiones interesantes que instalar: gitlens y git graph__

Visual Studio Code es un IDE desarrollado por Microsoft que puede usarse en Windows, Linux, macOS y web. Tiene integradas muchísimas funciones: control de git, resaltado de sintaxis, atajos...

Es un editor muy completo que además nos permite instalar extensiones que nos permitirán trabajar con diferentes lenguajes de programación y nos facilitarán la integración con servicios, resaltado de sintaxis, creación de snippets, autocompletado de código, depuración, etc.

Podremos descargar visual studio code desde su web https://code.visualstudio.com/

Para trabajar con GitHub se recomienda la instalación de las extensiones [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) y [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens).

## __5) Trabajando con GIT: Comandos básicos__

    $ git pull

Descarga los últimos cambios del repositorio.

    $ git add nombre_del_archivo.txt

Añade los archivos especificados a staging. Añade todas las modificaciones si en vez de un nombre de archivo ponemos .

    $ git commit -m "Mensaje git"

Guarda permanentemente los cambios existentes en el staging.

    $ git push

Envía los cambios realizados al repositorio

    $ git diff

Muestra las diferencias en el archivo que no ha sido metido en staged.

    $ git diff -staged

Muestra las diferencias entre el contenido del archivo que hay en staged y la última versión.

    $ git reset 73bbca4299432978a

Deshace los commits hechos después del commit especificado y preserva los cambios locales.

    $ git reset --hard 73bbca4299432978a

Descarta todos los cambios realizados y va al commit especificado.

    $ git status

Lista todos los archivos que pueden ser comiteados.

    $ git rm archivo.txt

Elimina un archivo del directorio de trabajo y guarda el borrado en el staging.

    $ git log

Muestra el historial de versiones en la rama activa.

    $ git stash

Guarda de forma temporal las modificaciones de archivo.

    $ git stash pop

Recupera los archivos del stash.

    $ git stash drop

Elimina los archivos del stash.


## __6) Git branches__

Una rama es una división en un camino de desarrollo diferente y paralelo de la evolución del código. Se usa para por ejemplo añadir nuevas funcionalidades, probar nuevos elementos, arreglar un error, etc. 

Cuando se trabaja dentro de un equipo de muchas personas son fundamentales, pues de esta manera pueden trabajar múltiples personas de forma concurrente en la evolución de un mismo código informático.

La forma de trabajar es la siguiente: 

Existe una rama principal denominada master, main, etc. Entonces, cada desarrollador suele crear una rama donde implementará las funcionalidades que tiene asignadas. Una vez haya acabado el desarrollo, los cambios realizados se implementan en la rama principal y la rama usada para los cambios se borra.

    $ git branch

Lista todas las ramas existentes

    $ git branch mi_nueva_rama

Crea una nueva rama

    $ git checkout mi_nueva_rama

Para cambiar de rama

    $ git checkout -b mi_otra_nueva_rama

Crea una nueva rama y automáticamente cambia a ella

    $ git branch -d mi_nueva_rama

Para borrar la rama

    $ git merge mi_otra_nueva_rama

Para unificar la rama especificada en la rama activa

En la unificación puede ocurrir que un mismo fragmento de código haya cambiado en las dos ramas a la vez. En este caso se produce lo que se denomina un conflicto. En este caso los cambios no se hacen automáticamente y GIT preguntará al usuario como ha de actuar: quedándose con el contenido de la rama activa, con el de la rama a unificar o dándole al usuario la oportunidad de reescribir el código.

## __7) Back to the Future__

GIT nos permite también volver a cualquier commit que hayamos hecho. Podremos a su ver crear una nueva rama a partir del mismo.

    $ git checkout 2c77009f223affb0fa60132cf79d66c4785d0363

Cambia la rama activa al commit seleccionado

## __8) Ejercicios__

1. Crear una cuenta en GitHub y crear un repositorio llamado mecofin_2023_fundamentos_bi

2. Crear un archivo README.md donde pondréis los comandos utilizados en el ejercicio

3. Hacer un commit con los cambios

4. Crear un archivo llamado documento_privado.md y una carpeta denominada carpeta_privada.md y hacer que sean ignorados por GIT. 

5. Crear un archivo denominado fichero1.txt y añadirle texto.

6. Hacer un commit con los cambios.

7. Crear una nueva rama denominada nueva_rama

8. Crear un nuevo archivo denominado fichero2.txt y añadirle texto.

9. Mergear nueva_rama a master

10. En la rama nueva_rama, cambiar el contenido de fichero2.txt y volver a mergearlo a master

11. Borrar la rama nueva_rama

12. Crear un nuevo equipo denominado mecofin_2023 y añadir a todos los compañeros de clase.

## Para saber más

* https://git-scm.com/book/es/v2

* https://es.wikipedia.org/wiki/Git

* https://www.youtube.com/watch?v=PW_A-lOpVV0

* https://www.youtube.com/watch?v=VdGzPZ31ts8