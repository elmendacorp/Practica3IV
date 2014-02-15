# Practica 3
Gestion y comparación de máquinas virtuales

## Introducción
En esta practica lo que haremos sera montar difentes sistemas linux orientados a servidores y comprar diferentes montajes y comparando los rendimientos entre ellos para saber como funciona mejor o peor un sistema.
Los sistemas que he elegido son centos, comunmente utilizado para montar servidores dada su robustez de seguridad y zentyal, una version edulcorada de ubuntu server orientada y preparada para el montaje de servidores.

## Montaje de las maquinas
Las maquinas van a estar montadas sobre qemu, y usare el gestor de maquinas virtuales para configurarlas, ya que es muy sencillo asignar recursos y montar los almacenamientos y los sistemas, soporta tanto a qemu como lxc, pero despues de juju lxc y yo no nos llevamos muy bien que digamos.

Las configuraciones iniciales seran ambas maquinas con 512 Mb de ram y 1 core, el almacenamiento no va a ser determinante ya que al ser sistemas vacios solo ocuparan el sistema instalado, con 1 GB sera mas que suficiente.

Los discos virtuales esta en formato raw, hechos antes de preparar el sistema con qemu. Ambas maquinas se han instalado por red, haciendo uso del adaptador que tiene qemu en el sistema.

Sin mayor problemas los sistemas se han instalado, se pueden alterar las caracteristicas desde el gestor de maquinas virtuales.
