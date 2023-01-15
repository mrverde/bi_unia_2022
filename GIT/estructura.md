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

## __3) Repositorios online: GITHub, Azure, Gitlab, Bitbucket...__

Que son, como se muestra un repositorio, cómo copio un repositorio, cómo me copio un repositorio. Archivos de interés en un repositorio (gitignore, readme.md...)

Abrir una cuenta en GitHub.

## __4) VSCode - Extensiones interesantes que instalar: gitlens y git graph__


## __5) Trabajando con GIT: Comandos básicos__

Git pull, git push, git commit -m "Mensaje del GIT"

## __6) Git branches__

Qué es una rama, cómo se crea, Merges y conflictos. Borrar ramas. Flujo de trabajo normal en una empresa.

## __7) Back to the Future__

Cómo volver a un commit anterior, git pop


## __8) Reflexiones: Portfolio, ver evolucionar el código y lo que sabemos hacer__

Ejercicio

Crear una cuenta en GitHub para la asignatura. Copiar la base del repositorio de pandas del ejercicio del día siguiente.

## Para saber más

* https://git-scm.com/book/es/v2

* https://es.wikipedia.org/wiki/Git