# Communication System Project 
**Table of Contents:** 
1. [Planning](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-a-planning)
1. [Design](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-b-design)
1. [Development](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-c-development)
1. [Functionality](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-d-functionality) 
1. [Evaluation](https://github.com/isabelandreatta1/Unit2/blob/main/Communication%20System.md#criteria-e-evaluation) 

## Criteria A: Planning 
### Identified Problem 
The client has asked to create a communication system which will send messages from the moon to Earth and vice versa. The station on Earth is able to read Morse code and the station on the moon is able to read in binary. We have to create the communication system for the Earth, which is able to **input English**, and **output in Binary**, and is also able to **translate morse code to English**. The user will have to manually input in English and in morse code, but the sending of the messsage and the translation should be automated. The client has also specificed some material limitations: only using two buttons, an LCD screen for the display, and an arduino. 

### Proposed Solution 
Our proposed solution is to create a circuit using an Arduinom with C++. We will also use a large lightbulb to indicate the binary code, and the LCD screen to display the English and morse code. The way the user will input English is by having a screen with the alphabet, and starting from the middle and moving towards the edge of the screen, will blink two letters at the same time. Once the letter desired is blinking, the user is able to press either the left button or right button to indicate which letter to print. The first screen would display the letters A-P, the second screen (accessible via specific-button-pattern) will display the rest of the alphabet, and puncutation. And finally, the last screen would display the numbers 0-9 and some immediate commands such as delete, error, SOS, and acknowledge. Depending on different button-press combinations, the arduino will interpret different commands. For example, by pressing the right button-combination, the device will change from English mode to morse mode, where the user can input morse code and translate it to English. 

### Justification 

**Arduino** 

We are using an arduino set because, despite it being small and portable, has a lot of potential power -- it is a very popular hard-ware used when creating a new device because of it's accessibility and also flexibility. It's accessibility is due to its simple circuit system, needing only to be plugged in with a computer via USB, and because it uses C++. We have had previous experience with Python so it might have seemed simpler to create a program with a language we are already familar with, however, C++ is mostly used for developing hardware while Python has a more general use, so C++ seemed like a better option. In addition, although C++ is a more difficult langauge than Python, it is still understandable to a beginner student and it gives you more control (for instance, memory management). The fact that it is a more low-level language (hence why it gives more control but also is more difficult), means that it works faster than Python. Low-level language means that it is a programming language with syntax more understandable to a computer, while a high-level language like Python, means that the syntax is more accessible to people, but is slower because the computer needs to do more tasks to understand. Also, another pro for C++ is that it is a very common langauge, with many platforms and applications written in C++ and also with many learning-resources available online. This means that while we don't have any previous experience with C++, it makes it easy for us to learn, and also it makes our project accessible to larger community.

**Our Design** 

After our first consultation with our client, we were informed that he prioritised minimising number of button presses over amount of time spent. This heavily shaped our deisgn, coming up with the final decision of displaying all the letters and automating the navigation on the screen using the blinking-letters, instead of making the user manually pressing the buttons. By making the letters blink and automating the nagivation process, it would radically cut-down the number of button presses, with a majority of each word taking either the same number of button presses as number of letters, with perhaps a few additional presses due to needing to access a different screen.  

### Feasibility Report 

**Technical Feasibility: Is there existing technology sufficient to implement the proposed system?**

There is plenty of existing technology that can send messages in English to binary, however, none which fit our client's specific limitations (two buttons),, in addition to merging the english-to-binary feature and morse-to-english feature. 

**Economic Feasibility: Is the proposed system cost-effective?** 

Our proposed solution only uses a basic arduino building set, and a laptop to power it. This makes it very cost-effective and accessible. 

**Legal Feasibility: Any conflicts between proposed system and regulations/laws?**  

No conflicts because we are not looking into getting our device copyrighted or patented, it's purpose is to remain small-scale. 

**Operational Feasibility: Are the existing organisational practices and procedures sufficient to support the operation of the new proposed system?**  

Yes, they are sufficient since the project is only aimed for short-term use, as well as its basic functions will be accessible to anyone who has limited knowledge on the Arduino. We are keeping track and documenting our process so if there is any need to revisit the project for the future, it will be easier to understand. 

**Schedule Feasibility: How long will we wait?**  

The project due date was by end of Dececmber 2020, which means that the development of this project will only span a couple of months.  

### Success Criteria 
Based on a further conversation we had with the client, these were the success criteria agreed upon: 

1. Must use one LCD, one arduino, two buttons, and one LED 
1. Must include a table which informs the operator with the instructions 
1. Must allow the user to enter English and output in  binary 
1. Must allow the user to enter either morse code and output to English
1. Must be able to carry out the commands delete, error, acknowledge, send and SOS 
1. Must be able to send at least 10 words per minute  

**Sketches of our first Design Drafts** 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/Communication%20System%20Draft.jpg" width="401" height="537"/>

*Figure 1: Communication System Design Draft* 

### Tinkercad Prototype 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/Tinkercad.png" width="712" height="357"/>

*Figure 2: Our Tinkercad prototype including both hardware and code* 

We used Tinkercad to create our prototype. Tinkercad is an online 3D modelling program, which allows you to create digital prototypes of circuits. Due to its easy usability and clear design, it was a good tool to first test our code and also understand the hardware circuit. Once we arrived to a functioning online model, we then copied and uploaded the code on the arduino, and used the tinkercad circuit as a reference as we built the physical one. After we created our first prototype, we then worked alternating between Tinkercad and the physical device, always first checking with Tinkercad when adding a new feature, and then copying it down to our device. 

## Criteria B: Design 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/System%20Diagram.jpg" width="744.8" height="295.2"/>

*Figure 3: System Diagram* 

## Criteria C: Development 
<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/English%20to%20Binary%20Flowchart.png" width="430" height="940"/>

*Figure 4: Flow Diagram of the English to Binary* 

### Completed Code 

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

This is a video

## Criteria E: Evaluation 

### Alpha Testing 

| Test No. | Procedure | Inputs | Expected Output | Success Criteria                                                                |Criteria Met| 
|----------|-----------|--------|-----------------|---------------------------------------------------------------------------------|------------|
| 1        |           |        |                 | Must allow the user to enter English and output in binary                       |.  |
| 2        |           |        |                 | Must allow the user to enter either morse code and output to English            |.  |
| 3        |           |        |                 | Must be able to carry out the commands delete, error, acknowledge, send and SOS |.  |
| 4        |           |        |                 | Must be able to send at least 10 words per minute                               |.  |

### Limitations and Further Improvements 

**Limitations** 

**Further Improvements** 
