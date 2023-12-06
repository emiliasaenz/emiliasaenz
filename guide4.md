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

4. 
5. What are some common applications that use UDP?
6. Discuss the role of ports in UDP communication.



### TCP

1. What is TCP and why is it considered a reliable protocol?
2. Explain the three-way handshake process used by TCP to establish a connection.
3. How does TCP handle flow control and congestion control?
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
