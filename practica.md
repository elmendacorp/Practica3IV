#Práctica 3
Gestión y comparación de máquinas virtuales

## Introducción
En esta práctica lo que haremos será montar diferentes sistemas linux orientados a servidores y comprar diferentes montajes y comparando los rendimientos entre ellos para saber como funciona mejor o peor un sistema.
Los sistemas que he elegido son centos, comúnmente utilizado para montar servidores dada su robustez de seguridad y zentyal, una versión edulcorada de ubuntu server orientada y preparada para el montaje de servidores.

##Montaje De las máquinas
Las máquinas van a estar montadas sobre qemu, y usare el gestor de máquinas virtuales para configurarlas, ya que es muy sencillo asignar recursos y montar los almacenamientos y los sistemas, soporta tanto a qemu como lxc, pero después de juju lxc y yo no nos llevamos muy bien que digamos.

Las configuraciones iniciales serán ambas máquinas con 512 Mb de ram y 1 core, el almacenamiento no va a ser determinante ya que al ser sistemas vacios solo ocupan el sistema instalado, con 1 GB será más que suficiente.

Los discos virtuales esta en formato raw, hechos antes de preparar el sistema con qemu. Ambas máquinas se han instalado por red, haciendo uso del adaptador que tiene qemu en el sistema.

Sin mayor problemas los sistemas se han instalado, se pueden alterar las características desde el gestor de máquinas virtuales.

![](https://raw.github.com/elmendacorp/Practica3IV/master/imagenes/instalandomaquinas.png)

![](https://raw.github.com/elmendacorp/Practica3IV/master/imagenes/maquinadebian.png)

![](https://raw.github.com/elmendacorp/Practica3IV/master/imagenes/maquina%20ubuntu.png)

Tras instalar las dos máquinas procedi a instalar apache2 en ambas, y comprobé que ambas máquinas eran accesibles con ping desde la máquina anfitriona que era la que iba a hacer los test.
 En la máquina anfitriona instale apache benchmark, para que las pruebas fueran significativas hice 100000 peticiones con 50 usuarios, La prueba era en local y tenía que tener resultados significativos.
 
 ![](https://raw.github.com/elmendacorp/Practica3IV/master/imagenes/comparativa.png)

## Impresiones y conclusiones
Como podemos ver la maquina de ubuntu server con 1024 MB y 1 core es mejor que la debian, algo que me sorprendió, pero al duplicarle las características a ambas se normalizaron mostrando que eran similares, Para ver cual era la característica que mejoraba notablemente el rendimiento opte por poner la prueba en extremos de ram y procesadores.
Al aumentar los procesadores la mejora de rendimiento fue ínfimo, mientras que al reducir la ram se vio un notable deterioro del rendimiento.

Como conclusión puedo decir que a la hora de servir contenido estático el manejo de la ram del sistema influye proporcionalmente en el rendimiento final del servidor.
