# Iniciación a Arduino



# Software:

IDE

[arduino.cc/en/Main/Software](http://www.arduino.cc/en/Main/Software)


(instalación de driver en Windows) jiji




# ¿Qué es arduino?

[Arduino UNO](./imagenes/ArduinoPartes.png)



# ¿Qué tiene arduino?

Microcontrolador ATMega328

* 14 Entradas/Salidas digitales
* 6 Entradas Analógicas 0-5V de 10bits
* 32Kb de Memoria de programa
* 2Kb de Memoria RAM
* 512 bytes de EEPROM
* CPU a 16MHz
* Funciona a 5V
* Conexión USB




# Primera prueba

Ejemplo 1. Básicos - > Blink

[blink](./imagenes/arduino_blink-slow.gif)

    digitalWrite(pin_led,Estado); // Estado HIGH o LOW



### Programamos la placa

* Conectamos la placa con el cable USB

(instalación de driver en Windows) jiji

En el menú herramientas

* Seleccionamos el puerto
* Seleccionamos el tipo de placa
* Pulsamos el botón subir

[arduino-upload.gif](./imagenes/arduino_upload_button.png)



## Código

Veamos el código ....

[Blink.png](./imagenes/Blink.png)



# Led en el pin 9

[LED ](./imagenes/Led_bb.png)

## ¡¡¡ Resistencia Siempre 

[Breadboards](./imagenes/Sidekick_Breadboard_Internal_Connections.jpg)



## Código para led en 9

[Blink_9](./imagenes/Blink_9.png)




## Cuidados

* Montaje sin alimentación
* Led tiene polaridad
* Resistencia de al menos 220 Ohmios


# Programamos C++

## Está preparado para que sea sencillo



## Ejercicio: Kit o Cylon

#### 5 leds (con sus 5 resistencias)

[Kit_cylon_bb.png](./imagenes/Kit_cylon_bb.png)

[Código](./imagenes/kit.png)




# No todo es digital

    analogWrite(pin_led,brillo); // brillo entre 0 y 255

(Es un truco llamado [PWM](./imagenes/0_LPC1768_PWM.gif))

0 ----- 100 %

0 ----- 255

Ejemplo - > 1.Basic - > FADE



# Leemos voltajes

    int valor = analogRead(pin_analogico);
    // valor entre 0 y 1023

Rangos de lectura

0 ------ 5V

0 ------ 1023



# Potenciómetro

[potenciometro.jpg](./imagenes/potenciometro.jpg)

Ejemplos -> 3. Analog -> AnalogInput



# Lo sensores igual

#### Convertiremos voltaje a magnitud física

### Ejemplo TMP36 o LM35




## LM35 - Montaje

[LM35](./imagenes/LM35_bb.png)



## LM35 - Codigo

10 mV/C

[CodigoLM35](./imagenes/CodigoLM35.png)

by Luis Llamas [luisllamas.es](https://www.luisllamas.es/medir-temperatura-con-arduino-y-sensor-lm35/)





## Ejercicio:
### Ccontrolar brillo con potenciometro

[AnalogIn_PWMOut](./imagenes/AnalogIn_PWMOut.png)




#### Ejercicio: indicador de temperatura

* Leemos temperatura
* "Mapeamos" en brillo del led
* Usamos 2 leds (o led RGB) y
  * A más calor más rojo
  * A más frío más azul



#### Iindicador RGB temperatura


[Temperatura_RGB.png](./imagenes/Temperatura_RGB.png)



# Librerías

* Instalamos una librería
  * Gestor de librerías o Zip

* Usamos ejemplos
  * Servo -> Servo
  * Pantalla LCD - > LiquidCrystal
  * Sensor DHT - > SimpleDHT




## ¿Más allá de Arduino?

#### ESP8266 o NodeMCU

[NodeMCU_LoLin.png](./imagenes/NodeMCU_LoLin.png)



Todos los esquemas con [Fritzing](http://fritzing.org/)



# Para aprender más...

#### &lt; publicidad &gt; by @javacasm

## udemy.com/arduino-cero

#### &lt; /publicidad &gt;

## aprendiendoarduino.com

## programarfacil.com

## programoergosum.com
