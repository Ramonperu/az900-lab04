# Redes Virtuales Azure
*Diciembre 21 de 2022*, Ramón Peinado Ruiz



A continuación disponemos de una guía para la realización de una red virtual en Azure la cual constara con 2 maquinas virtuales una Windows y una Windows Server 2019.

Planteamiento en diagrama

<img src="/img/1ºimagenn.png" alt="1ºimagenn" style="zoom: 80%;" />

## Paso 1:

### Creación del grupo de recursos:

Hemos de crear un grupo de recursos donde se encontraran todos nuestros elementos, accederemos mediante el portal de azure

***Home -> Resource Groups -> Create***

Nombramos el grupo y selecionamos la region de Azure

<img src="/img/2ºimagenn.png" alt="2ºimagenn"  />

<img src="/img/3ºimagenn.png" alt="3ºimagenn"  />

Por ahora no vamos a seleccionar etiquetas, clickamos en ***Review and Create*** para que se despliegue nuestro nuevo grupo de recursos

## Paso 2:

### Creación de la maquina virtual de Windows Server 2019:

Tras crear el grupo de recursos podemos empezar creando la red o con las maquinas virtuales.

Elegimos empezar haciendo las maquinas entonces deberemos de crear la red al mismo tiempo que editamos los parámetros de nuestro maquina.

Accedemos a nuestro grupo de recursos

***Home -> Resource Groups -> RG-Vnet3***

Y creamos la maquina buscandola en el marketplace dentro de nuestro recurso

<img src="/img/4ºimagenn.png" alt="4ºimagenn"  />

Obligatoriamente hemos de asociar la maquina a **un grupo de recursos**, darle un **nombre**, indicar la **región**, la **imagen** que preseleccionamos en el marketplace, los **discos** de los cual dispondrá, un **usuario y una contraseña** y los **puertos de entrada** que queremos abrir

<img src="/img/5ºimagenn.png" alt="5ºimagenn" style="zoom:150%;" />

En este caso en concreto abriremos el puerto 80 nombraremos a la maquina 1Wserv19 y seleccionaremos los discos de menor facturación 

**DISCOS**

Seleccionaremos los discos Standard SSD's

<img src="/img/6ºimagenn.png" alt="6ºimagenn" style="zoom:150%;" />

**RED**

Como hemos comenzado creando primero la maquina ahora deberemos crear la red dentro de este menú  y asociarle los datos correspondientes

Creamos una red nueva y se nos muestra el siguiente menú:

<img src="/img/7ºimagenn.png" alt="7ºimagenn" style="zoom:150%;" />

Nombramos a la subred subnet01 y modificamos el rango de ips 10.0.0.0/20, la subred tendrá el siguiente rango 10.0.0.0/24



Asignación nombre y parámetros ip publica

<img src="/img/8ºimagenn.png" alt="8ºimagenn" style="zoom:150%;" />

**NSG**

Network Security Group

Abrimos puerto HTTP y RDP (80, 3389)

**TAGGING O ETIQUETAS**

Hemos de acostumbrarnos a asociar los recursos a unas etiquetas para poder identificarlos de manera mas simple, creamos este proyecto para el Dpto de Marketing

<img src="/img/9ºimagenn.png" alt="9ºimagenn" style="zoom:150%;" />

Tras esto damos esto en review + create y se nos mostrara un resumen con los datos con los que hemos diseñado nuestra maquina, creamos y tardara unos minutos en desplegar nuestra maquina.

<img src="/img/10ºimagenn.png" alt="10ºimagenn" style="zoom:150%;" />

## Paso 3:

### Creación de la maquina virtual de Windows 10:

Nuevamente dentro del grupo de recursos vamos al marketplace y buscamos maquina virtual

Le asociamos ***el nombre usuario contraseña, red y subred ya creadas, ip publica y tags y el NGS*** igual que el anterior pero sin el puerto 80 abierto ya que no lo necesitamos en el W10

<img src="/img/11ºimagenn.png" alt="11ºimagenn" style="zoom:150%;" />

## Paso 4:

### Admin Center en el WServ19

Ingresamos al apartado de Windows Admin Center dentro de la configuración de nuestra maquina y abrimos nuestros puerto 6516 tickando las 2 opciones e instalamos

<img src="/img/12ºimagenn.png" alt="12ºimagenn" style="zoom:150%;" />

También necesitaremos el admin center en nuestra maquina local, a la hora de instalarlo via ejecutable nos salto un error y debimos de instalarlo con este comando

*msiexec -i WindowsAdminCenternºversion.msi productLanguage="1033"*

**CONFIGURACION EXTRA WServer2019**

Añadimos el admin center en la maquina virtual de Azure, lo asociamos en nuestro admin center local con el ***TENANT ID***.

Tras esto se nos conectara con nuestra cuenta de Azure, iniciaremos sesión y se nos pedirá identificar la suscripción grupo de recursos y maquina.



Por ultimo hemos de revisar la pertenencia al rol "Windows Admin Center Administrator Login" Role dentro de Acces control (IAM)

<img src="/img/13ºimagenn.png" alt="13ºimagenn" style="zoom:150%;" />



**Windows Defender**

Habilitamos dentro de cada maquina las reglas  ICMP(En W10 y Wserv) para habilitar el ping en LAN entre nuestros equipos

Dentro de WServ19 añadimos ***roles y características de Web Services*** IIS

Comprobamos en lan y editamos la pagina a traves de esta ruta *C:\inetpub\wwwroot* **via CMD**

<img src="/img/14ºimagenn.png" alt="14ºimagenn" style="zoom:150%;" />

**DIAGRAMA FINAL**

<img src="/img/16ºimagenn.png" alt="16ºimagenn" style="zoom:150%;" />

## Paso 4:

### Control coste

Apagamos las maquinas y comprobamos que solo tarife el almacenamiento de estas mismas



<img src="/img/15ºimagenn.png" alt="15ºimagenn" style="zoom:150%;" />
