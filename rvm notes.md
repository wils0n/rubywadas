Notas del uso del rvm
====================
Ruby es un lenguaje que siempre me ha llamado la atención y viniendo del mundo python me preguntaba como se podria trabajar al igual que hacemos en python con *entornos virtuales* (para trabajar con  diferentes versiones de módulos), pues  al parecer una de las formas de hacerlo es con **rvm gemset**


##Instalando varias versiones de ruby
con rvm, puedes instalar diferentes versiones de ruby con

    rvm install ruby-1.9.3
    rvm install 1.9.3

en caso de no encontrar la version, te sugerira una version por ejm *ruby-1.9.3-p484*

     rvm list #listamos todas las versiones de ruby instaladas
     
##Creando un entorno virtual

    rvm use 1.9.3  # elegimos que versiond de ruby deseamos usar en el entorno
    rvm gemset create game  # creamos el entorno llamado 'game'
    rvm gemset use game  # usamos el entorno virtual creado


si no sabemos que version de ruby estamos usando, podemos averiguarlo de 2 maneras:

    rvm list
    which ruby
    

##Comandos en entornos viruales

    rvm gemset list  # listar todos los gemsets
    rvm gemset delete name_gemset  # eliminando un gemset llamado name_gemset
    
##Mostrando todas las dependencias de un gemset

generando todas las dependencias del gemset actual, te mostrará todas las dependencias en un archivo llamado igual a tu gemset con extension .gems

    rvm gemset export
    
generando el archivo de dependencias con un nombre específico

    rvm gemset export requirements.gems
    
##Importando las dependencias de un archivo .gems
Para hacer un clon de un entorno virtual, tendriamos que importar un archivo .gems (donde estan todas las dependencias del entorno que queremos clonar).

Esto es muy util cuando trabajamos en un proyecto en equipo, ya que deseamos tener exactamente todas las dependencias que con la cual se esta trabajando los demás integrantes del equipo

Supongamos que tenemos un archivo *requirements.gems* y estamos ubicados en otro gemset, entonces para instalar las dependencias que estan en *requirements.gems*, ejecutamos:

    rvm gemset import requirements.gems

    
    

    
    