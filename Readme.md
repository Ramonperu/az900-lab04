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

Nombramos a la maquina 1Wserv19, y abrimos el puerto HTTP 80.

Podemos configurar las opciones de disponibilidad y tipos de seguridad y además podremos editar el nombre y contraseña del usuario a nuestro gusto.

Seleccionamos los discos que se adapten a nuestra disponibilidad 

<img src="/img/5ºimagenn.png" alt="5ºimagenn" style="zoom:150%;" />
