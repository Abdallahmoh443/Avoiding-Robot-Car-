void compression(int r , int l );
void off(void);
void reverse(void);
void tleft90(void);
void tright90(void);
void forward(void);
void tleft180(void);
int fdistance(void);
long duration;
#include <Servo.h>
#define in1 2
#define in2 3
#define in3 4
#define in4 7
#define en1 5
#define en2 6
#define switch A5   // هنا اتعرف انالوج علشان نستخدم انبوت بول اب علشان مش نستخدم مقاومات
int distance ;
int distance1 ;
int rightdistance ;
int leftdistance ;
bool state;    // حاله المفتاح 
Servo myservo;   // تعريف من المكتبه علشان نتحكم في السيرفو 
int pos = 85;     // موضع بدايه السيرفو
void setup() {
  pinMode(switch,INPUT_PULLUP);
  Serial.begin(9600);
  pinMode(in1,OUTPUT);
  pinMode(in2,OUTPUT);
  pinMode(in3,OUTPUT);
  pinMode(in4,OUTPUT);  
  pinMode(en1,OUTPUT); 
  pinMode(en2,OUTPUT);
  myservo.attach(9);    // تعريف من المكتبه جاهز
  myservo.write(85);
  pinMode(11,OUTPUT);
  pinMode(12,INPUT);
}

void loop() {
  state = digitalRead(A5);
 if(state == HIGH){
    distance1 = fdistance();
    if(distance1 > 30){
      forward();
    }else{ 
      if(distance1<=10 && distance1>=2){
      reverse();
    }
    off();
    myservo.write(25);
    delay(300);
    rightdistance = fdistance();
    myservo.write(165);
    delay(300);
    leftdistance =fdistance();
    myservo.write(85);
    compression(rightdistance,leftdistance);
    off();
    delay(150);
 }
}else{off();}
}
void compression(int r , int l ){
  if(r>25 || l>25){
    if(r >= l){
      tright90();
    }else if (l>r){
      tleft90();
    }
  }else if(r<25 && l<25){
    tleft180();
  }
}
void forward(void){
  analogWrite(en1,110);
  analogWrite(en2,110);
  digitalWrite(in1,HIGH);
  digitalWrite(in2,LOW);
  digitalWrite(in3,HIGH);
  digitalWrite(in4,LOW);
}
void tright90(void){
  analogWrite(en1,100);
  analogWrite(en2,105);
  digitalWrite(in1,HIGH);
  digitalWrite(in2,LOW);
  digitalWrite(in3,LOW);
  digitalWrite(in4,HIGH);
  delay(750);
}
void tleft90(void){
  analogWrite(en1,105);
  analogWrite(en2,100);
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  digitalWrite(in3,HIGH);
  digitalWrite(in4,LOW);
  delay(650);
}
void reverse(void){
  analogWrite(en1,110);
  analogWrite(en2,110);
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  digitalWrite(in3,LOW);
  digitalWrite(in4,HIGH);
  delay(450);
}
void off(void){
  digitalWrite(in1,LOW);
  digitalWrite(in2,LOW);
  digitalWrite(in3,LOW);
  digitalWrite(in4,LOW);
}
void tleft180(void){
  analogWrite(en1,100);
  analogWrite(en2,100);
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  digitalWrite(in3,HIGH);
  digitalWrite(in4,LOW);
  delay(1500);
}
int fdistance(void){
  distance = 0;
  digitalWrite(11,LOW);
  delayMicroseconds(2);
  digitalWrite(11,HIGH);
  delayMicroseconds(10);
  digitalWrite(11,LOW);
  duration = pulseIn(12,HIGH);
  distance = duration * (0.034/2) ;
  return distance ;
}
