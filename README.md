# Introducción

Node-RED es una plataforma de código abierto basada en Node.js para desarrollar aplicaciones IoT y automatización del hogar. Es una herramienta visual de programación, lo que significa que los desarrolladores pueden crear flujos de trabajo utilizando bloques de construcción en lugar de escribir código. Los bloques se conectan entre sí para crear un flujo de trabajo, y los datos fluyen entre los bloques a medida que se ejecuta el flujo.

Node-RED se utiliza a menudo para integrar diferentes dispositivos y servicios, como sensores, dispositivos IoT, aplicaciones web y servicios en la nube. Los desarrolladores pueden crear flujos de trabajo para recopilar datos de sensores, enviar alertas, controlar dispositivos, y más. También se puede utilizar para automatizar tareas en el hogar, como encender y apagar las luces, regular la temperatura y la humedad, y para recibir alertas de seguridad.

# Material Necesario

- [Instalar NodeJS](https://github.com/RaulToribio/13-Instalar-NodeJS)

# Instrucciones

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(1).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(1).png)

Utilizar la línea de comando `nslookup broker.hivemq.com` para obtener la Dirección IP del Broker HiveMQ.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(2).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(2).png)

Copiar la Dirección IP.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(3).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(3).png)

Utilizar la línea de comando `mosquitto_sub -h 18.197.239.198 -p 1883 -i RaulToribio -q 0 -t codigoIoT/G8/mosquitto/msg` para suscribirse.

El host en este caso no será localhost debido a que deseamos recibir información externa a nuestra red.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(4).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(4).png)

Flujo 04 - Node-RED.

El objetivo de este ejercicio en Node-RED es poder visualizar una gráfica de tipo “Gauge” la temperatura y el nombre de todas las personas que publiquen el el tema “codigoIoT/G8/mosquitto/msg”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(5).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(5).png)

En la terminal se observará la información recibida al tema “codigoIoT/G8/mosquitto/msg”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(6).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(6).png)

Resultado (información recibida desde el broker).

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(7).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(7).png)

Nodo “MQTT In”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(8).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(8).png)

Configuración del “Broker”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(9).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(9).png)

Nodo “JSON” separará los datos “ID” y “Temperatura”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(10).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(10).png)

Nodo “Function”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(11).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(11).png)

Nodo “Chart”.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(12).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(12).png)

Nodo “Inject” contiene la información a enviar en un formato que JSON reconozca.

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(13).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(13).png)

Nodo “MQTT Out”

![https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(14).png](https://raw.githubusercontent.com/RaulToribio/21-Flujo-04/main/Im%C3%A1genes/Flujo%2004%20(14).png)

Configuración del “Broker”.

# Créditos

> [José Raúl Toribio Gabriel](https://github.com/RaulToribio)
> 

> [Codigo IoT](https://github.com/codigo-iot)
>
