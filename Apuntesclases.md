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

># Divir es trabajo por ramas














