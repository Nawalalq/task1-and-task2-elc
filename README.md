# task1-and-task2-elc

task1: servo motor ,stepper motor,brushless motor ,tack2:on -off system

# task1: servo motor ,stepper motor,brushless motor :

 1-servo motor:

Code1:

#include < Servo.h > 

Servo myservo ; 

int potpin - A0 ; 

int val ; 

void setup ( ) { 

myservo.attach ( 9 ) ;

} 

void loop ( ) { 

val = analogRead ( potpin ) ; 

val = map ( val , 0 , 1023 , 0 , 180 ) ; myservo.write ( val ) ; 

delay ( 15 ) ; 


2-stepper motor:

Code2:

#include < Servo.h > 

Servo myservo ; 

int potpin - A0 ; 

int val ; 

void setup ( ) { 

myservo.attach ( 9 ) ; 

} 

void loop ( ) { 

val = analogRead ( potpin ) ; 

val = map ( val , 0 , 1023 , 0 , 180 ) ; myservo.write ( val ) ; 

delay ( 15 ) ; 


# Task 2: ON-OFF :

Code:

#define LED_PIN 2

#define BUTTON_PIN 4

#define Relay_PIN 7


byte lastButtonState = LOW;

byte ledState = LOW;



void setup() {

  pinMode(LED_PIN, OUTPUT);
  
  pinMode(BUTTON_PIN, INPUT);
  
  pinMode(Relay_PIN, OUTPUT);
  
}

void loop() {

  byte buttonState = digitalRead(BUTTON_PIN);
  
  if (buttonState != lastButtonState) {
  
    lastButtonState = buttonState;
    
    if (buttonState == LOW) {
    
      ledState = (ledState == HIGH) ? LOW: HIGH;
      
      digitalWrite(LED_PIN, ledState);
      
      digitalWrite(Relay_PIN, ledState);
      
    }
    
  }
  
}
