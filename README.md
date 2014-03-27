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
  int part4 = 0;
  //third part
  int part5 = 111100100;
  int part6 = 111110100;
  //fourth part
   int part7 = 111101100;
   int part8 = 101000000;
   //fifth part
   int part9 = 100001000;
   
for(int i = 4; i < 6; i++){
  
  /* if(i == 0 ){
    updateShiftRegister(part1);
    updateShiftRegister2(part2);
    delay(1000);
    
  }
  if(i == 1){
  updateShiftRegister(part3);
  updateShiftRegister2(part2);
    delay(1000);
 }
  if(i == 2){
     updateShiftRegister(part5);
    updateShiftRegister2(part2);
    delay(1000);
 }
    if(i == 3){
   updateShiftRegister(part5);
   updateShiftRegister2(part1);
   delay(1000);
      }
      */
   if(i == 4){
   updateShiftRegister(part5);
   updateShiftRegister2(part9);
   delay(1000);
      }
     if(i == 5){
   updateShiftRegister(part5);
   updateShiftRegister2(part5);
   delay(1000);
   }
   /*
   if(i == 6){
   updateShiftRegister(part6);
   updateShiftRegister2(part5);
   delay(1000);
}
 if(i == 7){
   updateShiftRegister(part7);
   updateShiftRegister2(part5);
   delay(1000);
}
  if(i == 8){
   updateShiftRegister(part5);
   updateShiftRegister2(part6);
   delay(1000);
}
 if(i == 9){
   updateShiftRegister(part5);
   updateShiftRegister2(part6);
   delay(1000);
}
*/
}
}
  
  
*/  void setup() {Serial.begin(9600); }

void loop() 
{
  int num = analogRead(0);
  Serial.println(num);
  delay(500);
}
*/
 

