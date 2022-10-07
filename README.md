# git-commands
Lista de comandos para Git de uso cotidiano

## Contents

- [Configurando Git](#configurando-git)
- [Manejo de repositorios](#manejo-de-repositorios)
  - [Crear un nuevo repositorio](#crear-un-nuevo-repositorio)
  - [Clonar un repositorio existente](#clonar-un-repositorio-existente)
  - [Clonar un repositorio remoto](#clonar-un-repositorio-remoto)
  - [Clonar un repositorio local](#clonar-un-repositorio-local)

## Configurando Git

Configura el Autor y Email a usar al realizar
commits

```sh
git config --global user.name "John Appleseed"
git config --global user.email john_appleseed@example.com
```

## Manejo de repositorios

### Crear un nuevo repositorio

Crea un repositoio en el directorio actual

```sh
git init
```

### Clonar un repositorio existente

Crea una copia de un repositorio en el directorio
donde es ejecutado.

El repositorio a clonar puede ser local (existe actualmente
en tu sistema), o remoto (existe en una plataforma de manejo
de versiones. GitHub, GitLab o BitBucket).

#### Clonar un repositorio remoto

```sh
git clone <Path to Remote>

# Ejemplo
git clone https://github.com/palyzambrano/git-commands.git

# Ejemplo usando SSH
git@github.com:palyzambrano/git-commands.git
```

#### Clonar un repositorio local

```sh
git clone direccion/al/repositorio

# Ejemplo
git clone ~/Projects/MySuperProject
```

## Agrega un archivo para hacer commit

Antes de realizar un commit se deben de elegir los
archivos asociados a dicho commit.

Para ello se emplea el comando `git add`

```sh
# Agrega un archivo o directorio
git add <filename>

# Agrega el directorio actual
git add .

# Alternativamente se puede utilizar
# el asterisco para agregar todo el
# directorio actual
git add *
```

## Realiza un commit

El commit crea un punto de referencia de en la historia
del proyecto al que se puede volver en el futuro.

Un commit debe llevar un mensaje asociado al conjuto de
cambios realizados.

> Es recomendable usar 80 caracteres maximo al realizar un commit

```sh
git commit -m "Mensaje para el commit"

# Ejemplo
# Un commit donde se implementa una caracteristica
git commit -m "feat: implement user profile UI"

# Un commit donde se soluciona un error en el codigo
git commit -m "fix: unable to upload picture bug"

# Un commit donde se realiza un cambio en la configuracion
# del proyecto. Pero no esta relacionado al codigo fuente
# de la aplicacion
git commit -m "chore: specify node_modules in the .gitignore file"
```

## Sube los commits realizados al repositorio remoto

```sh
git push <Nombre Remoto> <Branch (Rama)>

# Ejemplo
# En el caso de clonar un repositorio de la web (GitHub,
# GitLab o BitBucket) el nombre del remoto suele ser "origin"
git push origin main

# Siempre se debe specificar la rama actual
# si se encuentra en una rama de nombre feat/reset-password
# se debe hacer push a esa rama en el origen
git push origin feat/reset-password
```

## Crea un nuevo branch (rama)

Crea un branch a partir del branch actual. Si no se ha
realizado commit de los cambios actuales, los mismos seran
transferidos al nuevo branch y podran hacer commit de los
mismos en el futuro.

```sh
git checkout -b nombre/rama

# Ejemplo
# Un branch para trabajar en una nueva caracteristica
git checkout -b feat/nombre-de-caracteristica

# Un branch para realizar un arreglo
git checkout -b fix/nombre-del-arreglo
```

## Cambiar de branch

Se puede cambiar de branch a medida que se necesita
trabajar en dos versiones con fines distintos.

Cada branch tendra su copia del repositorio y puede compartir
o no commits.

```sh
git checkout nombre/rama

# El comando usado es el mismo que se utiliza para crear un
# nuevo branch pero no es acompañado por el parametro -b
```

## Eliminar un branch

> Si se ejecuta este comando en un branch y el mismo no ha sido fusionado con otro, los commits del branch seran eliminados

```sh
git branch -d nombre/branch
```
