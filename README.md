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
  pinMode(LATCH2,OUTPUT);
  pinMode(CLOCK2,OUTPUT);
  pinMode(DATA2, OUTPUT);
}

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
 
  //start
  int part1 = 100010000;
  int part2 = 101000000;
  //second part
  int part3 = 101101001;
  int part4 = 101000000;
  //third part
  int part5 = 111100100;
  int part6 = 101000000;
  //fourth part
   int part7 = 111010100;
   int part8 = 101000000;
   //fifth part
   int part9 = 111101100;
   int part10 = 101000000;
     //sixth part
   int part11 = 111100100;
   int part12 = 101000000;
for(int i = 0; i < 15; i++){
  
 //  if(i < 5){
  //   updateShiftRegister(part1);
   //   updateShiftRegister2(part2);
      
    
  //}
  //if(i > 5 && i > 10){
  //  updateShiftRegister(part3);
  // updateShiftRegister2(part4);
    
 //}
 // if(i > 10 ){
  //   updateShiftRegister(part5);
  //  updateShiftRegister2(part6);
 // }
     //if(i == 11){
   //updateShiftRegister(part5);
  // updateShiftRegister2(part1);
   //   }
   //if(i == 11){
  // updateShiftRegister(part5);
  // updateShiftRegister2(part5);
   //   }
     //if(i == 11){
    //updateShiftRegister(part7);
    //updateShiftRegister2(part8);
   //   }
   //if(i == 11){
   //updateShiftRegister(part9);
   // updateShiftRegister2(part10);
   //   }
    //if(i == 11){
    // updateShiftRegister(part11);
    //updateShiftRegister2(part12);
   //   }
   //if(i == 11){
     updateShiftRegister(part11);
    updateShiftRegister2(part7);
   //   }
   
   //}
  
 // }
  }
  }
 

