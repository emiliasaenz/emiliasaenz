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

Ethernet es un estándar utilizado para redes LAN, que define el hardware y los protocolos de comunicación utilizados para conectar diferentes dispositivos dentro de una red localizada, y así obtener una transmisión rápida de datos a través de cables coaxiales o de fibra óptica. Opera en la capa de enlace de datos (Capa 2) y la capa física (Capa 1) del modelo OSI, y divide la capa de conexión de datos en dos capas distintas: la capa de control de enlace lógico y también la capa de control de acceso al medio (MAC). 

Proporciona una interfaz de usuario sencilla. Es más confiables y menos susceptibles a interferencias o colisiones de paquetes que las redes inalámbricas. Algunas redes de Ethernet funcionan en modo dúplex y otras se basan en el protocolo CSMA/CD, para permitir que cada computadora escuche la conexión antes de enviar datos a través de la red. Emplea una topología en estrella o bus lineal. 

La transmisión de tramas Ethernet implica que un dispositivo encapsula datos en una trama Ethernet para enviarlos a otro dispositivo en la misma red, y la trama contiene información esencial como direcciones MAC de origen y destino. Cada dispositivo en la red Ethernet posee una dirección MAC única para un direccionamiento efectivo, designando el origen y el destinatario previsto. En las redes Ethernet tradicionales que funcionan en modo Half-Duplex, se emplea la detección de colisiones, donde los dispositivos escuchan las señales portadoras antes de transmitir para evitar colisiones y, si se detectan, un período de interrupción aleatorio precede a la retransmisión. En las redes Ethernet modernas con conmutadores que funcionan en modo Full-Duplex, la comunicación es más eficiente ya que los switches utilizan tablas de direcciones MAC para reenviar tramas de forma inteligente, lo que reduce las colisiones.


2. Explain the concept of a collision domain in Ethernet.

El dominio de colisión se refiere a la posibilidad de que tramas de datos colisionen al transmitirse en el mismo canal de comunicación. Este fenómeno es prominente en redes semidúplex, donde varios dispositivos comparten el mismo medio de comunicación y dependen del protocolo CSMA/CD para evitar colisiones. En este contexto, el dominio de colisión incluye todos los dispositivos en un segmento de red que comparten el mismo canal, requiriendo que otros dispositivos se abstengan de transmitir cuando uno está enviando datos para evitar colisiones. En redes más extensas o propensas a colisiones frecuentes, el rendimiento de la red puede disminuir debido a retransmisiones y una reducción en el rendimiento efectivo.

La introducción de switches ha transformado la dinámica de los dominios de colisión. En una red con switches, cada puerto del conmutador representa un dominio de colisión independiente, aislando dispositivos conectados a diferentes puertos y reduciendo la probabilidad de colisiones. Este cambio mejora la eficiencia de la red, especialmente en entornos de comunicación full-duplex, donde los dispositivos pueden enviar y recibir simultáneamente sin depender del CSMA/CD.

Con la evolución de las redes Ethernet, la adopción generalizada de la comunicación full-duplex y el uso extendido de conmutadores han mitigado considerablemente el impacto de las colisiones, volviendo menos relevante la noción de dominios de colisión en las implementaciones modernas de Ethernet.


3. What are learning bridges?

Un learning bridge reduce la cantidad de tráfico de transmisión en las LAN, ya que escucha todas las tramas en los dos segmentos de LAN tal como lo hace un bridge básico y aprende dónde está ubicada cada dirección física. Hace una lista de las direcciones físicas y a qué puerto están conectadas. Debido a que almacena cada trama a medida que la recibe, luego la reenvía de forma selectiva según la LAN en la que se encuentra esa dirección física. Siempre que encuentra una trama que contiene una dirección física que no conoce, reenvía esa trama a todos los demás puertos a las otras LAN.

4. Explain the Spanning Tree Algorithm

Es un protocolo empleado en redes informáticas para evitar la aparición de bucles, broadcast storm e inestabilidad de la red en entornos Ethernet. El protocolo funciona designando un nodo raíz mediante un proceso que implica la elección del switch con el ID de nodo más bajo, combinando un valor de prioridad y una dirección MAC. El nodo raíz sirve como punto de referencia para establecer los caminos más cortos dentro de la red.

Una vez que se identifica el nodo raíz, cada switch no raíz selecciona la ruta con el costo acumulativo más bajo para llegar a este. Simultáneamente, en cada segmento de red, el algoritmo designa un puerto designado con el costo de ruta más bajo hasta el nodo raíz. Luego, otros puertos en el segmento se colocan en un estado de bloqueo, lo que previene efectivamente los bucles al crear una topología similar a un árbol.

El spanning tree monitorea continuamente la red en busca de cambios, adaptándose a las variaciones en la topología causadas por fallas o adiciones de enlaces. Esta adaptabilidad es crucial para mantener una estructura sin bucles. Además, el protocolo incorpora el Rapid Spanning Tree Protocol (RSTP), que mejora el tiempo de convergencia después de cambios de red, minimizando el tiempo necesario para que la red se estabilice.

En esencia, garantiza la creación de una topología de red estable y eficiente seleccionando rutas óptimas, designando puertos específicos y ajustándose dinámicamente a los cambios, mitigando así los riesgos asociados con los bucles en las redes Ethernet.


5. What are VLANs?

Las redes de área local virtuales son una técnica de gestión de redes que permite la segmentación lógica de una red física en múltiples redes virtuales. Esta segmentación es independiente del diseño físico, lo que permite a los administradores de red agrupar dispositivos según criterios como función, departamento o requisitos de seguridad. Las VLAN proporcionan un medio para crear dominios de transmisión aislados dentro de una única red física, lo que mejora la seguridad y la eficiencia de la red.

Los dispositivos dentro de la misma VLAN son parte de un dominio de transmisión compartido, que contiene el tráfico de transmisión dentro de los límites de esa VLAN y evita la propagación innecesaria a dispositivos en otras VLAN. Este aislamiento contribuye a optimizar el ancho de banda y el rendimiento de la red. Además ofrecen flexibilidad y escalabilidad, lo que permite a los administradores adaptar las configuraciones de red a los requisitos cambiantes sin necesidad de volver a cablear físicamente. Esto es particularmente ventajoso en grandes redes u organizaciones con necesidades operativas dinámicas. 


## Internet (IP)

### Questions:
1. What is the Internet Protocol (IP)? How does it work?

El Protocolo de Internet sirve como un conjunto fundamental de reglas que rigen la transmisión de datos a través de redes y desempeña un papel vital en la comunicación por Internet y LAN. Al operar en la capa de red, emplea etiquetas numéricas (direcciones IP) para identificar de forma única los dispositivos en una red. Las direcciones IP son esenciales para el enrutamiento, ya que permiten a los enrutadores dirigir paquetes de datos a sus destinos a través de redes interconectadas.

El proceso de comunicación IP, basado en packet switching, implica direccionar dispositivos con direcciones IP únicas, dividir los datos en paquetes y la toma de decisiones de los switches para el reenvío basadas en las direcciones IP de destino. Los paquetes viajan de forma independiente y sin ninguna conexión preestablecida, a través de la red, tomando distintos caminos antes de llegar a su destino. A su llegada, los paquetes se reensamblan para reconstruir los datos originales, y el dispositivo receptor utiliza la dirección IP de destino para identificar y organizar los paquetes que pertenecen a la misma sesión de comunicación.

En esencia, IP sirve como columna vertebral de la comunicación global, proporcionando un enfoque estandarizado y escalable para que los dispositivos intercambien datos a través de diversas redes. Sus características, que incluyen direccionamiento, paquetización, enrutamiento y operación sin conexión, contribuyen a la eficiencia y confiabilidad de la transmisión de datos en el Internet.


2. Explain the difference between IPv4 and IPv6.

• Longitud de la dirección:

- IPv4: tiene 32 bits de longitud, lo que da como resultado aproximadamente 4,3 mil millones de direcciones únicas
  
- IPv6: tiene 128 bits de longitud, lo que proporciona un espacio de direcciones astronómicamente mayor: alrededor de 3,4 x 10^38 direcciones únicas

• Notación de dirección:

- IPv4: las direcciones IPv4 se expresan en notación decimal con puntos, con cuatro conjuntos de números decimales separados por puntos (por ejemplo, 192.168.1.1)
  
- IPv6:  las direcciones IPv6 utilizan notación hexadecimal y se expresan como ocho grupos de cuatro dígitos hexadecimales, separados por dos puntos (por ejemplo, 2001:0db8:85a3:0000:0000:8a2e:0370:7334)

• Configuración de dirección:

- IPv4: las direcciones IPv4 se pueden configurar manualmente (estáticas) o asignarse dinámicamente a través de protocolos como DHCP
  
- IPv6: incorpora configuración automática de direcciones sin estado, lo que permite a los dispositivos generar sus propias direcciones basadas en información de la red

• Radiodifusión:

- IPv4: utiliza comunicación de transmisión para enviar datos a todos los dispositivos en un segmento de red
  
- IPv6: elimina la comunicación de transmisión tradicional, y utiliza métodos más eficientes de multidifusión y difusión directa, lo que reduce el tráfico innecesario.

• Seguridad y Movilidad:

IPv6 incorpora características como IPsec como requisito estándar, lo que mejora las capacidades de seguridad. Además, IPv6 está diseñado para admitir dispositivos móviles de manera más efectiva, con funciones integradas para movilidad y flexibilidad de configuración.


3. What is an IP address? How is it structured?

Una dirección IP, es una etiqueta numérica asignada a cada dispositivo que participa en una red que utiliza el Protocolo de Internet para comunicarse. Las direcciones IP tienen dos propósitos principales: identificar el host o la interfaz de red y proporcionar la ubicación del host en la red. Hay dos versiones principales de direcciones IP: IPv4 e IPv6.

Las direcciones IPv4, utilizan un formato de dirección de 32 bits y se expresan como cuatro conjuntos de números decimales. Cada número decimal, u octeto, representa 8 bits de la dirección general. La estructura de las direcciones IPv4 implica una división en porciones de red y host, determinada por la máscara de subred, que especifica los bits que representan la red y el host dentro de una red determinada.

IPv6, introducido para abordar las limitaciones de IPv4, utiliza un formato de dirección de 128 bits expresado como ocho grupos de cuatro dígitos hexadecimales. La estructura de direcciones IPv6 es jerárquica: el prefijo de enrutamiento global identifica la red general, el ID de subred identifica las subredes dentro de la red y el ID de interfaz identifica de forma única un host o interfaz específico dentro de una subred.

Tanto IPv4 como IPv6 tienen rangos de direcciones reservados para fines específicos, como redes privadas y direcciones de bucle invertido. Las direcciones IP se pueden asignar de forma estática o dinámicamente.


4. What is the purpose of subnetting in IP addressing?

La creación de subredes en el direccionamiento IP sirve para varios propósitos en el diseño y administración de redes. El objetivo principal es mejorar la eficiencia de la red dividiendo una red grande en subredes más pequeñas y manejables. Esta división reduce el dominio de transmisión dentro de cada subred, minimizando el tráfico de transmisión y mejorando el rendimiento general de la red. 

La segmentación lógica de la red permite un mejor control del tráfico entre subredes, facilitando la implementación de routers y firewalls para contener brechas de seguridad y limitar el impacto de actividades maliciosas. Además, la creación de subredes optimiza la gestión de direcciones IP al permitir a los administradores asignar rangos de direcciones más pequeños y específicos a subredes individuales, lo que reduce el desperdicio de direcciones y promueve un uso más eficiente del espacio de direcciones disponible.


6. What is the role of the Internet Control Message Protocol (ICMP) in IP?

ICMP es una parte integral del conjunto de protocolos IP y sirve como protocolo de soporte. Una de sus funciones principales es gestionar los informes de errores en la transmisión de paquetes IP. Cuando se producen problemas como destinos inalcanzables o valores de tiempo de vida excedidos, ICMP genera mensajes de error para informar al host de origen o al dispositivo de red sobre el problema, lo que facilita la resolución de problemas y el diagnóstico efectivos.

ICMP hace uso de la función ping, que utiliza mensajes ICMP Echo Request y Echo Reply. Ping es una herramienta para probar la accesibilidad de un host en una red IP, proporcionando un medio sencillo de diagnóstico de red. Además, ICMP contribuye al descubrimiento de la unidad de transmisión máxima de ruta (PMTU), determinando el tamaño máximo de paquete que se puede transmitir sin fragmentación en una ruta de red específica.

El protocolo también admite la optimización de la red a través de mensajes Redirect, que informan a los hosts y routers sobre mejores direcciones de siguiente salto para destinos específicos. Esto ayuda a mejorar la eficiencia del routing y la optimización de rutas. Los mensajes de Tiempo excedido de ICMP desempeñan un papel crucial en la identificación de bucles de routing y otros problemas que causan retrasos excesivos al señalar cuando el valor del tiempo de vida en un paquete IP llega a cero.


### Exercises:
1. Convert the following IPv4 address to binary: 192.168.0.1.

192 en binario: 11000000
168 en binario: 10101000
0 en binario: 00000000
1 en binario: 00000001

192.168.0.1 => 11000000.10101000.00000000.00000001 


2. Research and list three different classes of IP addresses.

Las direcciones IP se clasifican en tres clases principales según sus rangos de primeros octetos. Cada clase está diseñada para adaptarse a diferentes tamaños de redes, desde pequeñas hasta grandes. 

• Clase A:

- Rango del primer octeto: 1.0.0.0 a 126.255.255.255

- Se caracterizan por un patrón de bits inicial de 0 en el primer octeto. Los tres octetos restantes se utilizan para identificar hosts dentro de la red. Las direcciones de clase A son adecuadas para redes grandes con una gran cantidad de hosts. La máscara de subred predeterminada es 255.0.0.0.

• Clase B:

- Rango del primer octeto: 128.0.0.0 a 191.255.255.255

- Tienen un patrón de bits inicial de 10 en el primer octeto. Los dos octetos siguientes se utilizan para identificar hosts. Las direcciones de clase B se asignan comúnmente a redes de tamaño mediano y ofrecen alrededor de 65.000 direcciones de host únicas. La máscara de subred predeterminada es 255.255.0.0.

• Clase C:

- Rango del primer octeto: 192.0.0.0 a 223.255.255.255

- Comienzan con un patrón de bits inicial de 110 en el primer octeto. Los primeros tres octetos identifican la red y el último octeto se utiliza para la identificación del host. Las direcciones de clase C son adecuadas para redes más pequeñas y proporcionan alrededor de 254 direcciones de host únicas. La máscara de subred predeterminada es 255.255.255.0.

3. Configure a computer to use a static IP address. Document the steps you followed.

1. Abrir Preferencias del Sistema
   
2. Acceder a las preferencias de red

3. Seleccionar Conexión de red: esocger Wi-Fi o Ethernet

4. Desbloquear configuración de red

5. Configurar los ajustes de IPv4: seleccionar "Manualmente".

6. Ingresar la dirección IP estática, la máscara de subred y la dirección IP del enrutador

7. Configurar los ajustes del servidor DNS:

8. Ingresar las direcciones del servidor DNS en la sección Servidores DNS.

9. Aplicar cambios y verificar configuración
- Para verificar que la dirección IP estática se haya configurado correctamente, abrir la Terminal y escribir el comando ifconfig o ipconfig getifaddr en0 para Wi-Fi o ipconfig getifaddr en1 para Ethernet.

## Routing

### Questions:
1. What is routing in computer networking?

Routing es el proceso de dirigir paquetes de datos desde un origen a un destino a través de una red. Los routers utilizan tablas y algoritmos de enrutamiento para tomar decisiones sobre la ruta óptima para reenviar paquetes. El enrutamiento implica la actualización dinámica de las tablas de enrutamiento en función de los cambios y configuraciones de la red. Varios algoritmos y protocolos de enrutamiento, como RIP, OSPF y BGP, gobiernan la selección y el intercambio de información de enrutamiento entre routers. La elección entre métodos de enrutamiento estáticos y dinámicos, así como la evaluación de factores como el ancho de banda del enlace y la latencia, influyen en el proceso de selección de ruta. El enrutamiento desempeña un papel crucial al permitir la comunicación, el intercambio de datos y la entrega eficiente de datos en redes informáticas, lo que contribuye al rendimiento y la escalabilidad generales de la red.

2. Explain the difference between static routing and dynamic routing.

El enrutamiento estático implica que los administradores configuren manualmente tablas de enrutamiento y definan rutas predeterminadas para los paquetes de datos. Las rutas permanecen fijas a menos que los administradores las modifiquen. La simplicidad y previsibilidad del enrutamiento estático lo hacen ideal para redes pequeñas con topologías estables. Sin embargo, el enrutamiento estático tiene una falta de adaptabilidad a los cambios en la red. 

El enrutamiento dinámico implica que los enrutadores utilizan protocolos de enrutamiento, como RIP, OSPF o BGP, para intercambiar y actualizar de forma autónoma información de enrutamiento con enrutadores vecinos, lo que facilita una comprensión dinámica de la topología de la red y la adaptación a los cambios. Es adecuado para entornos grandes y complejos. Sin embargo, el enrutamiento dinámico introduce complejidad y la posibilidad de un mayor tráfico de red debido al intercambio continuo de información. 

En general, el enrutamiento dinámico es superior, tanto en flexibilidad, como en escalabilidad y mantenimiento. El enrutamiento dinámico es más adaptable a los cambios en la topología de la red y a modificaciones en redes más grandes con configuraciones cambiantes, además requiere menos mantenimiento manual una vez configurado.


3. What is a routing table? How is it used in the routing process?

Una tabla de enrutamiento, alojada dentro de un enrutador, sirve como una estructura de datos que contiene información esencial sobre diversas rutas que conducen a destinos específicos en una red. Su función fundamental es ayudar a los enrutadores a tomar decisiones informadas sobre la ruta óptima para reenviar paquetes de datos desde el origen al destino. Cada entrada de la tabla incluye detalles de la red de destino, el enrutador para el reenvío de paquetes, la interfaz de red para el reenvío, el valor numérico que representa el costo de la ruta y la máscara de subred, que define los límites de la red para tomar decisiones de enrutamiento precisas. 

En el proceso de enrutamiento, al recibir un paquete de datos, un enrutador examina la dirección IP de destino del paquete y consulta su tabla de enrutamiento para determinar el siguiente salto y la interfaz óptimos para el reenvío de paquetes. Esta determinación se basa en el prefijo coincidente más largo en la tabla de enrutamiento, establecido mediante una comparación de la dirección IP de destino con las entradas de la tabla. El proceso implica que el enrutador examine la dirección IP de destino del paquete entrante, busque una entrada coincidente en la tabla de enrutamiento utilizando el prefijo coincidente más largo y, posteriormente, seleccione el siguiente salto y la interfaz de salida adecuados. Una vez que se toman estas decisiones, el enrutador procede a reenviar el paquete al siguiente salto especificado utilizando la interfaz de salida designada, lo que permite un reenvío de paquetes de datos eficiente y preciso dentro de la red.

4. What is the purpose of a default gateway in routing?

El default getaway funciona como punto de salida para el tráfico sin una ruta específica en la tabla de enrutamiento local. Cuando un dispositivo busca comunicarse con un destino más allá de su red o subred local, verifica su tabla de enrutamiento; si no se encuentra una ruta explícita, se utiliza el default gateway. Esta ruta predeterminada es crucial para enrutar el tráfico externo, manejar paquetes con destinos desconocidos y conectar diferentes subredes dentro de la red. Además, el default gateway desempeña un papel clave a la hora de facilitar el acceso a Internet, actuando como el punto central a través del cual el tráfico saliente puede llegar a redes externas, convirtiéndolo en un elemento integral para una comunicación fluida entre los dispositivos dentro de la red e Internet en general.

5. Describe the process of routing a packet from source to destination.

Enrutar un paquete desde el origen al destino en una red implica un proceso sistemático en el que el dispositivo de origen genera un paquete de datos con direcciones IP de origen y destino. El dispositivo de origen consulta su tabla de enrutamiento para determinar el siguiente salto y la interfaz de salida, y reenvía el paquete en consecuencia. Los enrutadores a lo largo del camino continúan tomando decisiones de enrutamiento basándose en sus tablas, mientras que los switch facilitan el reenvío dentro de los segmentos de la red local utilizando direcciones MAC. El paquete llega a la subred de destino y la dirección MAC del dispositivo de destino se resuelve mediante ARP. Tras la entrega al dispositivo de destino, el paquete se somete a un procesamiento de capa IP, dirigiendo la carga útil a la aplicación o servicio relevante. A lo largo de este proceso, las tablas de enrutamiento, las tablas de direcciones MAC y los protocolos como ARP e IP garantizan un reenvío de paquetes preciso y eficiente, lo que permite una comunicación fluida entre dispositivos.


## Exercises

![net](./network.png)

1. For the network given in figure above, show how the link-state algorithm builds the routing table for node D.

<img width="163" alt="Captura de pantalla" src="https://github.com/emiliasaenz/emiliasaenz/assets/143628612/59a613ce-09e6-40dd-ade7-bde34a68c2b6">
<img width="367" alt="Captura de pantalla" src="https://github.com/emiliasaenz/emiliasaenz/assets/143628612/8920f934-0795-440d-9b55-66d7d2fc74f0">

