# **Practicas de clase**
---
## **Practica 1 - Encendido de LED**

### Introduccion y Objetivos

La práctica se enmarcó dentro de la materia de Introducción a la Mecatrónica y tuvo como finalidad el estudio y la aplicación del circuito integrado temporizador 555. El manejo de temporizadores y la generación de señales de reloj son fundamentales para el diseño de sistemas de control y automatización.

- Objetivos

Los objetivos principales de esta práctica fueron:

1.-Comprender el principio de funcionamiento del circuito integrado 555 en su configuración astable.

2.-Diseñar e implementar un circuito intermitente capaz de controlar el encendido y apagado de un LED.

3.-Calcular y ajustar los componentes pasivos ($R_1$, $R_2$ y $C_1$) para lograr un periodo de oscilación total (T) entre 1 y 5 segundos.


### Marco Teorico




### Procedimiento

- Materiales y Equipo
  * Circuito Integrado 555
  * LED 
  * Resistencias: $R_1 = 1 k\Omega$, $R_2 = 10 k\Omega$, $R_4 = 1 k\Omega$ (limitadora del LED).
  * Capacitor: $C_1 = 10 \mu F$, $C_2 = 0.01 \mu F$
  * Fuente de alimentación de $9V$ (VCC).
  * Protoboard y cables de conexión.
  * Osciloscopio y/o cronómetro (para verificación).


### Resultados



### Conclusion

- Descripción: Esta practica consisitio en llevar a cabo un circuito electrico utilizando un capacitor y un circuito integrado (chip 555) teniendo como objetivo encender y apagar una luz LED en un lapso de tiempo entre 1 a 5 segundos.

-<img src="recursos/imgs/practica1led.jpg" alt="Diagrama del sistema" width="300">


-[Video de Encendio del Led](recursos/archivos/practica1video.mp4)




## **Practica 2- Encendido de LED con ESP32**

- Descripción: 




## **Practica 3- Movimiento de motores con ESP32**

### Introduccion y Objetivos


### Marco Teorico




### Procedimiento

- **Materiales y Equipo**

1.- Microcontrolador ESP32 
2.- Motor de Corriente Continua 
3.- Módulo Puente H
4.- Protoboard
5.- Cables Jumper
6.- Fuente de Alimentación Externa (para el motor)
7.- Computadora con IDE de Arduino
8.- Cable USB (para el ESP32)

- **Procedimiento**
  
- 1. Montaje y Conexión del Hardware
     
1.- Conexión del Driver de Potencia: Conecta los pines de control lógico del Driver de Motor (Puente H) a los pines digitales del ESP32.
 * Conectar el pin de entrada 1 del driver a GPIO 25 (in1).
 * Conectar el pin de entrada 2 del driver a GPIO 26 (in2).

2.- Conexión del Motor: Conectar las dos terminales del Motor DC a las terminales de salida del Driver de Motor.

3.- Alimentación: Conectar la fuente de alimentación externa (ej. 9V) al pin de voltaje del Driver de Motor.
 * Asegúrarnos de que la tierra (GND) del ESP32 esté conectada a la tierra (GND) del Driver de Motor y de la fuente externa (tierra común).

4.- Alimentación Lógica: Conectar el ESP32 a la computadora mediante el cable USB para la alimentación lógica y la carga del código.


- 2. Codigo
 
```cpp
#define in1 25
#define in2 26

void setup() {
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
}

void loop() {

    digitalWrite(in1, 1); 
    digitalWrite(in2, 0); 
    delay(3000);
    digitalWrite(in1, 0); 
    digitalWrite(in2, 0); 
    delay(1000);
    digitalWrite(in1, 0); 
    digitalWrite(in2, 1); 
    delay(1000); 
  }

```


### Resultados



### Conclusion



- Descripción: Esta practica consistio en el funcionamiento de motores, como usarlos con las ESP32 y el codigo para hacerlos funcionar,  en esta practica teniamos que hacer que el motor acelerara poco a poco hasta la velocidad maxima y que luego desacelerara poco a poco hasta que se parara.

-<img src="recursos/imgs/Motores1.jpeg" alt="Diagrama del sistema" width="300">
-<img src="recursos/imgs/Motores2.jpeg" alt="Diagrama del sistema" width="300">
-<img src="recursos/imgs/Motores3.jpeg" alt="Diagrama del sistema" width="300">
-<img src="recursos/imgs/Motores4.jpeg" alt="Diagrama del sistema" width="300">

-[Video de Encendidi de Motores con ESP32](recursos/archivos/practicamotores.mp4)




## **Practica 4- Movimiento de servo-motores con ESP32**

### - 

- Descripción: 

