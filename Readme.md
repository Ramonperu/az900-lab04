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

Como hemos comenzado creando primero la maquina ahora deberemos crear la red dentro de este menu  y asociarle los datos correspondientes
