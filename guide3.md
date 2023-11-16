# Study Guide: Computer Networking Chapter 3



### Required reading
Sections: 3.1, 3.2 (except 3.2.2), 3.3, and 3.4

## Switching Basics

### Questions:
1. What is switching in computer networking?

Es proceso de reenviar o dirigir paquetes de datos de un dispositivo de red a otro (fuente a destino) o de una red a otra, usando switches. Tiene lugar en la capa de enlace de datos del modelo OSI. El switching de paquetes sucede inmediatamente después de la generación de paquetes de datos en la capa física. 


2. Explain the difference between circuit switching and packet switching.

• Circuit switching
- Establece una ruta de comunicación dedicada entre dos dispositivos durante la duración de su conversación.

- El ancho de banda de la ruta de comunicación está reservado para los participantes durante toda la conversación, incluso si no están transmitiendo datos activamente.

- En ejemplo son las redes telefónicas tradicionales

• Packet switching:

- Los datos se dividen en paquetes antes de su transmisión. Luego, cada paquete se envía individualmente al destino, donde se vuelven a ensamblar en los datos originales.

- Permite que múltiples paquetes de diferentes fuentes compartan los mismos recursos de red.

- Hay dos tipos principales: switching sin conexión (datagramas) y switching orientada a conexión (virtual circuit switching).

- En los datagramas cada paquete se trata de forma independiente y puede tomar una ruta diferente para llegar al destino.

- En virtual circuit switching, se establece una conexión antes de la transferencia de datos y los paquetes siguen una ruta predeterminada.


3. What are the advantages of packet switching over circuit switching?

• Eficiencia: packet switching es más eficiente en la utilización de los recursos de la red, ya que permite que múltiples paquetes de diferentes fuentes compartan la misma infraestructura de red simultáneamente. En cambio, circuit switching reserva una ruta dedicada durante toda la conversación

• Escalabilidad: packet switching es altamente escalable, ya que a medida que aumenta la cantidad de dispositivos y el tráfico de datos, puede adaptarse más fácil dividiendo y administrando los datos en paquetes.

• Flexibilidad: packet switching es más flexible en el manejo de diferentes tipos de tráfico de datos, ya que admite velocidades de datos variables y  varios tipos de aplicaciones, incluidas voz, video y texto. Circuit switching está optimizada para un tipo específico de tráfico y adaptarse a diferentes tipos de datos puede resultar complicado.

• Resiliencia: packet switching es más resistente, dado que los paquetes pueden tomar diferentes caminos para llegar a su destino, la falla de un único enlace o nodo de red no necesariamente interrumpe toda la comunicación. Por el contrario, circuit switching pueden experimentar un fallo total de comunicación si se interrumpe una ruta dedicada.

4. What is a switch? How does it differ from a hub?

Un switch es un componente de hardware en la infraestructura de red que facilita la conexión de varios dispositivos, como computadoras y servidores, opera en la capa de enlace de datos (Capa 2). Actúa como un policía de tráfico, dirigiendo eficientemente paquetes de datos entre dispositivos conectados, con el uso de direcciones MAC, lo que lo hace más avanzado que un hub. Mantiene una tabla de direcciones MAC que asocia las direcciones con los puertos físicos, permitiéndoles enviar datos solo al dispositivo específico al que están destinados.

Determina de forma inteligente el destino de cada paquete y evita la interferencia entre dispositivos y les permite compartir la red sin problemas. Crean dominios de colisión separados para cada puerto, reduciendo la probabilidad de colisiones y mejorando el rendimiento de la red. Usa comunicación full-duplex, lo que facilita la transmisión y recepción simultánea de datos en un puerto.

Un hub es el dispositivo más básico que sirve como centro de una red de área local (LAN). Aquí cada dispositivo conectado está en la misma subred y recibe todos los datos enviados al hub. Luego, el centro envía esos datos a todos los demás dispositivos conectados, creando un sistema para compartir datos entre usuarios.

No tiene tablas de enrutamiento ni inteligencia sobre dónde enviar información y transmite todos los datos de la red a través de cada conexión. Puede detectar errores básicos de red, como colisiones, pero no transmitir toda la información a múltiples puertos, lo que causa cuellos de botella. En el pasado, los concentradores de red eran populares porque eran más baratos que un conmutador o enrutador. 

5. Describe the process of switching a packet within a switch.

Funciona de la siguiente manera:

• Llegada del paquete: cuando un paquete llega a uno de los puertos del switch, este examina el encabezado del paquete para extraer información crucial, como las direcciones MAC de origen y destino.

• Búsqueda de tabla de direcciones MAC: el switch consulta su tabla de direcciones MAC para determinar el puerto asociado con la dirección MAC de destino. Esta tabla se crea y se mantiene dinámicamente a medida que los dispositivos se comunican a través del switch.

• Aprendizaje de direcciones: si la dirección MAC de destino no se encuentra en la tabla, el switch aprende agregando una entrada para la dirección MAC de origen y el puerto correspondiente a través del cual llegó el paquete.

• Decisión de reenvío: si la dirección MAC de destino ya está en la tabla, el switch reenvía el paquete directamente al puerto apropiado. Si no, el switch puede hacer flooding del paquete a todos los puertos

• Reenvío de paquetes: el switch reenvía el paquete al puerto determinado, asegurando que los datos lleguen al destino previsto. Este proceso se produce a velocidad de cable, lo que permite que sea de alta velocidad y baja latencia.

• Actualizar la tabla de direcciones MAC: después de reenviar exitosamente el paquete, el switch actualiza su tabla de direcciones MAC para reflejar la asociación de puerto y origen más reciente. Esto garantiza que los paquetes futuros destinados a la misma dirección se puedan reenviar de manera más eficiente.


6. What is store-and-forward switching? How does it ensure data integrity?

Es una técnica de switching de red en la que un dispositivo de red recibe y almacena la trama de datos completa antes de reenviarla al siguiente dispositivo de la red. En este proceso, el switch examina toda la trama en busca de errores, descarta las tramas con errores y solo reenvía tramas sin errores. 

Así garantiza la integridad de los datos:

• Recepción de frames: el switch recibe la trama de datos completa antes de comenzar el proceso de reenvío. Esto incluye el encabezado, los datos y el avance del marco.

• Comprobación de errores: el switch realiza una verificación de errores en la trama recibida, utilizando la secuencia de verificación de trama (FCS), que es una suma de comprobación, en el avance de la trama.

• Almacenamiento de marcos: si la trama pasa la verificación de errores, el switch almacena la trama completa en su memoria intermedia.

• Decisión de reenvío: después de almacenar la trama y confirmar su integridad, el switch toma una decisión de reenvío basándose en la dirección de destino de la trama. Luego, comienza a reenviar la trama al puerto de salida apropiado.

La integridad de los datos se asegura mediante la recepción completa y almacenamiento del marco de datos, seguido de una verificación de errores. Solo los marcos libres de errores se reenvían, garantizando que la integridad de los datos se mantenga a lo largo de la red. Este enfoque contribuye a la detección y corrección de errores, evitando la propagación de datos corruptos en la red.


### Exercises:
1. Compare and contrast the performance characteristics of circuit switching and packet switching.

• Utilización de recursos:

- Circuit switching: uso ineficiente de los recursos, ya que se reserva una ruta dedicada durante toda la conversación, independientemente de si los datos se transmiten activamente.

- Packet switching: utilización más eficiente de los recursos, ya que el ancho de banda se comparte entre varios usuarios, lo que permite una asignación dinámica según la demanda.

• Latencia:

- Circuit switching: menor latencia ya que la ruta dedicada se establece antes de que comience la transmisión de datos.

- Packet switching: mayor variabilidad de latencia debido al procesamiento de almacenamiento y reenvío y posibles retrasos en las colas. 

• Adaptabilidad:

- Circuit switching: menos adaptable a velocidades de datos variables y patrones de tráfico en ráfagas. Adecuado para flujos de datos continuos.

- Packet switching: Altamente adaptable a diferentes tipos de datos, velocidades de datos variables y patrones de tráfico en ráfagas.

• Previsibilidad:

- Circuit switching: rendimiento predecible y estable para flujos de datos continuos.

- Packet switching: el rendimiento puede ser menos predecible, especialmente durante períodos de congestión de la red.

• Escalabilidad:

- Circuit switching: escalabilidad limitada ya que se requiere una ruta dedicada para cada conversación, lo que la hace menos adecuada para redes con una gran cantidad de dispositivos.

- Packet switching:ltamente escalable, lo que la hace adecuada para redes con numerosos dispositivos.

2. Research and list three different types of switches commonly used in computer networks.

• Eternet switch: son el tipo más común de conmutadores utilizados en LAN. Operan en la capa de enlace de datos (Capa 2) y utilizan direcciones MAC para reenviar tramas de datos a los dispositivos apropiados dentro de la misma red. Los conmutadores Ethernet son cruciales para crear LAN eficientes y de alto rendimiento.

• Multilayer switch: opera tanto en la capa de enlace de datos (Capa 2) como en la capa de red (Capa 3)  Además del reenvío basado en direcciones MAC, puede tomar decisiones de enrutamiento basadas en direcciones IP. Combinan las funciones de un switch y un hub, ofreciendo eficiencia y rendimiento mejorados.

• Managed switch : brindan características y capacidades más avanzadas que los unmanaged switches. Optimizan el rendimiento de la red, monitorean el tráfico e implementan medidas de seguridad. Admiten funciones como VLAN, QoS y duplicación de puertos, lo que proporciona un mayor control de la red


3. Design a simple network topology using switches to connect multiple computers. Label the switches and computers in your diagram.

<img width="367" alt="Captura de pantalla" src="https://github.com/emiliasaenz/emiliasaenz/assets/143628612/4b1fb086-8ac4-4672-9781-13279780c621">

• Es una topología en estrella donde todas las computadoras están conectadas a un switch central (Switch 1).

• El switch B está conectado al switch A, creando una estructura jerárquica.

• Las computadoras 1 y 2 están conectadas directamente al Switch 1

## Switched Ethernet

### Questions:
1. What is Ethernet? How does it work?



2. Explain the concept of a collision domain in Ethernet.



3. What are learning bridges?



4. Explain the Spanning Tree Algorithm




5. What are VLANs?


## Internet (IP)

### Questions:
1. What is the Internet Protocol (IP)? How does it work?



2. Explain the difference between IPv4 and IPv6.



3. What is an IP address? How is it structured?



4. What is the purpose of subnetting in IP addressing?



5. Describe the process of IP packet forwarding.



6. What is the role of the Internet Control Message Protocol (ICMP) in IP?




### Exercises:
1. Convert the following IPv4 address to binary: 192.168.0.1.
2. Research and list three different classes of IP addresses.
3. Configure a computer to use a static IP address. Document the steps you followed.

## Routing

### Questions:
1. What is routing in computer networking?
2. Explain the difference between static routing and dynamic routing.
3. What is a routing table? How is it used in the routing process?
4. What is the purpose of a default gateway in routing?
5. Describe the process of routing a packet from source to destination.



## Exercises

![net](./network.png)

1. For the network given in figure above, show how the link-state algorithm builds the routing table for node D.
