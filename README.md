# INTERFAZ-II
1. [Hola Mundo](#ejercicio-n-1-arduino-hola-mundo) <br>
2. [Semáforo](#ejercicio-n-2-arduino-sem%C3%A1foro) <br>
3. [Led Parpadeante](#ejercicio-n-3-arduino-led-parpadeante) <br>
4. [Control por Pulsador](#ejercicio-n-4-arduino-control-por-pulsador) <br>
5. [Led potenciometro](#ejercicio-n-5-arduino-led-potenciometro) <br>

### Ejercicio n° 1 Arduino: "Hola mundo"

```js
void setup() {
  Serial.begin(9600); // Inicia la comunicación serie a 9600 bps
  Serial.println("Hola, Mundo!"); // Envía "Hola, Mundo!" al monitor serie
}

void loop() {
  // No es necesario poner nada en el loop para este ejemplo
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/holamundo.png" width="1024" height="550" />

### Ejercicio n° 2 Arduino: "semáforo"
```js
// C++ code - Semáforo Autos y Peatones

// Definición de pines
int LED_1 = 6;  // Luz roja autos
int LED_2 = 7;  // Luz amarilla autos
int LED_3 = 8;  // Luz verde autos
int LED_4 = 9;  // Luz verde peatones
int LED_5 = 10; // Luz roja peatones

void setup() {
  // Configuramos todos los pines como salida
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(LED_3, OUTPUT);
  pinMode(LED_4, OUTPUT);
  pinMode(LED_5, OUTPUT);
}

void loop() {
  // 🚦 Fase 1: Autos en verde, peatones en rojo
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 2: Amarillo autos, peatones siguen en rojo
  digitalWrite(LED_3, LOW);   // Verde autos apagado
  digitalWrite(LED_2, HIGH);  // Amarillo autos encendido
  delay(2000); // 2 segundos
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado

  // 🚦 Fase 3: Rojo autos, verde peatones
  digitalWrite(LED_1, HIGH);  // Rojo autos encendido
  digitalWrite(LED_5, LOW);   // Rojo peatones apagado
  digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 4: Rojo autos, rojo peatones (tiempo intermedio)
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  //delay(2000); // se borra el delay
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/sem%C3%A1foro.png" />


### Ejercicio n° 3 Arduino: "Led parpadeante"

```js
void setup() {  // Configuración inicial (ej: pines como entrada/salida)
pinMode(13, OUTPUT); // Pin 13 como salida
pinMode(8, OUTPUT);
  
}

void loop() {   // Se repite infinitamente
  digitalWrite(13, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(13, LOW);   // Apagar LED
  //delay(1000);  // Esperar 1 segundo

  digitalWrite(8, HIGH);  // Encender LED
  delay(500);             // Esperar 1 segundo
  digitalWrite(8, LOW);   // Apagar LED
  //delay(500);   

}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/LedParpadeante.png" width="1024" height="550" />

### Ejercicio n° 4 Arduino: "control por pulsador"

```js
void setup() {
  pinMode(2, INPUT);  // Botón como entrada
  pinMode(13, OUTPUT);
}
void loop() {
  if (digitalRead(2) == HIGH) {  // Si se presiona el botón
    digitalWrite(13, HIGH);
  } else {
    digitalWrite(13, LOW);
  }
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/Controlpulsador.png" width="1024" height="550" />

<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/BotonPulsador.png" />


### Ejercicio n° 5 Arduino: "Led potenciometro"

```js
void setup() {
  pinMode(9, OUTPUT);  // Pin PWM (símbolo ~)
}
void loop() {
  int valor = analogRead(A0);           // Leer potenciómetro (0-1023)
  int brillo = map(valor, 0, 1023, 0, 255);  // Convertir a rango PWM
  analogWrite(9, brillo);               // Ajustar brillo
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/Ledpotenciometro.png" width="1024" height="550" />


### Ejercicio n° 6 Arduino: "Semáforo parpadeante"
```js
// C++ code - Semáforo Autos y Peatones

// Definición de pines
int LED_1 = 6;  // Luz roja autos
int LED_2 = 7;  // Luz amarilla autos
int LED_3 = 8;  // Luz verde autos
int LED_4 = 9;  // Luz verde peatones
int LED_5 = 10; // Luz roja peatones

void setup() {
  // Configuramos todos los pines como salida
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(LED_3, OUTPUT);
  pinMode(LED_4, OUTPUT);
  pinMode(LED_5, OUTPUT);
}

void loop() {
  // 🚦 Fase 1: Autos en verde, peatones en rojo
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 2: Amarillo autos, peatones siguen en rojo
  digitalWrite(LED_3, LOW);   // Verde autos apagado
  digitalWrite(LED_2, HIGH);  // Amarillo autos encendido
  delay(2000); // 2 segundos
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado

  // 🚦 Fase 3: Rojo autos, verde peatones
  digitalWrite(LED_1, HIGH);  // Rojo autos encendido
  digitalWrite(LED_5, LOW);   // Rojo peatones apagado
  digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(5000);
  digitalWrite(LED_4, LOW);
  delay(500);
  digitalWrite(LED_4, HIGH);
  delay(500);
  digitalWrite(LED_4, LOW);
  delay(500);
  digitalWrite(LED_4, HIGH);
  delay(500);
  digitalWrite(LED_4, LOW);
   delay(500);
  digitalWrite(LED_4, HIGH);
  delay(500);
  digitalWrite(LED_4, LOW);
  delay(500);
  digitalWrite(LED_4, HIGH);
  delay(500);
  digitalWrite(LED_4, LOW);
  delay(500);


  // 🚦 Fase 4: Rojo autos, rojo peatones (tiempo intermedio)
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  //delay(2000); // 2 segundos
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/semaforo%20parpadeante.png" />

### Ejercicio n° 7 Arduino + Processing: "Potenciometro"

#### Codigo Arduino
```js
unsigned int ADCValue;
void setup(){
    Serial.begin(9600);
}

void loop(){

 int val = analogRead(0);
   val = map(val, 0, 300, 0, 255);
    Serial.println(val);
delay(50);
}
```

#### Codigo Processing
```js
import processing.serial.*;

Serial myPort;  // Crear objeto de la clase Serial
static String val;    // Datos recibidos desde el puerto serial
int sensorVal = 0;

void setup()
{
  //background(0); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM3";// Cambia el número (en este caso) para que coincida con el puerto correspondiente conectado a tu Arduino. 

  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);

}

void draw()
{
  if ( myPort.available() > 0) {  // Si hay datos disponibles,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // léelos y guárdalos en vals!
  }  
 //background(0);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 0 y 175
  float c = map(sensorVal, 0, width, 0, 400);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 40 y 300
  float d = map(sensorVal, 0, width, 40,400);
  fill(255, c, 0);
  ellipse(width/5, height/4, d, d);   
  ellipse(width/5, height/3, d, d); 
  ellipse(width/5, height/2, d, d); 
  ellipse(width/5, height/1, d, d); 
  ellipse(width/5, height/7, d, d);   
  ellipse(width/1.5, height/7, d, d); 
  ellipse(width/1.5, height/1.2, d, d); 
  ellipse(width/1.5, height/2, d, d); 
  
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/potenciometro.png" />

### Ejercicio n° 8 Boton Arduino + Processing: Circulos

#### Codigo Arduino
```js
int buttonPin = 2;  // Pin del botón
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    Serial.println(1);        // Enviar un "1" a Processing
    delay(200);               // Evitar rebotes
  }
}
```

#### Codigo Processing
```js
import processing.serial.*;

Serial myPort;
ArrayList<PVector> circles; 

void setup() {
  size(1920, 1080);
  background(#E8DFCC);
  
  // Ajusta el nombre del puerto según tu Arduino
  println(Serial.list());
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<PVector>();
}

void draw() {
  //background(0);
  
  // Dibujar círculos almacenados
  fill(169, 210, 242);
  //noStroke();
  stroke(252, 254, 255);
  for (PVector c : circles) {
    ellipse(c.x, c.y, 100, 50);
    ellipse(c.x, c.y, 50, 100);
  }
  
  // Revisar si llega algo de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        // Cada vez que se aprieta el botón, agregar un círculo en posición aleatoria
        circles.add(new PVector(random(width), random(height)));
      }
    }
  }
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/Arduino%2BProcessing%20pulsador.png" width="1024" height="550" />

### Ejercicio n° 9 Arduino + processing + boton + potenciometro

#### Codigo Arduino
```js
int buttonPin = 2;       // Pin del botón
int potPin = A0;         // Pin del potenciómetro
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    int potValue = analogRead(potPin);   // 0 - 1023
    Serial.print("BTN,");     // etiqueta para Processing
    Serial.println(potValue); // mando el valor junto con el evento
    delay(200);               // debounce simple
  }
}
```
#### Codigo Processing
```js
import processing.serial.*;

Serial myPort;
ArrayList<CircleData> circles; 

void setup() {
  size(1200, 720);
  background(#F0E1FA);
  
  // Ajusta el puerto según tu Arduino
  println(Serial.list());
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<CircleData>();
}

void draw() {
  //background(0);
  
  // Dibujar todos los círculos guardados
  //fill(0, 150, 255);
  //noStroke();
  stroke(241, 239, 232);
  for (CircleData c : circles) {
    fill(240, 213, 155);
    ellipse(c.x, c.y, c.size*2, 200);
    
    fill(197, 156, 224);
    ellipse(c.x, c.y, c.size*2, 100);
    
  }
  
  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.startsWith("BTN")) {
        // Extraer el valor del potenciómetro
        String[] parts = split(val, ',');
        if (parts.length == 2) {
          float potVal = float(parts[1]);
          float circleSize = map(potVal, 0, 1023, 10, 100); // tamaño 10-100 px
          circles.add(new CircleData(random(width), random(height), circleSize));
        }
      }
    }
  }
}

// Clase para guardar datos de cada círculo
class CircleData {
  float x, y, size;
  CircleData(float x, float y, float size) {
    this.x = x;
    this.y = y;
    this.size = size;
  }
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/Arduino%2Bprocessing%2Bboton%2Bpulsador.png" width="1024" height="550" />


### ejercicio n° 10 Arduino Botón processing 

#### Processing
```js
import processing.serial.*;

Serial myPort;
ArrayList<CircleData> circles;

void setup() {
  size(1200, 720);
  background(0);
 
  // Ajusta el puerto según tu Arduino
  println(Serial.list());
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);
 
  circles = new ArrayList<CircleData>();
}

void draw() {
  //background(random(0, 10), random(0, 255));
 
  // Dibujar todos los círculos guardados
  //fill(0, 150, 255);
  //noStroke();
  fill(0, 150, 0);
  //stroke(0, 150, 0);
  for (CircleData c : circles) {
    ellipse(c.x, c.y, c.size, random (10, 200));
  }
 
  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.startsWith("BTN")) {
        // Extraer el valor del potenciómetro
        String[] parts = split(val, ',');
        if (parts.length == 2) {
          float potVal = float(parts[1]);
          float circleSize = map(potVal, 0, 1023, 10, 100); // tamaño 10-100 px
          circles.add(new CircleData(random(width), random(height), circleSize));
        }
      }
    }
  }
}

// Clase para guardar datos de cada círculo
class CircleData {
  float x, y, size;
  CircleData(float x, float y, float size) {
    this.x = x;
    this.y = y;
    this.size = size;
}
```
### Ejercicio n° 11 Arduino Botonera

```js
// --- Configuración de botones ---
const int numButtons = 3;
const int buttonPins[numButtons] = {2, 4, 7};
const int ledButtonPins[numButtons] = {9, 10, 11}; // LEDs botones

// --- Configuración de potenciómetros ---
const int numPots = 2;
const int potPins[numPots] = {A0, A1};
const int ledPotPins[numPots] = {3, 5}; // LEDs PWM

// Variables de estados previos
int lastButtonState[numButtons];
int lastPotValue[numPots];

void setup() {
  Serial.begin(9600);

  // Configurar botones y LEDs
  for (int i = 0; i < numButtons; i++) {
    pinMode(buttonPins[i], INPUT_PULLUP);
    pinMode(ledButtonPins[i], OUTPUT);
    lastButtonState[i] = digitalRead(buttonPins[i]);
  }

  // Configurar LEDs de potenciómetros
  for (int i = 0; i < numPots; i++) {
    pinMode(ledPotPins[i], OUTPUT);
    lastPotValue[i] = analogRead(potPins[i]);
  }
}

void loop() {
  // Leer y enviar botones
  for (int i = 0; i < numButtons; i++) {
    int buttonState = digitalRead(buttonPins[i]);

    // LED se enciende cuando botón está presionado
    digitalWrite(ledButtonPins[i], buttonState == LOW ? HIGH : LOW);

    if (buttonState != lastButtonState[i]) {  // enviar cambios
      Serial.print("B");
      Serial.print(i);
      Serial.print(":");
      Serial.println(buttonState);
      lastButtonState[i] = buttonState;
    }
  }

  // Leer y enviar potenciómetros
  for (int i = 0; i < numPots; i++) {
    int potValue = analogRead(potPins[i]); // 0–1023
    int pwmValue = potValue / 4;           // 0–255

    // Ajustar LED según valor
    analogWrite(ledPotPins[i], pwmValue);

    if (abs(pwmValue - lastPotValue[i]) > 2) { // evitar ruido
      Serial.print("P");
      Serial.print(i);
      Serial.print(":");
      Serial.println(pwmValue);
      lastPotValue[i] = pwmValue;
    }
  }

  delay(10);}
}
```

### Processing Botonera
```js
// Importamos librería para comunicación serial
import processing.serial.*;
// Importamos librería Minim para manejar audio
import ddf.minim.*;

// Declaramos el objeto serial para comunicarnos con Arduino
Serial myPort;
// Objeto principal de Minim
Minim minim;
// Array de reproductores de audio (3 pistas)
AudioPlayer[] players;
// Variable para guardar el índice de la pista que está sonando
int currentTrack = -1;  // -1 significa que no hay pista activa al inicio

void setup() {
  size(400, 200); // Ventana de 400x200 píxeles
 
  // --- Configuración del puerto serial ---
  printArray(Serial.list()); // Muestra en consola la lista de puertos disponibles
  myPort = new Serial(this, Serial.list()[0], 9600); // Abrimos el primer puerto de la lista a 9600 baudios
 
  // --- Configuración de audio ---
  minim = new Minim(this); // Inicializamos Minim
  players = new AudioPlayer[3]; // Creamos un array de 3 reproductores
 
  // Cargamos los 3 archivos de audio desde la carpeta "data"
  players[0] = minim.loadFile("1.mp3", 2048);
  players[1] = minim.loadFile("2.mp3", 2048);
  players[2] = minim.loadFile("3.mp3", 2048);
}

void draw() {
  background(0); // Fondo negro
  fill(255);     // Color blanco para el texto
  textSize(16);  // Tamaño del texto
 
  // Mostramos en pantalla qué botón está activo
  text("Botón actual: " + (currentTrack == -1 ? "ninguno" : currentTrack), 20, 40);
}

void serialEvent(Serial myPort) {
  // Leemos la cadena que llega desde Arduino hasta el salto de línea
  String inString = trim(myPort.readStringUntil('\n'));
 
  // Si no llega nada, salimos
  if (inString == null) return;

  // --- Si el mensaje recibido empieza con "B" significa que es un botón ---
  if (inString.startsWith("B")) {
    // Quitamos la letra "B" y separamos el mensaje en partes (ejemplo "0:0")
    String[] parts = split(inString.substring(1), ':');
   
    // Si realmente recibimos dos partes (índice y estado)
    if (parts.length == 2) {
      int buttonIndex = int(parts[0]); // Número del botón (0,1,2)
      int state = int(parts[1]);       // Estado del botón (0 = presionado, 1 = suelto)
     
      // Si el botón fue presionado (LOW = 0 en Arduino)
      if (state == 0) {
        playTrack(buttonIndex); // Llamamos a la función para reproducir la pista correspondiente
      }
    }
  }
}

// --- Función que reproduce una pista según el botón ---
void playTrack(int index) {
  // Si ya había una pista sonando, la pausamos y la rebobinamos al inicio
  if (currentTrack != -1 && players[currentTrack].isPlaying()) {
    players[currentTrack].pause();
    players[currentTrack].rewind();
  }
 
  // Reproducimos en bucle la pista seleccionada
  players[index].loop();
 
  // Actualizamos la variable para saber cuál es la pista activa
  currentTrack = index;
}
```
### Ejercicio n° 13 Arduino + processing "nebulosa con potenciometro"

#### codigo Noise 3D (processing)
```js
/**
 * Noise3D. 
 * 
 * Using 3D noise to create simple animated texture. 
 * Here, the third dimension ('z') is treated as time. 
 */
 
float increment = 0.01;
// The noise function's 3rd argument, a global variable that increments once per cycle
float zoff = 0.0;  
// We will increment zoff differently than xoff and yoff
float zincrement = 0.02; 

void setup() {
  size(640, 360);
  frameRate(30);
}

void draw() {
  
  // Optional: adjust noise detail here
  // noiseDetail(8,0.65f);
  
  loadPixels();

  float xoff = 0.0; // Start xoff at 0
  
  // For every x,y coordinate in a 2D space, calculate a noise value and produce a brightness value
  for (int x = 0; x < width; x++) {
    xoff += increment;   // Increment xoff 
    float yoff = 0.0;   // For every xoff, start yoff at 0
    for (int y = 0; y < height; y++) {
      yoff += increment; // Increment yoff
      
      // Calculate noise and scale by 255
      float bright = noise(xoff,yoff,zoff)*255;

      // Try using this line instead
      //float bright = random(0,255);
      
      // Set each pixel onscreen to a grayscale value
      pixels[x+y*width] = color(bright,bright,bright);
    }
  }
  updatePixels();
  
  zoff += zincrement; // Increment zoff
  
  
}
```

#### codigo arduino

```js
void setup() {
  Serial.begin(9600);
}

void loop() {
  int val = analogRead(A0);       // Lee el potenciómetro (valor entre 0 y 1023)
  Serial.println(val);            // Envia el valor por el puerto serial
  delay(20);                      // Pequeño retraso para evitar saturar el puerto
}
```

#### codigo processing

```;
import processing.serial.*;

Serial myPort;
String val;
int sensorVal = 0;

float increment = 0.01;
float zoff = 0.0;
float zincrement = 0.02;

void setup() {
  size(920, 720);
  frameRate(30);
  noSmooth();

  println(Serial.list());  // Imprime la lista de puertos seriales para verificar
  String portName = Serial.list()[0];  // Cambia el índice si no es el puerto correcto
  myPort = new Serial(this, portName, 9600);
  myPort.bufferUntil('\n');  // Configura para leer hasta salto de línea
}

void draw() {
  background(0);

  // Mapear valores del potenciómetro (0-1023) a parámetros visuales
  zincrement = map(sensorVal, 0, 1023, 0.005, 0.05);
  float colorShift = map(sensorVal, 0, 1023, 0, 2530);

  loadPixels();

  float xoff = 0.0;

  for (int x = 0; x < width; x++) {
    xoff += increment;
    float yoff = 0.0;

    for (int y = 0; y < height; y++) {
      yoff += increment;

      float n = noise(xoff, yoff, zoff);

      float r = map(sin(TWO_PI * n + radians(colorShift)), -1, 1, 40, 250);
      float g = map(cos(TWO_PI * n + radians(colorShift * 1.2)), -1, 1, 50, 255);
      float b = map(sin(TWO_PI * n + radians(colorShift * 0.5)), -1, 1, 20, 255);

      pixels[x + y * width] = color(r, g, b);
    }
  }

  updatePixels();

  zoff += zincrement;
}

// Evento que se llama cuando llega una línea completa por serial
void serialEvent(Serial myPort) {
  val = myPort.readStringUntil('\n');
  if (val != null) {
    val = trim(val);
    if (val.length() > 0) {
      try {
        sensorVal = int(val);
        // println(sensorVal);  // Descomenta para depurar
      } catch (Exception e) {
        println("Error al convertir:", val);
      }
    }
  }
}

```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/nebulosa.png" width="1024" height="550" />

### Ejercicio n° 14 Arduino + processing: "sensor de movimiento"

#### codigo arduino
```;
// Definir el pin del sensor Sharp
int sharpPin = A0;

void setup() {
  Serial.begin(9600); // Iniciar comunicación serial
}

void loop() {
  int sensorValue = analogRead(sharpPin); // Leer valor del sensor
  Serial.println(sensorValue); // Enviar valor a Processing
  delay(100); // Esperar un momento
}
```

#### codigo processing
```;
import processing.serial.*;

Serial myPort;  // Create object from Serial class
static String val;    // Data received from the serial port
int sensorVal = 0;

void setup()
{
  background(0); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM5";// Change the number (in this case ) to match the corresponding port number connected to your Arduino. 

  myPort = new Serial(this, Serial.list()[0], 9600);
}

void draw()
{
  if ( myPort.available() > 0) {  // If data is available,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // read it and store it in vals!
  }  
 //background(0);
  // Scale the mouseX value from 0 to 640 to a range between 0 and 175
  float c = map(sensorVal, 0, width, 0, 400);
  // Scale the mouseX value from 0 to 640 to a range between 40 and 300
  float d = map(sensorVal, 0, width, 40,500);
  fill(255, c, 0);
  ellipse(width/2, height/2, d, d);   

}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/sensor.png" width="1024" height="550" />

### Ejercicio n° 15 processing: "VIDEO ascii"

```;
import processing.video.*;

Capture cam;
String asciiChars = "<3 * -+ :p";  // Characters from dark to light
int cols, rows;
int cellSize = 15; // Size of each ASCII cell

void setup() {
  size(640, 480);
  cam = new Capture(this, 640, 480);
  cam.start();
  textAlign(CENTER, CENTER);
  textSize(cellSize);
  cols = width / cellSize;
  rows = height / cellSize;
}

void draw() {
  if (cam.available() == true) {
    cam.read();
  }

  cam.loadPixels();
  background(0);

  for (int y = 0; y < rows; y++) {
    for (int x = 0; x < cols; x++) {
      int pixelX = x * cellSize;
      int pixelY = y * cellSize;
      int index = pixelX + pixelY * cam.width;
      color c = cam.pixels[index];
      
      // Calculate brightness and map it to ASCII characters
      float bright = brightness(c);
      int charIndex = int(map(bright, 0, 255, asciiChars.length() - 1, 0));
      String asciiChar = asciiChars.substring(charIndex, charIndex + 1);

      fill(255);
      text(asciiChar, pixelX + cellSize * 0.5, pixelY + cellSize * 0.5);
    }
  }
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/video.png" width="1024" height="550" />

### Ejercicio n° 16 "VIDEO Glitch"

#### codigo arduino
```;
void setup() {
  Serial.begin(9600);
}

void loop() {
  int pot1 = analogRead(A0);  // Read first potentiometer
  int pot2 = analogRead(A1);  // Read second potentiometer

  // Send potentiometer values as comma-separated values
  Serial.print(pot1);
  Serial.print(",");
  Serial.println(pot2);
  
  delay(50);  // Delay to reduce data rate
}
```

#### codigo processing
```;
import processing.serial.*;
import processing.video.*;

Serial arduinoPort;
Movie video;
boolean glitch = false;
int glitchIntensity = 0; // Adjusts how many pixels are affected
float glitchFrequency = 0; // Adjusts how frequently glitch is applied

void setup() {
  size(640, 480);
  
  // Set up serial communication
  arduinoPort = new Serial(this, Serial.list()[0], 9600); // Adjust port if needed
  
  // Load video
  video = new Movie(this, "video.mp4");
  video.loop();
}

void draw() {
  if (video.available()) {
    video.read();
  }
  
  video.loadPixels();
  
  // Apply glitch effect based on potentiometer values
  if (glitch) {
    for (int i = 0; i < video.pixels.length; i++) {
      if (random(1) < glitchFrequency) {
        video.pixels[i] = color(random(255), random(255), random(255), glitchIntensity);
      }
    }
  }
  
  video.updatePixels();
  image(video, 0, 0, width, height);
}

// Toggle glitch effect when mouse is pressed
void mousePressed() {
  glitch = !glitch;
}

// Read values from Arduino
void serialEvent(Serial port) {
  String data = port.readStringUntil('\n');
  if (data != null) {
    String[] values = split(trim(data), ',');
    
    if (values.length == 2) {
      int pot1Value = int(values[0]);
      int pot2Value = int(values[1]);
      
      // Map potentiometer values to control glitch properties
      glitchIntensity = int(map(pot1Value, 0, 1023, 0, 255));
      glitchFrequency = map(pot2Value, 0, 1023, 0, 0.1);  // Adjust this for sensitivity
    }
  }
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/Glitch.png" width="1024" height="550" />

### Ejercicio n° 17 "Sensor de humedad"

#### codigo arduino
```;

void setup()
{
  Serial.begin(9600);// abre el puerto serial y Establece la velocidad en baudios a 9600 bps
}
void loop()
{
  int sensorValue;
  sensorValue = analogRead(0);   //conectar el sensor de humedad al pin analogo 0
  Serial.println(sensorValue); //imprime el valor a serial.
  delay(200);
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/sensor%20humedad.png" />

### Ejercicio n° 18 "Cuerpo, vídeo, sensor sharp"

#### codigo arduino
```;
// --- Sensor Sharp conectado al pin A0 ---
int sensorPin = A0;
int valor;

void setup() {
  Serial.begin(9600);
}

void loop() {
  valor = analogRead(sensorPin);
  Serial.println(valor);
  delay(50); // envío cada 50 ms
}
```

#### codigo processing
```;
// --- Librerías necesarias ---
import processing.serial.*;
import processing.video.*;

// --- Variables de cámara y serial ---
Capture cam;
Serial myPort;

// --- Variables del sensor ---
float sensorValue = 0;
float suavizado = 0;

// --- Parámetros para detección de silueta ---
float umbral = 100; // controla el contraste para definir la silueta

void setup() {
  size(1280, 720);
  background(0);
  
  // --- Inicializar cámara ---
  String[] cameras = Capture.list();
  if (cameras.length == 0) {
    println("No se encontró cámara.");
    exit();
  } else {
    println("Cámara encontrada: " + cameras[0]);
    cam = new Capture(this, cameras[0]);
    cam.start();
  }
  
  // --- Inicializar puerto serie (Arduino) ---
  // Puedes ver la lista de puertos con println(Serial.list());
  String portName = Serial.list()[0]; 
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  //myPort = new Serial(this, portName, 9600);
}

void draw() {
  background(0);
  
  // --- Leer datos del sensor ---
  while (myPort.available() > 0) {
    String inString = trim(myPort.readStringUntil('\n'));
    if (inString != null) {
      sensorValue = float(inString);
      suavizado = lerp(suavizado, sensorValue, 0.1);
    }
  }
  
  // --- Mapear los valores del sensor ---
  float escala = map(suavizado, 0, 1023, 1.5, 0.5); // tamaño de la silueta
  float alpha = map(suavizado, 0, 1023, 255, 80);   // opacidad según distancia
  
  // --- Captura de video ---
  if (cam.available()) {
    cam.read();
  }

  // --- Dibujar silueta desde la cámara ---
  cam.loadPixels();
  loadPixels();
  
  for (int y = 0; y < cam.height; y++) {
    for (int x = 0; x < cam.width; x++) {
      int loc = x + y * cam.width;
      color c = cam.pixels[loc];
      float brillo = brightness(c);
      
      // Si el brillo es menor que el umbral, dibujamos píxel blanco (silueta)
      if (brillo < umbral) {
        int px = int(x * escala);
        int py = int(y * escala);
        if (px < width && py < height) {
          stroke(255, alpha);
          point(px, py);
        }
      }
    }
  }
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/sensor%20y%20glich.png" />

### Ejercicio n° 19 "Promedio de imágenes"

#### codigo arduino
```;
void setup() {
  Serial.begin(9600);
}

void loop() {
  int potValue = analogRead(A0);
  Serial.println(potValue);
  delay(20);
}
```

#### codigo processing
```;
import processing.serial.*;

Serial myPort;
PImage[] imgs;
int numImages = 8;
PImage avgImg;
float mixAmount = 0;

void setup() {
  size(1920, 1080);
  //println(Serial.list());
  
  //Cambia el índice según tu puerto (0, 1, 2, etc.)
  myPort = new Serial(this, Serial.list()[0], 9600);
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort.bufferUntil('\n');

  // Cargar imágenes
  imgs = new PImage[numImages];
  imgs[0] = loadImage("1.png");
  imgs[1] = loadImage("2.png");
  imgs[2] = loadImage("3.png");
  imgs[3] = loadImage("4.png");
  imgs[4] = loadImage("5.png");
  imgs[5] = loadImage("6.png");
  imgs[6] = loadImage("7.png");
  imgs[7] = loadImage("8.png");

  avgImg = createImage(imgs[0].width, imgs[0].height, RGB);
}

void draw() {
  // Dibujar la imagen promedio según el valor del potenciómetro
  background(0);
  calcAverage(mixAmount);
  image(avgImg, 0, 0, width, height);
  
  fill(255);
  textSize(20);
  text("Mezcla: " + nf(mixAmount, 1, 2), 20, height - 20);
}

void serialEvent(Serial p) {
  String val = p.readStringUntil('\n');
  if (val != null) {
    val = trim(val);
    float sensor = float(val);
    mixAmount = map(sensor, 0, 1023, 0, 1); // 0 a 1
  }
}

void calcAverage(float t) {
  avgImg.loadPixels();

  for (int i = 0; i < avgImg.pixels.length; i++) {
    color c1 = imgs[0].pixels[i];
    color c2 = imgs[1].pixels[i];
    color c3 = imgs[2].pixels[i];
    color c4 = imgs[3].pixels[i];
    color c5 = imgs[4].pixels[i];
    color c6 = imgs[5].pixels[i];
    color c7 = imgs[6].pixels[i];
    color c8 = imgs[7].pixels[i];
   

    // Promedio ponderado según el potenciómetro
    float r = red(c1)*(1-t) + red(c2)*t*0.5 + red(c3)*t*0.5 + red(c4)*(1-t) + red(c5)*t*0.5 + red(c6)*t*0.5 + red(c7)*(1-t) + red(c8)*t*0.5;
    float g = green(c1)*(1-t) + green(c2)*t*0.5 + green(c3)*t*0.5 + green(c4)*(1-t) + green(c5)*t*0.5 + green(c6)*t*0.5 + green(c7)*(1-t) + green(c8)*t*0.5;
    float b = blue(c1)*(1-t) + blue(c2)*t*0.5 + blue(c3)*t*0.5 + blue(c4)*(1-t) + blue(c5)*t*0.5 + blue(c6)*t*0.5 + blue(c7)*(1-t) + blue(c8)*t*0.5;

    avgImg.pixels[i] = color(r, g, b);
  }
  avgImg.updatePixels();
}
```
<img
src="https://raw.githubusercontent.com/zzof04/INTERFAZ-II/refs/heads/main/img/sensor%20de%20imagenes.png" />


### Ejercicio n° 20 proyecto "espacio entre texturas"

#### Alumnas: Jacqueline Peralta, Sofia Salazar y Javiera León
```;
El proyecto "Espacio entre Texturas" nace desde nuestros intereses en común; la botánica y la astronomía como dos opuestos
que se pueden relacionar y a su vez el uso del cuerpo humano como una herramienta que "controla"
a través del sensor sharp estas dos facetas para crear una conexión entre lo micro y lo macro, lo natural y el universo.

Nuestro objetivo es crear un juego de texturas relacionados a estos dos campos:
Desde una mirada tanto de lo micro, donde se utilizan gofrados e impresiones que simulan raíces y lo relacionado a la tierra.
Como una mirada desde lo macro, utilizando renderizados de nebulosas y lo relacionado al universo. 
```


#### codigo arduino
```;
void setup() {
  Serial.begin(9600);  // Inicializamos la comunicación serial
}

void loop() {
  int sensorValue = analogRead(A0);  // Leemos el valor del sensor Sharp (valor analógico entre 0 y 1023)
  Serial.println(sensorValue);  // Enviamos el valor leído al puerto serial
  delay(50);  // Espera de 20 ms
}
```

#### codigo processing
```;
// --- Librerías necesarias ---
import processing.serial.*;

Serial myPort;
float sensorValue = 0;

PImage[] imgs;
PImage avgImg;

void setup() {
size(1920, 1080);

imgs = new PImage[30];
for (int i = 0; i < imgs.length; i++) {
String filename = "imagenes/" + (i + 1) + ".jpg";
imgs[i] = loadImage(filename);
if (imgs[i] == null) {
println("No se pudo cargar: " + filename);
} else {
imgs[i].resize(width, height);
println("Cargada: " + filename);
}
}

avgImg = createImage(width, height, RGB);

printArray(Serial.list());
myPort = new Serial(this, Serial.list()[0], 9600);
}

void draw() {
background(0);

readSerial();

float mixValue = map(sensorValue, 0, 1023, 0, imgs.length - 1);

blendImagesWithTransparency(mixValue);

image(avgImg, 0, 0);

fill(255);
textSize(20);
text("Valor sensor: " + nf(sensorValue, 1, 0), 10, height - 40);
text("Imagen mezclada: " + nf(mixValue, 1, 2), 10, height - 15);
}

// --- NUEVA FUNCIÓN: mezcla con transparencia visible ---
void blendImagesWithTransparency(float mix) {
mix = constrain(mix, 0, imgs.length - 1);

int i1 = floor(mix);
int i2 = min(i1 + 1, imgs.length - 1);
float t = mix - i1;

// Crea un gráfico temporal
PGraphics pg = createGraphics(width, height);
pg.beginDraw();

// Dibuja la primera imagen con algo de transparencia
pg.tint(255, 255 * (1.0 - t) * 0.8); // opacidad 80% ajustable
pg.image(imgs[i1], 0, 0);

// Superpone la segunda imagen con transparencia proporcional a 't'
pg.tint(255, 255 * t * 0.8);
pg.image(imgs[i2], 0, 0);

pg.endDraw();

avgImg = pg.get(); // guarda el resultado en avgImg
}

void readSerial() {
while (myPort.available() > 0) {
String val = myPort.readStringUntil('\n');
if (val != null) {
val = trim(val);
if (val.length() > 0) {
sensorValue = float(val);
}
}
}
}


```
