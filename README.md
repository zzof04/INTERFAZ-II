# INTERFAZ-II
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

## Processing Botonera
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
  
  // Inicializa el puerto serial (ajusta el índice si es necesario)
  String portName = Serial.list()[0];
  myPort = new Serial(this, portName, 9600);
}

void draw() {
  readSerial();  // Lee el valor del potenciómetro

  // Mapea el potenciómetro a parámetros que afectan el color y velocidad
  zincrement = map(sensorVal, 0, 1043, 0.005, 0.05);  // Velocidad del ruido
  float colorShift = map(sensorVal, 0, 1050, 0, 2530); // Desfase de color
  
  loadPixels();

  float xoff = 0.0;

  for (int x = 0; x < width; x++) {
    xoff += increment;
    float yoff = 0.0;

    for (int y = 0; y < height; y++) {
      yoff += increment;

      // Ruido 3D
      float n = noise(xoff, yoff, zoff);

      // Convertir ruido a colores tipo nebulosa
      // Cambia de tonalidad según el potenciómetro (colorShift)
      float r = map(sin(TWO_PI * n + radians(colorShift)), -1, 1, 40, 250);
      float g = map(cos(TWO_PI * n + radians(colorShift * 1.2)), -1, 1, 50, 255);
      float b = map(sin(TWO_PI * n + radians(colorShift * 0.5)), -1, 1, 20, 255);

      pixels[x + y * width] = color(r, g, b);
    }
  }

  updatePixels();

  zoff += zincrement;
}

void readSerial() {
  while (myPort.available() > 0) {
    val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.length() > 0) {
        try {
          sensorVal = int(val);
        } catch (Exception e) {
          println("Error al convertir:", val);
        }
      }
    }
  }
```
