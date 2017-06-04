


#Redes de computadoras

Un conjunto de computadoras conectadas para compartir información u otros recursos es una **red** de computadoras. En cualquier red se distinguen por lo menos tres elementos de hardware:

- Las computadoras conectadas se llaman **hosts** o nodos terminales.
- Los **enlaces** que conectan las computadoras. Los enlaces suelen llamarse **punto a punto** cuando conectan únicamente dos nodos, o **compartidos** cuando al mismo enlace se conectan más de dos nodos.
- Otros **nodos intermedios**, los **routers**, que sirven para encaminar el tráfico de información entre los nodos terminales.

Para utilizar la red, todos los nodos que están conectados a ella, ya sean terminales o intermedios, corren software de red como **protocolos** y **aplicaciones de red**. Los protocolos son, por un lado, convenciones que establecen con todo detalle cómo se realiza una comunicación, y por otro lado, los componentes de software que implementan esa forma de comunicación. 

Las aplicaciones de red son aplicaciones **distribuidas**, es decir, se componen de al menos dos partes, preparadas para comunicarse unas con otras, y esas partes funcionan en nodos terminales de la red diferentes. Cada aplicación de red utiliza un protocolo, porque la interacción entre las partes debe estar perfectamente determinada para que los nodos se entiendan sin errores ni ambigüedades. Un protocolo puede ser utilizado por varias aplicaciones.

Hoy, la mayoría de las redes están interconectadas por una única red global llamada **Internet**. Para conectarse a Internet, todos los nodos, terminales e intermedios, ejecutan un protocolo básico llamado **IP (Internet Protocol)**, y se puede decir que, desde el punto de vista del software, constituyen una sola red. 

Sin embargo, desde el punto de vista de la administración, dentro de Internet existen numerosas redes. Cada red es propiedad de una persona u organización que tiene el control sobre los nodos y enlaces de esa red, decide qué nodos pertenecen o no pertenecen a ella, y qué protocolos y aplicaciones utilizan. 

Estas diferentes redes se pueden clasificar por su tamaño. 

- Una red cuyos límites (o **diámetro**) son pequeños, se llama una **red de área local o LAN (Local Area Network)**. Típicamente, una LAN está contenida en una oficina, piso o edificio.
- Una red que abarca el área de una ciudad (y por lo tanto, cuyos enlaces utilizan espacios públicos) suele llamarse **red metropolitana o MAN (Metropolitan Area Network)**.
- Una red mayor, que cubre distancias entre ciudades, países o continentes, se llama una **red de área extensa o WAN (Wide Area Network)**. Las redes de los **proveedores de servicios de Internet (ISPs)** suelen clasificarse como WANs.


##Switches 
En las redes de área local, o LAN, encontramos enlaces compartidos. El cableado de una oficina, un aula o un edificio suele ser un único medio de comunicación compartido por todos los nodos de la red. El cableado se concentra en un punto de conmutación llamado **switch** o, justamente, conmutador, que distribuye el tráfico entre los nodos conectados. Un switch tiene muchas **interfaces** donde se conectan cables punto a punto hacia los nodos de la LAN. 

Es posible conectar switches entre sí para mejor distribución del tráfico, formando una **topología** de estrella o de árbol. Todo el conjunto de switches y enlaces de la LAN constituye un enlace compartido, ya que todos los nodos de la LAN pueden comunicarse a través de él.

Los switches y los nodos de las redes de área local ejecutan un protocolo de enlace definido por la norma **IEEE 802.3**. Este protocolo deriva de uno anterior, llamado **Ethernet**. Aunque el diseño original de Ethernet era diferente del de 802.3, y el hardware sobre el que funcionaba Ethernet era muy diferente del de los switches actuales, este nombre de Ethernet sigue usándose informalmente para las redes construidas con switches 802.3.

Un switch 802.3 conduce unas unidades de tráfico básicas, los **frames o tramas** 802.3, entre los nodos de la red de área local, conectados al enlace compartido formado por todos los switches y cableado de la LAN. La misión de este protocolo de enlace termina donde termina la red de área local. Los frames o tramas jamás salen fuera de la LAN. Por eso decimos que la función de **nivel de enlace** de una red es entregar el tráfico **entre nodos adyacentes**. Es decir, los que se encuentran sobre el mismo enlace.



##Routers
Suele definirse a Internet como "red de redes". 
Las redes mayores, y en particular Internet, se componen interconectando redes a través de enlaces, a veces de gran longitud. 
Entre cada dos de estas redes siempre existe un **router**.  

El router presta el servicio que no alcanza a prestar el nivel de enlace, que es el de enviar el tráfico fuera de la red de origen. El nivel al que pertenecen los routers se llama **nivel de red**.

Los routers son los elementos que toman las decisiones de **enrutamiento** o ruteo, al determinar por cuál de sus interfaces, a veces muchas, debe ser enviada la información que reciben. Esta tarea de enrutar la información se cumple mediante software de enrutamiento. 

El hardware y el sistema operativo de los routers pueden estar altamente especializados en la tarea de ruteo, pero también es perfectamente posible construir un router a partir de una computadora corriente de escritorio y un sistema operativo multipropósito. Es decir que los routers no son sino computadoras, con un sistema operativo y un hardware similares a los que encontramos en muchas otras computadoras, pero dedicadas a la tarea del enrutamiento. 

Dependiendo del ambiente donde deben trabajar y de la cantidad de tráfico que deben procesar, los routers pueden adoptar muchas formas físicas y tamaños.

- Los routers pueden ser pequeños y baratos, para uso doméstico. 


- Algunos pueden dar servicio a muchos nodos terminales al incluir múltiples dispositivos de nivel de enlace, como un switch 802.3 de varias interfaces, y un **punto de acceso** para una **red inalámbrica** secundaria basada en tecnología de radio.


- Algunos, de muy altas prestaciones, usados por los proveedores de servicios de Internet, son **modulares** y pueden ser configurados a medida de las necesidades. Cada módulo contiene **interfaces** especializadas en alguna tecnología de enlace, lo que les permite conectar redes de tecnologías completamente diferentes.



##Interfaces

La interfaz es el punto de conexión entre un enlace y un nodo de la red. Es la pieza de hardware que convierte bits a señales capaces de viajar por la red, y viceversa. Cuando un nodo debe comunicar algo a otro, prepara su mensaje, de una cantidad dada de bytes, en una zona de la memoria, y entrega esos contenidos a la interfaz a través de un bus de comunicación. 

La interfaz contiene el hardware necesario para traducir ese **tren de bits** a señales eléctricas (cuando los enlaces son cableados), de radio (cuando el enlace es inalámbrico), o luminosas (cuando el enlace es de fibra óptica). 

Las modernas interfaces de red pueden funcionar a **velocidades de transmisión** de muchos bits por segundo. Una LAN cableada actual funciona comúnmente en velocidades de 1 a 10 Gbps (gigabits por segundo). Una LAN inalámbrica suele funcionar a una velocidad de transmisión mucho menor.

El tren de bits viaja en forma de señales físicas por el enlace hasta llegar a la interfaz del nodo destino dentro de la red de área local. La interfaz receptora decodifica las señales, recuperando los bits originales y comunicándolos al software que espera los datos. Ambas partes de la aplicación distribuida se han comunicado un mensaje.


##Enlaces
Las tecnologías de construcción de los enlaces son muchas. 

- Cuando las señales se codifican mediante impulsos eléctricos, como en las redes de cables de **par trenzado** o **coaxial**, el medio es un conductor como el cobre.  
- Para distancias mayores (como las transoceánicas) o para ambientes donde existe mucho **ruido** o interferencia electromagnética (como en fábricas), se utiliza **fibra óptica**.
- Cuando no es posible, o práctico, tender un cable, no queda más solución que utilizar emisiones de **radio**. Ejemplos de tecnologías de radio son los enlaces satelitales, los de microondas, y las LAN inalámbricas bajo norma **802.11** conocidas popularmente como **WiFi**.


Las principales compañías de conectividad del mundo tienden enlaces de fibra óptica transoceánicos. Como la instalación de estos cables es una maniobra muy compleja y tiene un costo altísimo, se aseguran de instalar capacidad de transmisión en abundancia. Por ejemplo, uno de estos enlaces tiene una capacidad de 3.2 Tbps, lo que permitiría transmitir el contenido completo de un disco rígido de 1 TB en menos de tres segundos. Esta capacidad es compartida entre varios proveedores de Internet que compran el servicio de transporte.


En el pasado también se usaron los enlaces satelitales para resolver el problema de cubrir grandes distancias. Los satélites son repetidores de radio colocados en órbita. Reciben emisiones de una estación terrena y la comunican a otra, distante, superando el problema de la curvatura terrestre que no permitiría la propagación en línea recta de la emisión de radio. 

Su principal inconveniente es la alta latencia o retardo en la llegada de la señal desde un punto a otro, debido a las grandes distancias que la señal debe recorrer. Paulatinamente van siendo abandonados en favor de la fibra óptica para comunicación de datos. Sin embargo, siguen siendo una buena solución para atravesar áreas continentales, o para distribuir tráfico hacia muchos puntos simultáneos de bajada, como los medios de comunicación televisivos (aplicación llamada **broadcasting**).












































































