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





