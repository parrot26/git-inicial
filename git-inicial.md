![Imagen.](/image/git-logo.png "Imagen.")

# 
# _GIT - Inicial_
 
### Comenzando 🚀
_[Git](https://es.wikipedia.org/wiki/Git) es un sistema de control de versión distribuida de código abierto y gratuito diseñado por por [Linus Torvalds](https://es.wikipedia.org/wiki/Linus_Torvalds) para manejar todo tipo de proyectos._ 

_En su página oficial [Git](https://git-scm.com/) podemos encontrar su [Descarga](https://git-scm.com/downloads), [Instalación](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) y mucho más._

# 
### Pre-requisitos 📋
_Ganas de aprender_

# 
### Los tres estados 📋

_Git tiene tres estados principales: **Modificado** (modified), **Preparado**(staged) y **Confirmado** (committed)._

_**Modificado** significa que el archivo fue modificado pero todavía no está confirmado a la base de datos._ 

_**Preparado** significa que se marcó un archivo modificado en su actual versión para la próxima confirmación._

_**Confirmado** significa que los datos están en tu base de datos local._ 

_En un ambiente local el flujo sería:_

_**Working Directory**  > **Staging** > **Local Repository**_


# 
### Configuración básica  ⚙️
 
_Después de instalar **Git** es importante configurar tu nombre de usuario y tu dirección de correo electrónico._ 

_Esto no es obligatorio para su funcionamiento pero las confirmaciones (commits) de cambios que hagas quedan registrados con esta información y es muy útil cuando se trabaja con varias personas._

`git config --global user.name "[tu-nombre]"`  # se configura tu nombre de usuario.

`git config --global  user.email "[tuemail@ejemplo.com]"`  # se configura tu correo.

`git config --list ` # lista la configuración actual de git.

_Para personalizar **Git** se puede consultar con el comando `man git-config ` o directamente en su [documentación oficial](https://git-scm.com/docs/git-config.html)_

# 
### Comandos 📋

_Para conocer la versión de **Git** que acabamos de instalar utilizamos `git --version `

```ssh
$git --version
git version 2.25.1 
```
###### _En este momento la versión utilizada para estos ejemplos es la **2.25.1**_

_Con el comando `git --help `se puede obtener una lista de comandos más utilizados._

_Una vez ejecutado sale algo parecido a:_

```ssh
git --help
uso: git [--version] [--help] [-C <ruta>] [-c <nombre>=<valor>]
           [--exec-path[=<ruta>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<ruta>] [--work-tree=<ruta>] [--namespace=<nombre>]
           <comando> [<args>]

Estos son comandos comunes de Git usados en varias situaciones:

comienza un área de trabajo (ver también: git help tutorial)
   clone             Clona un repositorio dentro de un nuevo directorio
   init              Crea un repositorio de Git vacío o reinicia el que ya existe

trabaja en los cambios actuales (ver también: git help everyday)
   add               Agrega contenido de carpetas al índice
   mv                Mueve o cambia el nombre a archivos, directorios o enlaces simbólicos
   restore           Restaurar archivos de árboles de trabajo
   rm                Borra archivos del árbol de trabajo y del índice
   sparse-checkout   Inicializa y modifica el sparse-checkout

examina el historial y el estado (ver también: git help revisions)
   bisect            Use la búsqueda binaria para encontrar el commit que introdujo el bug
   diff              Muestra los cambios entre commits, commit y árbol de trabajo, etc
   grep              Imprime las líneas que concuerdan con el patron
   log               Muestra los logs de los commits
   show              Muestra varios tipos de objetos
   status            Muestra el estado del árbol de trabajo

crece, marca y ajusta tu historial común
   branch            Lista, crea, o borra ramas
   commit            Graba los cambios en tu repositorio
   merge             Junta dos o más historiales de desarrollo juntos
   rebase            Vuelve a aplicar commits en la punta de otra rama
   reset             Reinicia el HEAD actual a un estado especifico
   switch            Cambiar branches
   tag               Crea, lista, borra o verifica un tag de objeto firmado con GPG

colabora (mira también: git help workflows)
   fetch             Descarga objetos y referencias de otro repositorio
   pull              Realiza un fetch e integra con otro repositorio o rama local
   push              Actualiza referencias remotas junto con sus objetos asociados

'git help -a' y 'git help -g' listan los subcomandos disponibles y algunas
guías de concepto. Consulte 'git help <command>' o 'git help <concepto>'
para leer sobre un subcomando o concepto específico.
Mira 'git help git' para una vista general del sistema.

```

###### _Al final de la salida de la ejecución del comando se puede observar más formas de obtener información detallada._

# 
### Hora de meter mano y utilizar los comandos básicos 🛠️


* _Creamos el directorio **test** en el directorio vamos a usar, por ejemplo: **~/Documentos/IT/GIT/test**._

```ssh
$mkdir test
$cd test/
```
* _Agregamos el archivo **ejemplo.txt** y dentro un comentario._

```ssh
$nano ejemplo.txt
$cat ejemplo.txt 
Hola, esto es un ejemplo
```

* _Ejecutando `git init ` creamos el repositorio para que sea manejado por **Git**._

```ssh
$git init
Inicializado repositorio Git vacío en ~/Documentos/IT/GIT/test/.git/
```
* _En este ejemplo estamos generando nosotros el repositorio pero si queremos trabajar con uno existente:_

   * _Desde repo local: `git clone /path/to/repository `_

   * _Desde repo remoto: `git clone username@host:/path/to/repository `_


###### _Se puede consultar como obtener un [repositorio](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Obteniendo-un-repositorio-Git) en su página oficial._

* _Con `ls -alh ` nos va a listar el archivo **ejemplo.txt** y el directorio **.git** oculto._

```ssh
$ls -alh
total 4,0K
drwxr-xr-x 1 jps jps  30 oct 18 15:41 .
drwxr-xr-x 1 jps jps 232 oct 18 15:39 ..
-rw-r--r-- 1 jps jps  26 oct 18 15:41 ejemplo.txt
drwxr-xr-x 1 jps jps  98 oct 18 15:41 .git
```
* _Ahora con `git status ` podemos ver en qué estado se encuentran los archivos de nuestro repositorio._

```ssh
$git status
En la rama master

No hay commits todavía

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	ejemplo.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
```
###### _En esta guía inicial vamos a trabajar todo sobre la misma rama (**branch**)_

* _Ahora con `git add [nombre-archivo] ` lo prepara para que pueda ser rasteable y pendiente a cambios. También se puede ejecutar `git add . ` para incluir todos._

```ssh
$git add ejemplo.txt
```
* _Revisamos nuevamente el estado._

```ssh
$git status
En la rama master

No hay commits todavía

Cambios a ser confirmados:
  (usa "git rm --cached <archivo>..." para sacar del área de stage)
	nuevo archivo:  ejemplo.txt
```
* _Confirmamos el cambio para que pase a la base de datos local y le agregamos un comentario._

```ssh
$git commit -m "agregamos el archivo ejemplo"
[master (commit-raíz) 3969ef1] agregamos el archivo ejemplo
 1 file changed, 2 insertions(+)
 create mode 100644 ejemplo.txt
```
* _Gracias a `git log ` podemos ver los cambios que se hicieron._

```ssh
$git log
commit 3969ef18d2130a8d984c985060cbedd2ca95b40a (HEAD -> master)
Author: Juan Pablo Soto <juanpablo.soto@protonmail.com>
Date:   Mon Oct 18 15:44:40 2021 -0300

    agregamos el archivo ejemplo
```
###### _Al ver los logs podemos ver quien hizo cada cambio._

* Volvemos a ver el estado.

```ssh
$git status
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
```
* _Ahora vamos a modificar el archivo y le agregamos, por ejemplo, otra línea de texto._

```ssh
$nano ejemplo.txt 
cat: _filedir: No existe el fichero o el directorio
$cat ejemplo.txt 
Hola, esto es un ejemplo
Ahora se agregó esta línea
```
* _Al ver el estado vemos que fue modificado._

```ssh
$git status
En la rama master
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificado:     ejemplo.txt

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
```
* _Preparamos el archivo, lo confirmamos y le agregamos un nuevo comentario._

```ssh
$git add .
$git commit -m "Se agregó una nueva línea"
[master 23cf09b] Se agregó una nueva línea
 1 file changed, 1 insertion(+)
```
* _Verificamos su estado y vemos los cambios a nivel de logs._

```ssh
$git status
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
$git log
commit 23cf09b49560396bf744b77345e4840f20708778 (HEAD -> master)
Author: Juan Pablo Soto <juanpablo.soto@protonmail.com>
Date:   Mon Oct 18 15:51:16 2021 -0300

    Se agregó una nueva línea

commit 3969ef18d2130a8d984c985060cbedd2ca95b40a
Author: Juan Pablo Soto <juanpablo.soto@protonmail.com>
Date:   Mon Oct 18 15:44:40 2021 -0300

    agregamos el archivo ejemplo
```

* _Nos damos cuenta que la última línea que pusimos no iba y hay que volver para atrás. Para eso usamos `git reset HEAD~ `._

```ssh
$git reset HEAD~
Cambios fuera del área de stage tras el reset:
M	ejemplo.txt
$git status
En la rama master
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificado:     ejemplo.txt
	
	sin cambios agregados al commit (usa "git add" y/o "git commit -a")
```
* _El archivo salió de la confirmación pero sigue modificado y ahora usamos `git checkout ` y volvemos a revisar el estado._

```ssh
$git checkout ejemplo.txt
Actualizada 1 ruta desde el index
$git status
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
```
* _Observando los logs verificamos que se ha vuelto al primer cambio._

```ssh
$git log
commit 3969ef18d2130a8d984c985060cbedd2ca95b40a (HEAD -> master)
Author: Juan Pablo Soto <juanpablo.soto@protonmail.com>
Date:   Mon Oct 18 15:44:40 2021 -0300

    agregamos el archivo ejemplo
```
* _Con `git reflog ` podemos ver el historial completo._

```ssh
$git reflog
3969ef1 (HEAD -> master) HEAD@{0}: reset: moving to HEAD~
23cf09b HEAD@{1}: commit: Se agregó una nueva línea
3969ef1 (HEAD -> master) HEAD@{2}: commit (initial): agregamos el archivo ejemplo
```
____

_Esta es una guía inicial para empezar a entender como funciona **Git** pero esto es solo el comienzo._

_Existen muchísimos comandos más, nuevas funcionalidades, trabajar con diferentes ramas (branches), etiquetas (tags), varios usuarios, confictos, flujo de trabajo, utilizar repositorios en la nube [GitHub](https://github.com/) etc. y etc..._

# 
### Contribuyendo 🖇️

_Las contribuciones son lo que hacen que la comunidad de código abierto sea un lugar mejor. Cualquier contribución que hagas será muy apreciada._

_Si queres aportar con alguna sugerencia para mejorarlo, simplemente un **fork** en el repo y crear un **pull request**. También podes abrir un issue con la etiqueta **enhancement**. ¡No te olvides de sumar una estrella al repo! **¡Gracias de nuevo!**_

# 
### Autor ✒️

* **Juan Pablo Soto** - [GitHub](https://github.com/parrot26) - [Linkedin](www.linkedin.com/in/juanpablosoto26)

# 
### Licencia 📄

Este proyecto está bajo la Licencia **MIT** - mira el archivo [LICENSE](LICENSE) para detalles


# 
### Expresiones de Gratitud 🎁

* Comenta a otros sobre este repo 📢
* Invita una cerveza 🍺 o un café ☕ a alguien del equipo. 
* Da las gracias públicamente 🤓.

#### _Gracias a:_

* [GitHub](https://github.com/)
* [Git](https://git-scm.com/)
* [ParrotOS](https://www.parrotsec.org/)
* [Linkedin](https://www.linkedin.com/)


---
⌨️ con ❤️ por [Juan Pablo Soto](https://github.com/parrot26)

