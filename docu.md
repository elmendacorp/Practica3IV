# Instalación de un servidor de minecraft en la nube
Disponiendo de la cuenta de azure, procedo a configurar las características del mismo, pudiendo funcionar este tanto en linux como windows, me decanto por windows, ya que al depender de java para su funcionamiento prefiero no arriesgarme.
### Inicio
Características, maquina mediana, 3,5gb de ram y 2 núcleos.
Caracteristicas maáquina pequeña, 1,75Gb de ram y 1 núcleo.
En la configuración de la maquina se instala todo automáticamente, salvo el java que lo hago a mano desde su pagina oficial:[java](http://javadl.sun.com/webapps/download/AutoDL?BundleId=81821).
Para trabajar con el servidor, azure nos da una configuración para usar el escritorio remoto de windows, con el que trabajamos con el servidor como si estuviéramos en local, un gustazo vaya.
![servidor](http://raw2.github.com/elmendacorp/Practica3IV/master/imagenes/conectar.jpg)
Después de esto en la maquina de azure he de configurar los puertos para el servidor,
![https://raw2.github.com/elmendacorp/Practica3IV/master/imagenes/puertos.jpg](https://raw2.github.com/elmendacorp/Practica3IV/master/imagenes/puertos.jpg). Paralelamente descargo desde bukkit, una versión modificada del juego, que le permite cambiar el contenido del mismo así como funciona, [bukkit](http://wiki.bukkit.org/Setting_up_a_server)
![](http://raw2.github.com/elmendacorp/Practica3IV/master/imagenes/Captura1.jpg).

El proyecto es de codigo abierto, de hecho se gestiona en github,
[bukkit](https://github.com/Bukkit/Bukkit)
### Configuración
El propio script de lanzamiento del servidor permite limitar el rendimiento del mismo, que al darle la orden de lanzamiento.
`java -Xmx1024M -jar craftbukkit.jar
PAUSE`
Como punto de partida, ya que hemos configurado el puerto en el que funciona, el cliente es funcional,
![img](https://github.com/elmendacorp/Practica3IV/raw/master/imagenes/corre.PNG)
![juego](https://github.com/elmendacorp/Practica3IV/raw/master/imagenes/juego.PNG)
### Pruebas de ambas máquinas
Ultilizo para ello un benchmark de java, que me permite mantener en ejecución un programa usando todos los recursos durante cierto tiempo, obteniendo así un resumen de como se comportaria una aplicación al maximo dentro de mi sistema.
Benchmark utilizado:
[testjmv](http://sourceforge.net/projects/opt/)
Test máquina con un nucleo:
[test1](https://github.com/elmendacorp/Practica3IV/blob/master/test1)
Test máquina con 2 nucleos:
[test2](https://github.com/elmendacorp/Practica3IV/blob/master/test2.txt)

La configuración de dos núcleos nos da un rendimiento de 444.53691526468117 E6 operaciones aritméticas por segundo, mientras que la de uno 231.03281973069193 E6, con lo que la configuración de dos nucleos nos asegura más fluidez, a la vez que más usuarios en el sistema.
Porque nos basamos en este calculo, minecraft no realiza por parte del servidor ningun tratado de imagenes, sino que solo se limita a operaciones matemáticas para provabilidades de encontrar objetos o calculo de explosiones, pero principalmente para la generacion del terreno o como ellos lo llaman chunks
### Conclusión
Comenzando por 1024 MB de Ram para que java no se colapse, puede dar un alojamiento de hasta 20 usuarios, aunque la principal preocupación era la red del servidor, pero no tenia ningún tipo de problema superando los 50Mb.
El servidor lleva corriendo 2 meses sin sufrir ningún percance, teniendo mas o menor afluencia de gente pero para su función se ha mostrado útil. La mejor prueba es que a día de hoy funciona correctamente.
La configuración que da azure desde el momento 0 podemos decir que no seria la mas acertada, sin embargo los servicios que corren alrededor de la maquina, ya sea el gestor de volúmenes, el firewall, y el gestor de estadísticas, hacen que, al margen de su coste, que en este caso es 0, sea un servicio rápido y sencillo, no distando mas de montar una maquina en local, mucho mas sencillo para mi gusto, solo hay que esperar a que azure instale el sistema operativo y el servidor esta disponible.
