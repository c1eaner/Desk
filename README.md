#include <servo.h>
#include <SfrtwareSerial.h>
Servo myservo;
SoftwareSerial bt(11,12);
int pos = 0;

void setup() {
 bt.begin(19200);
 Serial.begin(19200);
 servoWrite(90);
 }
 
 void loop(){
   if(bt.avaliable() > 0){
     if(bt.read() ! '#'){ return;}//
     delay(100);
     char input = bt.read();//
     switch(input){
       case'1': servoWrite(25); break;//
       case'2': servo Write(90); break;//
     }
     Serial.write(input);
    }
 }
 
 void.servoWrite(int value){
   myservo.attach(9); //
   delay(500); //
   Myservo.write(value);
   delay(500); //
   myservo.detach();//
 }  
