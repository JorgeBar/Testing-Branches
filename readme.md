# Instrucciones para navegar entre ramas
 
 Principales comandos que vamos a necesitar son :

 ```
    1- git checkout (moviemiento entre ramas ,creación , eliminación)
    2- branch (vemos las ramas disponibles)
```
Lo fundamental es saber siempre en que rama estamos trabajando. Nos lo indicara entre paréntesis al lado de la ruta de nuestro proyecto.

### Procedemos a crear una rama 

```
 git checkout -b rama2
```
Una vez creada comprobaremos que estamos dentro de ella. 

Aquí procedemos a hacer los cambios o avanzar en el proyecto como creamos conveniente.

Por ejemplo añadimos un texto nuevo. Hacemos los correspondientes
```
git status
git add . 
git commit -m
```

Y esto se añadirán en github a commits de nuestra nueva rama.

## Hemos realizado los cambios y queremos fusionarlos al original
### Diff (para ver los cambios diferencias)
#### 1- A través de la consola

Vamos a hacer lo que se conoce como merge para fusionar lo que tenemos con la main. Una vez comiteado todo escribimos el siguiente comando para ver las diferencias entre una rama y otra
```
git diff "rama de origen"  "rama destino"
```
Veremos en verde los nuevos cambios para comprobarlo.
Si lo hacemos en la otra dirección veremos los cambios en rojo que quiere decir que faltan esos archivos.

```
git diff "rama destino" "rama origen"

```
#### 2- En github 

Veremos un pull request creado en el que se verán los cambios de una rama a otra. Allí tendremos un textArea para añadir comentarios y solicitar al usuario que sea responsable de la main que aplique los cambios necesarios o crear un hilo de debate.

### Merge

Hemos llegado al caso en que los cambios han sido comprobados y revisados y queremos fusionar el trabajo que hemos hecho en la rama nueva con la principal.

#### 1- En github.

Aqui es muy sencillo. Dentro de la ventana de pull request veremos la opción de merge. Allí si no hay ningún problema se fusionará correctamente.

Recordad una vez fusionado hacer en la terminal un :
```
git pull
```
Para tener la disponibilidad de los cambios

#### 2- En la consola.

Procedemos a escribir en la cosonla 

```
 git merge "rama actual" "rama destino"
```

Recordad que este orden quiere decir que desde rama1 por ejemplo fusionamos nuestro código con la rama destino que en este ejemplo será la main. 

**Para que el merge funcione debemos de estar en la rama main**
```
git checkout main
git merge rama1 main
```
***Cosas a tener en cuenta con merge***

Habrá muchas veces que la consola nos dará un aviso de conflicto en el merge. Porque estaremos solicitando modificar el contenido original sustityéndolo por el de la nueva rama.

Se nos abrirá un archivo de texto y podremos modificar los cambios que creamos convenientes y quedarnos con lo que nos convenga.

### Borrar ramas una vez mergeadas o porque no sean necesarias o porque se hayan crado por error.

#### 1- En github veremos la opción en el panel de borrar la rama

#### 2- En la consola

Escribimos:

```
git checkout -d    Para eliminar la rama una vez mergeada
git checkout -D    Para eliminar la rama aunque no se haya mergeado
```