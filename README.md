# Creación de Maquina Virtual

## Introducción y objetivo:
En el mundo de la ciberseguridad, es fundamental contar con un ambiente de pruebas robusto y bien configurado para analizar aplicaciones de manera segura y efectiva, basicamente para proteger la información, ya que es equivalente a proteger el funcionamiento del negocio. 

Este write-up tiene como objetivo documentar el proceso de creación y configuración de un ambiente de pruebas para aplicaciones, utilizando herramientas y tecnologías ampliamente reconocidas en el campo, como Kali Linux, Docker, y OWASP Juice Shop.

A lo largo de este documento, detallaremos cada paso necesario para establecer este entorno, que será utilizado en futuras actividades y prácticas relacionadas con la seguridad informática. Desde la instalación de una máquina virtual con Kali Linux hasta la configuración de un proxy de interceptación y la ejecución de un contenedor Docker con OWASP Juice Shop, este write-up proporcionará una guía completa que podrá ser replicada por cualquier usuario interesado en el tema.

### Primero, comenzaremos descargando todo lo necesario para poder crear nuestra maquina virtual con Kali Linux.
1. [Descargar Virtual Box](https://www.virtualbox.org/wiki/Downloads)
2. [Descargar Kali Linux](https://www.kali.org/downloads/)

Clickeando en el primer link deberia de aparecer una pagina similar a la siguiente foto, en la cual debemos de elegir el sistema opertaivo en el cual vamos a descargar el programa.

![VirtualBox](./Descargas/VirtualBox-Descarga.png)


Una vez descargado, si ejecutamos la aplicacion de Virtual Box, puede ser que nos aparezca en mensaje de error (como el de la imgen), en ese caso deberiamos de ir a la pagina de [Microsoft](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170). En esta pagina, debemos de scrollear un poco para encontrar una tabla como la de la siguiente imagen y seleccionaremos la versión de Visual C++ que necesitamos para nuestro sistema operativo.

![Error](Posible-Error.png)
___
Clickeando en el segundo link deberia de aparecer una pagina similar a la siguiente foto, en la cual debemos elegir el tipo de instalación que queremos realizar.
Podemos elegir la opción de "Virtual Machines" o "Installer Images". En la opción de "Virtual Machines", te descarga una carpeta con dos archivos, aunque el que nos interesa es el que tiene terminación ".vdi". 
De la misma forma, en la opción de "Installer Images", te descarga un archivo con terminación ".iso". Para este tutorial, elegimos la opción de "Installer Images".

![Kali Linux](./Descargas/Kali_Linux.png)

Una vez clickeado en el boton "Download", deberia de aparecer una pagina similar a la siguiente foto, en la cual debemos de elegir el sistema opertaivo en el cual vamos a descargar el programa. Nosotros haremos click en el recuadro de "VirtaulBox", mas precisamente en el boton que tiene el simbolo de "descarga".

![VirtualBox](./Descargas/Kali_Linux_sist_operativo.png)

___

## Comencemos a configurar nuestra maquina virtual

Apenas iniciemos nuestra aplicacion de virtual box, y deberia de aparecer una ventana similar a la siguiente foto. 

![VirtualBox](VirtualBox-Inicio.png)

En esta instancia, apretariamos el boton "Nueva" para crear una nueva maquina virtual y se nos desplegaria una ventana similar a la siguiente foto.

![Creación maquina](./Configuración%20Maquina%20Virtual/Primer-Ventana.png)

<!--Quiero hacer una lista -->
En esta ventana, debemos de elegir:</br>
1. El nombre que tendra nuestra maquina virtual. Este nombre lo veremos al iniciar nuestra aplicación de Virtual Box.</br>
2. La carpeta donde se guardar la informacion de nuestra maquina virtual.</br>
3. Dentro de "Imagen ISO", debemos de elegir el archivo que hemos descargado anteriormente. (el ".iso")</br>

Después de haber completado esos campos, le daremos al boton de "Siguiente" para seguir configurando nuesta maquina virtual.

![Creación maquina](./Configuración%20Maquina%20Virtual/Segunda-Ventana.png)

En esta ventana, configuraremos la memoria ram y la cantidad de procesadores que queremos asignar a nuestra maquina virtual. De esto depende la velocidad de nuestro sistema operativo, por lo que es importante elegir la cantidad adecuada para nuestro sistema operativo, aunque después de tener configurado nuestra maquina, tambien podremos cambiar esta parte de la configuración</br>
Una vez tengamos todo listo, le daremos al boton de "Siguiente" para seguir configurando nuesta maquina virtual.

![Creación maquina](./Configuración%20Maquina%20Virtual/Tercer-Ventana.png)

En esta ventana, configuraremos la cantidad de espacio en el disco duro que queremos asignarle a nuestra maquina virtual. Esto va a depender mucho del ususario, ya que depende de la cantidad de datos que queremos guardar en nuestra maquina virtual.</br>
Una vez tengamos todo listo, le daremos al boton de "Siguiente" para seguir configurando nuesta maquina virtual.

![Creación maquina](./Configuración%20Maquina%20Virtual/Ventana-Comprobacion.png)

Esta es la ultima ventana que tendremos antes de tener nuestra maquina lista y sirve para ver los valores que hemos configurado. Si todo ha ido bien, le daremos al boton de "Terminar" para crear nuestra maquina virtual.
___

## Configurando Kali Linux

Una vez creada nuestra maquina virtual, debemos de entrar a ella para poder configurar su sistema. Para ello, debemos de hacer click en el boton "Iniciar" de la maquina virtual que hemos creado. Una vez dentro de nuestra maquina virtual, deberia de aparecer una ventana similar a la siguiente foto.</br>
NOTA: En esta sección solo podremos navegar entre las diferentes opciones con las flecha de nuestro teclado y para seleccionar una opción, debemos de presionar "Enter".</br>

![Iniciar maquina](VirtualBox-Inicio-Con-Maquina.png)

Una vez dentro de nuestra maquina virtual, tendremos para elegir entre distintas opciones para configurar nuestro sistema operativo.</br>
Por defecto, vendra marcada la primera opción, pero nosotros queremos seleccionar "Start Installer".

<!-- Reemplazar esta imagen por una que no tenga lo de "Autocapturar teclado"-->
![Selccionar opciones](./Configuración%20Kali%20Linux/Kali_Selector.png)

Aqui, escogemos el idioma que queremos que nuestro sistema use, en este caso, elegimos Español.

![Selccionar Idioma](./Configuración%20Kali%20Linux/Kali_Idioma.png)

Aqui, escogemos la ubicación donde queremos que nuestro sistema use, en este caso, elegimos "Uruguay".

![Selccionar Ubicación](./Configuración%20Kali%20Linux/Kali_Ubicacion.png)

Aqui, escogemos el teclado que queremos que nuestro sistema use, en este caso, elegimos "LatinoAmericano".

![Selccionar Teclado](./Configuración%20Kali%20Linux/Kali_Teclado.png)

Aqui, escogemos el nombre que queremos que nuestro sistema use, en este caso, elegimos "kali".

![Selccionar Nombre Maquina](./Configuración%20Kali%20Linux/Kali_Nombre_Maquina.png)

Aqui, escogemos el nombre de dominio que queremos que nuestro sistema use, en este caso, elegimos "Kali".

![Selccionar Nombre Dominio](./Configuración%20Kali%20Linux/Kali_Nombre_Dominio.png)

Aqui, escogemos el nombre de usuario que queremos que nuestro sistema use, en este caso, elegimos "k4l1".

![Selccionar Nombre Usuario](./Configuración%20Kali%20Linux/Kali_Nombre_Usuario.png)

Aqui, escogemos la contraseña que queremos que nuestro sistema use. Recuerde guardar esta contraseña, ya que la necesitaremos para acceder a nuestra maquina virtual.

![Selccionar Contraseña](./Configuración%20Kali%20Linux/Kali_Contraseña.png)

Aqui, simplemente escogeremos la opción 1 "Guiado - utilizar todo el disco", ya que es la forma sencilla de hacerlo.

![Selccionar Disco](./Configuración%20Kali%20Linux/Kali_Disco.png)

Aqui escogeremos el disco que querramos utilizar para guardar la información. En mi caso, al solo tener un disco, solo tengo una opción, pero depende de cada maquina y donde el usuario quiera guardar la información.</br>
**NOTA:** Lo que dice acerca de que se borrara la información, solo sucede en caso de que el sistema se este instalando como sistema principal, pero en nuestro caso que estamos instalando como una maquina virtual, no se borrará la información.

![Selccionar Disco](./Configuración%20Kali%20Linux/Kali_Disco2.png)

Aqui escogeremos la primera opción ya que es la recomendada para novatos. El resto de la opciones son opciones avanzadas.

![Selccionar Disco](./Configuración%20Kali%20Linux/Kali_Disco3.png)

Aqui escogeremos la opción de "Finalizar el particionado (...)", para poder continuar con la configuración del sistema.

![Selccionar Disco](./Configuración%20Kali%20Linux/Kali_Disco4.png)

Cuando aparezca esta foto, seleccionarmeos la opción "Si" para que se escriban las opciones de configuración que fuimos seleccionando en el correr de esta configuración.

![Selccionar Disco](./Configuración%20Kali%20Linux/Kali_Disco5.png)

Aqui le daremos a la opción "Si" para que se instalen los paquetes que necesitamos para nuestro sistema operativo.

![Selccionar Gestor de Paquetes](./Configuración%20Kali%20Linux/Kali_Gestor_Paquetes.png)

En esta pantalla, deajremos el espacio en blanco y simplemente le daremos a "Enter", ya que no contamos con la información que se nos pide.

![Selccionar Gestor de Paquetes](./Configuración%20Kali%20Linux/Kali_Gestor_Paquetes2.png)

Aqui le daremos a la opción "Si" para que se instale el cargador de sistema.

![Selccionar Cargador de Arranque](./Configuración%20Kali%20Linux/Kali_Arranque.png)

En esta pantalla selecionaremos el disco que anteriormente configuramos, para que el sistema arranque desde alli.

![Selccionar Cargador de Arranque](./Configuración%20Kali%20Linux/Kali_Arranque2.png)

Finalmente, le daremos a la opción "Si" para que se instale el sistema operativo. La maquina debera reiniciarse para que el sistema quede correctamente instalado.

![Terminado](./Configuración%20Kali%20Linux/Kali_Terminado.png)
___

## Instalando Docker

Una vez dentro de nuestra maquina virtual, tendremos que abrir la terminal. Estando dentro de la terminal, escribiremos:
```
sudo apt update
sudo apt install docker.io
```
Esto nos instalara el docker en nuestra maquina virtual.

![Instalar Docker](./Docker/Instalar-Docker.png)

Si intentamos ejecutar el comando "docker ps" en nuestra terminal para ver los contenedores que tenemos y esta nos muestra un mensaje de error, debemos de ejecutar los siguientes comandos de la forma que se muestra en la siguiente imagen:
```
sudo usermod -aG docker ${USER}
su - ${USER}
sudo usermod -aG docker "nombre de usuario"
```
Esto nos dara permisos para que nuestro usuario pueda ejecutar el comando "docker" en nuestra terminal.

![Super usuario Docker](./Docker/Super-usuario-Docker.png)

Después de tener permisos para ejecutar el comando "docker", debemos de descargar la imagen de docker que queremos que nuestro contenedor use. Para ello, debemos ejecutar el siguiente comando:
```
docker pull bkimminich/juice-shop //Esto nos descargara la imagen de docker.

NOTA: Esta linea se puede ejecutar con cualquier usuario, no solo con el superusuario como muestra la foto de abajo.
```
Una vez ejecutada ese comando, podes ejecutar:
```
docker image ls //Esto nos mostrara las imagenes que tenemos en nuestra maquina virtual.
```

![Super Usuario Docker](./Docker/Descarga-Imagen-Contenedor-Docker.png)

Una vez tengamos la imagen descargada, es hora de cresr el contenedor en base a la imagen anteriormente descargada. Para ello, debemos ejecutar una de las siguientes lineas de comandos:
```
docker run -d -p 8000:3000 --name juice-shop bkimminich/juice-shop 

docker run -d -p 8000:3000 bkimminich/juice-shop //Esto nos creara el contenedor en nuestra maquina virtual.

NOTA: La diferencia entre ellas es "--name", que nos permite darle un nombre al contenedor.
```
Esto nos creara y arrancara el contenedor en nuestra maquina virtual.
```
docker start juice-shop //Esto arrancara el contenedor en nuestra maquina virtual.
```
Finalmente, para ver el sitio web que tenemos en nuestra maquina virtual, debemos de acceder a la siguiente direccion:
[http://localhost:8000/](http://localhost:8000/)</br>

![Creacion Contenedor Docker](./Docker/Creacion-Contenedor-Docker.png)

### Comenzar o Detener el funcionamiento de un contenedor

Después de tener creado el contenedor, podemos arrancarlo utilizando el sisguiente comando:
```
docker start {NAME or CONTAINER ID} //CONTAINER ID, se encuentra en la tabla y es otra forma de iniciar o finalizar el contenedor en caso de no habrle puesto un nombre. 
```

Para finalizar el contenedor, debemos de ejecutar el siguiente comando:
```
docker stop {NAME or CONTAINER ID} 
```
![Detener Contenedor](./Docker/Detener-Contenedor-Docker.png)
___

## Instalando ZAP

Esta es una herramienta que ya puede venir instalada en nuestra maquina virtual, pero si queremos instalarla, debemos de descargarla desde el siguiente link: 
[https://www.zaproxy.org/download/](https://www.zaproxy.org/download/)</br>
Una vez en la pagina, debemos seleccionar el sistema operativo que queremos que nuestra maquina virtual use, en este caso, elegimos "Linux Installer".

![Descarga ZAP](./ZAP/Descarga-ZAP.png)


Una vez descargado, debemos de ejecutar los siguientes comandos para instalar el software en nuestra maquina virtual como se muestra en la imagen de abajo.
```
sudo su //Para que el comando sea ejecutado con el superusuario.

cd/Downloads

ls      //Es opcion, pero sirve para ver los archivos que se encuentran dentro de la carpeta que estamos posiscionados.

chomd +x ZAP_2.15_0_unix.sh //Esto nos permitira ejecutar el archivo que descargamos.

ZAP_2.15_0_unix.sh //Esto nos instalara el software en nuestra maquina virtual.


```
Esto nos instalara el software en nuestra maquina virtual.

![Instalacion ZAP](./ZAP/Instalacion-ZAP.png)

___






