# Mi recopilación de la guia oficial de GIT 


[Pro Git book](https://git-scm.com/book/es/v2)

## 2.1 Fundamentos de Git - Obteniendo un repositorio Git

### Para inicializar un nuevo repositorio local 

 `$ git init`  

De esta manera, se crea el direcotrio oculto *.git*, donde se almacenara toda la informacion del repositorio y su historial.  

### Clonando un repositorio existente

`$ git clone https://github.com/libgit2/libgit2`

## 2.2 Fundamentos de Git - Guardando cambios en el Repositorio

Mientras editas archivos, Git los ve como modificados, pues han sido cambiados desde su último commit. Luego preparas estos archivos modificados y finalmente confirmas todos los cambios preparados, y repites el ciclo.

![Ciclo de los archivos git](https://git-scm.com/book/en/v2/images/lifecycle.png)

### Revisando el Estado de tus Archivos

La herramienta principal para determinar qué archivos están en qué estado es el comando git status. Si ejecutas este comando inmediatamente después de clonar un repositorio, deberías ver algo como esto:

`$ git status
On branch master
nothing to commit, working directory clean`

### Rastrear Archivos Nuevos

Para comenzar a rastrear un archivo debes usar el comando git add. Para comenzar a rastrear el archivo README, puedes ejecutar lo siguiente:
`$ git add README`

### Estado Abreviado

`$ git status -s`

### Ignorar Archivos

Esta técnica es bastante útil a la hora de excluir archivos cambiantes en un repositorio, o tambien innecesarios para la construccion o ejecución del proyecto.
Un ejemplo de esto son la carpeta *node_modules/* cuando se trabaja con un protecto de npm.

[Ejemplo de una aplicacion node js, MERN ](https://github.com/santiquinterog/PageTour-ReactApp/blob/master/.gitignore)

- Otro ejemplo mas completo 

*ignora los archivos terminados en .a*

*.a

*pero no lib.a, aun cuando había ignorado los archivos terminados en .a en la línea anterior*

!lib.a

*ignora unicamente el archivo TODO de la raiz, no subdir/TODO*

/TODO

*ignora todos los archivos del directorio build/*

build/

*ignora doc/notes.txt, pero no este: doc/server/arch.txt*

doc/*.txt

*ignora todos los archivos .txt del directorio doc/*

doc/**/*.txt

### Ver los Cambios Preparados y No Preparados

Este comando compara lo que tienes en tu directorio de trabajo con lo que está en el área de preparación. El resultado te indica los cambios que has hecho pero que aun no has preparado


`$ git diff`

# Confirmar tus Cambios

Confirmar tus cambios significa enviarlos al stage, asi pues estos cambios seran rastreados y enviados al repositorio remoto.
Cada vez que se hace un commit sen guarda una instatanea del proyecto.

`$ git commit`

Este último comando es mas rápido y funcional.

`$ git commit -m "Story 182: Fix benchmarks for speed"`

**Sin embargo exitste una manera de saltar el area de preparación de git**

La opción -a es como si antes de hacer el commit ya hubiesemos hecho el git add.

`$ git commit -a -m 'added new benchmarks'`

Otra cosa que puedas querer hacer es mantener el archivo en tu directorio de trabajo pero eliminarlo del área de preparación. En otras palabras, quisieras mantener el archivo en tu disco duro pero sin que Git lo siga rastreando. Esto puede ser particularmente útil si olvidaste añadir algo en tu archivo .gitignore y lo preparaste accidentalmente, algo como un gran archivo de trazas a un montón de archivos compilados .a. Para hacerlo, utiliza la opción --cached:

`$ git rm --cached README`

# Ramas

## Ramas remotas

### Actualizar ramas remotas

`git remote update origin --prune`

## Activar la autocorrecion en git bash

`git config --global help.autoCorrect 1`



