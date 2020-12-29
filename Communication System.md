# Communication System Project 
**Table of Contents:** 
1. [Planning](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-a-planning)
1. [Design](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-b-design)
1. [Development](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-c-development)
1. [Functionality](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-d-functionality) 
1. [Evaluation](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-e-evaluation) 

## Criteria A: Planning 
### Identified Problem 
The client has asked to create a communication system which will send messages from the moon to Earth and vice versa. The station on Earth is able to read Morse code and the station on the moon is able to read in binary. We have to create the communication system for the Earth, which is able to input English, and output in Binary, and is also able to translate morse code to English. The use will have to manually input in English and in morse code, but the sending of the messsage and the translation should be automated. The client has also specificed some material limitations: only using two buttons, an LCD screen for the display, and an arduino. 

### Proposed Solution 
Our proposed solution is to create a circuit using an Arduino. We will use a large lightbulb to indicate the binary code, and also 

**Why did we use an Arduino?**

We are using an arduino set because, despite it being small and portable, has a lot of potential power -- it is a very popular hard-ware used when creating a new device because of it's accessibility and also flexibility in projects. It's accessibility is due to its simple circuit system, needing only to be plugged in with a computer via USB, and because it uses C++. C++, while a more difficult langauge than Python or Java, is still understandable to a beginner student and it gives you more control (for instance, memory management). Also, C++ is a very common langauge, with many platforms and applications written in C++ and also with many learning-resources available online. 

**Why our specific design?** 


### Success Criteria 
Based on the conversation we  had with the client, these were the success criteria agreed upon: 

1. Must use one LCD, one arduino, two buttons, and one LED 
1. Must include a table which informs the operator with the instructions 
1. Must allow the user to enter Englishs and output in  binary 
1. Must allow the user to enter either morse code and output to English
1. Must be able to carry out the commands delete, error, acknowledge, send and SOS 
1. Must be able to send at least 10 words per minute  

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/Communication%20System%20Draft.jpg" width="401" height="537"/>

*Figure : Communication System Design Draft* 

### Tinkercad Prototype 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/Tinkercad.png" width="712" height="357"/>

*Figure : Our Tinkercad prototype including both hardware and code* 

## Criteria B: Design 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/System%20Diagram.jpg" width="744.8" height="295.2"/>

*Figure : System Diagram* 

## Criteria C: Development 
```py
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 7, 6, 5, 4);

//char letters_b[17]
String msg = "";
String to_send = "";
char letters[17] = "ABCDEFGHIJKLMNOP";
char letters2[17] = "QRSTUVWXYZ!.@$()";
int pos_l = 7;
int pos_r = 8;
int time = 0;
int pos = 0;
int d=0;
int it=0;
int last_bpl=0;
int last_bpr=0;
int led = 13; 

int inByte = 0; // sets up the variable that will store incoming data from serial (keyboard)
const int ledPin = 10; // sets pin 10 as the pin to which the LED light is attached
const int time_base = 100; // sets a dot to 100 milliseconds
const int dash = 3*time_base; // sets a dash to 300 milliseconds

void setup() {
  
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  
  // set up the buttons
  pinMode(3, INPUT);
  pinMode(2, INPUT);
  pinMode(13, OUTPUT); 
  
  //Interrupts
  attachInterrupt(digitalPinToInterrupt(3), L_Button, RISING);
  attachInterrupt(digitalPinToInterrupt(2), R_Button, RISING);
  
  // serial monitor
  Serial.begin(9600);
  
  // print initial letters
  lcd.setCursor(0, 0);
  for (int i=0; i<sizeof(letters)-1; i++) {
  	lcd.print(letters[i]);
  }
}

  
void blinkon(){
  	lcd.setCursor(pos_l - (d%8), 0);
  	lcd.print(" ");
  	lcd.setCursor(pos_r + (d%8), 0);
  	lcd.print(" ");
  	delay(200); 
}

void blinkoff(){
  lcd.setCursor(pos_l - (d%8), 0);
  lcd.print(letters[pos_l - (d%8)]);    
  lcd.setCursor(pos_r + (d%8), 0);
  lcd.print(letters[pos_r + (d%8)]);
  delay(200);
}

void loop() {
  if (it%6 == 0 && it>0) {
      d+=1;
  }

  blinkon();
  blinkoff(); 
  it+=1;

}
    
  void L_Button() {
    if (it-last_bpl<=1 && it>0) {
      Serial.print("double click ");
      dcl_L();
    }
      
    else {
      msg.concat(letters[pos_l-(d%8)]);
      lcd.setCursor(0, 1);
      lcd.print(msg); 
      last_bpl = it;
    }
  }
  
  void R_Button() {
    if (it-last_bpr<=1 && it>0) {
      Serial.print("double click");
      dcl_R();
    }
    
    else {
    	msg.concat(letters[pos_r+(d%8)]);
    	lcd.setCursor(0, 1);
    	lcd.print(msg);
    	last_bpr = it;
    }
  }

//Double-click left -> Delete letter
void dcl_L() {
  msg.remove(msg.length()-1);
  msg.remove(msg.length()-1);
  
  lcd.setCursor(msg.length()+1, 1);
  lcd.print(" ");
  
  lcd.setCursor(msg.length(), 1);
  lcd.print(" ");
  
  lcd.setCursor(0, 1);
  lcd.print(msg);
}

 
//Double-click right -> Send message
void dcl_R() {
  to_send = msg;
  for (int i =0; i< msg.length()-1; i++){
    char msgchar = msg.charAt(i);
    Serial.print(msgchar);
    String binary = String(msgchar-65,BIN);
    Serial.println(binary +" break ");
    Serial.println(binary.length());  
    for (int x=0; x<binary.length(); x++){
     
      if (binary[x] == '0'){
        Serial.println("Zero");
		digitalWrite(led,LOW); 
        delay(50000);  
      	digitalWrite(led,HIGH); 
  		delay(10000); 
  		digitalWrite(led,LOW); 
      	delay(1000); 
        }
      if (binary[x] =='1'){
      	Serial.println("One");
      	digitalWrite(led, HIGH);
 	 	delay(50000); 
  		digitalWrite(led,LOW);
        delay(10000); 
        digitalWrite(led,HIGH); 
  		delay(10000); 
  		digitalWrite(led,LOW); 
      	delay(10000);
       }
  	}
  }
  
  to_send.remove(to_send.length()-1);
  msg = "";
  
  for (int i=0; i<=to_send.length()+1; i++){
    lcd.print(" ");
    lcd.setCursor(0+i, 1);
  	lcd.print(" ");
  }
  
}
```

## Criteria D: Functionality 

## Criteria E: Evaluation 
