# HyperBlog

## CURSO PLATZY GIT Y GITHUB

###### COMANDOS
```
git status --->para ver los status de el git

git commit -m "descripcion de lo que se hizo"---> para ya subir

git add --->para agregar algo proximo a hacer commit

git config --global user.name "kevinEsquivel" --->determinar nombre del git

git config --global user.email "chivatico2@gmail.com" --->configgurar correo

git log nombreArchivo ---> historial de todo lo que es  modificaciones

git show # muesta mucha info sobre los cambio y mas cosas 

git reset #commit  -- hard --->nos vuelve a una version anterior seleccionando el 
                            numero del commit, pero borra las modificaciones que 
                            se hicieron despues de ese archivo

it reset --soft:    --->Borramos todo el historial y los registros de Git pero guardamos los 
                     cambios que tengamos en Staging, así podemos aplicar las últimas 
                     actualizaciones a un nuevo commit.

git reset HEAD:      --->Este es el comando para sacar archivos del área de staging. 
                        No para borrarlos ni nada de eso, solo para que los últimos cambios de 
                        estos archivos no se envíen al último commit, a menos que cambiemos de opinión 
                        y los incluyamos de nuevo en staging con git add, por supuesto.

git reset --hard:   --->Borra todo. Todo todito, absolutamente todo. Toda la información de los 
                     commits y del área de staging se borra del historial.

git rm --cached:   --->Elimina los archivos de nuestro repositorio local y del área de 
                    staging, pero los mantiene en nuestro disco duro. Básicamente le 
                    dice a Git que deje de trackear el historial de cambios de estos 
                    archivos, por lo que pasaran a un estado untracked.

git rm --force:    --->Elimina los archivos de Git y del disco duro. Git siempre guarda todo, 
                    por lo que podemos acceder al registro de la existencia de los archivos, 
                    de modo que podremos recuperarlos si es necesario 
                    (pero debemos usar comandos más avanzados).

git checkout      ---> te permite darle una mirada a una version es especifico y para 
                    regresar tienes que poner git checkout master --->nombre archivo
```
aqui agregare para ver algo mas

| DIRECTORIO       |  STAGING(RAM)   |    REPOSITORIO  LOCAL            |                       |  REPOSITORIO REMOTO   |
| ---------------- | --------------- | -------------------------------- | --------------------- | --------------------- |
| /proyecto1/  < _ | _______________ | ____ git merge ___________  < __ | ______ git fetch ____ |                       |
| .holaEstoES.txt  |                 |                                  |                       |                       |
| con git add ____ | _ >Se mueve a   |                                  |                       |                       | 
|                  | Memoria ram.    |                                  | _____ git push ___ >  |                       | 
|                  |Con git commit _ | ___ > se mueve al repositorio    |                       |                       |
|                  | Con git rm borra|   a master que es la branch      |                       |                       |
|            < ___ | git reset HEAD  |                                  |                       |                       |
|            < ___ | _______________ | ________________________________ | ______ git pull _____ |                       |



```
git branch "nombreRama"   #este comando me pertmite ccrea una rama con 
                              git checkout "NOmbreRama" puedo moverme entre cabeceras

git merge  "nombreRama"   #nos permite crear un nuevo commit con la combinación
                            de dos ramas (la rama donde nos encontramos cuando 
                            ejecutamos el comando y la rama que indiquemos después del comando).

```

___________________________________________________________________________
## Hacer lo remoto el repositorio
 Primero: Guardar la URL del repositorio de GitHub
git remote add origin URL # con el nombre de origin


--Segundo: Verificar que la URL se haya guardado
--correctamente:
```
git remote
git remote -v
```
-- Tercero: Traer la versión del repositorio remoto y
-- hacer merge para crear un commit con los archivos
-- de ambas partes. Podemos usar git fetch y git merge
-- o solo el git pull con el flag --allow-unrelated-histories:
```
git pull origin main --allow-unrelated-histories
```
--Por último, ahora sí podemos hacer git push para guardar
--los cambios de nuestro repositorio local en GitHub:
```
git push origin main
git push origin HEAD:master  #Lo use porque me crea una rama 
```
___________________________________________________________________________
## CONFIGURAR LLAVES EN LOCAL
Primer paso: Generar tus llaves SSH. Recuerda que es muy buena idea proteger tu llave privada con una contraseña.
```
ssh-keygen -t rsa -b 4096 -C "tu@email.com"
```
Segundo paso: Terminar de configurar nuestro sistema.

En Windows y Linux:

-Encender el "servidor" de llaves SSH de tu computadora:
```
eval $(ssh-agent -s)
```
-Añadir tu llave SSH a este "servidor":
```
ssh-add ruta-donde-guardaste-tu-llave-privada
```
En Mac:

- Encender el "servidor" de llaves SSH de tu computadora:
```
eval "$(ssh-agent -s)"
```

- Si usas una versión de OSX superior a Mac Sierra (v10.12)
- debes crear o modificar un archivo "config" en la carpeta
- de tu usuario con el siguiente contenido (ten cuidado con
- las mayúsculas):
Host *
        AddKeysToAgent yes
        UseKeychain yes
        IdentityFile ruta-donde-guardaste-tu-llave-privada

- Añadir tu llave SSH al "servidor" de llaves SSH de tu
- computadora (en caso de error puedes ejecutar este
- mismo comando pero sin el argumento -K):

###### CONEXION DE GITHUB A SSH
```
ssh-add -K ruta-donde-guardaste-tu-llave-privada
```
Ahora podemos actualizar la URL que guardamos en nuestro repositorio remoto, solo que, en vez de guardar la URL con HTTPS, vamos a usar la URL con SSH:
```
git remote set-url origin url-ssh-del-repositorio-en-github
```
___________________________________________________________________________
## AGREGAR COLABOLADORES 
Para agregar COLABOLADORES tengo que ir a seting y a colaboladores agregarlos
ya se a por correo o por el usuario de GitHub

## Guardar cambios en memoria y recuperarlos despues
```
git stash para regresar el cambio anterior que hicimos.

git stash es típico cuando estamos cambios que no merecen una rama o no merecen un rebase si no simplemente estamos probando algo y luego quieres volver rápidamente a tu versión anterior la cual es la correcta.

git clean --dry-run  --> mostrara todos los archivos que se borraran,!no borra CARPETAS, ni datos que esten en el .gitignore!

git clean --f --> remueve todos los datos listados de arriba

git commit --amend --> amend en inglés es remendar y lo que hará es que los cambios que hicimos nos los agregará al commit anterior.

```
## Buscar archivos y commits en git


```
git grep color -->use la palabra color
git grep la --> donde use la palabra la
git grep -n color–> en que lineas use la palabra color
git grep -n platzi --> en que lineas use la palabra platzi
git grep -c la --> cuantas veces use la palabra la
git grep -c paltzi --> cuantas veces use la palabra platzi
git grep -c “<p>”–> cuantas veces use la etiqueta <p>

git log-S “cabecera” --> cuantas veces use la palabra cabecera en
todos los commits.

grep–> para los archivos
log --> para los commits.
```

## Comandos y recursos colaborativos en git y github
```
git shortlog -sn = muestra cuantos commit han hecho cada miembros del equipo.
git shortlog -sn --all = muestra cuantos commit han hecho cada miembros del equipo hasta los que han sido eliminado
git shortlog -sn --all --no-merge = muestra cuantos commit han hecho cada miembros quitando los eliminados sin los merges
git blame ARCHIVO = muestra quien hizo cada cosa linea por linea
git COMANDO --help = muestra como funciona el comando.
git blame ARCHIVO -Llinea_inicial,linea_final= muestra quien hizo cada cosa linea por linea indicándole desde que linea ver ejemplo -L35,50
**git branch -r **= se muestran todas las ramas remotas
git branch -a = se muestran todas las ramas tanto locales como remotas

```