![](https://i.imgur.com/crJC9GI.png)

# Indice

**18. GitHub**

# Clase 18: Uso GitHub

## Crear a new repository

* Publico

* Private

## Traer al proyecto lo hecho en Git

>## Clone or download|


Copiar html

Ir a la terminal
verificar pwd que estemos en master
Decir a Git para agregar al origen remotos nuestros archivos

si no tengo creado el remoto  debo hacer lo siguiente


># $ git remote add origin url (copiada)


># $ git remote


verbal
>## $ git remote -v


origin----- (fetch)
origin----- (push)

realizamos push a master

>## $ git push origin maaster

# Clase 19: Cómo funcionan  las llaves publicas y privadas

Cómo funcionan las llaves ssh

# Clase 20: Configurar tus llaves SSH en local

SSH no son por repositorio sino por persona

1. Verificamos estar en la carpeta home por medio del comando $ Cd y enter (aunque podriamos esta en cualquier carpeta pero lo ideal es estar en el home)

2. Crear las llave SSH con el siguiente comando

>## $ ssh-keygen -t rsa -b 4096 -C "ktalina.va@gmail.com"

* rsa: algotirmo para crear la llave, este es el mas popular

* 4096: que tan compleja es la llave, complegidad de la llave

* a que correo electrónico va esta conectada la llave

3. Enter y me pregunta donde quiero guardar la llave, lo ideal es dejarlo en ese lugar

4. Contraseña adicional a la llave y enter

5. Confirma la creación de la llave

6. Ver la llave visual estudio code

7. Copio la llave publica

8. Revisar que las llaves estén corriendo

>## $ eval $(ssh-agent -s)

R/ agent pid 4724 

agent: indica que el servidos ssh está corriendo

pid: process id, identificador  del proceso que confirma que las llaves estan corriendo

9. Agregar la llave al sistema

>## $ ssh-add ~/.ssh/id_rsa

R / Identity addend

~ variable con el nombre de mi carpeta home bash: /c/Users/cata vargas: Is a directorybash: /c/Users/cata vargas: Is a directory

# Clase 20: Conexión a GitHub con SSH

1. Las llaves estan creadas

2. Carpeta .ssh y copiamos la llave publica

3. En Github vamos a menú de usuario y ingresamos a setting SSH and GPG keys

4. Nueva llave SSH
* Title Portatil Anakta
* key: copiamos la llave publica

5. Añadir solicita la contraseña y listo

6. llave publica registrada

7. Ir al repositories en el menú de usuario

8. Selecciono el repositorios

9. Copio en clone la url SSH y vamos a el entorno local

10. En la carpeta de nuestro proyecto

>## $ git remote -v

R/ todavia se ve https

>## $ git remote set-url origin git@github.com:anakta86/ApuntesClases-.git

>## $ git remote -v

R/ todavia se ve ssh, ya no dice https


# Clase 22: Tags y versiones en Git y GitHub

Los commits
>## $ git log
Todos los commits 
>## $ git log --all
Vision grafica de los branches
>## $ git log --all --graph 

>## $ git log --all --graph --decorate --oneline

Para no aprendernos todo este comando utilizamos aliases

>## $ alias arbolito="git log --all --graph --decorate --oneline"

Solo con escribir la palabra arbolito ejecuta el comando

#  Crear Tags

1. Copiar el hash del commit

2. Enviar el siguiente comando

>## $ git tag -a v0.1 -m "mensaje" hash

# Consultar lista de los tags creados


>## $ git tag

# A que commite o hash está conectado un tags

>## git show-ref --tags

# Mandar tags a internet GitHub

1. Hacer pull

2. Enviar el tag a Github

>## $ git push origin --tags

3. Listo en github en branches tambien tenemos los tags

# Borra tags

por la terminal

1. Consultar los tags

>## $ git tag

2. Borrar

>## $ git tag -d 'tagAborrar'

3. Pull

4. push para subir los tags pero no se borra en git Hub, no se borra porque lo podemos utilizar como release

5. para borrarlo

>## $ git push origin :refs/tags/´tagAeliminar´

# Clase 23: Manejo de ramas en GitHub

cuales ramas exiten y cuales han sido su historia

>## $ git show-branch

Mas datos historia de cada una de las ramas

>## $ git show-branch --all

Visualizacion en un software instalado por defecto

>## $ gitk

Cada rama se debe subir al Git Hub ubicandonos en la rama y hacer pull y hacer push

# Clase 24: Configurar multiples colaboradores en un repositorio de github

1. Nueva persona en la empresa

* Tener intalado gitbash en el computador, configurado con su correo
* Tener cuenta en GitHub con el correo registrado en git
* Entrar al repositorio de GitHub del trabajo

># https://github.com/anakta86/ApuntesClases-

* Entramos a clonar por HTTPS o por SSH, copiando el link
* En git ingresa el siguiente comando

># $ git clone https://github.com/anakta86/ApuntesClases-.git

Si el repositorio es plublico lo permite clonar sin problemas

* Asi queda clonado el repositorio en el computador

el nombre por defecto es el que está en GitHub, pero no hay probleme al cambiarlo


Realiza actualizaciones en uno de los documentos

* Realiza todo el ciclo de git, puede hace pull a las ramas, ver los commits

* Al querer realizar push pide correo y contraseña, al dar enter me indica que no es posible, por que el jefe no le dio acceso

2. Agregar nueva persona en el repositorio

* Ingrear al setting del repositorio
* Opción collaborater
* Agregar correo del nuevo colaborador, pero ese colaborador debe tener un email publico, pero pude ser agregario con su nombre de usuario
* Add Colaborator
* Copiar invitación y el nuevo colaborador puede ingresar y copiar el link desde el gmail

3. Aceptar Invitación
* Ya tiene acceso al push al repositorio
* Colaborar con el equipo de trabajo
* Puede realizar push ingresando correo y contraseña de git, porque se clonó el repositorio en HTTPS

4. Puede hacer push al repositorio

5. Ver los cambio  haciendo git pull traer lo que hizo el nuevo colaborador

># Dividir el trabajo por ramas


# Clase 25: Flujo de trabajo profesional: Haciendo merge de ramas de desarrollo a master

1. Crear dos branches para dividir el trabajo en diferentes partes del proyecto

2. Cambiamos de ramas con el siguiente comando

># $ git checkout ´Nombre de la rama´

># Agregar imagenes al repositorio no es buen practica porque es un archivo binario, la forma de agregarlo es con el siguiente comando

># $ git add imagenes/gragon.png

3. Realizar cambio y hacer commit, hacemos pull y push de la rama correspondiente

4. Vemos los cambios en GitHub

># Entre mas archivos binarios mas va pesar el respositorio ademas no va identificar facilmente los cambios realizados, y no actulizar cambios realizado a estos archivos pero si lo actualiza, para forzar esa actualización en win Ctrol F5  o Ctrol Shif R para actualizar cache

5.realizo cambios en dos ramas diferentes dos usuario diferentes 


## Hacer Merge de las ramas

1. Revisar historias de ramas y los cambios en GitHub

2. En gitBash traer los cambios realizados en otras ramas por medio de pull

3. Fusionar las ramas

* Ubicarme en la rama en la que quiero fusinar los cambios en este caso master

* Hacer merge de la primera rama

># $ git merge nombre de la rama

* Realiza el merge al indicar el mensaje

* Actualizar master a internet pero primero haciendo el pull y lusego push

* Hacer el mismo procedimiento con las otras ramas


# Clase 26:  Flujo de trabajo profesional con Pull requests

># Aplicado generamente cuando don desarrolladores  externos, es decir trabajan por fuera de la compañia en el proyecto

># Generalmente la rama master es bloqueada

Antes de realizar merge al master debe haber un *code review*

Pull request estado intermedio antes de realizar el merge, permite que otros miembros del equipo miren los cambios realizados y les gusta aprobarlos, despues probados en stage se pruede hacer otro pull reques a master produccipon 

En GitLab, se llama MR

# Clase 27: Utilizando Pull Request en GitHub

1. Hacer cambios para corregir erores por ejemplo de escritura en una nueva rama

* Git pull de master
* Crear nueva rama llamada fix-typo
* Hacer git checkout hacia fix-typo
* Hacer el cambio
* Subir a GitHub con push origin de esa rama que creamos
* Hacer commit del cambio realizado
* Git push origin fix-type

2. Crear pull request en Github para fusionar la rama conmaster

* Seleccionamos la rama fix-typo en GitHub
* Seleccionamos New pull request
* Seleccionamos comparar master con fix-typo o en compare & pull request me permite especificar mas detalle
* En compare & pull request permite agregar personas que revisen 
* Crar pull request para que otra persona lo revise

3. Revisar y aceptar pull request

* Review changes, comentar aprobar o solicitar cambios
* Aprobar los cambios checkbox listo
* Realizar merge pull Request

4. Realizar pull request y verificar cambios realizados en master

# Clase 28: Creando un Fork, contribuyendo a un repositorio

Aportar a un proyento cuando no es un colaborador en el proyecto


## Cuando no es un calaborador

Fork: tenedor 

1. hacer un fork es tomara una copia del proyecto, solo lo es permitido para proyecto publico

2. GitHub clonar proyecto
># $ Git clone y el link url

3. New pull request, abre uanventana para camparar las ramas master por medio de fork

4. Create pull request: es como hacer un commit intermedio solicitar aceptar el merge

5. Esperar que acepten los cambios

## Jefe aceptar la colaboración al proyecto

1. En el home puede ver las acciones realizadas al proyecto, y las notificaciones

2. En notificaciones veo el pull request con el detalle

3. Review lo puedo aprobar  con un mensaje

4. Confirmar el merge

5. Fusionado en master y reviso lo realizado

El fork se va quedando atras si quiere esta igual al master originar, debe traerse los cambios

># Traer cambios en master hacia el respositorio del contribuyener no colaborador

1. Una forma en GitHub es realizar pull request desde master original hasta el master del fork

2. Forma dos en git realizar lo siguiente:

* Ubicarme en la carpeta en en git status me doy cuenta que estoy en la rama master

* Copiar el link del proyecto original

* Git remote add upstream y copio el link (upstream es opcional puede ser otra cosa)
Git remote -v ( vemos que hay una nueva rama para el repositorio remoto)

* Hacer Git pull de upstream master y enter: traemos todo los cambios de master

* Git commit -am "mensaje"

* git pull origin master

# Clase 29: Haciendo deployment a un servidores

# Clase 30: Hazme un pull request

# Clase 31: Ignorar archivos en el repositorio con .gitignore

Se deben ignorar 
contraseñas
imagenes o archivos binarios
base de datos

1. Crear archivo .gitignore en la raiz del proyecto

2. En este archivo escribimos la lista de los archivos que vamos a ignorar

*.jpg   

* significa que todo tipo de archivo en esta extensión

3. Git add .gitignore

4. Commit

5. Git pull y Git push

Subir imagenes

imgur.com/


# Clase 32: Readme.md es una excelente práctica

Realizar readme en markdown

# Clase 33: Sitio web público con GitHub Pages

Realizar una pagina 

1. Entramos a GitHub Pages

2. Entrar a GitHub crear un repositorio nuevo que tenga tu nombre de usuaario

3. Copiar url con llaves ssh ir al consola y ubicarse en el home

4. enviar el siguiente comando y copiar la url

># $ git clone git@github.com:anakta86/anakta86.git

5. Crear nuevo archivo llamado index.html con tipico archivo de prueba

># code index.html

6. pull a orgin master y ya tenemos el archivo intex.html en el nuevo reposidtorio anakta86

7. Configurara que el repositorio es el que va a quedar como pages

* Vamos a setting del repositorio
* opción GitHub Pages
* en source cambiamos none por master branches

8. Listo tenemos la url de la pagina

9. Para que la pagina quede en la raiz se hacen los siguiente pasos 

* Cambiar el nombre del repositorio a anakta.github.io en setting del respositorio y rename

* Verificar en setting y ya la url está en la raiz


7. Ingresamos a la siguiente pagina

anakta86.github.io

# Clase 34: Git Rebase: reorganizando el trabajo realizado

Es una mala practica no se debe usar, aunque se puede usar en repositorios local pero aun asi no se debe hacer, ya que es un parche

Con *rebase* puedes escoger todos los cambios confirmados en una rama y ponerlos sobre otra 

1. tener una rama master (agregar una linea y lo agregamos en master por commit)

2. Creamos nueva rama 

3. pasamos de la rama master a la rama de exprimento por checkout (agregamos otra linea y lo subimos a la nueva rama con un commit)

4. Agregamos otra linea en esta nueva rama y lo agregamos conun commit

5. Checkout a master  y solo existe lo que agregamos a master

5. Checkout a la otra rma   y existe las tres lineas incluyendo la de master

6. La idea es que lo de la rama nueva esté en master si dejar rastro de esta nueva rama 

7. Esto se hace de la siguiente manera:

* Pasar lo de master en la otra rama 

Dentro de la rama que voy a eliminar y llevar sus commits a master

># $ git rebase master

Volvemos a la rama master y vamos agregar un commit adicional 

volvemos a la otra rama

Dentro de la rama que voy a eliminar y llevar sus commits a master

># $ git rebase master

Queda que la rama nueva tiene todo lo de master, cambia la historia de donde arancó el branchs 

* Pasar lo de la nueva rama a master

Dentro de la rama master y llevar sus commits a la otra rama

># $ git rebase otra rama

se tiene todo en la rama master 

Existe la rama experimento pero siempre ha tenido lo de master

a nivel de historia es como si fueran los mismos commit en la misma rama

ya podemos borrar la rama sin que pase nada

># git branch -D la otra rama

y se elimina

># primero rebase en la rama donde hubo los cambios 

># segundo rebase a la rama final la que va a quedar

no queda historia y se sabe que se hizo y si el master avanzo mucho puede generar muchos conflictos

# Clase 35: Git stash: Guardar cambios en memoria y recuperarlos después

Sirve para guardar cambios realizado en staging sin realizar el commit, por que no requiere rama o porque si realizo el commit en ese momento podria tener conflictos

># git stash 

Después de realizar un cambio y realizo git status y se ve la modificacion con este comando lo recupera, volve al estado anterior, dejando lo otro guardado, para visualizar esos cambios los listo con el siguiente comando

># git stash list

Lista los que tengo con el comando git stash que son WIP


># git stash pop

Vuelve a como estaba antes y cotrol z y queda original sin cambio por agregar


## Guardar mis cambios y ponerla en una rama 

1.  Realizar un cambio

># $ git stash

># $ git stash list

2. Veo el WIP

3. Poner ese stash en una rama

># $ git stash branch NombreDeLaRama

4. Crea automaticamante la rama y me ubica allí y el archivo está modificado

5. Adicionar y crear el commit

># $ git commit -am "mensaje del cambio"

6. Ya el cambio se encuentra en la nueva rama sin modificar master

## Lo que tendo en stash lo quiero borrar

1. Tengo cambios que quiero deshacer

2. $ git stash queda en un WIP pero quiero borrar esto y master queda como estaba original master 

3. $ git stash list con el WIP

4. Para borrar este WIP envio el siguiente comando

># $ git stash drop

5. Ya no exite el WIP 



# Clase 36: Git Clean: Limpia tu proyecto de archivos no deseados

1. Cree varios archivos que en realidad no necesito y no los he agregado a staging, con el siguiente comando simulo los archivos que serán borrados:

># $ git clear --dry-run

2. Autorizar borrar todo lo que simuló, lista de los archivos del comando anterior

># $ git clear -f

3. Veo que no borró algo css copia por ser carpeta y git lo considera trackeado

4. Ademas las extenciones que estaba en la carpeta .gitignore


# Clase 37: Git cherry-pick: trael commits viejos al head de un branch

Puedo ir avanzando en una rama pero necesito en master uno de estos cambios de la rama para ello se utiliza el comando que se llama cherry pick

1. Agregar cambio en un archivo estando en master

2. voy a guardar este cambio 

># $ git stash

># $ git stash branch "NuevaRama"

3. En la nueva rama 

># $ git commit -am "mensaje"

4. Agregar otro cambio en esta nueva rama y los agrego con un commit a la rama 

5. Agregar otro cambio en esta nueva rama y los agrego con un commit a la rama 

6. Necesito traer uno de los cambios realizados a la nueva rama en master

* Ver cual es el commit que necesito que está en la nueva rama y copio el hash del commit 

* Ir al master y desde allí:

># $ git cherry-pick CopiarElHash

7. Queda un commit viejo a la rama master, sin necesidad de hacer commit impediatamente queda en el Head

8. ya puedo hacer pull y push a origin en history está el commit que agregamos a master y parece que el commit se hubiera realizado en master sabiendo que fue realizado en otra rama

9. Ya finalizamos fusionado las dos ramas va tener conflicto porque esta la misma linea en master y en la nueva rama

10. Soluciono los conflictos realizo el commit con los conflictos ya solucionados

11. de nuevo pull y push al origin

># cherry pick es una mala practica porque estás recostruyendo la historia, y se puede realizar en cualquier rama

# Clase 38: Reconstruir commit en Git  con amend

A veces se hace un commit y no se queria mandar por que faltaba algo mas, lo podemos solucionar con el siguiente comando 

1. tenemos un commit con un cambio

2. pero me falto algo 

3. Realizo el cambio que me faltaba
 y lo agrego con add
4. Hacer el siguiente comando para añadir el cambio

># $ git commit --amend

Este comando adiciona el cambio al commit anterior y me pregunta si quiero cambiar el texto o mensaje de ese commit

5. Los cambios quedaron en el primer commit

# Clase 39: Git Reset y Reflog: úsese en caso de emergencia

Que pasa cuando todo se daña y no sabemos que hacer 

1. Ejecutar el siguiente comando

># $ git reflog

Con este comando puede ver todo, principalmente me interesa los head que han ido muriendo 

2. Buscar en el listado el head que tenia todo correcto y copio el hash de head{5}  y lo copio

3. envio el siguiente comando 

># $ git reset --soft(mantiene lo que está pendiente por un commit) o --Hard(resetea todo) 

volver a trae esa posición donde estabamso antes

># # git reset copiamosElHashHead{} 

Esto lo realiza pero antes de generar el commit

># $ git reflog

para visualizar el head que corresponde y vamos a realizar 

># $ git reset --HARD CopiamoselHashDelcommit

y todo vuelve a la normalidad y no queda evidencia de lo sucedido por eso es tan peligroso, solo debe usuarse en caso de emergencia

# Clase 40: Buscar en archivos y commits de Git con Grep y log

Permite buscar en git cualquier palabra dentro de tu repositorio

># $ git grep Palabra

Permite busar en git cualquier palabra e indicar la linea

># $ git grep -n Palabra

Permite contar la cantidad de veces que una palabra ocurre

># $ git grep -c Palabra

para buscar algo en cogigo que no reconozga git lo colocamos entre commillas ejemplo "<p>"

* Para buscar directamente en git en los commit realizamos los siguiente comandos

># $ git log -S "palabra"

# Clase 41: Comandos y recursos colaborativos en Git y GitHub

* Ver cuantos commits ha hecho cada miembro del equipo

El siguiente es un log por cada miembro

># $ git shortlog   

Cantidad de commit por cada miembro

># $ git shortlog -sn

Todos los commit por cada miembro hasta los que han sido eliminados

># $ git shortlog -sn --all

Todos los commit sin contar los merges

># $ git shortlog -sn --all --no-merges


## registrar comandos anteriores como alias 

Crear comando stats y que ejecute el comando anterior

># $ git config --global alias.stats "shortlog -sn --all --no-merges"

Ejecutar el comando solo escribiento

># $ git stats

## Saber quie hizo que 

># git blame NombreDelArchivo

ver esto mejor:

># git blame -c NombreDelArchivo

## Quien modificó entre lineas 

># git blame NombreDelArchivo -L35,53

Ver esto mejor

># git blame -c NombreDelArchivo -L35,53

## como vemos ramas locales y ramas remotas

* Ver ramas actuales

># $ git branch

* Ver ramas remotas

># $ git branch -r

* Ver tanto ramas locales como remotas

># $ git branch -a

Blanco las locales
* en la que estamos en ese momento 
Rojas las remotas

permite ver a cuales les falta hacer push al repositorio remoto por que no existen allí

## En hithub

* pulse es importante ver todo del repositorio
* Contributors
* Community
* traffic
* Commit por día
* Codefrequency
* Alert
* Network
* Fork

# Clase 42: Tu futuro con Git y GitHub

finalizado el curso

siguiente paso:

Curso gitlab
* Manage
* Plan 

Curso de DevOps con GitLab

curso profesional de DevOps





















































