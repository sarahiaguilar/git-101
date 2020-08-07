La naturaleza de un proyecto de desarrollo de software es cambiante. Al poco tiempo de arrancar un proyecto, habremos desarrollado ya múltiples versiones del mismo código fuente, y naturalmente, perderemos la pista de los cambios que hemos hecho. Y cuando se trata de un proyecto colaborativo, el escenario anterior puede terminar complicándose aún más. *#TrueStory*

<br>

**Git** es un sistema de control de versiones creado para mejorar la confiabilidad y eficiencia de la manipulación de código. Su propósito es llevar registro de los cambios en un archivo o en un conjunto de estos, y coordinar el trabajo que varias personas realizan sobre ellos. 

Ahora bien, existen varias plataformas de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git. GitHub, GitLab y Bitbucket son algunos ejemplos. 

<br>

:arrow_right: **En esta página se aborda una sencilla introducción al uso de Git utilizando respositorios de código alojados en GitHub**. :arrow_left:

<br> 

## :warning: Requerimientos previos :warning:

1. Instalar git en tu computadora. Para ello, no hace falta más que seguir las sencillas instrucciones de la [documentación oficial de Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
- Si tu sistema operativo es una distribución de Linux o macOS, únicamente será necesario ejecutar una línea comando en la terminal. 
- Si tu sistema operativo es Windows, deberás descargar el [instalador](https://git-scm.com/download/win) y seguir las instrucciones. No es necesario modificar las opciones que vienen seleccionadas por *default*. Una vez la instalación se haya completado, verifica que en tus programas instalados se encuentre Git Bash. 

2. Una cuenta en GitHub. Regístrate [aquí](https://github.com/join). No olvides verificar tu cuenta.  

<br>

## :white_square_button: La terminal: tu aliada :white_square_button:

Para manejar Git, utilizarás líneas de comando desde la terminal. En caso de que tu sistema operativo sea Windows, entonces ejecutarás las líneas de comando desde Git Bash. 

Es importante familiarizarte con la terminal. 

A continuación se enlistan algunos comandos básicos que te serán de gran ayuda para el manejo de archivos más adelante.

- Conocer el directorio en el que te encuentras
```markdown
pwd
```

- Enlistar archivos y carpetas contenidas en el directorio en el que te encuentras
```markdown
ls
```

- Cambiar de directorio
```markdown
cd folder_name_1/folder_name_1_1 
```

- Crear un nuevo directorio
```markdown
mkdir new_folder
```

<br>

## :wave: ¡Hola, Git! :wave:

Lo primero que deberás hacer es configurar tus credenciales. Git tiene que saber tu identididad para poder registrar los cambios a tu nombre. 

```markdown
git config --global user.name “Tu nombre”
git config --global user.email tu@tudominio.com
```
<br>

## :octocat: Inicializar un nuevo repositorio de git :octocat:

Crea un directorio nuevo, úbicate dentro de él y ejecuta:

```markdown
git init
```
<br>

## :checkered_flag: Inicializar un repositorio desde GitHub :checkered_flag:

Un repositorio de GitHub es un almacenamiento virtual de un proyecto. 

Hay múltiples formas de inicializar un repositorio; una de ellas es desde GitHub. 

1. Inicia sesión en el sitio web de GitHub.
2. Diríjete desde tu perfil al tab de *Respositories*.
3. Da clic en el botón de *New*. 
4. Asíganle un nombre a tu nuevo repositorio. La recomendación es que el nombre de un repositorio sea corto pero explicativo, y que no contenga caracteres especiales. 
5. Opcionalmente, escribe una breve descripción.
6. ¿Quieres que tú repositorio de código sea público para todo el Internet o que se mantenga privado? Selecciona una opción: *Public* o *Private*. 
7. Selecciona si quieres incluir un [archivo de texto *README.md*](https://www.makeareadme.com/) en tu repositorio al inicializarlo. Un archivo de texto *README.md* es un archivo que introduce el proyecto y contiene información relevante de este. 
8. Selecciona si quieres incluir un archivo [*.gitignore*](https://git-scm.com/docs/gitignore) en tu repositorio al inicializarlo, así como la [licencia](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/licensing-a-repository). Para los fines prácticos esta página, no abordaremos los detalles de estas últimas dos opciones.

<br>

## :sheep: Clonar un repositorio :sheep: 

Clonar un repositorio implica hacer una copia de este. 

Para clonar repositorios locales utilizando el path del repositorio, ejecuta:
```markdown
git clone my_projects/project_A
```

Para clonar repositorios remotos utlizando el URL del repositorio, ejecuta:
```markdown
git clone https://github.com/username/repo-name
```
Para clonar un repositorio de GitHub:
1. Entra al repositorio que deseas clonar.
2. Da clic en el botón de *Code*.  
3. Copia la URL desplegada en el recuadro y corre la línea de comando para clonar un repositorio remoto con la URL copiada. ¡Asegúrate de estar ubicado en el directorio en el que desees copiar el nuevo repositorio! 

También es posible descargar el repositorio como .zip y descomprimirlo en el directorio deseado para empezar a trabajar sobre él. 

<br>

## :file_folder: Conectar una carpeta ya existente a un repositorio :file_folder:

En caso de que tengas una carpeta de proyecto ya trabajada y quieras conectarla a un repositorio nuevo que acabas de crear en GitHub, úbicate dentro de tu carpeta y ejecuta: 

```markdown
git remote add origin https://github.com/username/repo-name
```

<br>

## :wavy_dash: El workflow de Git :wavy_dash: ## 

Git trabaja en 3 etapas:
1. **Working directory**: El directorio local que contiene y se modifican todos los archivos de un proyecto. 
2. **Index (Stage)**: El *área* en donde los cambios del *working directory* se deben registrar.  
3. **HEAD**: Apunta al último registro de cambios realizado. 
3. **Server**: El repositorio remoto en el que tus cambios se veran reflejados para todos aquellos que tengan acceso. 

Para subir los cambios de tu directorio local al repositorio remoto disponible para todos, primero debes registrarlos en el Index (Stage) mediante una instrucción de *add*. Después, mediante una instrucción de *commit*, quedaran registrados en el HEAD. Finalmente, con una instrucción *push*, los cambios serán enviados al Server y se verán reflejados en el repositorio remoto. 

<br>

## :envelope: Add :envelope:

Para registrar los cambios que has hecho en un archivo, ejecutamos:

```markdown
git add file_name_1.py
```

Para registrar los cambios que has hecho en varios archivos, ejecutamos:

```markdown
git add file_name_1.py file_name_2.py
```

Para registrar cualquier cambio que hayas hecho en el directorio, ejecutamos:

```markdown
git add .
```
<br>

## :outbox_tray: Commit :outbox_tray: 

Un commit representa la acción de guardar los cambios. 

Ejecuta añadiendo un mensaje informativo de tus cambios:

```markdown
git commit -m "Changed file_name_1.py "
```
<br>

## :rocket: Push :rocket:

Después de hacer un commit, tus cambios están ahora en el HEAD de tu copia local. Para enviar estos cambios al repositorio remoto, ejecuta: 

```markdown
git push 
```
<br>

## :inbox_tray: Pull :inbox_tray:

Para actualizar tu repositorio loca al commit más nuevo, ejecuta:

```markdown
git pull
```
<br>

## :deciduous_tree: Merge :deciduous_tree:

Las ramas son líneas de tiempo del proyecto. Sirven para trabajar de forma independiente sobre el mismo respositorio, es decir, los commits son propios de una rama. 
Por ejemplo, un equipo de desarrolladores emplea ramas para desarrollar funcionalidades aisladas unas de otras dentro de su aplicación. 
Una vez que los cambios de una rama están listos, estos se deberán fusionar con el resto en la rama *master*. La rama *master* es la rama "por defecto" cuando creas un repositorio.

Para crear una nueva rama llamada "feature_x", ejecuta:
```markdown
git checkout -b feature_x
```

Para regresar a trabajar a la rama master, ejecuta:
```markdown
git checkout master
```

Para borrar la rama "feature_x", ejecuta :
```markdown
git branch -d feature_x
```

Una rama nueva no estará disponible para los demás a menos que ejecute sun push a la rama hacia tu repositorio remoto. Para ello, ejecuta:
```markdown
git push origin feature_x
```

Cuando finalmente quieras fusionar otra rama a tu rama activa, ejecuta:
```markdown
git merge feature_x
```
Cabe mencionar que a pesar de que git intentará fusionar automáticamente los cambios en el proyecto contenidos en ambas ramas, esto no siempre será posible y se podrán producir conflictos. Tú serás responsable de fusionar esos conflictos manualmente.

![Alt Text](https://media0.giphy.com/media/cFkiFMDg3iFoI/giphy.gif)

<br>

## :boom: ¿Y si todo sale mal? :boom:

(Escucha [esta](https://www.youtube.com/watch?v=dQw4w9WgXcQ) canción.)

Si quieres deshacer todos los cambios locales y commits, puedes traer la última versión del servidor y apuntar a tu copia local principal ejecutando:
```markdown
git fetch origin
git reset --hard origin/master
```
<br>

## :shipit: Pull requests :shipit:

Un *pull request* es la acción de validar un código que se va a fusionar de una rama a otra. Es la forma de colaborar con proyectos de terceros más común en GitHub. 

Cuando querramos *proponer* la fusión de una rama que hemos creado nosotros al dueño del repositorio, una opción es seguir los siguientes sencillos pasos desde GitHub:
1. Ir al repositorio del proyecto a la pestaña de *Pull requests*.
2. Da clic en el botón de *New pull request*.
3. Selecciona en los dos menús drop-down las ramas que quisiéramos que se fusionaran. 
4. Da clic en el botón de *Create pull request*.
5. Agrega un comentario informativo. 
6. Da clic en el nuevo botón de *Create pull request*. 
7. Ahora, el dueño del proyecto se hará cargo de aceptar el *pull request*. 

Si quieres acceder a los *pull requests* de un proyecto tuyo, deberás acceder a la pestaña de *Pull requests* desde tu proyecto. En ella podrás dar clic en el botón de *Merge pull request* a todos aquellos cambios que decidas aceptar. Recuerda que habrá algunos en los que el *merge* no sea *compatible*.

<br>

## :star: Notas finales :star:

**¡Estás list@!** 

Git es una herramienta compleja y robusta, pero por esa misma razón es tan escalable como lo sea un proyecto. No obstante, saber utilizar un control de versiones resulta una habilidad fundamental entre desarrolladores. Si has terminado de leer esta página, ahora cuentas con las herramientas básicas de git para arrancarte. :sunglasses:

**¡Happy *commiting*! :blush:**

*(Comienza por deshacerte de tus capetas proyecto_final, proyecto_final_2 y proyecto_final_2_con_cambios. :sweat_smile:)*


![Alt Text](https://imgs.xkcd.com/comics/git.png)
