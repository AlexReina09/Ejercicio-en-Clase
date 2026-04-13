
RESPUESTAS DE TALLER EN CLASE:
 
Yolo es un algoritmo de visión artificial diseñado para la detección de objetos en imágenes y videos en tiempo real. A diferencia de otros métodos que analizan una imagen varias veces, YOLO utiliza una única pasada por una red neuronal para predecir simultáneamente qué objetos hay y dónde están.

  Características:

* Velocidad extrema
* Enfoque global
* Predicción simultánea
* Capacidad de generalización

  Arquitectura que usa YOLO:

  YOLOv1 hasta YOLOv11), su estructura general se divide tradicionalmente en tres partes fundamentales

1). Backbone (Columna vertebral)
2). Neck (Cuello)
3). Head (Cabeza)

-------------------------------------------------------------------------------------

La descarga de modelos utiliza TCP porque garantiza la integridad y el orden de los datos, evitando archivos corruptos, mientras que la transmisión de video usa UDP por su baja latencia y alta velocidad al priorizar el envío en tiempo real sobre la corrección de errores.

Características:

Confiabilidad, Orden Secuencial, Reenvío de paquetes.

En video en vivo, es mejor perder unos pocos fotogramas (pixeles temporales) que detener la transmisión esperando a que lleguen.

Características Clave:
Velocidad y baja latencia: No necesita establecer una conexión previa (handshake).
Eficiencia: Sin control de congestión ni retransmisión, lo que permite un flujo continuo.
Ligeros: Los encabezados son más pequeños, consumiendo menos recursos.
-------------------------------------------------------------------------------------

Un TCP Retransmission ocurre cuando el emisor vuelve a enviar un segmento porque:

No recibió el ACK (confirmación) a tiempo
El paquete se perdió en la red
Hubo congestión o errores en la transmisión
TCP detecta que algo falló y reintenta enviar los datos.

TCP está diseñado para priorizar la fiabilidad, no la velocidad. Por eso:

Garantiza que los datos lleguen completos y en orden
Puede volverse más lento si hay muchas retransmisiones
Cada retransmisión introduce retardo adicional (latencia).

Descargas (como HTTP, FTP):

Necesitas que el archivo llegue 100% correcto
Si falta un solo byte → el archivo puede dañarse

Las retransmisiones aseguran:
Integridad de los datos
Corrección de errores
Entrega completa

Streaming en vivo (como videollamadas):

El tiempo es más importante que la perfección
Los datos “viejos” ya no sirven si llegan tarde

Problemas de retransmisión:

Retrasos (buffering)
Congelamientos
Aumento de latencia

En estos casos se prefiere UDP, que:

No retransmite
Es más rápido pero menos confiable.
-----------------------------------------------------------------------------------------------


En tu tráfico se observan dos IP principales:

172.28.0.12
172.28.0.1

Mira estas pistas clave en tu imagen:

Peticiones HTTP GET:
GET /api/colab/resources?authuser=0 HTTP/1.1
Source: 172.28.0.12 → Destination: 172.28.0.1

Respuesta:

HTTP/1.1 200 OK
Source: 172.28.0.1 → Destination: 172.28.0.12

Conclusión:

172.28.0.12 = tu cliente (tu máquina)
172.28.0.1 = servidor (Google Cloud / backend que entrega el modelo)



tráfico del servidor (respuestas)
ip.src == 172.28.0.1

Datos descargados
Respuestas HTTP
Segmentos TCP del archivo
