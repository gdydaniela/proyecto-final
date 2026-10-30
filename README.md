
# <span style="color: #d63384;">🌸 Carpeta de Campo: Proyecto EcoSign BOT</span>
<div style="background-color: #f8d7da; padding: 2px; margin-bottom: 20px;"></div>

## <span style="color: #e83e8c;">1. Información General</span>
* **Título del Proyecto:** EcoSign BOT - Asistente robótico interactivo para la enseñanza  de la Lengua de Señas Argentina (LSA).
* **Institución:** Instituto Superior Santa María
* **Materia:** Robótica y Programación
* **Integrantes del Equipo:** Godoy Daniela, Portillo Catalina, Rodríguez Ariana y Gimenez Tanya
* **Profesor:** Juan Jose Campis

---

## <span style="color: #e83e8c;">2. Introducción y Justificación</span>
Hoy en día, la comunicación inclusiva es súper importante, pero la gran mayoría de las personas no sabe Lengua de Señas. Esto genera una barrera invisible que aísla a las personas sordas o con dificultades auditivas en su día a día, ya sea en la escuela, en el trabajo o en la calle.

* **Objetivo principal:** Diseñar la maqueta conceptual de un robot interactivo que sirva como una herramienta de apoyo y práctica para aprender Lengua de Señas, facilitando la interacción entre personas oyentes y no oyentes, la idea es implementarlos principalmente con los niños de nivel inical y primario.
* **Alcance:** Presentación del diseño, planificación, bocetos y el anteproyecto funcional de la maqueta, detallando los componentes electrónicos que se planean utilizar.

---

## <span style="color: #e83e8c;">3. ¿Cómo ayudaría este proyecto a la sociedad?</span>
Decidimos idear este proyecto porque creemos que la tecnología tiene que servir para resolver problemas reales. EcoSign BOT está pensado para aportar lo siguiente:

* **Facilita el aprendizaje:** Funciona como un tutor súper accesible para tener en la escuela o en casa y practicar LSA de forma divertida y sin miedo a equivocarse.
* **Rompe barreras:** Si más gente aprende desde chica, nos preparáremos para ser una sociedad mucho más empática y conectada con la comunidad sorda.
* **Inclusión real:** Demuestra que con pocos recursos se pueden planificar herramientas tecnológicas útiles para integrar a personas con discapacidad.
* **Da confianza:** Al ser un robot interactivo, ofrece un espacio propio para practicar, equivocarse y corregirse mediante luces y sonidos.

---

## <span style="color: #e83e8c;">4. Pros y Contras proyectados del diseño</span>

###  Pros 
* **Bajo costo y materiales accesibles:** El diseño contempla componentes fáciles de conseguir (**Arduino Uno**, **protoboard**, servomotores) y materiales reciclados como cartón o en caso de ser posible impresion 3D (que no seria tan economico)  
* **Es interactivo:** Combina movimientos físicos con luces LED y un parlante, haciendo que aprender sea dinámico y atrapante.
* **Fácil de adaptar:** Su estructura permite sumar más funciones o mejorar el código a futuro.

###  Contras 
* **Desgaste de los materiales:** Al proyectar el uso de cartón e hilos tensores para los dedos, sabemos que con el uso continuo requerirá mantenimiento, por eso es mas recomendable la impresion 3D
* **Calibración:** Dependiendo de la luz del ambiente, la cámara o los sensores pueden presentar pequeños desafíos al leer gestos.
* **Energía:** Al conectar varios componentes en la protoboard, habrá que cuidar bien la fuente de alimentación para evitar reinicios en la placa.

---

## <span style="color: #e83e8c;">5. Componentes Tecnológicos planificados</span>
Para armar la maqueta y el futuro prototipo de EcoSign BOT pensamos usar:
* **Placa Arduino Uno:** Será el cerebro de todo el proyecto para procesar las órdenes y controlar el circuito.
* **Protoboard:** Nos servirá para armar las conexiones eléctricas de manera ordenada y sin soldar de entrada.
* **Servomotores:** Los usaremos para mover los dedos de la mano robótica mediante hilos (como tendones).
* **Cámara:** Detectará los movimientos que haga el usuario frente al robot.
* **Luces LED:** Indicarán si la seña es correcta (verde), si hay que reintentar (amarillo) o si hubo un error (rojo).
* **Parlante:** Emitirá sonidos y avisos para acompañar la práctica.
* **Estructura:** Cartón corrugado, cartón rígido y materiales reciclados para darle forma al robot o impresion 3D

---

## <span style="color: #e83e8c;">6. Planificación de la Programación (Arduino Uno)</span>

### ¿Cómo se planea programar?

1. Conectaremos la placa **Arduino Uno** a la PC mediante un cable USB.
2. Cargaremos el código de prueba para verificar que los componentes respondan correctamente.

### Lógica prevista para los servomotores
Para mover los dedos del robot (simulando tendones con hilos), utilizaremos la librería de control de motores (`Servo.h`). En el bloque `setup()` configuraremos los pines y en el `loop()` programaremos los movimientos y las respuestas con luces y sonidos.

### Código base de prueba para el sistema:
```cpp
#include <Servo.h> // Librería para controlar los servomotores

Servo dedoPulgar;  // Objeto para el servomotor del dedo

const int ledVerde = 4;
const int ledRojo = 5;
const int pinParlante = 8;

void setup() {
  dedoPulgar.attach(9); // Servomotor conectado al pin digital 9
  
  pinMode(ledVerde, OUTPUT);
  pinMode(ledRojo, OUTPUT);
  pinMode(pinParlante, OUTPUT);
  
  dedoPulgar.write(0); // Posición inicial de reposo
}

void loop() {
  // Simulación de respuesta correcta del sistema
  digitalWrite(ledVerde, HIGH);          
  tone(pinParlante, 1000, 200);          
  
  // Mueve el servomotor para realizar la seña
  dedoPulgar.write(90); 
  delay(1500);                           
  
  // Regresa a la posición de descanso
  digitalWrite(ledVerde, LOW);
  dedoPulgar.write(0);
  delay(1500);                           
}
![enter image description here](https://raw.githubusercontent.com/gdydaniela/proyecto-final/refs/heads/main/imagen/7daf2817-466d-43d1-a259-ec5cd59abcc2.jfif)