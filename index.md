# Git 101 

La naturaleza de un proyecto de desarrollo de software es cambiante. Al poco tiempo de arrancar un proyecto, habremos desarrollado ya múltiples versiones del mismo código fuente, y naturalmente, perderemos la pista de los cambios que hemos hecho. Y cuando se trata de un proyecto colaborativo, el escenario anterior puede terminar complicándose aún más. *#TrueStory*

<br>

**Git** es un sistema de control de versiones creado para mejorar la confiabilidad y eficiencia de la manipulación de código. Su propósito es llevar registro de los cambios en un archivo o en un conjunto de estos, y coordinar el trabajo que varias personas realizan sobre ellos. 

Ahora bien, existen varias plataformas de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git. GitHub, GitLab y Bitbucket son algunos ejemplos. 

<br>

:arrow_right: **En esta guía se aborda una sencilla introducción al uso de Git utilizando respositorios de código alojados en GitHub**. :arrow_left:

<br> 

## :warning: Requerimientos previos :warning:

1. Instalar git en tu computadora. Para ello, no hace falta más que seguir las sencillas instrucciones de la [documentación oficial](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
- Si tu sistema operativo es una distribución de Linux o macOS, únicamente será necesario ejecutar una línea comando en la terminal. 
- Si tu sistema operativo es Windows, deberás descargar el [instalador](https://git-scm.com/download/win) y seguir las instrucciones. No es necesario modificar las opciones que vienen seleccionadas por *default*. Una vez la instalación se haya completado, verifica que en tus programas instalados se encuentre Git Bash. 

<br>

2. Una cuenta en GitHub. Regístrate [aquí](https://github.com/join). No olvides verificar tu cuenta.  

<br>

## :white_square_button: La terminal :white_square_button:

Para manejar Git, utilizarás líneas de comando desde la terminal. En caso de que tu sistema operativo sea Windows, entonces ejecutarás las líneas de comando desde Git Bash. 

Es importante familiarizarte con la terminal. 

A continuación se enlistan algunos comandos básicos que te serán de gran ayuda para el manejo de archivos más adelante.

- Conocer el directorio en el que te encuentras
```markdown
pwd
```

- Enistar archivos y carpetas contenidas en el directorio en el que te encuentras
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


```markdown

```



<br> 

Git trabaja en 3 etapas:
1. **Working directory**: La carpeta local que contiene y se modifican todos los archivos de un proyecto. 
2. **Index (Stage)**: El *área* en donde los cambios del *working directory* se deben declarar *listos*.  
3. **Server**: El repositorio remoto en el que tus cambios se veran reflejados para todos aquellos que tengan acceso. 




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
