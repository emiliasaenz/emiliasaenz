# Study Guide: Chapter 1 - Computer Networks: A Systems Approach

## Introduction
Welcome to the study guide for Chapter 1 of the textbook "Computer Networks: A Systems Approach" by Larry Peterson and Bruce Davie. This guide will help you understand the fundamental concepts of computer networks and provide you with questions and exercises to reinforce your understanding. Let's get started!

### Required reading
Sections: 1.1, 1.2, 1.3 and 1.5 

## 1. Building a Scalable Network

1. What are the key considerations when building a scalable network?

• Planear y diseñar con anticipación: entender las necesidades actuales y futuras de la organización para la cual se construya la red, incluyendo el posible crecimiento de usuarios, dispositivos y tráfico de datos. De igual manera es importante tomar en cuenta el ancho de banda y memoria para manejar cargas mayores. A parte es importante implementar un tipo de red que sea eficiente, por ejemplo packet-switched network. La red debe soportar multicast y broadcast. 

• Escalabilidad de hardware: invertir en routers y switches que permitan manejar mayor tráfico de datos sin interrupciones, y también que tengan la posibilidad de hacer escalamiento vertical y horizontal. Es importante que soporte QoS para priorizar el tráfico crítico y garantizar un rendimiento constante. 

• Escalabilidad de protocolos: desarrollar protocolos de enrutamiento que puedan escalar con el tamaño y la complejidad de la red. También se pueden aplicar estándares de Ethernet que admitan velocidades más altas.

- Explain the concept of network scalability and why it is important.

Es la capacidad de una red para manejar una cantidad cada vez mayor de tráfico, usuarios, dispositivos o recursos manteniendo su rendimiento, eficiencia y confiabilidad, es decir que la red tiene la capacidad de expandirse según sea necesario sin interrupciones o una caída significativa en la calidad del servicio

Es importante tener escalabilidad de la red porque a medida que la organización o empresa crece, su infraestructura de red debe crecer con ella, ya que debe adaptarse a la subida de la demanda de servicios y transferencia de datos. Además que esto permite tener una mayor eficiencia pues los recursos como ancho de banda, potencia de procesamiento o almacenamiento, se asignan de forma dinámica en función de la demada, lo que evita que los tiempos de respuesta a los usuarios sean muy grandes en momentos donde existe congestión en la red, lo que es increíblemente importante en servicios de tiempo real. Por último, cuando existen fallos en la red, una red escalable puede re dirigir el tráfico y los recursos para mantener la conectividad y disponibilidad del servicio, lo que ayuda a reducir la pérdida de datos y el tiempo de inactividad 

2. Provide examples of different applications that require a scalable network.

• Plataformas de redes sociales: estas plataformas deben acomodar a millones de usuarios que constantemente suben contenido como fotos y videos, pero que también realizan comunicación en tiempo real. Por lo que una red escalable permite que los recursos de estas plataformas crezcan con el número de usuarios 

• Online gaming: los juegos multiplayer en línea requieren conexiones de baja latencia y gran ancho de banda. Las redes escalables garantizan que los servidores de juegos puedan manejar una cantidad alta de jugadores simultáneos. 

• Educación y E-learning: las plataformas de educación en linea, deben manejar inicios de sesión de estudiantes, videoconferencias en tiempo real, y entrega de contenido simultáneos. Las redes escalables son vitales para brindar una experiencia de aprendizaje adecuada.

• Plataformas de video entretenimiento: las plataformas de entretenimiento, como netflix, suben cientos de películas diferentes diariamente en diferentes países, y la demanda de estas plataformas de igual manera crece todos los días. Las redes escalables aseguran que se puedan almacenar archivos multimedia de gran tamaño y que los usuarios tengan una experiencia sin interrupciones.

 3. Why does a network need to be cost-effective, fair, and have robust connectivity?

Construir y mantener una red es costoso, por lo que la rentabilidad de la misma garantiza que los recursos se utilicen de manera eficiente, ayudando a minimizar los gastos al mismo tiempo que se brindan los servicios requeridos. Es decir, para el operador de red, es indispensable manejar los costos de manera efectiva para asegurar la viabilidad a largo plazo del negocio de la red, incluyendo la optimización de inversiones en infraestructura, consumo de energía y gastos operativos. Además las redes rentables son meas fácilmente escalables, mientras crece la demanda, debería ser posible expandir la capacidad de la red sin aumentar los costos desproporcionalmente. 

Debe existir equidad en la red, en la cual se traten de manera igualitaria a los usuarios y aplicaciones, asegurando que nadie experimente discriminaciones o ventaja indebida. También es importante que exista neutralidad en la red, en donde no existe preferencia por ciertos tipos de datos, contenidos o servicios. Todo lo anteriormente mencionado se puede garantizar con la implementación de mecanismos de QoS que prioricen el tráfico crítico o urgente y al mismo tiempo asegure que el tráfico de menor prioridad siga recibiendo un servicio aceptable.

 Se necesita que la red tenga una conectividad robusta para que los usuarios puedan acceder a los servicios de forma confiable y sin interrupciones, lo que es crucial para mantener la satisfacción y confianza del usuario. Las redes robustas en varios casos implementan redundancia en varios niveles, incluido el hardware, los centros de datos y las rutas de comunicación, lo que ayuda a minimizar los puntos únicos de falla. Es de vital importancia que la red se mantenga activa incluso en periodos de alta demanda y  estrés de la red, es decir que la red mantenga consistencia, y además sea resilience ante todo tipo de retos, como fallos en el hardware o ciber ataques. 


4. Discuss the challenges involved in designing a network that can support various applications.

Primero, se debe tomar en cuenta si la aplicación es de tipo streaming, no streaming o tiempo real, pues cada una es enviada y leída de una manera distinta, ya que algunas se consumen de manera continua y las interrupciones en la misma son indeseadas porque generan trabas, además que el tiempo de respuesta es más estricto en otras. 

Debe implementarse en la red también QoS, para poder asegurar que existan una repartición justa de recursos, como ancho de banda, para controlar la calidad del servicio, lo que permite gestionar y optimizar la entrega de datos a través de la red.

El siguiente requerimiento para una red es que las aplicaciones corriendo en el host conectadas a una red deben poder comunicarse de manera significativa. Para que se logre esta comunicación se deben implementar servicios comunes y luego cada diseñador debe crear su app usando estos servicios 


## 2. Computer Network Architecture
1. Define computer network architecture in terms of layers and protocols

Un computer network es un marco estructurado que define cómo se organizan e interactúan los diversos componentes de una red. Se describe en términos de capas y protocolos, donde cada capa realiza funciones específicas y se comunica con las capas superiores e inferiores. El modelo más común es el modelo OSI (Open Systems Interconnection), que consta de siete capas. Otro modelo muy utilizado es el modelo TCP/IP, que tiene cuatro capas. 

Los protocolos son componentes clave en la arquitectura de redes de computadoras. Son conjuntos de reglas y convenciones que rigen la comunicación entre dispositivos en una red. Los protocolos se implementan en diferentes capas de la arquitectura de red para proporcionar servicios específicos y garantizar que la comunicación sea eficiente y confiable


2. Why are layers and protocols important?

Son importantes por diversos motivos:

• Modularización y abstracción: las capas permiten la modularización de la funcionalidad de la red, lo que simplifica su diseño e implementación. Cada capa realiza un conjunto específico de tareas y las capas se construyen una encima de la otra. En cada una de ellas se oculta las implementaciones de las capas inferiores, para dar abstracción, así se facilita la gestión y la comprensión de las operaciones de la red.

• Interoperabilidad: los protocolos estandarizados garantizan la interoperabilidad entre diferentes dispositivos de red y software de varios fabricantes, así se pueden comunicar de forma eficiente

• Escalabilidad: al dividir la funcionalidad de la red en capas, es más fácil escalar una red a medida que crece. Se pueden agregar o actualizar componentes en capas específicas sin afectar necesariamente a otras capas. 

•  Eficiencia y rendimiento: los protocolos optimizan el rendimiento de la red proporcionando una transmisión de datos y un manejo de errores eficientes. Los diferentes protocolos garantizan una transferencia de datos confiable o una transmisión de datos de alta velocidad


3. What is encapsulation, multiplexing and demultiplexing?

• Encapsulación: es la empaquetación datos en un formato estructurado antes de transmitirlos a través de una red. Este proceso es esencial para garantizar que los datos estén organizados adecuadamente y puedan transmitirse de manera confiable. El formato es un encabezado en donde se incluye información sobre las direcciones de origen y destino, tipo de protocolo y números de secuencia. Los encabezados se utilizan para enrutar y administrar datos mientras viajan a través de una red.

• Multiplexing: es el proceso de combinar múltiples flujos de datos en un solo canal para su transmisión, lo que permite el uso eficiente de recursos de la red. Existen varios tipos:

- Time Division Multiplexing: asigna intervalos de tiempo específicos a diferentes flujos de datos, lo que permite que múltiples señales compartan un solo canal para transmitir.
  
- Frquency Division Multiplexing:  asigna diferentes bandas de frecuencia a varios flujos de datos. Se utilizaen transmisiones de radio y televisión.
  
- Code Division Multiplexing: asigna códigos únicos a cada flujo de datos, lo que les permite coexistir en la misma frecuencia o dominio de tiempo.

• Demultiplexing: separa múltiples flujos de datos de un solo canal según los criterios que se utilizaron durante el proceso de multiplexing, encontrados en el encabezado. Toma un flujo de datos y los separa en sus partes para que cada uno pueda procesarse y entregarse adecuadamente. 

  
4. Discuss the role of each layer in the OSI and Internet protocol stack.

• OSI: tiene 7 capas

- Capa física: encargada de la transmisión de datos sin procesar a través del medio físico.

- Capa de enlace de datos: responsable de la detección y corrección de errores, así como de administrar el flujo de datos entre nodos.

- Capa de red: enruta y reenvía datos entre diferentes redes y subredes, ocupándose del direccionamiento lógico, enrutamiento y topología de red.

- Capa de transporte: gestiona la comunicación extremo a extremo, garantizando una transferencia de datos fiable y ordenada.

- Capa de sesión: establece, mantiene y finaliza conexiones entre aplicaciones, controlando diálogos y la gestión de sesiones.

- Capa de presentación: traduce datos entre la capa de aplicación y las capas inferiores, solucionando problemas de formato de datos y codificación de caracteres.

- Capa de aplicación: ofrece una interfaz entre la aplicación y las capas inferiores, permitiendo servicios de red para las aplicaciones.
  
• Internet Protocol stack: tiene 4 capas:

- Capa de interfaz de red: naneja los aspectos físicos y de enlace de datos en la comunicación de red, incluyendo la encapsulación de paquetes IP en tramas para su transmisión a través del medio físico.

- Capa de Internet: enruta paquetes entre diferentes redes utilizando direccionamiento IP, reenvío de paquetes y protocolos de enrutamiento.

- Capa de transporte: administra la comunicación de extremo a extremo y asegura una transferencia de datos confiable mediante la detección de errores y el control de flujo.

- Capa de aplicación: proporciona servicios de red para aplicaciones e implementa protocolos y servicios específicos de aplicaciones.


5. Provide examples of protocols used at each layer of the TCP/IP protocol stack.

• Capa de interfaz de red:

- Protocolo: Ethernet, es utilizado para redes de área local (LAN) y proporciona un estándar para estructurar datos en paquetes y direccionar dispositivos en la red.

- Protocolo: Point-to-Point Protocol (PPP), establece conexiones punto a punto, como conexiones de marcado y acceso a Internet de banda ancha. Proporciona autenticación, compresión y detección de errores.

- Protocolo: Asynchronous Transfer Mode (ATM), se utilizaba en redes WAN de alta velocidad y en redes de telefonía. Aunque ha disminuido en uso, todavía se encuentra en algunas aplicaciones.

• Capa de Internet:

Protocolo: Protocolo de Internet (IP), es responsable de enrutar paquetes de datos para que puedan viajar a través de diferentes redes y ser entregados a su destino.

Protocolo: Internet Control Message Protocol (ICMP), se utiliza para el control y la generación de mensajes de error y control en la capa de Internet.

Protocolo: Border Gateway Protocol (BGP), es un protocolo de enrutamiento utilizado en Internet para intercambiar información de enrutamiento entre sistemas autónomos. Es crucial para la conectividad de Internet y el enrutamiento entre redes de gran escala.

• Capa de transporte:

Protocolo: Protocolo de control de transmisión (TCP), está orientado a la conexión que proporciona una entrega de datos confiable, ordenada y con verificación de errores. Se usa en correos electrónicos y web browsing

Protocolo: Protocolo de datagramas de usuario (UDP), no requiere conexión y ofrece una transmisión de datos más rápida pero sin la confiabilidad de TCP. Se usa aplicaciones en tiempo real como transmisión de vídeo y juegos en línea.

Protocolo: Stream Control Transmission Protocol (SCTP), combina algunas de las características de UDP y TCP. Ofrece entrega fiable de datos y control de flujo, pero también es adecuado para aplicaciones que requieren múltiples flujos de datos en una única conexión.

• Capa de aplicación:

Protocolo: Protocolo de transferencia de hipertexto (HTTP), se utiliza para transferir páginas web y otros recursos en la WWW. 

Protocolo: Protocolo de transferencia de archivos (FTP), se utiliza para transferir archivos entre un cliente y un servidor en una red. Se usa para cargar y descargar archivos.

Protocolo: Protocolo simple de transferencia de correo (SMTP), se utiliza para enviar mensajes de correo electrónico entre servidores.

Protocolo: Sistema de nombres de dominio (DNS), traduce nombres de dominio en direcciones IP para localizar recursos en Internet.


## 3. Performance
1. Why is important to keep track of the performance of a network?

Realizar un seguimiento del rendimiento de la red es esencial para mantener la eficiencia, la seguridad y la confiabilidad de una red. Permite a las organizaciones responder a los problemas de forma proactiva, optimizar el uso de recursos y mejorar la calidad general de sus servicios de red.

• Resolución proactiva de problemas: permite a los administradores de red identificar y abordar problemas de rendimiento antes de que se conviertan en problemas críticos, lo que minimiza el tiempo de inactividad de la red y las interrupciones de los usuarios.

• Optimización de recursos: cuando se identifican recursos de red subutilizados o sobreutilizados, los administradores pueden asignar ancho de banda, potencia de procesamiento y otros recursos de manera más eficiente.

• Garantizar la calidad de servicio (QoS): se necesitan cumplir requisitos específicos de calidad de servicio, especialmente en aplicaciones en tiempo real, para garantizar una latencia, fluctuaciones y pérdida de paquetes mínimas.

• Seguridad: la supervisión puede detectar actividades de red inusuales o sospechosas, lo que ayuda a identificar posibles violaciones de seguridad, malware o intentos de intrusión. 


2. What are the main metrics we use to measure network performance?

Medir el rendimiento de la red ayuda a los administradores de red  a identificar problemas, optimizar el rendimiento y garantizar que la red cumpla con los requisitos de los usuarios y las aplicaciones. Las principales métricas con el ancho de banda y la latencia, pero también hay otras importantes como el jitter, packet loss o throughput

• Banda ancha: es la velocidad máxima de transferencia de datos de una conexión de red, se mide en bits por segundo (bps). Un gran ancho de banda es esencial para soportar aplicaciones con uso intensivo de datos.

• Latencia: es el tiempo que tardan los datos en viajar desde el origen hasta el destino, se mide en milisegundos (ms). La baja latencia es crucial para aplicaciones en tiempo real. 

• Packet loss: es el porcentaje de paquetes de datos que no llegan a su destino. Una gran pérdida de paquetes puede provocar retransmisiones, lo que afecta negativamente al rendimiento de la red.

• Jitter: es la variación en el retraso de los paquetes recibidos. Se mide en milisegundos y puede provocar problemas en aplicaciones en tiempo real si no se gestiona. 

• Throughput: es la tasa de transferencia de datos real lograda en la red, tiene en cuenta factores como la sobrecarga del protocolo y la congestión de la red. Se mide en bits por segundo (bps) y es un indicador práctico del rendimiento de la red.

3. Give some examples of the challenges of using different metrics in high speed networks 

El uso de diferentes métricas en redes de alta velocidad puede presentar varios desafíos, ya que la elección de las métricas afecta significativamente el análisis del rendimiento de la red y la toma de decisiones. 

• Interpretación de datos inconsistente: diferentes métricas pueden llevar a interpretaciones inconsistentes del rendimiento de la red. Por ejemplo mediciones de latencia y ancho de banda pueden discrepar y generar confusión

• Intensidad de recursos: la captura de paquetes para análisis detallados, pueden consumir muchos recursos, sobrecargando la red y limitando la escalabilidad de las herramientas de monitoreo y análisis.

• Análisis de datos complejos: diferentes métricas pueden requerir herramientas especializadas y experiencia para el análisis. La complejidad del análisis de datos puede ser una barrera para los administradores de red que intentan darle sentido a la información.

• Escalabilidad: las métricas que funcionan bien para redes pequeñas o de tamaño moderado pueden no escalarse de manera efectiva a redes de alta velocidad. Los desafíos de escala pueden afectar el monitoreo y análisis consistentes a medida que la red se expande.

• Condiciones dinámicas de la red: las redes de alta velocidad a menudo experimentan condiciones que cambian rápidamente, como congestión, tráfico en ráfagas y cambios de ruta. Las métricas deben adaptarse a estas condiciones dinámicas para un análisis preciso.


## Exercises
1. Calculate the total time required to transfer a 1000-KB file in the following cases, assuming an RTT of 50 ms, a packet size of 1 KB data, and an initial 2 × RTT of “handshaking” before data is sent:

Packet size = 1KB = 8192 bits

    a. The bandwidth is 1.5 Mbps, and data packets can be sent continuously.

Bandwidth = 1.5 Mps = 1500000 bits/s

- Transmit time per packet:
  
t = size packet / bandwidth

t = 8192 bits / 1500000 bits/s

t = 0.00546 s

- No of packts to be sent 

n = 1000 KB / 1KB

n = 1000

- Transmit time for all packets

tp = Transmit time per packet * No of packts to be sent 

tp = 0.00546 s * 1000

tp = 5.46 s

- Total time

TT = 2 RTT + Transmit time for all packets + RTT/2

TT = 2 * 0.05 s + 5.46 s + 0.005 / 2

TT = 5.58 s 

    b. The bandwidth is 1.5 Mbps, but after we finish sending each data packet we must wait one RTT before sending the next.

Estamos enviando 1000 paquetes, por lo que debemos esperar 999 RTT, por lo que debemos sumar al valor encontrado en a)

- The total time for 999 RTTs

TT = 5.585 s + 999*RTT

TT = 5.585 s + 999 * 0.05 s

TT = 5.585 s + 49.95 s

TT = 55.535 s
    
    c. The bandwidth is “infinite,” meaning that we take transmit time to be zero, and up to 20 packets can be sent per RTT.

Necesitamos enviar 1000 paquetes, luego necesitaremos 1000/20 = 50 RTT para transmitir todos los datos, pero hay que tener en cuenta que para los últimos 20 paquetes solo necesitamos (RTT/2)

Entonces el total de RTTs que necesitamos es 49.5

- Total time = Initial 2 RTT + Required RTTs

TT = 2*RTT + 49.5 * RTT

TT = 51.5 * RTT

TT = 51.5 * 0.05 s

TT = 2.575 s
    
    d. The bandwidth is infinite, and during the first RTT we can send one packet ($2^{1−1}$), during the second RTT we can send two packets ($2^{2−1}$), during the third we can send four ($2^{3−1}$), and so on

Con las ecuaciones dadas tenemos que la cantidad de packets enviados son:

1 + 2 + 4 + ... + 2^n = 2^(n+1) - 1 

Con n = 9 hemos enviado todos los 1000 paquetes

Then total time = Initial 2 RTT + 9 * RTT + 0.5 * RTT

TT = 2 * RTT + 9.5 * RTT

TT = 11.5 * RTT

TT = 11.5 * 0.05 s

TT = 0.575 s


2. For each of the following operations on a remote file server, discuss whether they are more likely to be delay sensitive or bandwidth sensitive:

    a. Open a file.

Es sensible al retraso, ya que los usuarios esperan que los archivos se abran rápidamente después de que lo solicitan. La demora en la apertura de un archivo puede provocar una mala experiencia del usuario. El uso de ancho de banda para abrir un archivo es relativamente bajo en comparación con las operaciones de transferencia de datos.

    b. Read the contents of a file.
    
Es sensible al retraso y al ancho de banda, dependiendo del tamaño del archivo. Para archivos pequeños, la sensibilidad al retraso es más importante porque los usuarios esperan un acceso rápido. En el caso de archivos grandes, ambos factores afectan. El ancho de banda se vuelve crucial cuando se transfiere una cantidad sustancial de datos y los retrasos en la lectura de archivos grandes pueden ser más notorios.
 
    c. List the contents of a directory.

Es sensible al ancho de banda. Si bien los usuarios pueden querer que la operación sea razonablemente rápida, es más importante que el servidor envíe eficientemente la lista de archivos y directorios sin consumir ancho de banda excesivo. 

    d. Display the attributes of a file.

 Es más sensible al retraso. Los usuarios esperan que esta información esté disponible cuando la soliciten y los retrasos pueden resultar frustrantes. La cantidad de ancho de banda utilizado para transmitir atributos de archivos suele ser mínima en comparación con la transferencia de datos de archivos.
    
3. Suppose a host has a 1-MB file that is to be sent to another host. The file takes 1 second of CPU time to compress 50% or 2 seconds to compress 60%.

    a. Calculate the bandwidth at which each compression option takes the same total compression + transmission time.

Option 1: 50% Compression

- Compression Time: 1 second
  
- File Size after Compression: 0.5 MB 
  
- Transmission Time: (0.5 MB) / (Bandwidth)

Option 2: 60% Compression

- Compression Time: 2 seconds
  
- File Size after Compression: 0.4 MB
  
- Transmission Time: (0.4 MB) / (Bandwidth)

Same total compression + transmission time:

1 + (0.5 MB) / (Bandwidth) = 2 + (0.4 MB) / (Bandwidth)


(0.5 MB) / (Bandwidth) - (0.4 MB) / (Bandwidth) = 2 - 1

(0.1 MB) / (Bandwidth) = 1

Bandwidth = 0.1 MB/s

Ambas opciones van a tener el mismo tiempo total cuando el bandwidth sea 0.1 MB/s
 
 
    b. Explain why latency does not affect your answer

La latencia no afecta el tiempo total de transmisión de un archivo, ya que se enfoca en la demora entre el envío y la confirmación de datos. El ancho de banda, que determina la velocidad de transmisión, es lo que importa para la rapidez de la transmisión después de la compresión. En resumen, la latencia no influye en el cálculo del ancho de banda necesario para igualar el tiempo total de transmisión entre diferentes opciones de compresión.

3. . Discuss the relative performance needs of the following applications in terms of average bandwidth, peak bandwidth, latency, jitter, and loss tolerance:
    
    a. File server.

- El ancho de banda promedio para el servidor de archivos no es muy importante, pero debe ser superior a un valor umbral para que pueda admitir una cantidad mínima de transferencias de archivos a la vez.

- El ancho de banda máximo para el servidor de archivos debe ser muy alto, de lo contrario, es posible que no pueda manejar múltiples solicitudes a la vez.
  
- La latencia y el jitter no tienen importancia

- La tolerancia a la pérdida debe ser lo más mínima posible y mayormente equivalente a cero porque la pérdida de datos durante la transferencia de archivos no debe ser tolerable.

    b. Print server.

- El ancho de banda promedio  no son muy importantes en el servidor de impresión. Este valor puede ser significativamente pequeño a menos que se dé la orden de imprimir una página con demasiada frecuencia o que las páginas que se imprimen sean de tamaño muy grande.

- La latencia como el jitter tienen una importancia insignificante

- La tolerancia a la pérdida debe ser mínima, de lo contrario, el comando de impresión no se podrá ejecutar con un documento en el que se hayan perdido algunos paquetes. Si los paquetes perdidos se retransmiten entonces se puede permitir poca tolerancia a la pérdida.
  
    c. Digital library.

- El ancho de banda promedio debe ser bastante bueno
  
- La latencia y el jitter tienen una importancia insignificante.

- La tolerancia a la pérdida debe ser mínima y los datos perdidos deben retransmitirse.
    
    d. Routine monitoring of remote weather instruments.

- Si el instrumento meteorológico remoto transmite datos a intervalos regulares, entonces el ancho de banda promedio es importante 

- La latencia no tiene importancia ya que los informes meteorológicos se generan a intervalos regulares. El jitter también tiene una importancia insignificante.

- Se acepta tolerancia a pérdidas hasta cierto nivel, pero no es necesario retransmitir los datos perdidos.
  
    e. Voice.

- El ancho de banda promedio debe ser alto para voz. La voz se transmite continuamente en el canal y, por lo tanto, se debe garantizar cierto valor de ancho de banda promedio.

- La latencia puede ser pequeña pero debe ser constante.

- El jitter debe ser equivalente a cero. De lo contrario, la salida puede volverse discontinua y ruidosa.

- La tolerancia a la pérdida hasta cierto punto es aceptable, pero provocará una caída en el extremo de salida.

    f. Video monitoring of a waiting room.

- La aplicación de vídeo da importancia al ancho de banda medio

- La latencia de hasta algunos segundos es aceptable.

- El jitter debe ser bajo para obtener una salida de video sin fallas. Si se pierden algunos paquetes, tampoco se crea un impacto significativo en la salida de vídeo.

- La tolerancia a la pérdida puede ser alta 

    g. Television broadcasting.

- Requiere un gran ancho de banda ya que atiende a miles de usuarios a la vez. 

- La latencia puede ser del orden de minutos.

- El jitter no importa siempre que algunos paquetes se almacenen en el búfer en el destino antes de mostrarlos.

- La tolerancia a la pérdida debe ser baja, de lo contrario la salida será discontinua y estará llena de fallos.

```python

```
