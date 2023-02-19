# rotor_plus_plus
Rotor con azimuth y elevación + Lora (enmarcado dentro de la aventura tinyGS.com)

Como he comentado en la anterior versión, rotor plus, he identificado un problema que afecta a la recepción de la señal de los satelites: la señal Wifi que generan, tanto de la TinyGS como el controlador del rotor, afecta negativamente a la recepción de los satelites, principalmente los que operan cerca de los 400 Mhz.
Supongo que por ser la frecuencia de estos satelites (~ 400 Mhz) un submultiplo de la frecuencia WIFI (~ 2400 Mhz).

Pudiera ser otra la causa, pero alejar la TinyGS de la antena y generar silencio de radio mediante esp_wifi_stop() en la controladora del rotor durante el seguimiento de los satelites, ha mejorado la recepción de estas frecuencias, y obteniendo menor numero de errores de CRC.

![image](https://user-images.githubusercontent.com/48222471/219964735-e9b03ab3-8a8c-4862-ba71-bbfcd501dcd3.png)

Diagrama de bloques:

![image](https://user-images.githubusercontent.com/48222471/219963042-5a910ad9-36ba-454b-956b-77bf34b30299.png)
Creo que esta es la mejor instalación posible:

1- La TinyGS los mas alejada de la antena + LNA + filtro PasaBanda para que no le afecte a la señal recibida la emisión WIFI de la TinyGS.

2- La tarjeta controladora de los motores de azimuth y elevation, en silencio de radio, es decir solo recibira los datos referente a donde tiene que posicionar los motores. Tambien se le habilitará, en los momentos que no se esta siguiendo ningun satelite, el envio de información como RSSI, SNR, temperatura, etc.

Este es el esquema de la placa con el ESP32. Dependiendo de donde este situada montaremos mas o menos componentes:

![image](https://user-images.githubusercontent.com/48222471/219963378-4f51618b-5d57-4e55-a12d-66700e77d537.png)

En la parte del rotor, esta tarjeta debe llevar el ESP32, el modulo LORA, los TMC2209 de control de motores paso a paso y sus componentes asociados (resistencias y condensadores y convertidor cc/cc).

En la parte que estará en casa, solo se necesitará el ESP32, el modulo LORA y los componenente asociados  (resistencias y condensadores y convertidor cc/cc).

Esta placa es muy flexible, de hecho, puede funcionar como TinyGS con los componentes adecuados, tanto en la banda de 400 Mhz como en la de 800/900 Mhz.

Me pongo a realizar la programación e ire subiendo fotos y resultados a medida que vaya avanzando.
