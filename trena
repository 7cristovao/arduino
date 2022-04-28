/Trena
//ligar VCC no 5V
//ligar GND no GND
//ligar TRIG no 8
//ligar ECHO no 9

//Ligar Led pino grande no 13 e pino pequeno no GND

// variáveis
int gatilho = 8; // pino TRIG do sensor ultrassônico
int echo = 9; // pino ECHO do sensor ultrassônico
float tempo; // para armazenar o tempo de ida e volta do sinal em microsegundos
float distancia_cm; // para armazenar a distância em centímetros
float distancia_in; // para armazenar a distância em polegadas

// setup (executado apenas uma vez)
void setup() {
// configura pino GATILHO como saída
pinMode(gatilho,OUTPUT);
// deixa pino em LOW
digitalWrite(gatilho,LOW);
delayMicroseconds(10);

// configura pino ECHO como entrada
pinMode(echo,INPUT);

Serial.begin(9600);
Serial.println("Lendo dados do sensor...");

}

// laço principal (executado indefinidamente)
void loop() {
// disparar pulso ultrassônico
digitalWrite(gatilho, HIGH);
delayMicroseconds(10);
digitalWrite(gatilho, LOW);

// medir tempo de ida e volta do pulso ultrassônico
tempo = pulseIn(echo, HIGH);

// calcular as distâncias em centímetros e polegadas
distancia_cm = tempo / 29.4 / 2;
distancia_in = tempo / 74.7 / 2;

Serial.println(distancia_cm);

if (distancia_cm < 3)
{
digitalWrite(13, HIGH); // set the LED on
}
else
{
digitalWrite(13, LOW); // set the LED off
}

// aguardar um pouquinho antes de começar tudo de novo
delayMicroseconds(200);
}
