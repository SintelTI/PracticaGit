GIT - Control de versiones distribuido

Esta es una breve introducción y práctica de Git, elaborada por Sintel TI, Git es un sistema de control de versiones distribuido (DVCS).

Para los que han utilizado CVS o Subversion, hay conocimiento que ajustar, ya que CVS/Subversion funcionan de manera centralizada.

Git está diseñado para funcionar de manera distribuida. Esto significa que con Git no necesariamente existe un repositorio central al cuál llegarán todos los commits como en Subversion, ni que será el principal, ni el que resguarde siempre la última versión para todos los que hicieron "checkout" (en términos de Subversion, porque en git "checkout" es algo diferente). Con Git, cada "clon" realizado es todo un repositorio que puede funcionar independientemente, y nutrirse o nutrir a otros cuando sea necesario, esto aumenta la flexibilidad en cuanto a las opciones que tiene un equipo de trabajo para trabajar en conjunto, además de que existen más libertades.

Este esquema distribuido ha venido como anillo al dedo a proyectos de software libre, y no es casualidad, Git fue diseñado por Linus Torvalds, el padre del kernel de Linux, y lo diseñó precisamente por la necesidad que tuvo el equipo que mantiene el kernel. Con Git fácilmente pueden crearse forks de proyectos de SL y modificar lo que sea conveniente, y compartir entre forks cambios o nuevas funcionalidades de manera muy sencilla.

Instalación y configuración de Git
Es simple, sigue los pasos del tutorial de Github para tu sistema operativo, estos pasos también te guían para utilizar Git Bash y para configurar tus datos.

Para Windows: http://help.github.com/win-set-up-git/
Para Mac OS X: http://help.github.com/mac-set-up-git
Para Linux: http://help.github.com/linux-set-up-git

Git Bash
Git Bash es una aplicación que integra una shell (Bash) en el sistema operativo Windows. Si alguna vez has utilizado Linux o Unix, Bash es el intérprete de comandos en donde ejecutamos instrucciones o programas en el sistema operativo. Bash cuenta con el 'prompt' de signo de pesos ($), el cuál indica que la shell está a la espera de que ejecutemos comandos.

Eso es parecido a la shell de Windows (MS-DOS o Símbolo del Sistema), pero más poderoso y amigable.

Dentro de Git Bash, puedes ejecutar comandos simples, como crear directorios (mkdir), copiar (cp), mover (cp), cambiar de directorio (cd), listar archivos(ls) etc... Puedes leer más al respecto en: http://doc.ubuntu-es.org/Manual_de_bash

También puedes ver algunos comandos básicos y su descripción aquí: http://doc.ubuntu-es.org/Comandos_de_uso_frecuente

Creando un repositorio.
Una vez que tengas instalado Git en tu equipo, crear un repositorio es tan simple como posicionarte en dicho directorio y ejecutar 'git init'. Esto hará que Git comience a seguir todos los cambios que se hagan dentro del directorio, nuevos archivos, nuevas carpetas y nuevos archivos dentro de ellas. Git guarda una base de datos donde almacena todo el historial de cambios en la carpeta .git, debajo del directorio raíz (donde se hizo 'init').

Git Status
Uno de los comandos más frecuentes de Git es 'git status'. Al ejecutar este comando, git te informará:
 	* Los archivos que Git aún no sigue.
	* Los archivos que Git ya sigue y que fueron modificados.
	* Los archivos que Git sigue, fueron modificados y ya están agregados al siguiente commit.

Git Add.
Una vez que hemos hecho cambios, ya sea crear nuevos archivos o modificarlos, podemos agregarlos a un commit con el comando 'git add', agregando al final la ruta del/los archivo(s) involucrados en ese commit. Por ejemplo:

$ git add /ruta/al/archivo.png

Si por equivocación agregamos un archivo o una ruta que no queríamos en el commit, es posible revertir haciendo:

$ git reset HEAD /ruta/al/archivo.png

Git Checkout
Posiblemente hemos hecho cambios en nuestros archivos y aún no los agregamos con 'git add', pero estos cambios no nos han gustado del todo y queremos regresar el archivo a su estado anterior. Si no lo hemos agregado al siguiente commit con 'git add' es posible deshacer sus cambios realizando 'git checkout -- /ruta/a/una/clase.java

El comando 'git checkout' también tiene otra funcionalidad para manejo de 'branches', que se detallará más adelante.

Git Commit
El comando 'git commit', sirve para integrar un nuevo cambio al repositorio. Esto es muy parecido al 'commit' de Subversion o CVS, pero en definitiva no es lo mismo, ya que en Git el commit va hacia el repositorio local, recordemos que en Git no existe un único repositorio central, entonces, si queremos enviarlo a un repositorio remoto tenemos que efectuar 'git push', previamente habiendo registrado un repositorio remoto.

Git Revert
Podrá haber ocasiones en las que queremos revertir un cambio, pero git checkout o git reset no nos sirven porque el commit donde van dichos cambios ya fue realizado. Para estos casos usamos 'git revert' más el commit que deseamos revertir, por ejemplo 'git revert HEAD' revertirá los cambios del último commit. La manera en la que funciona 'git revert' es creando un commit nuevo para deshacer los cambios, eso hace que se reviertan de manera segura, ya que si este commit ya había sido enviado a un repositorio remoto, ahora habrá nuevo commit que revierta los cambios como si fuesen 'cambios nuevos', y no solamente desapareciendo o deshaciendo los cambios revertidos.

Git Clone.
Clonar un repositorio remoto con 'git clone' es algo similar a hacer "checkout" en Subversion o CVS, con la diferencia de que en Subversion se obtiene la última versión (HEAD) del código fuente (o solamente la de la revisión que se especifique), mientras que en Git se obtiene una copia completa del repositorio, incluyendo todo el historial de cambios que ha habido desde que inició el repositorio, desde el primer commit. Esta es una diferencia central entre Git y Subversion/CVS, y es una ventaja que permite que aún sin conexión a una red, cada persona de un equipo pueda continuar enviando commits, ya que estos van a su repositorio local, y en cuanto tenga una red disponible, enviar los cambios vía 'git push'.

Git Pull
Una vez que ya clonamos un repositorio, en el que quizá ya hicimos varios commits, necesitamos también obtener lo que los demás desarrolladores han enviado al repositorio remoto para estar actualizados, y esto lo hacemos con 'git pull', de esta manera descargaremos los cambios que tenga el repo remoto. Esto es muy parecido a 'svn update' en Subversion.

Git Branch
//TODO

Github.com
//TODO

Como verán, Git es una manera muy diferente y poderosa para trabajar en equipo, por lo que requiere estudio y práctica más allá de lo que conocen de Subversion o CVS.

Las dudas sobre esta práctica o sobre Git pueden enviarlas al TeamLab de SintelTI <http://sintelti.teamlab.com/>, o por correo a aramirez[at]sintelti[dot]com.

Alberto Ramírez. 
