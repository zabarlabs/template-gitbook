# template-gitbook
Esta es una plantilla para poder publicar libros utilizando Gitbook en GitHub.

Como duplicar este repositorio 
https://help.github.com/articles/duplicating-a-repository/

1. Crear un nuevo repositorio en GitHub  


2. Crear un clon desnudo de este repositorio
`git clone --bare https://github.com/zabarlabs/template-gitbook.git`

3. En el repositorio local hacer un push al nuevo repositorio de Github
`cd template-gitbook.git`  
`git push --mirror https://github.com/useraccount/new-repository.git`  

4. Eliminar el repositorio temporal creado anteriormente  
`cd ..`
`rm -rf old-repository.git`

Aternativamente tambien se puede descargar a local el archivo ZIP de la plantilla y usar comandos para primero inicializarlo como un repositorio GIT y a continuacion conectar dicho repositorio con el remoto en GitHub. Finalizaremos subiendo al remoto el contenido del repositorio local. (ESTA ES LA OPCIÓN QUE UILIZO) 

```bash
git init
git add .
git commit -m"Primer commit"
git remote add origin git@github.com:useraccount/new-repository.git  
git push -u origin master
```
5. Una vez hecho esto vamos a instalar los paquetes *npm* que necesita nuestro proyecto.
`npm install`

6. Dentro del archivo `package.json` podemos cambiar algunos parñametros que personalizarán nuestro proyecto:
* **name**: el nombre de nuestro repositorio no puede contener espacios.
* **descripcion**: descripcion de nuestro repositorio.
* **author**: nombre del autor.
* **license**: desde aquí podemos cambiar el **[tipo de licencia](https://spdx.org/licenses/)**
* **repository url**: la URL usada para clonar el repositorio.
* **homepage**: la URL donde estará alojado nuestro proyecto.

6. Ahora debemos instalar los plugins que hemos incluido en el archivo `book.json`

`gitbook install`

7. Vamos a introducir nuestro contenido mediante un editor que facilite la escritura de archivos de tipo Markdown. En mi caso voy a utilizar **VS Code**, que ademas nos permite un Live Preview de como se va viendo nuestros documentos.

8. Hasta ahora lo que hemos creado son archivos de tipo Markdown, para poder convertir esos archivos a formato *html* en nuestro repositorio local necesitamos correr el siguiente comando:
`gulp`

9. Las paginas *html* se crearán dentro de una carpeta dentro de nuestro proyecto llamado `docs/`.

>Cada vez que realice alguna modificación, por ejemplo añadir una nueva página
>tengo que volver a crear esa página *html* volviendo a correr `gulp`.

10. Publicar el contenido en GitHub pages
Una vez subamos los cambios a nuestro repositorio en GitHub, ya con los achivos *html*, GitHub nos permite poder publicar nuestro contenido como una página estática. Para ello debemos ir al apartado **Settings** y desde allí hacer el scroll hasta llegar al apartado que pone **GitHub Pages**. Aquí tenemos dos apartados que modificar:

 * Source: Debemos escoger **master branch/docs folder**
 * Theme Chooser: escogeremos un theme entre los que trae por defecto.




