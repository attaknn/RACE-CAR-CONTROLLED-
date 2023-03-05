# RACE-CAR-CONTROLLED-
BY A ARDUINO AND L241D
THE CODE
void setup() {
  // put your setup code here, to run once:
pinMode(6,OUTPUT);
pinMode(9,OUTPUT);
pinMode(10,OUTPUT);
pinMode(11,OUTPUT);
Serial.begin(9600);
}
void FORWARD(){
   digitalWrite(6,HIGH);
  digitalWrite(9,LOW);
  digitalWrite(10,HIGH);
  digitalWrite(11,LOW); 
}
void BACKWARD(){
  digitalWrite(6,LOW);
  digitalWrite(9,HIGH);
  digitalWrite(10,LOW);
  digitalWrite(11,HIGH);
}
void LEFT(){
  digitalWrite(6,LOW);
  digitalWrite(9,HIGH);
  digitalWrite(10,HIGH);
  digitalWrite(11,LOW);
}
void RIGHT(){
  digitalWrite(6,HIGH);
  digitalWrite(9,LOW);
  digitalWrite(10,LOW);
  digitalWrite(11,HIGH);
}
void STOP(){
   digitalWrite(6,LOW);
  digitalWrite(9,LOW);
  digitalWrite(10,LOW);
  digitalWrite(11,LOW); 
}
void loop() {
  // put your main code here, to run repeatedly:
    if(Serial.available()>0)
   { 
       char data= Serial.read();
       Serial.println(data) ;
       if (data=='Q'){
        BACKWARD();
        }
        else if(data=='R'){
          FORWARD();
        }
        else if(data=='P'){
          RIGHT();
        }
        else if(data=='O'){
          LEFT();
        }
        else if(data=='S'){
          STOP();
        }
   }
  }
