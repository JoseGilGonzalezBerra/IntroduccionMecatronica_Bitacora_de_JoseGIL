# **Practicas de clase**
---
## **Practica 1 - Encendido de LED**

### Introduccion y Objetivos

La práctica se enmarcó dentro de la materia de Introducción a la Mecatrónica y tuvo como finalidad el estudio y la aplicación del circuito integrado temporizador 555. El manejo de temporizadores y la generación de señales de reloj son fundamentales para el diseño de sistemas de control y automatización.

- Objetivos

Los objetivos principales de esta práctica fueron:

 * Comprender el principio de funcionamiento del circuito integrado 555 en su configuración astable.
 * Diseñar e implementar un circuito intermitente capaz de controlar el encendido y apagado de un LED.
 * Calcular y ajustar los componentes pasivos ($R_1$, $R_2$ y $C_1$) para lograr un periodo de oscilación total (T) entre 1 y 5 segundos.


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

### Introduccion

La Práctica 3, "Movimiento de motores con ESP32", tuvo como objetivo principal la integración de un sistema embebido (ESP32) con un sistema de actuación (motor DC) utilizando un módulo controlador Puente H. Esta práctica es fundamental en el campo de la Mecatrónica, ya que establece las bases para el control de movimiento y la dirección de actuadores en sistemas automatizados y robótica.

- Objetivos:

- Los objetivos principales de esta práctica fueron:
 * Establecer la comunicación y el control de un motor de corriente continua (DC) mediante el microcontrolador ESP32 y un driver de motor.
 *  Implementar el control de dirección del motor, logrando que gire en un sentido, se detenga y luego gire en el sentido opuesto.
 *   Programar y controlar la temporización de cada estado de movimiento (avance, paro y reversa) utilizando funciones de retardo (delay).

### Marco Teorico

- Motores DC (Actuador)
El Motor de Corriente Continua (DC) es el componente que convierte la energía eléctrica en movimiento mecánico. Su característica esencial en esta práctica es que su dirección de giro está determinada por la polaridad del voltaje que se le aplica a sus terminales.

- Driver de Motor (Puente H)
El circuito Puente H es un módulo de potencia indispensable que actúa como intermediario. Su función principal es doble: primero, suministrar la alta corriente necesaria para el motor utilizando una fuente externa (ya que el ESP32 no puede hacerlo); y segundo, controlar la dirección del motor. El Puente H invierte la polaridad del voltaje aplicado al motor según las señales lógicas que recibe.

- Interconexión y Control Lógico
La interconexión se establece utilizando los pines del ESP32 para enviar señales de control al Puente H. Específicamente, dos pines del ESP32 (in1 e in2) se conectan a las entradas lógicas del Puente H.


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
  
- Montaje y Conexión del Hardware
     
1.- Conexión del Driver de Potencia: Conecta los pines de control lógico del Driver de Motor (Puente H) a los pines digitales del ESP32.
 * Conectar el pin de entrada 1 del driver al pin 25 (in1).
 * Conectar el pin de entrada 2 del driver al pin 26 (in2).

2.- Conexión del Motor: Conectar las dos terminales del Motor DC a las terminales de salida del Driver de Motor.

3.- Alimentación: Conectar la fuente de alimentación externa al pin de voltaje del Driver de Motor.
 * Asegúrarnos de que la tierra (GND) del ESP32 esté conectada a la tierra (GND) del Driver de Motor y de la fuente externa (tierra común).

4.- Alimentación Lógica: Conectar el ESP32 a la computadora mediante el cable USB para la alimentación lógica y la carga del código.

5.- Subimo el codigo a la ESP32
 
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

El circuito implementado con el ESP32 ejecutó la secuencia programada, logrando el control de la dirección y la temporización del motor.

- Sentido 1 (Avance/Giro): El motor giró en la primera dirección durante 3 segundos (delay(3000)).
- Paro por Inercia: El motor se detuvo por completo por inercia durante 1 segundo (delay(1000)).
- Sentido 2 (Reversa/Contragiro): El motor giró en la dirección opuesta durante 1 segundo (delay(1000)).


### Conclusion

La práctica fue exitosa al demostrar el control básico de dirección y temporización de un motor DC utilizando el ESP32 y un driver Puente H. Se logró controlar la dirección de giro y la duración de cada estado (avance, paro y reversa) mediante los comandos digitalWrite() y delay(). Esto confirmó la comprensión de la lógica del driver y la capacidad del ESP32 para manejar la actuación.


-<img src="recursos/imgs/Motores1.jpeg" alt="Diagrama del sistema" width="300">
-<img src="recursos/imgs/Motores2.jpeg" alt="Diagrama del sistema" width="300">
-<img src="recursos/imgs/Motores3.jpeg" alt="Diagrama del sistema" width="300">
-<img src="recursos/imgs/Motores4.jpeg" alt="Diagrama del sistema" width="300">

-[Video de Encendidi de Motores con ESP32](recursos/archivos/practicamotores.mp4)




## **Practica 4 - Aceleracion y desaceleracion de motores con ESP32**

### Introduccion

La Práctica de Control de Velocidad con ESP32 tuvo como enfoque principal la aplicación de la Modulación por Ancho de Pulso (PWM) para lograr un control fino y gradual del movimiento de un motor de corriente continua (DC). El objetivo fue ir más allá del control simple de encendido/apagado para implementar una variación dinámica de la velocidad.

- Objetivos:

- Los objetivos principales de esta práctica fueron:
   1.- Configurar y utilizar el hardware de PWM del microcontrolador ESP32 para generar una señal de velocidad.
   2.- Implementar un algoritmo que permita al motor acelerar progresivamente hasta su velocidad máxima.
   3.- Implementar un algoritmo que, al alcanzar la velocidad máxima o un umbral predefinido, inicie una desaceleración o un cambio en la rampa de velocidad.

### Marco Teorico

- Motores DC (Actuador):

El Motor DC es el actuador cuya velocidad se controla. Su velocidad de rotación es directamente proporcional al voltaje promedio que recibe. La dirección de giro se mantiene fija en esta práctica mediante una polaridad constante.

- Driver de Motor (Puente H)

El Driver de Motor (Puente H) es esencial para suministrar la alta corriente que el ESP32 no puede proveer. En esta práctica, el Puente H cumple dos funciones:

 * Control de Dirección: Los pines in1 y in2 se fijan en un estado lógico (1 y 0) para mantener una dirección constante.
 * Control de Velocidad: El pin PWM del ESP32 se conecta al pin de Enable del driver para modular el voltaje promedio que llega al motor.

- Modulación por Ancho de Pulso (PWM):

El PWM es la técnica central para el control de velocidad. El ESP32 utiliza la API ledc para generar una señal digital cuyo ciclo de trabajo (el tiempo que la señal está en ALTO) varía.

 * ledcAttachChannel(pin, freq, bits, channel): Inicializa un canal PWM. En el código, la resolución de 8 bits define que la velocidad varía de $0$ (apagado) a $255$ (máximo).
 * 
 * ledcWrite(): Es la función que establece el ciclo de trabajo, controlando directamente la velocidad del motor.


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
  
1. Montaje y Conexión del Hardware
     
1.- Conexión del Driver de Potencia: Conecta los pines de control lógico del Driver de Motor (Puente H) a los pines digitales del ESP32.
 * Conectar el pin de entrada 1 del driver a pin 32 (in1).
 * Conectar el pin de entrada 2 del driver a pin 33 (in2).

2.- Conexión del Motor: Conectar las dos terminales del Motor DC a las terminales de salida del Driver de Motor.

3.- Conexión PWM: El pin 25 (definido implícitamente por el canal 0 en ledcAttachChannel) o un pin equivalente (esto debe revisarse, ya que ledcWrite usa el número de canal o el pin) se conecta al pin de Enable/Velocidad del driver.

4.- Alimentación: Conectar la fuente de alimentación externa al pin de voltaje del Driver de Motor.
 * Asegúrarnos de que la tierra (GND) del ESP32 esté conectada a la tierra (GND) del Driver de Motor y de la fuente externa (tierra común).

5.- Alimentación Lógica: Conectar el ESP32 a la computadora mediante el cable USB para la alimentación lógica y la carga del código.


6.- Subimos el codigo a la ESP32
 
```cpp
#define in1 32
#define in2 33
int var=20;
 
void setup() {
 
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  ledcAttachChannel(25, 1000, 8 , 0);
  Serial.begin(115200);
 
 
}
 
void loop() {
  Serial.println(var);
  ledcWrite(25, var);
  digitalWrite(in1,1);
  digitalWrite(in2,0);
  delay(1000);
  var=var+20;
  if(var>255){
     var=var-80;
  }  
  delay(1000);
 
}

```


### Resultados

- Aceleración: El motor aumentó su velocidad en pasos de 20 unidades de PWM cada 2 segundos.

- Desaceleración/Salto: En lugar de una desaceleración gradual, se observó un salto repentino a una velocidad menor cuando el contador var superó 255, seguido de una nueva aceleración.

- Dirección: La dirección de giro se mantuvo fija durante todo el experimento.

### Conclusion

La práctica fue exitosa en la implementación de PWM para el control de velocidad del motor DC con el ESP32. Se logró un control dinámico donde el motor aceleró continuamente. El principal aprendizaje fue el uso de la función ledcWrite() para modular la velocidad y la importancia de la resolución de 8 bits (0-255). Sin embargo, el mecanismo implementado para manejar el exceso de velocidad (la caída de 80 unidades) resultó en un salto brusco de velocidad, no en una desaceleración progresiva y suave.



