# Study Guide: Computer Networking Chapter 5 and Chapter 6



### Required reading
Sections: 5.1, 5.2, 6.1, 6.2, and 6.3

## Computer Networking Study Guide

### End-to-End Protocols

1. What is the purpose of end-to-end protocols in computer networking?

Son esenciales para una comunicación confiable y eficiente entre dispositivos a través de una red. Su función principal incluye garantizar la integridad de los datos, donde realizan comprobaciones de errores y solicitan la retransmisión de datos si es necesario, lo que ayuda a mantener la precisión de los datos transmitidos.

Otra función clave es proporcionar una transmisión confiable. Garantizan que los paquetes de datos enviados sean recibidos por el destino en el orden correcto, sin pérdidas ni daños. Además, manejan el control de flujo, regulando la velocidad de transmisión de datos para evitar la congestión de la red y asegurar un uso eficiente de los recusos de la red, evitando sobrecarga en la mimsa.

2. Explain the difference between connection-oriented and connectionless protocols.

Los protocolos orientados a la conexión, como TCP, requieren un proceso de configuración inicial para establecer una conexión entre el remitente y el receptor antes de transmitir cualquier dato. Esta configuración, que implica un mecanismo de protocolo de enlace, es crucial para definir los parámetros de la sesión de comunicación. Estos protocolos son confiables, ya que mantienen el estado de la conexión, monitorean la transmisión de paquetes de datos y brindan funciones como verificación de errores o retransmisión de paquetes perdidos. También gestionan el control del flujo y la congestión, lo que los hace ideales para aplicaciones donde la integridad y el orden de los datos son esenciales, como la navegación web, el correo electrónico y las transferencias de archivos.

Por el contrario, los protocolos sin conexión, como UDP, no requieren una conexión preestablecida. Cada paquete de datos se envía de forma independiente, sin un protocolo de enlace ni un estado de sesión mantenido. La transmisión de datos es más rápida y eficiente, sin embargo, no es tan confiable, ya que no garantiza que los paquetes de datos lleguen en orden o lleguen en absoluto, y normalmente no existe ningún mecanismo para reconocer los paquetes recibidos o retransmitir los perdidos. Esto los hace adecuados para aplicaciones de transmisión de medios o juegos en línea.

3. What are the advantages and disadvantages of using end-to-end protocols?

Ventajas

- Confiabilidad: proporcionan mecanismos para verificar errores y retransmitir paquetes perdidos, lo que garantiza una transmisión de datos confiable.

- Integridad y orden de los datos: garantizan que los datos se reciban tal como se enviaron, sin corrupción y en el orden correcto.

- Control de flujo: gestionan la velocidad a la que se envían los datos, evitando que el receptor se vea abrumado por datos que llegan más rápido de lo que se pueden procesar.

- Multiplexing: admiten múltiples aplicaciones de red que se ejecutan simultáneamente, administrando de manera eficiente múltiples flujos de datos.

- Seguridad: incorporan funciones de seguridad como cifrado y autenticación, lo que garantiza una transmisión de datos segura. 

Desventajas

- Gastos generales: establecer y mantener conexiones, verificación de errores y otros mecanismos de confiabilidad pueden generar gastos generales significativos, lo que genera ineficiencias.

- Latencia: establecer de conexiones, junto con los mecanismos de confiabilidad y control de flujo, puede introducir latencia, lo que es problemático para aplicaciones en tiempo real

- Complejidad: implementar y gestionar protocolos de un extremo a otro puede resultar complejo debido a la necesidad de manejar diversos aspectos como la corrección de errores, la secuenciación y el control de flujo.

- Uso intensivo de recursos: mantener la información de estado, como el estado de la conexión y el seguimiento de paquetes, requiere memoria y potencia de procesamiento adicionales.

4. How does the Internet Protocol (IP) provide end-to-end delivery?

El IP es esencial para la entrega de datos de un extremo a otro a través de Internet, aunque no garantiza confiabilidad en la entrega. La función principal del IP es el direccionamiento y el enrutamiento. Asigna direcciones únicas a cada dispositivo de la red, que son cruciales para identificar dispositivos y guiar los paquetes de datos desde su origen hasta su destino. Además, IP emplea enrutamiento de red descentralizado, donde los enrutadores deciden de forma independiente las mejores rutas para el reenvío de paquetes, adaptándose dinámicamente a los cambios en el estado de la red.

Sin embargo, IP es un protocolo sin estado, lo que significa que trata cada paquete de forma independiente y no mantiene información sobre el historial de paquetes, lo que contribuye a la escalabilidad y solidez de Internet. Admite la fragmentación y el reensamblaje, descomponiendo paquetes grandes para ajustarlos a las restricciones de la red y reensamblándolos en su destino. La interoperabilidad de IP también es clave, ya que permite que varias redes y dispositivos se comuniquen sin problemas. 


5. What is the role of the Transport Layer in end-to-end protocols?

La capa de transporte es parte integral de la comunicación de un extremo a otro, cerrando la brecha entre la capa de aplicación y la capa de Internet de nivel inferior. Su función principal es proporcionar servicios de comunicación a las aplicaciones, permitiéndoles enviar y recibir datos sin preocuparse por la infraestructura de red subyacente. La clave para su funcionamiento es la provisión de una transferencia de datos confiable, particularmente en protocolos orientados a conexión.

Además, la capa de transporte gestiona el control de flujo, regulando la velocidad de transmisión de datos para evitar que el receptor se vea abrumado. También desempeña un papel fundamental en el control de la congestión, ayudando a prevenir sobrecargas de la red y a mantener un funcionamiento eficiente de la red. Puede manejar datos de múltiples aplicaciones simultáneamente mediante la asignación de identificadores únicos a diferentes flujos de datos.

### UDP

1. What is UDP and how does it differ from TCP?

UDP es un protocolo sin conexión, por lo que no establece una conexión dedicada antes de enviar datos. Esto hace que UDP sea más rápido y eficiente para aplicaciones donde la velocidad es más importante que la precisión. UDP envía datagramas, sin esperar la confirmación del receptor y no proporciona corrección de errores. Si un paquete se pierde o se daña, UDP no lo reenvía. Además, UDP carece de control de flujo, lo que permite enviar datos en cualquier momento sin tener en cuenta la capacidad del receptor para procesarlos. Esto lo hace adecuado para aplicaciones en tiempo real donde la latencia es un factor crítico.

TCP es un protocolo orientado a la conexión. Requiere que se establezca una conexión entre el remitente y el receptor antes de la transmisión de datos, lo que garantiza un canal de comunicación confiable, eficiente y sin congestión. TCP es responsable de la verificación y corrección de errores; retransmite paquetes perdidos o dañados hasta que se reciben correctamente. Además, TCP incorpora control de flujo y congestión, ajustando la velocidad de transmisión de datos en función de la capacidad de la red y las capacidades de procesamiento del receptor. 

2. Explain the advantages and disadvantages of using UDP.

Ventajas
 
 - Gastos bajos: UDP es liviano y tiene un costo mínimo de protocolo. No requiere configuración de conexión, lo que simplifica el protocolo y reduce los datos que se envían.

- Velocidad: debido a su simplicidad, permite una transmisión de datos más rápida. Esto lo hace adecuado para aplicaciones donde la velocidad es más importante que la confiabilidad.

- Sin control de congestión: puede enviar datos continuamente sin preocuparse por la congestión de la red ya que no la implementa

- Aplicaciones en tiempo real: su velocidad y baja latencia hacen que UDP sea ideal para aplicaciones en tiempo real como juegos en línea o transmisiones en vivo

Desventajas

- Poco confiable e inseguro: no garantiza la entrega, el orden o la integridad de los datos. No existe ningún mecanismo para reconocer los datos recibidos, retransmitir paquetes perdidos o detectar errores, lo que puede provocar la pérdida o corrupción de datos.

- Falta de control de flujo: sin control de flujo, un remitente puede abrumar a un receptor enviando paquetes más rápido de lo que pueden procesarse, lo que provoca la pérdida de paquetes.

- Susceptibilidad a la congestión: dado que UDP no gestiona la congestión, podría provocar pérdida de paquetes y un rendimiento degradado para todos los usuarios de la red.

- Sin funciones de seguridad integradas: carece de mecanismos de seguridad integrados, lo que puede ser una preocupación para las aplicaciones que requieren una transmisión de datos segura.

3. How does UDP handle error detection and correction?

UDP adopta un enfoque simple hacia la detección y corrección de errores, favoreciendo la velocidad y la eficiencia sobre la confiabilidad de la transmisión de datos. Incorpora un mecanismo básico de detección de errores mediante sumas de comprobación. Cada paquete UDP incluye un campo de suma de verificación, calculado por el remitente en función del contenido del paquete. En el destino, el receptor vuelve a calcular esta suma de verificación para comprobar la integridad de los datos. Si las sumas de verificación coinciden, los datos se consideran válidos; en caso contrario indica posibles errores durante la transmisión.

En términos de corrección de errores, UDP carece de capacidades inherentes. No hay funciones para la retransmisión o el acuse de recibo de paquetes, lo que significa que UDP no proporciona confirmación de la entrega de paquetes ni mantiene el orden de los paquetes. Esta ausencia contribuye a la eficiencia de UDP, ya que reduce la sobrecarga y la latencia.

4. What are some common applications that use UDP?

- Servicios de transmisión: UDP se utiliza para servicios de transmisión de video y audio. En streaming, mantener un flujo continuo de datos es más importante que garantizar la entrega de cada paquete. La baja latencia de UDP se adapta a la naturaleza del streaming en tiempo real.

- Juegos en línea: en juegos en línea multijugador, se prefiere UDP porque reduce la latencia y el retraso. La transmisión rápida de datos del estado del juego es crucial para una experiencia de juego perfecta, incluso si eso significa una pérdida ocasional de datos.

- Voz sobre IP (VoIP): aplicaciones como Skype y otros servicios de VoIP utilizan UDP para transmitir datos de voz. La prioridad aquí es mantener la comunicación en tiempo real, donde los retrasos causados ​​por las retransmisiones de paquetes serían perjudiciales.

- Transmisiones de difusión y multidifusión: UDP admite modos de transmisión de difusión y multidifusión, es buena opción para aplicaciones que envían datos a múltiples destinatarios simultáneamente, como en algunos tipos de sistemas de videoconferencia o servicios de distribución de información.
  
5. Discuss the role of ports in UDP communication.

En la comunicación UDP, los puertos sirven como componentes esenciales para dirigir el flujo de datos entre diferentes aplicaciones. Cada paquete UDP incluye dos campos de puerto en su encabezado: el puerto de origen y el puerto de destino. Este sistema de identificación de puertos permite que UDP admita la comunicación bidireccional de manera eficiente, asegurando que los paquetes de datos lleguen a la aplicación deseada en un dispositivo.

Los puertos en UDP facilitan la multiplexación, permitiendo que múltiples aplicaciones utilicen recursos de red simultáneamente en una única interfaz de red física o dirección IP. Esto se logra asignando números de puerto únicos a diferentes aplicaciones o servicios. Existen puertos estandarizados conocidos para servicios comunes y puertos efímeros para sesiones temporales iniciadas por aplicaciones cliente. Dado que UDP es un protocolo sin conexión, no mantiene ningún estado de conexión para los puertos, lo que simplifica la gestión de los puertos. Cada paquete UDP se trata de forma independiente, y los puertos actúan como identificadores simples para enrutar datos. 

### TCP

1. What is TCP and why is it considered a reliable protocol?

TCP es un protocolo que proporciona una entrega de datos confiable, ordenada y con verificación de errores. Como protocolo orientado a conexión, establece una conexión dedicada antes de que comience la transmisión de datos y la mantiene hasta que se completa el proceso de comunicación. Esto se inicia mediante un mecanismo de protocolo de enlace, lo que garantiza que tanto el remitente como el receptor estén preparados para el intercambio de datos. La confiabilidad de TCP se debe a su secuenciación de datos, donde a cada byte de datos se le asigna un número de secuencia, lo que permite al extremo receptor reordenar los segmentos que llegan fuera de secuencia y solicitar la retransmisión de cualquier dato perdido.

La confiabilidad de TCP se ve reforzada por sus mecanismos de detección y corrección de errores. Emplea sumas de verificación para validar la integridad de los paquetes de datos y, en caso de detectar errores, TCP descarta el paquete erróneo y activa una retransmisión. Además, TCP gestiona el control del flujo, ajustando la velocidad de transmisión de datos en función de la capacidad de procesamiento del receptor y de la red, lo que evita abrumar al receptor..


2. Explain the three-way handshake process used by TCP to establish a connection.

El protocolo de enlace de tres vías es un mecanismo central de TCP que se utiliza para establecer una conexión confiable entre un cliente y un servidor en una red. Este proceso comienza cuando el cliente envía un paquete SYN al servidor, indicando su intención de establecer una conexión e incluyendo un número de secuencia inicial (ISN). Este número de secuencia es crucial para organizar el orden de los paquetes. Al recibir este paquete, el servidor responde con un paquete SYN-ACK . Este paquete tiene dos propósitos: reconoce el paquete SYN del cliente al incluir un número de confirmación, y también incluye el propio ISN del servidor. Este intercambio garantiza que ambas partes estén listas para la comunicación y acuerden los números de secuencia iniciales.

El paso final del protocolo de enlace implica que el cliente envíe un paquete ACK (reconocimiento) al servidor, reconociendo el paquete SYN-ACK del servidor. Este reconocimiento se indica mediante la inclusión del ISN más uno del servidor. Con este intercambio se establece la conexión, lo que permite una transmisión de datos fiable. Este proceso de protocolo de enlace de tres pasos es fundamental para el funcionamiento de TCP, ya que configura los parámetros necesarios para una conexión y garantiza que tanto el cliente como el servidor estén sincronizados antes de que comience cualquier transferencia de datos real. 

3. How does TCP handle flow control and congestion control?

TCP es esencial para garantizar una transmisión de datos confiable y eficiente a través de Internet y lo hace mediante dos mecanismos: control de flujo y control de congestión.

- Control de flujo: gestiona la transferencia de datos entre el remitente y el receptor para evitar que el remitente abrume al receptor. Se realiza mediante sliding window. Ambas partes acuerdan un tamaño de ventana, que es la cantidad máxima de datos no reconocidos permitidos en tránsito. La ventana se ajusta a medida que se envían y confirman los datos, lo que permite al remitente enviar solo una cantidad de datos que el receptor puede manejar en un momento dado.

- Control de Congestión: gestiona el volumen de datos en toda la red para evitar sobrecargarla. Utiliza un conjunto de algoritmos para este propósito, comenzando con Slow Start, donde empieza con una pequeña ventana de congestión y luego la aumenta gradualmente. Esta ventana crece exponencialmente hasta que se alcanza un umbral o se produce una pérdida de paquetes, lo que indica una posible congestión de la red. Luego, cambia a Evitar la congestión, donde el aumento del tamaño de la ventana se vuelve lineal. En caso de pérdida de paquetes, TCP utiliza mecanismos como Fast Retransmit y Fast Recovery para manejar las retransmisiones y recuperarse de la pérdida de paquetes sin reducir drásticamente el tamaño de la ventana. Sin embargo, en escenarios de congestión severa indicados por tiempos de espera, TCP puede reducir significativamente la ventana de congestión e iniciar nuevamente el proceso de inicio lento.

En esencia, el control de flujo se centra en la relación emisor-receptor, garantizando que los datos se envíen a un ritmo manejable, mientras que el control de congestión se ocupa del tráfico general de la red, ajustando la velocidad de transmisión de datos para evitar la congestión de la red. Ambos sistemas son vitales para el funcionamiento fluido y eficiente de las comunicaciones TCP.

4. Discuss the advantages and disadvantages of using TCP.
5. What are some common applications that rely on TCP for communication?



### Congestion Control

1. What is congestion control and why is it important in computer networks?
2. Discuss the various congestion control algorithms used in TCP.
3. How does TCP react to congestion in the network?
4. What are some techniques used to measure and detect network congestion?


### TCP and Sliding Window


1. What is the sliding window protocol and how does it improve the efficiency of data transmission?
2. Explain the concept of window size in TCP and its impact on network performance.
3. How does TCP handle acknowledgments and retransmissions using the sliding window protocol?
4. Discuss the advantages and disadvantages of using the sliding window protocol.
5. What are some techniques used to optimize the sliding window protocol?



## Exercises

1. Consider a simple UDP-based protocol for requesting files (based somewhat loosely on the Trivial File Transport Protocol, or TFTP). The client sends an initial file request, and the server answers (if the file can be sent) with the first data packet. Client and server then continue with a stop-and-wait transmission mechanism.

    (a) Describe a scenario by which a client might request one file but get another; you may allow the client application to exit abruptly and be restarted with the same port.

    (b) Propose a change in the protocol that will make this situation much less likely.

2. The sequence number field in the TCP header is 32 bits long, which is big enough to cover over 4 billion bytes of data. Even if this many bytes were never transferred over a single connection, why might the sequence number still wrap around from 232 − 1 to 0?

3. The Nagle algorithm, built into most TCP implementations, requires the sender to hold a partial segment’s worth of data (even if PUSHed) until either a full segment accumulates or the most recent outstanding ACK arrives.
    
    (a) Suppose the letters abcdefghi are sent, one per second, over a TCP connection with an RTT of 4.1 seconds. Draw a timeline indicating when each packet is sent and what it contains.
    
    (b) If the above were typed over a full-duplex Telnet connection, what would the user see?

    (c) Suppose that mouse position changes are being sent over the connection. Assuming that multiple position changes are sent each RTT, how would a user perceive the mouse motion with and without the Nagle algorithm?

4. Suppose two hosts A and B are connected via a router R. The A–R link has infinite bandwidth; the R–B link can send one packet per second. R’s queue is infinite. Load is to be measured as the number of packets per second sent from A to B. Sketch the throughput-versus-load and delay-versus-load graphs, or if a graph cannot be drawn, explain why. Would another way to measure load be more appropriate?

5. Suppose that between A and B there is a router R. The A–R bandwidth is infinite (that is, packets are not delayed), but the R–B link introduces a bandwidth delay of 1 packet per second (that is, 2 packets take 2 seconds, etc.). Acknowledgments from B to R, though, are sent instantaneously. A sends data to B over a TCP connection, using slow start but with an arbitrarily large window size. R has a queue size of one, in addition to the packet it is sending. At each second, the sender first processes any arriving ACKs and then responds to any timeouts.

    (a) Assuming a fixed TimeOut period of 2 seconds, what is sent and received for T = 0, 1, . . . , 6 seconds? Is the link ever idle due to timeouts?

    (b) What changes if TimeOut is 3 seconds instead?
