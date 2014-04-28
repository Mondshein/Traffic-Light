
#include <IRremote.h>
int recieverpin = 0;
#define DATA 6
#define LATCH 8
#define CLOCK 10
#define DATA2 9
#define LATCH2 7
#define CLOCK2 5
#define red 13
#define blue 12

int count;

IRrecv irrecv(recieverpin);

decode_results results;

void setup(){
    irrecv.enableIRIn();
    pinMode(red,OUTPUT);
    pinMode(blue,OUTPUT);

 
    Serial.begin(9600);


}
int p = 0;
int a = pow(2,0);
int b = pow(2,1);
int c = pow(2,2);
int d = pow(2,3);
int e = pow(2,4);
int f = pow(2,5);
int g = pow(2,6);
int h = pow(2,7);
int j = pow(2,8);

void updateShiftRegister(int number)
{
digitalWrite(LATCH, LOW);
shiftOut(DATA,CLOCK, LSBFIRST, number);
digitalWrite(LATCH, HIGH);
}
void updateShiftRegister2(int number)
{
digitalWrite(LATCH2, LOW);
shiftOut(DATA2,CLOCK2, LSBFIRST, number);
digitalWrite(LATCH2, HIGH);
} 

void loop(){
  count = 1;
  updateShiftRegister(00000000);
  updateShiftRegister2(00000000);
  digitalWrite(red,LOW);
  digitalWrite(blue,HIGH); 
  delay(5000);

  /*
  for(int i = 0; i < 10; i++){
  if(irrecv.decode(&results)){ 
    switch(results.value){
      /////////////////////////////////1 BUTTON//////////////
      case 0x010:
      if(count%2 == 1){
      p = p + a;
      updateShiftRegister(p);
      }
    if(count%2 == 0){
      p = p + a;
   updateShiftRegister2(p);
    }
count++;
      break;
      
     
    ////////////////////2 BUTTON/////////////////////
      case 0x810:
          if(count%2 == 1){
            p = p + b;
    updateShiftRegister(p);
          }
    if(count%2 == 0){
      p = p + b;
     updateShiftRegister2(p);
    }
count++;
      break;

    ///////////////////////////////////////3 BUTTON/////////////////////
      case 0x410:
          if(count%2 == 1){
            p = p + c;
     updateShiftRegister(p); 
     }
    if(count%2 == 0){
       p = p + c;
    updateShiftRegister2(p);
    }
count++;
     break; 

    ///////////////////////////////////////4 BUTTON/////////////////////
      case 0xC10:
          if(count%2 == 1){
             p = p + d;
     updateShiftRegister(d);
          }
    if(count%2 == 0){
       p = p + d;
     updateShiftRegister2(d);
    }
count++;
     break;
     ///////////////////////////////////////5 BUTTON/////////////////////
      case 0x210:
          if(count%2 == 1){
             p = p + e;
     digitalWrite(red,HIGH);
          }
    if(count%2 == 0){
       p = p + e;
     digitalWrite(blue,HIGH);
    }
count++;
    
     break;
     ///////////////////////////////////////6 BUTTON/////////////////////
      case 0xA10:
          if(count%2 == 1){
             p = p + f + e;
    updateShiftRegister(p);
          }
    if(count%2 == 0){
       p = p + f;
     updateShiftRegister2(p);
    }
count++;
     break;
    ///////////////////////////////////////7 BUTTON/////////////////////
      case 0x610:
          if(count%2 == 1){
             p = p + g;
     updateShiftRegister(p);
          }
    if(count%2 == 0){
       p = p + g;
     updateShiftRegister2(p);
    }
count++;
     break;
     ///////////////////////////////////////8 BUTTON/////////////////////
      case 0xE10:
          if(count%2 == 1){
             p = p + h;
   updateShiftRegister(p);
          }
    if(count%2 == 0){
       p = p + h;
    updateShiftRegister2(p);
    }
count++;
     break;
     ///////////////////////////////////////9 BUTTON/////////////////////
      case 0x110:      
          if(count%2 == 1){
             p = p + j;
     updateShiftRegister(p);
          }
    if(count%2 == 0){
       p = p + j;
     updateShiftRegister2(p);
    }
count++;
     break;
    }

  }
  }
  */

}

