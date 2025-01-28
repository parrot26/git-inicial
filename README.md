![Imagen.](/image/git-logo.png "Imagen.")

# 
# Git - Inicial
 
## Comenzando 🚀
[Git](https://es.wikipedia.org/wiki/Git) es un sistema de control de versión distribuida de código abierto y gratuito diseñado por por [Linus Torvalds](https://es.wikipedia.org/wiki/Linus_Torvalds) para manejar todo tipo de proyectos.

En su página oficial [Git](https://git-scm.com/) podemos encontrar su [Descarga](https://git-scm.com/downloads), [Instalación](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) y mucho más.

# 
### Pre-requisitos 📋
Ganas de meter mano.

# 
### Los 3️⃣ estados

Git tiene tres estados principales: **Modificado** (modified), **Preparado**(staged) y **Confirmado** (committed).

> **Modificado** significa que el archivo fue modificado pero todavía no está confirmado a la base de datos.

> **Preparado** significa que se marcó un archivo modificado en su actual versión para la próxima confirmación.

> **Confirmado** significa que los datos están en tu base de datos local.

En un ambiente local el flujo sería:

**Working Directory**  > **Staging** > **Local Repository**

# 
# 
# Comandos 📋

### Instalación ⬇️

Documentación oficial para la [Instalación de git](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalaci%C3%B3n-de-Git) en Linux, Mac y Windows.

## Git Cheat Sheet

### Configuración ⚙️

*   **`git config --global user.name "Tu Nombre"`**: Configura tu nombre de usuario para los commits.
*   **`git config --global user.email "tu.email@example.com"`**: Configura tu dirección de correo electrónico para los commits.
*   **`git config --global color.ui auto`**: Habilita el coloreado automático de la salida de Git en la terminal.
*   **`git config --list`**: Muestra la configuración actual de Git.
*   **`git --version`**: Muestra versión utilizada de Git.
*   **`git --help`**: Ayuda sobre los comandos.

## Inicio de un proyecto 🙌

*   **`git init`**: Inicializa un nuevo repositorio Git en el directorio actual.
*   **`git clone <url_del_repositorio>`**: Clona un repositorio Git existente desde una URL.

## Trabajo con cambios 🔄

*   **`git status`**: Muestra el estado de los archivos en el directorio de trabajo (modificados, añadidos, etc.).
*   **`git add <archivo>`**: Añade un archivo al área de preparación (staging area) para el próximo commit.
*   **`git add .`**: Añade todos los archivos modificados y nuevos al área de preparación.
*   **`git commit -m "Mensaje del commit"`**: Crea un nuevo commit con los cambios en el área de preparación.
*   **`git diff`**: Muestra las diferencias entre el directorio de trabajo y el área de preparación.
*   **`git diff --staged`**: Muestra las diferencias entre el área de preparación y el último commit.
*   **`git rm <archivo>`**: Elimina un archivo del repositorio y del directorio de trabajo.
*   **`git mv <archivo_antiguo> <archivo_nuevo>`**: Renombra o mueve un archivo.

## Trabajo con ramas (branches) 🌿

*   **`git branch`**: Lista todas las ramas locales.
*   **`git branch <nombre_de_la_rama>`**: Crea una nueva rama.
*   **`git checkout <nombre_de_la_rama>`**: Cambia a una rama diferente.
*   **`git checkout -b <nombre_de_la_rama>`**: Crea y se cambia a una rama nueva.
*   **`git merge <nombre_de_la_rama>`**: Fusiona una rama con la rama actual.
*   **`git branch -d <nombre_de_la_rama>`**: Elimina una rama (solo si ya ha sido fusionada).
*   **`git branch -D <nombre_de_la_rama>`**: Elimina una rama (forzado, incluso si no ha sido fusionada).

## Trabajo con repositorios remotos ☁️

*   **`git fetch <remoto>`**: Descarga los objetos y referencias del repositorio remoto especificado, pero no los integra en tus ramas locales.
*   **`git fetch <remoto> <rama>`**: Descarga los objetos y referencias de una rama específica del repositorio remoto.
*   **`git pull <remoto> <rama>`**: Descarga los cambios del repositorio remoto y los fusiona (merge) en tu rama local actual. Es equivalente a `git fetch` seguido de `git merge`.
*   **`git pull --rebase <remoto> <rama>`**: Similar a `git pull`, pero utiliza rebase en lugar de merge para integrar los cambios remotos. Esto crea un historial de commits más lineal y limpio.
*   **`git push <remoto> <rama>`**: Envía tus commits locales a la rama especificada del repositorio remoto.
*   **`git push <remoto> <rama> --force`**: Fuerza la subida de tus commits locales a la rama remota. ¡Úsalo con precaución, ya que puede sobrescribir cambios de otros!
*   **`git push --all <remoto>`**: Envía todas tus ramas locales al repositorio remoto.
*   **`git remote`**: Lista los repositorios remotos configurados.
*   **`git remote -v`**: Lista los repositorios remotos con más detalle, mostrando las URLs de fetch y push.
*   **`git remote add <nombre> <url>`**: Añade un nuevo repositorio remoto con un nombre específico.
*   **`git remote remove <nombre>`**: Elimina un repositorio remoto.
*   **`git remote rename <antiguo_nombre> <nuevo_nombre>`**: Renombra un repositorio remoto.


## Historial y revisión 📰

*   **`git log`**: Muestra el historial de commits.
*   **`git log --oneline`**: Muestra el historial de commits en una línea por commit.
*   **`git show <commit_hash>`**: Muestra los detalles de un commit específico.
*   **`git blame <archivo>`**: Muestra quién hizo cada cambio en un archivo.

## Deshacer cambios ◀️

*   **`git revert <commit_hash>`**: Crea un nuevo commit que deshace los cambios de un commit anterior.
*   **`git reset HEAD <archivo>`**: Quita un archivo del área de preparación (pero no lo modifica en el directorio de trabajo).
*   **`git checkout -- <archivo>`**: Descarta los cambios en un archivo del directorio de trabajo y lo restaura a la versión del último commit.

## Stashing (Cambios temporales) 😶

*   **`git stash`**: Guarda los cambios no confirmados en un "stash" temporal.
*   **`git stash list`**: Lista los stashes guardados.
*   **`git stash apply`**: Aplica el último stash guardado.
*   **`git stash drop`**: Elimina el último stash guardado.

## Tags (Etiquetas) 🚩

*   **`git tag`**: Lista todas las etiquetas (tags) en el repositorio.
*   **`git tag -l "patrón"`**: Lista las etiquetas que coinciden con un patrón específico.
*   **`git tag <nombre_de_la_etiqueta>`**: Crea una etiqueta ligera (ligera) que apunta al commit actual.
*   **`git tag -a <nombre_de_la_etiqueta> -m "Mensaje de la etiqueta"`**: Crea una etiqueta anotada con un mensaje.
*   **`git tag -a <nombre_de_la_etiqueta> <commit_hash> -m "Mensaje de la etiqueta"`**: Crea una etiqueta anotada para un commit específico.
*   **`git show <nombre_de_la_etiqueta>`**: Muestra información sobre una etiqueta específica.
*   **`git push origin <nombre_de_la_etiqueta>`**: Envía una etiqueta al repositorio remoto.
*   **`git push origin --tags`**: Envía todas las etiquetas al repositorio remoto.
*   **`git tag -d <nombre_de_la_etiqueta>`**: Elimina una etiqueta local.
*   **`git push origin --delete <nombre_de_la_etiqueta>`**: Elimina una etiqueta en el repositorio remoto.


## Otros comandos útiles ✏️

*   **`git help <comando>`**: Muestra la ayuda para un comando específico.
*   **`git diff <rama1> <rama2>`**: Muestra las diferencias entre dos ramas.
*   **`git bisect`**: Utiliza la búsqueda binaria para encontrar el commit que introdujo un error.
*   **`git ls-tree --name-only <nombre_de_la_rama>`**: Lista los archivos actuales en la rama específicada.

## Alias 👽

*   **`git config --global alias.<alias> "<comando>"`**: Crea un alias para un comando. Por ejemplo: `git config --global alias.co checkout` te permite usar `git co` en lugar de `git checkout`.

Este es un "cheat sheet" completo, pero Git tiene muchos más comandos y opciones. ¡Explora la documentación oficial de Git para obtener información más detallada!

# Aprendiendo Git: ¡Hora de usarlo! 😄

Vamos a sumergirnos en el mundo de Git con un ejemplo práctico. Aprenderás a configurar Git, crear un proyecto, realizar cambios, guardar versiones, explorar el historial, trabajar con ramas y fusionar cambios.

## 0. Configuración inicial de Git

Antes de empezar a usar Git, necesitamos configurarlo con tu información personal. Abre la terminal o línea de comandos y ejecuta los siguientes comandos:

1.  **Configura tu nombre de usuario:**

    ```bash
    git config --global user.name "Tu Nombre Completo"
    ```

2.  **Configura tu dirección de correo electrónico:**

    ```bash
    git config --global user.email "[dirección de correo electrónico eliminada]"
    ```

    ¡Importante! Asegúrate de usar tu nombre y correo electrónico reales, ya que esta información se asociará a tus commits.

3.  **(Opcional) Configura el editor de texto:** Git utiliza un editor de texto para algunos comandos. Puedes configurar tu editor preferido (como Nano, Vim, VS Code, etc.). Por ejemplo, para configurar VS Code:

    ```bash
    git config --global core.editor "code --wait"
    ```

    Si no estás familiarizado con la línea de comandos, te recomiendo usar un editor con interfaz gráfica como VS Code.

## 1. Creando tu proyecto y el repositorio Git

1.  **Crea una carpeta:** Elige un lugar en tu computadora y crea una carpeta para tu proyecto. Puedes llamarla "mi\_proyecto\_git".

2.  **Abre la terminal:** Abre la terminal o línea de comandos y navega hasta la carpeta de tu proyecto.

3.  **Inicializa Git:** Convierte tu carpeta en un repositorio Git. ¡Es como darle superpoderes de control de versiones!

    ```bash
    git init
    ```

## 2. Agregando archivos y haciendo tu primer commit

1.  **Crea archivos:** Dentro de la carpeta "mi\_proyecto\_git", crea algunos archivos. Pueden ser archivos de texto, imágenes, código, ¡lo que quieras! Por ejemplo, crea un archivo llamado "README.md" y escribe una breve descripción de tu proyecto.

2.  **Agrega archivos a Git:** Dile a Git qué archivos quieres controlar. ¡Es como prepararlos para la máquina del tiempo!

    ```bash
    git add .  # Agrega todos los archivos
    ```

3.  **Haz tu primer commit:** Guarda la primera versión de tus archivos. ¡Es como tomar la primera foto de tu proyecto!

    ```bash
    git commit -m "Primer commit: Archivos iniciales"
    ```

## 3. Explorando el historial y volviendo atrás

1.  **Ve el historial:** Observa todas las versiones que has guardado (los commits). ¡Es como ver el álbum de fotos de tu proyecto!

    ```bash
    git log
    ```

2.  **Vuelve a una versión anterior:** Viaja en el tiempo a un commit anterior. ¡Puedes ver cómo era tu proyecto en ese momento!

    ```bash
    git checkout <hash_del_commit>  # Reemplaza <hash_del_commit> con el código del commit
    ```

3.  **Regresa al presente:** Vuelve a la versión más reciente de tu proyecto.

    ```bash
    git checkout main  # O el nombre de tu rama principal
    ```

## 4. Trabajando con ramas (branches)

1.  **Crea una rama:** Imagina que quieres probar una nueva función sin afectar la versión principal de tu proyecto. ¡Crea una rama para experimentar!

    ```bash
    git branch nueva_funcionalidad
    ```

2.  **Cambia a la nueva rama:** Ahora estás trabajando en la rama "nueva\_funcionalidad". ¡Cualquier cambio que hagas aquí no afectará la rama principal!

    ```bash
    git checkout nueva_funcionalidad
    ```

3.  **Haz cambios en la nueva rama:** Modifica archivos, agrega nuevos, ¡lo que necesites para tu nueva función!

4.  **Guarda los cambios en la nueva rama:**

    ```bash
    git add .
    git commit -m "Añadida nueva funcionalidad"
    ```

## 5. Fusionando ramas (merging)

1.  **Vuelve a la rama principal:** Ya estás listo para integrar tu nueva función en la versión principal del proyecto.

    ```bash
    git checkout main
    ```

2.  **Fusiona la rama:** Une los cambios de la rama "nueva\_funcionalidad" a la rama principal. ¡Es como combinar las fotos de tus experimentos con las fotos principales del proyecto!

    ```bash
    git merge nueva_funcionalidad
    ```

3.  **¡Listo!** Los cambios de la nueva rama ahora están en la rama principal.

## 6. Resolviendo conflictos (si es necesario)

A veces, al fusionar ramas, Git puede encontrar conflictos (cambios en el mismo lugar de un archivo). En ese caso, tendrás que editar los archivos manualmente para resolver los conflictos y luego volver a agregar los archivos modificados a Git.

## ¡Felicidades! 🏆

Has completado un viaje épico por el mundo de Git. Aprendiste a configurar Git, crear un proyecto, guardar versiones, explorar el historial, trabajar con ramas y fusionar cambios. ¡Ahora estás listo para dominar el control de versiones y colaborar en proyectos de cualquier tamaño!

**¡Sigue explorando y practicando Git, tarde o temprano lo vas a tener que utilizar!**

# 
## Contribuyendo 🖇️

Las contribuciones son lo que hacen que la comunidad de código abierto sea un lugar mejor. Cualquier contribución que hagas será muy apreciada.

Si queres aportar con alguna sugerencia para mejorarlo, simplemente un **fork** en el repo y crear un **pull request**. También podes abrir un issue con la etiqueta **enhancement**. ¡No te olvides de sumar una estrella al repo! **¡Gracias de nuevo!**

# 
## Autor ✒️

* **Juan Pablo Soto** - [GitHub](https://github.com/parrot26) - [Linkedin](www.linkedin.com/in/juanpablosoto26)

# 
## Licencia 📄

Este proyecto está bajo la Licencia **MIT** - mira el archivo [LICENSE](LICENSE) para detalles


# 
## Expresiones de Gratitud 🎁

* Comenta a otros sobre este repo 📢
* Invita una cerveza 🍺 o un café ☕ a alguien del equipo. 
* Da las gracias públicamente 🤓.

#### Gracias a:

* [Git](https://git-scm.com/)
* [GitHub](https://github.com/)

---
⌨️ con 💪 por [Juan Pablo Soto](https://github.com/parrot26)
