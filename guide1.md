# Study Guide: Chapter 1 - Computer Networks: A Systems Approach

## Introduction
Welcome to the study guide for Chapter 1 of the textbook "Computer Networks: A Systems Approach" by Larry Peterson and Bruce Davie. This guide will help you understand the fundamental concepts of computer networks and provide you with questions and exercises to reinforce your understanding. Let's get started!

### Required reading
Sections: 1.1, 1.2, 1.3 and 1.5 

## 1. Building a Scalable Network
- What are the key considerations when building a scalable network?

• Planear y diseñar con anticipación: entender las necesidades actuales y futuras de la organización para la cual se construya la red, incluyendo el posible crecimiento de usuarios, dispositivos y tráfico de datos. De igual manera es importante tomar en cuenta el ancho de banda y memoria para manejar cargas mayores. A parte es importante implementar un tipo de red que sea eficiente, por ejemplo packet-switched network. La red debe soportar multicast y broadcast. 

• Escalabilidad de hardware: invertir en routers y switches que permitan manejar mayor tráfico de datos sin interrupciones, y también que tengan la posibilidad de hacer escalamiento vertical y horizontal. Es importante que soporte QoS para priorizar el tráfico crítico y garantizar un rendimiento constante. 

• Escalabilidad de protocolos: desarrollar protocolos de enrutamiento que puedan escalar con el tamaño y la complejidad de la red. También se pueden aplicar estándares de Ethernet que admitan velocidades más altas.

- Explain the concept of network scalability and why it is important.

Es la capacidad de una red para manejar una cantidad cada vez mayor de tráfico, usuarios, dispositivos o recursos manteniendo su rendimiento, eficiencia y confiabilidad, es decir que la red tiene la capacidad de expandirse según sea necesario sin interrupciones o una caída significativa en la calidad del servicio

Es importante tener escalabilidad de la red porque a medida que la organización o empresa crece, su infraestructura de red debe crecer con ella, ya que debe adaptarse a la subida de la demanda de servicios y transferencia de datos. Además que esto permite tener una mayor eficiencia pues los recursos como ancho de banda, potencia de procesamiento o almacenamiento, se asignan de forma dinámica en función de la demada, lo que evita que los tiempos de respuesta a los usuarios sean muy grandes en momentos donde existe congestión en la red, lo que es increíblemente importante en servicios de tiempo real. Por último, cuando existen fallos en la red, una red escalable puede re dirigir el tráfico y los recursos para mantener la conectividad y disponibilidad del servicio, lo que ayuda a reducir la pérdida de datos y el tiempo de inactividad 

- Provide examples of different applications that require a scalable network.

• Plataformas de redes sociales: estas plataformas deben acomodar a millones de usuarios que constantemente suben contenido como fotos y videos, pero que también realizan comunicación en tiempo real. Por lo que una red escalable permite que los recursos de estas plataformas crezcan con el número de usuarios 

• Online gaming: los juegos multiplayer en línea requieren conexiones de baja latencia y gran ancho de banda. Las redes escalables garantizan que los servidores de juegos puedan manejar una cantidad alta de jugadores simultáneos. 

• Educación y E-learning: las plataformas de educación en linea, deben manejar inicios de sesión de estudiantes, videoconferencias en tiempo real, y entrega de contenido simultáneos. Las redes escalables son vitales para brindar una experiencia de aprendizaje adecuada.

• Plataformas de video entretenimiento: las plataformas de entretenimiento, como netflix, suben cientos de películas diferentes diariamente en diferentes países, y la demanda de estas plataformas de igual manera crece todos los días. Las redes escalables aseguran que se puedan almacenar archivos multimedia de gran tamaño y que los usuarios tengan una experiencia sin interrupciones.


- Why does a network need to be cost-effective, fair, and have robust connectivity?

Construir y mantener una red es costoso, por lo que la rentabilidad de la misma garantiza que los recursos se utilicen de manera eficiente, ayudando a minimizar los gastos al mismo tiempo que se brindan los servicios requeridos. Es decir, para el operador de red, es indispensable manejar los costos de manera efectiva para asegurar la viabilidad a largo plazo del negocio de la red, incluyendo la optimización de inversiones en infraestructura, consumo de energía y gastos operativos. Además las redes rentables son meas fácilmente escalables, mientras crece la demanda, debería ser posible expandir la capacidad de la red sin aumentar los costos desproporcionalmente. 

Debe existir equidad en la red, en la cual se traten de manera igualitaria a los usuarios y aplicaciones, asegurando que nadie experimente discriminaciones o ventaja indebida. También es importante que exista neutralidad en la red, en donde no existe preferencia por ciertos tipos de datos, contenidos o servicios. Todo lo anteriormente mencionado se puede garantizar con la implementación de mecanismos de QoS que prioricen el tráfico crítico o urgente y al mismo tiempo asegure que el tráfico de menor prioridad siga recibiendo un servicio aceptable.

 Se necesita que la red tenga una conectividad robusta para que los usuarios puedan acceder a los servicios de forma confiable y sin interrupciones, lo que es crucial para mantener la satisfacción y confianza del usuario. Las redes robustas en varios casos implementan redundancia en varios niveles, incluido el hardware, los centros de datos y las rutas de comunicación, lo que ayuda a minimizar los puntos únicos de falla. Es de vital importancia que la red se mantenga activa incluso en periodos de alta demanda y  estrés de la red, es decir que la red mantenga consistencia, y además sea resilience ante todo tipo de retos, como fallos en el hardware o ciber ataques. 


- Discuss the challenges involved in designing a network that can support various applications.

Primero, se debe tomar en cuenta si la aplicación es de tipo streaming, no streaming o tiempo real, pues cada una es enviada y leída de una manera distinta, ya que algunas se consumen de manera continua y las interrupciones en la misma son indeseadas porque generan trabas, además que el tiempo de respuesta es más estricto en otras. 

Debe implementarse en la red también QoS, para poder asegurar que existan una repartición justa de recursos, como ancho de banda, para controlar la calidad del servicio, lo que permite gestionar y optimizar la entrega de datos a través de la red.

El siguiente requerimiento para una red es que las aplicaciones corriendo en el host conectadas a una red deben poder comunicarse de manera significativa. Para que se logre esta comunicación se deben implementar servicios comunes y luego cada diseñador debe crear su app usando estos servicios 


## 2. Computer Network Architecture
- Define computer network architecture in terms of layers and protocols

Un computer network es un marco estructurado que define cómo se organizan e interactúan los diversos componentes de una red. Se describe en términos de capas y protocolos, donde cada capa realiza funciones específicas y se comunica con las capas superiores e inferiores. El modelo más común es el modelo OSI (Open Systems Interconnection), que consta de siete capas. Otro modelo muy utilizado es el modelo TCP/IP, que tiene cuatro capas. 

Los protocolos son componentes clave en la arquitectura de redes de computadoras. Son conjuntos de reglas y convenciones que rigen la comunicación entre dispositivos en una red. Los protocolos se implementan en diferentes capas de la arquitectura de red para proporcionar servicios específicos y garantizar que la comunicación sea eficiente y confiable


- Why are layers and protocols important?

Son importantes por diversos motivos:

• Modularización y abstracción: las capas permiten la modularización de la funcionalidad de la red, lo que simplifica su diseño e implementación. Cada capa realiza un conjunto específico de tareas y las capas se construyen una encima de la otra. En cada una de ellas se oculta las implementaciones de las capas inferiores, para dar abstracción, así se facilita la gestión y la comprensión de las operaciones de la red.

• Interoperabilidad: los protocolos estandarizados garantizan la interoperabilidad entre diferentes dispositivos de red y software de varios fabricantes, así se pueden comunicar de forma eficiente

• Escalabilidad: al dividir la funcionalidad de la red en capas, es más fácil escalar una red a medida que crece. Se pueden agregar o actualizar componentes en capas específicas sin afectar necesariamente a otras capas. 

•  Eficiencia y rendimiento: los protocolos optimizan el rendimiento de la red proporcionando una transmisión de datos y un manejo de errores eficientes. Los diferentes protocolos garantizan una transferencia de datos confiable o una transmisión de datos de alta velocidad


- What is encapsulation, multiplexing and demultiplexing?


  
- Discuss the role of each layer in the OSI and Internet protocol stack.



- Provide examples of protocols used at each layer of the TCP/IP protocol stack.



## 3. Performance
- Why is important to keep track of the performance of a network?
- What are the main metrics we use to measure network performance?
- Give some examples of the challenges of using different metrics in high speed networks


## Exercises
1. Calculate the total time required to transfer a 1000-KB file in the following cases, assuming an RTT of 50 ms, a packet size of 1 KB data, and an initial 2 × RTT of “handshaking” before data is sent:

    a. The bandwidth is 1.5 Mbps, and data packets can be sent continuously.

    b. The bandwidth is 1.5 Mbps, but after we finish sending each data packet we must wait one RTT before sending the next.
    
    c. The bandwidth is “infinite,” meaning that we take transmit time to be zero, and up to 20 packets can be sent per RTT.
    
    d. The bandwidth is infinite, and during the first RTT we cansend one packet ($2^{1−1}$), during the second RTT we can send two packets ($2^{2−1}$), during the third we can send four ($2^{3−1}$), and so on
    
2. For each of the following operations on a remote file server, discuss whether they are more likely to be delay sensitive or bandwidth sensitive:

    a. Open a file.

    b. Read the contents of a file.
    
    c. List the contents of a directory.
    
    d. Display the attributes of a file.
    
3. Suppose a host has a 1-MB file that is to be sent to another host. The file takes 1 second of CPU time to compress 50% or 2 seconds to compress 60%.

    a. Calculate the bandwidth at which each compression option takes the same total compression + transmission time.
    
    b. Explain why latency does not affect your answer

4. . Discuss the relative performance needs of the following applications in terms of average bandwidth, peak bandwidth, latency, jitter, and loss tolerance:
    
    a. File server.
    
    b. Print server.
    
    c. Digital library.
    
    d. Routine monitoring of remote weather instruments.
    
    e. Voice.
    
    f. Video monitoring of a waiting room.
    
    g. Television broadcasting.


```python

```
