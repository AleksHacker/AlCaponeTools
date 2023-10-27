
# **Al Capone tools**

![enter image description here](https://i.ibb.co/F599KXj/image-8.png)

Al Capone tools es un conjunto de scripts diseñados para el análisis de cómo funciona el robo de información y vulnerabilidades de las redes WiFi. Al Capone tools se compone tanto de scripts de Rubber Ducky para ejecutar comandos en el sistema a atacar, como scripts encargados de actuar como un servidor web donde la información robada es almacenada. Externamente cuenta con un módulo nodemcu esp8266 que sustituye al costoso módulo oficial para auditar redes WiFi utilizando el Flipper Zero. Actualmente se enfoca en el sistema operativo Windows.

# Nuestro objetivo
Utilizar herramientas de hacking para analizar e investigar como diferentes ataques, especificamente de ingenieria social, pueden afectar a diferentes areas demograficas, y con esto poder generar soluciones y garantizar una seguridad.


# Instalacion general

 1. Tener el software de flipper al dia.
 2. Utilizar la interfaz web o la aplicacion de qFlipper para acceder a la carpeta de nfc y badusb
 3. Introducir los contenidos de la carpeta nfc a la carpeta nfc del explorador de archivos de flipper, asi mismo como los contenidos de la carpeta badusb a la carpeta badusb de flipper respectivamente. 

# Instalacion del modulo nodemcu esp8266

 1. Tener el software de flipper al dia.
 2. Descargar la herramienta de [esptool.py](https://github.com/espressif/esptool)
 3. Utilizar el comando `esptool.py -p PUERTO write_flash -fm dout 0x0000 PATH/deauther.py` reemplazando PUERTO por el puerto al que esta conectado el esp8266, y PATH/deauther.py con la ubicacion del archivo descargado dentro de la carpeta deauther.
 4. Conectar el pin VIN del nodemcu con el 5V del flipper zero, y el GND del nodemcu con el GND del flipper
 
# Lista de Herramientas

## Inyección de payloads para phishing

Por medio de la funcionalidad HID del flipper zero, Al Capone tools cuenta con scripts para lograr que una computadora ingrese a un sitio web de phishing, el cual tiene una apariencia nativa, al ser inyectado un comando para la pantalla completa, de esta manera haciendo que el sitio web aparente ser una alerta generado por el sistema operativo.


![enter image description here](https://i.ibb.co/mBcJRZc/BadUsb.png)

  

### Descripción del ataque: 
Dentro de esta ventana de línea de comandos, se lleva a cabo una serie de acciones, que incluyen la apertura del navegador web Chrome. A continuación, el navegador es dirigido a una página web que ha sido diseñada para parecer una página oficial de inicio de sesión, pero que está bajo el control del atacante. Una vez que los usuarios ingresan sus datos de inicio de sesión en esta página falsa, se produce un cambio en la visualización de la página, colocándola en modo de pantalla completa para ocultar la dirección web real.

  

Los datos de inicio de sesión recopilados de esta manera son posteriormente transmitidos a través de un servidor web controlado por el atacante. Esta transmisión de datos permite al atacante obtener las contraseñas de diversas cuentas en línea.

  

Para dificultar el rastreo de la información robada, se implementa una medida adicional de seguridad: la redirección de los datos a una página web llamada "Chicharronera Galileo". Esta página actúa como una capa de seguridad, ocultando aún más la conexión entre el atacante y la información robada.



### Inyección de payloads para robo de credenciales y escaneo de red
Por medio de la funcionalidad HID del flipper zero, Al Capone tools cuenta con scripts que ejecutan por medio de las funcionalidades netstat y curl de windows, un escaneo de las contraseñas de todas las redes WiFi guardadas en el dispositivo y generar un escaneo de los dispositivos y puertos abiertos dentro de la red a la que la máquina se encuentra conectada actualmente.




### NFC phishing
Por medio de la funcionalidad NFC del flipper zero, Al Capone tools cuenta con un script que genera una señal nfc que abre un sitio web de phishing. Siendo esta tercera herramienta más fácil de  detectar que las anteriores, más esta es compatible con dispositivos móviles como Iphones y Androids.


![enter image description here](https://i.ibb.co/b6cnCYL/BadUsb3.png)


### Space Hun Deauther
Space Hun Deauther es una herramienta para auditar redes WiFi en diferentes ataques inalambricos. Para lograr integrar de manera accesible esta herramienta al flipper zero, se utilizo un modulo nodemcu esp8266 conectado a traves de los GPIO del flipper zero para conseguir por medio de un add on accesible y facil de conseguir y fabricar, anadir una funcionalidad WiFi al dispositivo de flipper zero.


![enter image description here](https://i.ibb.co/LZmdHF8/BadUsb2.png)

