# rotor_plus_plus
rotor con azimuth y elevación + Lora 

![image](https://user-images.githubusercontent.com/48222471/219963042-5a910ad9-36ba-454b-956b-77bf34b30299.png)
Creo que esta es la mejor instalación posible:

1- La TinyGS los mas alejada de la antena + LNA + filtro PasaBanda para que no le afecte a la señal recibida la emisión WIFI de la TinyGS.
2- La tarjeta controladora de los motores de azimuth y elevation, en silencio de radio, es decir solo recibira los datos referente a donde tiene que posicionar los motores. Tambien se le habilitará, en los momentos que no se esta siguiendo ningun satelite, el envio de información como RSSI, SNR, temperatura, etc.

Este es el esquema de la placa con el ESP32. Dependiendo de donde este situada montaremos mas o menos componentes:

![image](https://user-images.githubusercontent.com/48222471/219963378-4f51618b-5d57-4e55-a12d-66700e77d537.png)
