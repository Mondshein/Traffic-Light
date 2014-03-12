#define DATA 9
#define LATCH 8
#define CLOCK 10
#define DATA2 6
#define LATCH2 4
#define CLOCK2 5
// Lights {GREEN, YELLOW, RED, PEDGREEN, PEDRED}

int light [2][5] = {{2,3,4,6,7},{8,9,10,12,13}};
// Buttons {light[0],light[1]}
int btn [] = {5,11};
// Timers
int tgreen = 30000; // 30s
int tyellow = 3000; // 3s
int tred = 3000; // 3s
int tpedwarn = 5000; // 5s (must be less than tgreen)
int tpedwarnint = 500; // 0.5s (must be less than tpedwarn)

// Other Vals. Don't Change

int btnval = 0;
boolean pedwait [] = {false,false};
boolean pedactive [] = {false,false};
int direct = 0;
int stp = 1;
boolean stpset = false;
unsigned long now = 0;
unsigned long changeat = -1;
unsigned long changeatped = -1;
boolean pedredon = true;

// SETUP

void setup() {

  // Assign all Pins
  for (int x = 0; x < 2; x++){
    for (int y = 0; y < 5; y++){
      pinMode(light[x][y], OUTPUT);
    }
    // Start everything stopped (red)
    digitalWrite(light[x][2], HIGH);
    digitalWrite(light[x][4], HIGH);
  }

 // Assign buttons
  for (int x = 0; x < 2; x++){
    pinMode(btn[x], INPUT);
}
  pinMode(LATCH,OUTPUT);
  pinMode(CLOCK,OUTPUT);
  pinMode(DATA, OUTPUT);
}

void updateShiftRegister(number)

{
digitalWrite(latchPin, LOW);
shiftOut(dataPin, clockPin, LSBFIRST, number);
digitalWrite(latchPin, HIGH);
}

void updateShiftRegister1(number2)
{
digitalWrite(latchPin, LOW);
shiftOut(dataPin, clockPin, LSBFIRST, number);
digitalWrite(latchPin, HIGH);
}
void updateShiftRegister2(number)

{
digitalWrite(latchPin, LOW);
shiftOut(dataPin, clockPin, LSBFIRST, number);
digitalWrite(latchPin, HIGH);
}


void loop()
{
   // Update Time
  now = millis();
 // Check if button pressed
  for (int x = 0; x < 2; x ++){
    btnval = digitalRead(btn[x]);
    if (btnval == HIGH){
      pedwait[x] = true; // We have someone waiting to cross      
      updateShiftRegister(00100000);
      updateShiftRegister1(00000000);
     
    }
  }
 for(int i = 0; i < 15; i++){
  
   if(i < 5){
      updateShiftRegister(00100000);
      updateShiftRegister1(00000000);
    
   }
   if(i > 5 && i > 10){
      updateShiftRegister(00001000);
      updateShiftRegister1(1000000);
    
   }
  if(i > 10 ){
      updateShiftRegister(00001000);
      updateShiftRegister1(00100000);
      if(i == 11){
      updateShiftRegister(100
      
      }
  
   }
  
   }
 
}
