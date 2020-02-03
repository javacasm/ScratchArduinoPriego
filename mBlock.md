## Entornos de programación

Se puede programar con cualquier entorno donde se programe Arduino (IDE, Arduinoblocks, biblock, mBlock, etc.)

## Programación

### Usaremos el IDE de mBlock https://ide.mblock.cc 

Soporta Bluetooth Controller, Codey Rocky, HaloCode, mBot, MotionBlock, Neuron, mBot Ranger, Ultimate 2.0, Arduino Uno, Arduino Mega2560, Nova Pi, MegaPi Pro


### Necesitamos el mblock mlink  https://www.mblock.cc/en-us/download/

![mlink instalar](./imagenes/InstalarMlink.png)

[Guía de instalación](https://www.mblock.cc/doc/en/basics/mlink-quick-start-guide.html#mlink-quick-start-guide)

### Ejecutamos mLink

En windows
 
![mLink icon](https://www.mblock.cc/doc/en/basics/images/mlink-4.png)

En osX

![mlink osX](https://www.mblock.cc/doc/en/basics/images/mlink-8.png)

En linux

    sudo mblock-mlink start 
  

### Seleccionamos el dispositivo

Y pulsamos conectar

![conectar](https://www.mblock.cc/doc/en/basics/images/chromebook-7.png)

## Ejemplos

### Hello LED!!

Haremos parpadear el led Rojo

![Hello LED!](./imagenes/HelloLed!.png)

Ahora vamos a usar un led conectado al pin 11

![](./imagenes/Led3Uno_bb.png)

[Proyecto](https://planet.mblock.cc/project/102035)

### Graduando el brillo del led

Vamos hora a graduar el nivel de brillo

![](./imagenes/ControlBrilloLed.png)

[Proyecto](https://planet.mblock.cc/project/109965)

### Led RGB

¿Y si mezclamos colores?

![](./imagenes/LedRGB.png)

![Mezcla colores](./imagenes/Colores-MezclaRGB.jpeg)

[Selector de colores](https://htmlcolorcodes.com/es/)

Utilizamos el led RGB (conectado a lo pines digitales 9,5,6)

Y a la vez haremos que se vayan leyendo los colores en inglés, con la extensión Text To Speech.

Parece que hay algo de desajuste. Tendremos que mejorar la comunicación con ... mensajes    

![Programa Arduino](./imagenes/Colores-Arduino.png)
![Programa Osito](./imagenes/Colores-Osito.png)

[Programa](https://planet.mblock.cc/project/projectshare/101707)

Para usar la interconexión y la interacción vamos a hacer que nuestro arduino envíe unos mensaje con los colores que está mostrando. Osito, cuando los escuche pronunciará esos nombres en chino mandarín. Para ello hemos usado la extensión TTS (para hablar) y el traductor para traducir los nombres de los colores a chino

![ColoresMensajes](./imagenes/ColoresMensajes.png)

![OsitoColoresMensajes](./imagenes/OsitoColoresMensajes.png)

[Proyecto](https://planet.mblock.cc/project/102464)

### Sistema de riego


Vamos a medir la humedad del suelo para crear un sistema automático de riego
* Conectamos un sensor de humedad de suelo a la entrada IN de echidna (A4)
* Conectamos un servomotor para simular a la válvula/grifo que enciende el riego. Alternativamente podemos usarlo para mover un cartel/indicador que nos diga que la planta tiene sed

![riego](./imagenes/RiegoReleUno_bb.png)

![riego](./imagenes/Riego-arduino.png)

![](./imagenes/SensorHumedadArduino.png)

En función del nivel de humedad enviamos 3 mensajes distintos: Húmedo, Seco y Muy Seco

Se han creado varios fondos y varios personajes que cambian al recibir los mensajes

![](./imagenes/SensorHumedadFondo.png)
![](./imagenes/SensorHumedadObjetos.png)


[Proyecto](https://planet.mblock.cc/project/103662)


### Nivel de luz

Vamos a leer el valor de un sensor de luz

![](./imagenes/LDRUno_bb.png)

Con un programa sencillo vemos las lecturas mínimas y máximas. Marcamos el tick de la variable para poder ver su valor en pantalla>

![RangoSensor](./imagenes/RangoSensor.png)
[Proyecto](https://planet.mblock.cc/project/116536)

Si sustituimos la resistencia por un potenciómetro de 10k podemos ajustar más aún el rango del sensor. Conectaremos la patilla central y uno de los laterales (no importa cual, el usar uno u otro solo cambia el sentido de giro del potenciómetro para alcanzar el valor máximo o el mínimo)



![](./imagenes/LDRPotUno_bb.png)


Podemos controlar la posición de un relé que simula el abrir o cerrar una persiana. Hemos enviado unos mensajes para que otros objetos del programa puedan recibirlos e interactuar. Es una de las maneras de comunicar los dispositivos con los objetos/personajes del ordenador

![](./imagenes/LDRPotServoUno_bb.png)

![](./imagenes/LDRServoMensajes.png)

[Proyecto](https://planet.mblock.cc/project/116313)

En el ejemplo anterior hemos utilizado un comportamiento discreto, es decir sólo contemplábamos 2 estados posibles. Podemos cambiarlo para utilizar un rango continuo, transformando la medida del sensor de luz en una respuesta continua (representada en el movimiento del servo).

Para ello usaremos el bloque **mapeo** que está en la paleta **Datos** y que nos va a permitir transformar el valor de una variable desde su rango (los valores mínimos y máximos que puede alcanzar) a otro rango distinto (en este caso los ángulos de movimiento del servo)

![](./imagenes/LuzServoContinua.png)

[Proyecto](https://planet.mblock.cc/project/116546)



Usaremos los 3 leds de colores para indicar el nivel de luz:
* Rojo: luz baja
* Amarillo: nivel de luz medio
* Verde: luz suficiente



![](./imagenes/LDR_3xLedsUno_bb.png)

![NivelLuminoso](./imagenes/NivelLuminoso.png)

[Proyecto](https://planet.mblock.cc/project/102785)


### Controlando el movimiento de Osito con el Joystick

Conectamos el joystick a los pines analógicos A0 (eje x) y A1 (eje y). Vamos a ver los valores que encontramos.

![](./imagenes/JoystickUno_bb.png)

Vemos como la lectura de los sensores analógicos fluctúa, es algo normal. Un hardware más preciso (y caro) tendría una lectura más exacta.

Creamos una variables x e y para Arduino y comprobamos los valores del joystick


![Joystick Arduino](./imagenes/Joystick-Arduino.png)

![Joystick Osito](./imagenes/Joystick-Osito.png)

[Proyecto](https://planet.mblock.cc/project/102052) 


### Controlamos la posición de 2 servos usando el joystick

![2xServos-Joystick](./imagenes/2xServos-Joystick.png)

Controlamos la posición de 2 servos usando el joystick

[Proyecto](https://planet.mblock.cc/project/102156)

### Haciendo ruído

Veamos como hacer sonido con el zumbador: activamos y desactivamos rápidamente

Un poquito de física sobre frecuencias y periodos....

![Frecuencias y periosdos](./imagenes/frecuenciaYperiodo.png)

![Sonido 440Hz Original](./imagenes/Sonido440HzOrig.png)

Veremos que en modo "en vivo" no es suficientemente rápido y tenemos que irnos a modo Arduino

![Sonido 440Hz](./imagenes/Sonido440.png)

[Programa](https://planet.mblock.cc/project/102073)

Ejercicio: Ver como cambia el movimiento al enviar el programa anterior de los servos en modo Arduino
