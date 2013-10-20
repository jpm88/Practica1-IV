# Documentación Práctica 1: Creación y despliegue de una aplicación en un PaaS

## Juan Antonio Pérez Maldonado

## Licencia de la aplicación: GPLv3

### - Aplicación

 La aplicación seleccionada para esta práctica consiste en un periódico digital realizado en otra asignatura,
 realizado en php, como el periódico no está configurado para usar bases de datos no será necesaria la instalación
 de ninguna base de datos.
 
 El periódico digital está compuesto por distintas secciones en las cuales se pueden encontrar distintas noticias
 según el tema que se haya seleccionado.
 
 Es posible acceder a un formulario de registro pero actualmente no se asocia a ninguna base de datos.

### - Elección del PaaS

El PaaS elegido para esta práctica es OpenShift, la principal razón de la elección es que en los anteriores
ejercicios de la asignatura ya se ha usado este PaaS, y ya estoy mas familiarizado con su uso, además gracias
a esta práctica se han mejorado mis conocimientos sobre dicho PaaS.

Otra de las razones por las que he elegido OpenShift es porque permite aplicaciones PHP, así como de otros
lenguajes conocidos para mí, es muy fácil de usar y da facilidades para poder gestionar nuestras aplicaciones 
ya sea por entorno Web o por línea de comandos.

Además dispone de una buena integración con GitHub, puesto que permite asociar las aplicaciones a repositorios de
GitHub.

### - Configuración y creación de la aplicación

Los siguientes pasos para crear una aplicación también son posibles a través del entorno Web que ofrece OpenShift, 
pero este manual se va a centrar en la creación de la aplicación a través de línea de comandos.

Primero ponemos todo a punto instalando lo que necesitamos con los siguientes comandos:

* sudo apt-get install rubygems
* sudo gem install rhc
* rhc setup

Al ejecutar el comando "rhc setup" nos pedirá nuestros credenciales de OpenShift (usuario y contraseña), 
con esto ya está configurado el cliente rhc, ahora pasamos a crear el proyecto con el siguiente comando:

* rhc create-app practica1 php-5.3

![cap1](https://raw.github.com/jpm88/IV-Ejercicios/master/captura1.png)

Una vez creado el proyecto pasamos a copiarlo a nuestro pc, usando la dirección que OpenShift nos ofrece para clonar
directorios a nuestro pc a través de SSH:

* git clone ssh://52643eeb5973ca7db20000c7@practica1-jpm88.rhcloud.com/~/git/practica1.git/

Una vez tengamos el directorio en nuestro pc, añadimos los archivos de nuestro periódico digital en la carpeta
php, ahora toca subirla, con los siguientes comando:

* git add -A 
* git commit -a -m "Practica 1 de IV" 
* git push origin master


![cap2](https://raw.github.com/jpm88/IV-Ejercicios/master/captura2.png)

Comentar que los fuentes de la aplicación también se han subido mediante git a nuestro repositorio de GitHub
con la licencia GPLv3.

Hecho esto ya estará nuestra aplicación subida y funcionando, entrando en el siguiente enlace:

http://practica1-jpm88.rhcloud.com/

