#define DATA 9
#define LATCH 8
#define CLOCK 10
#define DATA2 6
#define LATCH2 4
#define CLOCK2 5

// SETUP

void setup() {


  pinMode(LATCH,OUTPUT);
  pinMode(CLOCK,OUTPUT);
  pinMode(DATA, OUTPUT);
}

void updateShiftRegister(int number)
{
digitalWrite(LATCH, LOW);
shiftOut(DATA,CLOCK, LSBFIRST, number);
digitalWrite(LATCH, HIGH);
}

void updateShiftRegister2(int number)
{
digitalWrite(LATCH, LOW);
shiftOut(DATA,CLOCK, LSBFIRST, number);
digitalWrite(LATCH, HIGH);
}



void loop()
{

 // Check if button pressed
  //for (int x = 0; x < 2; x ++){
    //btnval = digitalRead(btn[x]);
   // if (btnval == HIGH){
    //  pedwait[x] = true; // We have someone waiting to cross      
    //  updateShiftRegister(00100000);
    //  updateShiftRegister1(00000000);
     
   // }
 // }
  
 for(int i = 0; i < 15; i++){
  
   if(i < 5){
      updateShiftRegister(00000000);
      updateShiftRegister2(11111111);
      
    
   }
  // if(i > 5 && i > 10){
  //    updateShiftRegister(00000000);
  //    updateShiftRegister2(0000000);
  //  
  // }
 // if(i > 10 ){
 //     updateShiftRegister(00000000);
 //     updateShiftRegister2(00000000);
 //    if(i == 11){
 //     updateShiftRegister(00000000);
      
   //   }
  
   //}
  
   }
 
}
