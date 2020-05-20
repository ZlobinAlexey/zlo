String inString;
String motor, shagov;
int shag;
int dirPin1 = 6;
int stepPin1 = 5;
int dirPin2 = 8;
int stepPin2 = 7;
int dirPin3 = 10;
int stepPin3 = 9;
int stepPin = 0;
int dirPin = 0;
void setup()
{
  pinMode(stepPin1, OUTPUT);
  pinMode(stepPin2, OUTPUT);
  pinMode(stepPin3, OUTPUT);
  pinMode(dirPin1, OUTPUT);
  pinMode(dirPin2, OUTPUT);
  pinMode(dirPin3, OUTPUT);
  Serial.begin(9600);
}
void loop()
{

  while (Serial.available()) {
    char inChar = Serial.read();
    inString += inChar; 
    if (inChar == '\n') {
     // Serial.print("String: ");
     // Serial.println(inString);

if(inString.indexOf('=') != -1){
motor = inString.substring(0, 1);
Serial.print("Мотор: "+motor);

if(motor == "1"){stepPin = 5; dirPin = 6;}
if(motor == "2"){stepPin = 7; dirPin = 8;}
if(motor == "3"){stepPin = 9; dirPin = 10;}

if(inString.indexOf('-') != -1)
{
Serial.print("Направление <"); digitalWrite(dirPin, HIGH); } else {Serial.print(" Направление >"); digitalWrite(dirPin, LOW);}
shagov = inString.substring(2);
shagov = shagov.substring(0);
if(shagov.indexOf('-') != -1){shagov = shagov.substring(1);}
Serial.println(" Шагов: "+shagov);
shag = shagov.toInt();

  for(int x = 0; x < shag; x++)
  {

//int DELAY_STEP = 100;
//int FADE_STEP = 200;
//if(x < shag - FADE_STEP){DELAY_STEP = DELAY_STEP + FADE_STEP;} else {DELAY_STEP = 100;}
    digitalWrite(stepPin, HIGH);
//delayMicroseconds(DELAY_STEP);
    delayMicroseconds(100);
    digitalWrite(stepPin, LOW);
    delayMicroseconds(100);
//delayMicroseconds(DELAY_STEP);
  }
}
      inString = ""; 



    }
  }
}
