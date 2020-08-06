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

## Inicializar un nuevo repositorio de git 

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

Para subir los cambios de tu directorio local al repositorio remoto, primero debes registrarlos en el Index (Stage) mediante una instrucción de *add*. Después, mediante una instrucción de *commit*, quedaran registrados en el HEAD. Finalmente, con una instrucción *push*, los cambios serán enviados al Server y se verán reflejados en el repositorio remoto. 

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

Depsués de hacer un commit, tus cambios están ahora en el HEAD de tu copia local. Para enviar estos cambios al repositorio remoto, ejecuta: 

```markdown
git push 
```
<br>









<br>
Ubicado dentro del directorio de tu proyecto, la siguiente línea de comando inicializará el repositorio de git. 

```markdown
git init
```




<br>


<br> 




<br>
<br>






You can use the [editor on GitHub](https://github.com/sarahiaguilar/git-101/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/sarahiaguilar/git-101/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

![Alt Text](https://imgs.xkcd.com/comics/git.png)
