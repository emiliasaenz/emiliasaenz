# Study Guide: Computer Networking Chapter 2


### Required reading
Sections: 2.1, 2.2, 2.4, 2.5, 2.6 and 2.7 

## Technology perspective

1. What are the different technologies used for connecting nodes in a computer network?

Las diferentes tecnologías utilizadas para conectar nodos en una red se clasifican en función de varios factores:

•	Según el medio:

-	Copper Wire: incluye diversas formas de cables de cobre como el par trenzado (DLS) y cables coaxiales, que se utilizan para conexiones Ethernet y teléfonos fijos. Ofrecen hasta 100 Mbps de ancho de banda 

-	Fibra óptica: se utiliza para conexiones de fibra hasta el hogar, para conexiones de larga distancia en el backbone del internet y para conexiones que requieren de conexiones de alta velocidad. Ofrecen hasta  1 Gbps de ancho de banda

-	Wireless Links: se utilizan en el aire o el espacio libre como medio, incluyendo el Wi-Fi, redes celulares y tecnologías inalámbricas 

•	Según la frecuencia: las ondas electromagnéticas abarcan un amplio rango de frecuencias, desde ondas de radio hasta luz infrarroja, luz visible, etc. Diferentes bandas de frecuencia se utilizan para diversos fines, incluyendo la transmisión de datos

•	Según el propósito:

- Last-Mile Links: conectan a los usuarios finales a Internet e incluyen tecnologías como DSL, G. Fast y PON. Son formas rentables de proporcionar conectividad a internet a los consumidores

- Backbone links: se utilizan para interconectar ciudades y se basan principalmente en fibra óptica, utilizando tecnología como SONET, para conexiones de alta velocidad y larga distancia 

-	Cellular links: conectan dispositivos móviles a internet y pueden servir como única conexión a internet para hogares u oficinas

-	LANs: son conexiones dentro di un edificio o campus y suelen utilizar tecnologías como Ethernet y Wi-Fi


## Encoding

1. What is encoding in the context of computer networking?

La codificación se refiere al proceso de convertir datos binarios en señales que pueden ser transmitidas a través de un enlace en la red. Se utiliza para que los nodos de la red puedan enviar información de un nodo a otro, a través de las señales que el enlace puede transportar, y posteriormente, decodificar esas señales en datos binarios en el nodo receptor. 

Se trabaja con dos señales discretas: high y low, que pueden corresponder a diferentes voltajes en un enlace. La codificación se realiza para que pueda distinguir entre los valores de 1 y 0 en función de estas señales y asegurar una transmisión efectividad de datos hasta el nodo destino


2. Explain the difference between analog and digital signals.

•	Señales Analógicas: 

-	Las señales analógicas representan datos de una manera continua y puede tomar cualquier valor dentro de un rango continuo.

-	 Pueden corresponder a diferentes voltajes en un enlace basado en cobre, niveles de potencia en un enlace óptico o amplitudes en una transmisión de radio.

-	No hay límites discretos en los valores que puede tomar una señal analógica, lo que significa que pueden tener infinitos valores posibles. Son sensibles al ruido 

-	Son sensibles al ruido y la interferencia, lo que puede hacer que la recuperación de datos sea más complicada 

•	Señales Digitales:

-	Representan datos de manera discreta y toman solo dos valores, de 1 y 0, que son high y low respectivamente o estados de on y off

-	Al tener valores discretos y definidos, facilita la detección de los datos y la recuperación de reloj 

-	Son menos susceptibles al ruido y la interferencia, lo que las hace más robustas en entornos de transmisión complicados


3. Explain the different types of encoding used in computer networks

Los diferentes métodos de codificación son esenciales para representar datos binarios como señales que pueden ser transmitidas a través de enlaces de la red. Los tipos son:

•	NRZ (Non-Return to Zero):

-	La codificación NRZ asigna un valor de datos 1 a la señal alta y un valor de 0 a la señal baja

-	Es un esquema de codificación directo en el que hay una correspondencia directa entre los bits a de datos y los niveles de la señal
 
- El problema con NRZ es que las largas secuencias de 1s o 0s consecutivos pueden dar lugar a problemas como la deambulación de la línea de base y problemas de sincronización de reloj
  

•	NRZI (Non-Return to Zero Inverted):

-	En la codificación NRZI, el remitente realiza una transmisión desde la señal actual para codificar un 1 y permanece en la señal actual para codificar un 0

-	Aborda eficazmente el problema de los 1s consecutivos, pero no ayuda con los 0s consecutivos


•	Manchester Encoding:

-	La codificación Manchester fusiona el clock signal con un data signal 

-	Codifica 0 como una transmisión de bajo a alto y 1 como una transmisión de alto a bajo

-	Asegura que el reloj se pueda recuperar de manera efectiva en el receptor, lo que ayuda con la sincronización del reloj

-	Duplica la velocidad a la que se producen transiciones de señal en el enlace 

•	4B/5B Encoding: 

-	La codificación 4B/5b inserta bits a adicionales en la secuencia de bits a para romper largas secuencias de 0 y 1

-	Cada 4 bits de datos reales se codifican en un código de 5 bitsa que se transmite al receptor 

-	Los códigos de 5 bits están diseñados de manera que no se trasmitan con más de tres 0 consecutivos 

-	Este esquema se utiliza para mejorar la eficiencia de la codificación en un 80%, sin duraciones se señales altas o bajas



## Error Detection

1. What is error detection and why is it important in computer networks?

La detección de errores es el proceso de identificar y reconocer si se han introducido errores o corrupción en los datos a medida que se transfieren a través de una red o cualquier canal de comunicación. Es importante para las redes por diversas razones:

•	Fiabilidad: las redes transmiten información crítica, por lo que se debe asegurar la integridad de los datos para el funcionamiento confiable de las redes

•	Integridad de datos: pueden ocurrir errores durante la transmisión de datos debido a factores como interferencia eléctrica, ruido o problemas de hardware. Detectar estos errores ayuda a garantizar que los datos recibidos sean precisos y no se hayan corrompido

•	Notificación de errores: la detección de errores permite tomar medidas inmediatas. El remitente o el receptor pueden ser informados de que se produjo un error y se pueden tomar medidas para corregir o volver a transmitir los datos

•	Experiencia del usuario final: Los mecanismos de detección de errores ayudan a prevenir escenarios en los que se produzcan errores inesperados para el usuario  y mantienen una experiencia de usuario sin problema

•	Eficiencia: la detección de errores es más eficiente que depender únicamente de la retransmisión, que puede consumir ancho de banda adicional e introducir latencia, lo que es problemático en aplicaciones que requieren tiempos de respuesta rápidos.


2. Explain the concept of parity checking for error detection.

La verificación de paridad es una técnica sencilla de detección de errores comúnmente utilizada en sistemas informáticos, especialmente en sistemas de memoria y almacenamiento. Implica agregar un bit adicional, conocido como bit de paridad, a un grupo de bits. El propósito del bit de paridad es ayudar a detectar errores que pueden ocurrir durante la transmisión o el almacenamiento de datos.

Existen dos tipos principales de verificación de paridad:

•	Paridad Par: aquí el bit de paridad se establece de manera que el número total de 1s,  sea un número par. Si ocurre un error de un solo bit durante la transmisión o el almacenamiento, resultará en un número impar de 1s en los datos recibidos, lo que indica un error. 

•	Paridad Impar: aquí el bit de paridad se establece de manera que el número total de 1s, sea un número impar. Si ocurre un error de un solo bit, resultará en un número par de 1s en los datos recibidos, lo que indica un error. 

Durante la transmisión o el almacenamiento de datos, el remitente calcula el bit de paridad y lo adjunta a los datos. El receptor luego recalcula el bit de paridad en función de los datos recibidos y verifica si coincide con el bit de paridad recibido. Si hay una discrepancia, indica que ha ocurrido un error en los datos. 


3. Discuss the advantages and limitations of parity checking.

•	Ventajas:

-	Sencillez: es una técnica de detección de errores simple de implementar. Requiere de la adición de un solo bit de paridad a un conjunto de datos, lo que la hace fácil de utilizar

-	Detección de errores simples: es efectiva para detectar errores de un solo bit en los datos. Si un solo bit se corrompe durante la transmisión o el almacenamiento, el bit de paridad revelará la presencia de un error.

•	Desventajas:

-	Limitada a errores de un solo bit: la verificación de paridad solo es capaz de detectar errores de un solo bit. Por lo tanto, es ineficaz para detectar errores más complejos o múltiples, ya que no distingue entre un número impar de bits corruptos y un número par de bits corruptos.

-	No corrige errores: solo tiene la capacidad de detectar errores, pero no puede corregirlos. Si se detecta un error, no se puede recuperar la información original y se debe solicitar una retransmisión de los datos.

-	Ineficaz para errores intermitentes: es ineficaz para errores intermitentes o transitorios que ocurren durante la transmisión y luego desaparecen antes de la verificación


4. Describe the process of using checksums for error detection.

Tiene varios pasos el proceso de checksum para la detección de errores:

•	Cálculo del checksum: el remitente calcula una suma de comprobación para un conjunto de datos, que se obtiene mediante la adición de información redundante a los datos, que se deriva de manera determinista utilizando un algoritmo específico.

•	Adjuntar checksum: el remitente lo adjunta a los datos. Esta suma de comprobación se convierte en parte integral de los datos que se enviarán a través de la red o se almacenarán.

•	Recálculo del checksum en el receptor: en el receptor, se recibe el conjunto de datos. El receptor realiza el mismo cálculo de la suma de comprobación utilizando los datos recibidos y el mismo algoritmo que se utilizó en el extremo del remitente.

•	Comparación de los checksums: una vez que el receptor ha calculado su propio checksum, la compara con el checksum recibido. Si los dos checksums coinciden, indica que no se han producido errores en la transmisión o el almacenamiento de los datos. 

•	Acción en caso de error:  En caso de que los checksums no coincidan, se toma una acción para abordar el error. Esto puede incluir solicitar una retransmisión de los datos o realizar otras acciones adecuadas según la aplicación.


5. Explain Cyclic Redundancy checks. 

Los Cyclic Redundacy checks son un método de detección de errores que utiliza la aritmética de polinomios para determinar si se han producido errores durante la transmisión o el almacenamiento de datos. El concepto central del CRC implica representar una secuencia de bits, como un polinomio. Este polinomio se crea tomando el valor de cada bit en el mensaje como coeficientes para los términos correspondientes en el polinomio.

La efectividad del CRC radica en su capacidad para detectar varios tipos de errores, incluidos errores de un solo bit, errores de dos bits, números impares de errores y muchos errores en ráfaga. Es particularmente poderoso para detectar errores en mensajes que pueden ser de miles de bytes de longitud. 

Los pasos para el CRC para la detección de errores son:

•	Division de polinomios: el remitente agrega un número específico de ceros (basado en el grado del polinomio generador) al final del mensaje (mensaje extendido). 

•	Polinomio divisor: el remitente y el receptor deben utilizar el mismo polinomio generador. El receptor utiliza este polinomio para realizar la división de polinomios en el mensaje extendido recibido.

•	Cálculo del resto: después de la división, el receptor calcula el polinomio resto. Si el mensaje recibido no tiene errores, el resto será cero.

•	Generación del checksum: el remitente, envía el mensaje extendido junto con el polinomio resto calculado durante la división, que es el checksum.

•	Verificación del checksum: en el extremo del receptor, se realiza la misma división de polinomios en el mensaje extendido recibido utilizando el polinomio generador acordado. El resto resultante se compara con el CRC recibido. Si coinciden, indica que no se han producido errores durante la transmisión o el almacenamiento de datos.

•	Detección de errores: si el resto no coincide con el CRC recibido, sugiere que se han producido errores.


## Reliable Transmission

1. What is reliable transmission and why is it important in computer networks?

La transmisión confiable en redes de computadoras se refiere a la capacidad de garantizar que los datos o frames se entreguen con un alto grado de certeza desde un punto de origen a un punto de destino, incluso en presencia de posibles errores o interrupciones en la red. 

Es importante en redes por varias razones:

•	Integridad de los Datos: la transmisión confiable garantiza que los datos transmitidos se reciban correctamente en el destino sin errores ni corrupción. Es fundamental para la entrega de datos críticos, como transacciones financieras.

•	Eficiencia de la Red: sin transmisión confiable, los protocolos de red podrían necesitar retransmitir datos para compensar errores, lo que conlleva un uso ineficiente de los recursos de la red y un rendimiento reducido.

•	Detección y Corrección de Errores: la transmisión confiable implica mecanismos de detección de errores, para identificar frames corruptos. Esto permite el manejo proactivo de errores y asegura que el receptor pueda solicitar la retransmisión

•	Recuperación de Pérdidas: en presencia de errores de red, los protocolos de transmisión confiable proporcionan un mecanismo para recuperar los datos perdidos mediante su retransmisión. 

•	Comunicación de Extremo a Extremo: La transmisión confiable es importante para aplicaciones que requieren comunicación de extremo a extremo, como la transferencia de archivos, donde los datos deben entregarse con precisión al usuario.


2. Explain the concept of stop-and-wait protocol for reliable transmission.

Este protocolo es un algoritmo de solicitud de repetición automática (ARQ) simple y fundamental utilizado para la transmisión confiable en redes. Su funcionamiento se explica a continuación:

•	Transmisión secuencial: el protocolo "stop-and-wait" sigue un enfoque de transmisión secuencial. Después de que el remitente ha transmitido un frame de datos, se detiene y espera a recibir un ACK antes de proceder a transmitir el siguiente frame

•	Timeout: si el remitente no recibe el ACK dentro de un período de tiempo específico (timeout), el remitente asume que el frame original podría haberse perdido o dañado en tránsito. En este caso, el remitente retransmite el frame original. 

•	Secuencia de números: si el ACK se pierde o llega con retraso, para evitar frames duplicados, el encabezado incluye un número de secuencia de 1 bit, que pueden ser 1 o 0, y se alternan para cada frame, de modo que el receptor puede distinguir entre frames originales y retransmitidos.


3. Discuss the advantages and limitations of stop-and-wait protocol.

•	Ventajas

-	Simplicidad: es sencillo y fácil de implementar. Es una forma básica de la solicitud de repetición automática (ARQ)

-	Detección de errores: detecta eficazmente errores en la transmisión de datos. Cuando no se recibe un ACK dentro del período de tiempo de espera, se asume que el frame se perdió o corrompió, lo que provoca una retransmisión. Esto garantiza la integridad y la confiabilidad de los datos.

-	Control de flujo: proporciona una forma de controlar el flujo de datos, ya que el remitente espera un ACK antes de enviar el siguiente frame. Esto previene la congestión de la red

-	Números de secuencia: la inclusión de números de secuencia de 1 bit en el encabezado ayuda a distinguir entre frames originales y retransmitidas, para evitar frames duplicados  cuando los ACK se retrasan o se pierden


•	Limitaciones
 
-	Bajo rendimiento: El remitente solo puede tener un frame pendiente en la red en un momento dado, lo que es ineficiente en redes con un ancho de banda alto y una latencia baja, ya que subutiliza la capacidad de la red.

-	Ineficiencia: No permite el uso de canalización, lo que resulta en un uso ineficiente del ancho de banda disponible

-	Impacto de latencia: el protocolo puede verse gravemente afectado por la latencia de la red. Un tiempo de ida y vuelta (RTT) largo puede ocasionar retrasos significativos entre la transmisión y recepción de frames. 

-	Escalabilidad limitada: en redes con múltiples dispositivos interconectados, se vuelve poco práctico debido a su escalabilidad limitada. No es adecuado para redes con un alto grado de paralelismo y requisitos de transmisión de datos.


4. Describe the process of using sliding window protocol for reliable transmission.

El protocolo de sliding window es un método eficiente para lograr la transmisión confiable en una red. Permite que el remitente transmita múltiples frames sin esperar una confirmación de cada frame individualmente. El proceso de uso del sliding window es: 

•	Asignación de Números de Secuencia: el remitente asigna un número de secuencia a cada frame. Los números de secuencia tienen un rango finito

•	Send window size (SWS): establece el límite superior en la cantidad de frames que el remitente puede transmitir. La diferencia entre LFS (última confirmación recibida) y LAR (último frame enviado) no puede superar el tamaño de Send Window

•	Receive window size (RWS): establece el límite superior en la cantidad de frames que el receptor puede aceptar. La diferencia entre LAF (frame más grande aceptable) y LFR (último frame recibido) no puede superar el Recieve Window Size 

•	Transmisión de Frames: se asocia un timeout con cada frame transmitido, y si expira antes de recibir una confirmación, se retransmite el frame, ya que el remitente no puede avanzar su ventana hasta que se confirme el frame perdido. 

•	Recepción de frames: cuando llega un frame con el número de secuencia al receptor, determina si el frame está dentro de su ventana de recepción, caso contrario se descarta.


## Ethernet and Multiple Access Networks

1. What is Ethernet and how does it work?

Ethernet, que funciona como una red de acceso múltiple,  es una tecnología que habilita la comunicación entre dispositivos de redes de datos que están conectados por medio de cables, como fibra óptica o cobre. Estos dispositivos tienen la capacidad de formar una red y, recibir y compartir paquetes de informacióna a través de un mismo enlace. De esta forma, se establece una red de área local (LAN) a través de conexiones Ethernet.

Ethernet envía paquetes de datos en forma de frames que contienen datos, direcciones de origen y destino (MAC addresses), etiquetas VLAN, corrección de errores y detalles de calidad de servicio. A demás dirige el tráfico solo al puerto necesario en lugar de inundar toda la red. Ethernet utiliza dos canales, lo que hace que la ruta sea más eficiente en comparación con otros métodos de envío de datos en una red.


2. Explain the concept of multiple access networks.

El concepto de redes de acceso múltiple se refiere a una tecnología o configuración de red en la que múltiples dispositivos comparten un medio de transmisión común, lo que les permite enviar y recibir datos en la misma red. 

En el caso de Ethernet, esta tecnología opera como una red de acceso múltiple, donde varios nodos pueden enviar y recibir paquetes de datos a través de un enlace compartido. La tecnología CSMA/CD permite que todos los nodos puedan determinar si el enlace está ocupado o libre, y detectar colisiones si dos nodos transmiten simultáneamente.

Los protocolos aplicados en esta red aseguran que el acceso al medio de transmisión sea equitativo, que se puedan detectar y gestionar colisiones, lo que facilita una comunicación efectiva entre los dispositivos conectados.


3. Discuss the advantages and limitations of Ethernet.

•	Ventajas:

-	Simplicidad y bajo costo: es fácil de administrar y mantener. No se manejan tablas de enrutamiento o configuraciones complejas. Es rentable por su uso de fibras económicas y adaptadores de red asequibles para los hosts.

-	Fiabilidad: utiliza detección de colisiones y mecanismos para gestionar problemas en el medio compartido. Garantiza que, incluso en presencia de colisiones, la transmisión de datos se realice de manera confiable.

-	Adaptabilidad: se pueden ampliar para adaptarse a diversas velocidades y tipos de conexiones, a demás de requisitos específicos de una red. Es flexible en cuanto a ancho de banda.

-	Estandarización: se define una amplia gama de medios físicos a través de los cuales Ethernet puede operar, convirtiéndolo en una tecnología ampliamente aceptada y compatible utilizada en diversas industrias, como centros de datos y redes de campus.

•	Limitaciones:

-	Congestión: en una red Ethernet compartida, todos los dispositivos forman parte del mismo dominio de colisión, lo que puede llevar a congestión y degradación del rendimiento a medida que aumenta el número de dispositivos.

-	Longitud del cable: La longitud de los segmentos de Ethernet está limitada, aunque se use pares de cobre trenzado o fibras ópticas, y el uso de repetidores para extender la red puede aumentar los dominios de colisión.

-	Tráfico broadcast: se genera tráfico innecesario porque cada frame transmitido en la red es recibido por todos los dispositivos en el mismo segmento. Esto consume ancho de banda y afecta el rendimiento de la red.

-	Baja escalabilidad: no es una opción eficiente para redes a gran escala donde el rendimiento y la escalabilidad son críticos 


4. Describe the process of collision detection in Ethernet.

•	Detección de Medio: antes de que un dispositivo transmita datos en la red, se asegura que el medio de transmisión esté libre

•	Transmisión de Datos: se comienza a transmitir datos, mientras se monitorea el medio para detectar cualquier colisión.

•	Colisión Detectada: Si dos nodos transmiten al mismo tiempo y sus señales colisionan en el medio, ambas nodos detectan la colisión, observando que la señal que están transmitiendo está distorsionada debido a la superposición con la señal del otro nodo

•	Generación de Jamming Signal: cuando se detecta una colisión, cada nodo que participa en la colisión detiene inmediatamente su transmisión y envía un jamming signal, que notifica a todos los nodos en la red que se ha producido una colisión.

•	Retransmisión:  Después de enviar esta señal, cada nodo espera un tiempo aleatorio antes de volver a intentar transmitir sus datos. Si la red está libre de colisiones, la transmisión se realiza con éxito. Si ocurre otra colisión, el proceso se repite.


5. Give examples of different multiple access techniques used in computer networks.

•	CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance): se utiliza en redes inalámbricas. Intenta evitar colisiones haciendo que los dispositivos escuchen un canal libre antes de transmitir. Se utiliza comúnmente en redes LAN inalámbricas.

•	Acceso Múltiple por División de Tiempo (TDMA):  divide el tiempo de transmisión disponible en espacios de tiempo. Esta técnica se utiliza comúnmente en redes celulares

•	Acceso Múltiple por División de Código (CDMA): permite que múltiples dispositivos transmitan simultáneamente utilizando diferentes códigos para diferenciar sus datos. Se utiliza comúnmente en sistemas de comunicación celular modernos como las redes 3G y 4G.

•	Acceso Múltiple por División de Frecuencia (FDMA): el espectro de frecuencia disponible se divide en subcanales múltiples, y a cada dispositivo se le asigna un subcanal específico para la comunicación. Esta técnica se utiliza en la radio analógica y algunos sistemas de comunicación por satélite.


## Wireless Networks

1. What are wireless networks and how do they work?

Las redes inalámbricas son un tipo de red de computadoras que posibilita la transferencia de datos sin requerir conexiones físicas mediante cables. Estas operan empleando señales electromagnéticas para establecer la comunicación entre dispositivos. Algunos componentes fundamentales en estas redes incluyen puntos de acceso, bandas de frecuencia, técnicas de modulación de datos, protocolos de seguridad y el proceso de autenticación de dispositivos. Dichas redes varían en alcance y pueden experimentar obstáculos y congestiones que afectan su rendimiento. En el caso de las redes móviles, como 4G y 5G, proporcionan conectividad en movilidad a través de torres de telefonía móvil. Las redes inalámbricas facilitan el acceso a Internet, el intercambio de archivos y otros servicios, desempeñando un papel esencial en la comunicación moderna. En resumen, en las redes inalámbricas, la transmisión de datos se realiza mediante señales electromagnéticas a través del aire, y los dispositivos se conectan mediante adaptadores inalámbricos que incorporan componentes como antenas y radios para la transmisión y recepción de datos sin cables físicos.

2. Explain the concept of wireless communication channels.

Los canales de comunicación wireless son las vías a través de las cuales las señales inalámbricas, como las ondas de radio o electromagnéticas, transmiten datos entre dispositivos. Estos canales utilizan el aire o espacios libre como medio, por lo cual se pueden encontrar con varias condiciones que afecten su rendimiento. Pueden operar dentro de bandas de frecuencia específicas, por lo que el ancho de banda disponible en estas bandas de frecuencia determina la cantidad de datos que se pueden transmitir.

Para diseñar y analizar sistemas de comunicación wireless, se utilizan modelos matemáticos para representar el comportamiento del canal wireless. Estos modelos ayudan a predecir cómo se propagarán las señales, incluidos factores como la pérdida de ruta, el desvanecimiento de la señal y la interferencia. 


3. Discuss the advantages and limitations of wireless networks.

•	Ventajas

-	Movilidad: brindan la libertad de conectarse a Internet u otros dispositivos desde cualquier lugar dentro de su área de cobertura. 

-	Conveniencia: eliminar la necesidad de cables físicos reduce el desorden y simplifica las conexiones de dispositivos. 

-	Escalabilidad: pueden escalarse fácilmente para acomodar dispositivos adicionales sin la molestia de instalar cables nuevos. 

-	Accesibilidad: permiten el acceso a Internet o recursos de red en áreas remotas o de difícil acceso

-	Bajo costo: a largo plazo,  pueden ser rentables ya que reducen los gastos asociados con la instalación y el mantenimiento de cables físicos.

•	Limitaciones

-	Interferencia: las redes inalámbricas son susceptibles a interferencias de otros dispositivos electrónicos, paredes y otros obstáculos físicos. Esta interferencia puede degradar la calidad y confiabilidad de la señal.

-	Alcance limitado: tienen un área de cobertura limitada, lo que puede ser un inconveniente en espacios más grandes o entornos al aire libre. 

-	Seguridad: son vulnerables a violaciones de seguridad y puede resultar complicado protegerlas adecuadamente. Los usuarios no autorizados pueden potencialmente acceder a la red si no están protegidos adecuadamente.

-	Velocidades más lentas: tienden a tener velocidades de transferencia de datos más lentas en comparación con las conexiones por cable, lo que puede ser una limitación en aplicaciones que requieren un gran ancho de banda.

-	Degradación de la señal: las señales inalámbricas pueden degradarse con la distancia y a través de obstáculos, lo que da como resultado una calidad de señal y velocidades de datos variables.


4. Describe the process of wireless signal propagation and interference.

Propagación:

•	Transmisión: un transmisor envía una señal electromagnética, en forma de ondas de radio, al aire. Esta señal transporta información y se modula para adaptarse al medio de transmisión.

•	Free Space Path Loss (FSPL): a medida que la señal viaja por el aire, experimenta atenuación natural de la señal con la distancia ya que se aleja del transmisor. Esta atenuación se calcula con la ley del cuadrado inverso. También puede experimentar problemas con los obstáculos físicos, afectando a la calidad de la señal, porque esta debe difractarse alrededor de los mismos.

• Trayectos múltiples: la señal puede tomar múltiples caminos para llegar al receptor. Las múltiples rutas de señal pueden interferir entre sí, lo que resulta en interferencias en el receptor.

•	Interferencia:

La interferencia es un fenómeno en el que múltiples dispositivos o señales inalámbricos que operan en el mismo rango de frecuencia interrumpen o degradan la comunicación entre sí. Puede resultar en una disminución en el rendimiento de datos, un aumento en la latencia o incluso una pérdida total de conectividad. 

Superposición de frecuencias: la comunicación es a través de canales de frecuencia específicos. Cuando los dispositivos funcionan en el mismo canal o en canales muy cercanos, existe la posibilidad de que se produzcan interferencias, porque las señales entran en competencia

Hay diferentes tipos de interferencia como co-channel interference (cuando los dispositivos comparten el mismo canal o frecuencia), adjacent-channel interference (cuando dos dispositivos usan canales muy cercanos) y non-Wi-Fi interference. 


5. Give examples of different wireless networking technologies used in computer networks.

## Exercises

1. Show the Manchester, 4B/5B encoding, and the resulting NRZI signal, for the
following bit sequence:
1110 0101 0000 0011

2. Show the Manchester, 4B/5B encoding, and the resulting NRZI signal, for the
following bit sequence:
1101 1110 1010 1101 1011 1110 1110 1111

3. Suppose we want to transmit the message "1011 0010 0100 1011" and protect it from errors using the CRC8 polynomial $x^8 + x^2 + x^1 + 1$.

- Use polynomial long division to determine the message that should be transmitted.
- Suppose the leftmost bit of the message is inverted due to noise on the transmission link. What is the result of the receiver’s CRC calculation? How does the receiver know that an error has occurred?

4. Consider an ARQ protocol that uses only negative acknowledgments (NAKs), but no positive acknowledgments (ACKs). Describe what timeouts would have to be scheduled. Explain why an ACK-based protocol is usually preferred to a NAK-based protocol.


5. Draw a timeline diagram for the sliding window algorithm with SWS = RWS = 3 frames, for the following two situations. Use a timeout interval of about 2 × RTT.

- Frame 4 is lost.
- Frames 4 to 6 are lost.
