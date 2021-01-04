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

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/English%20to%20Binary%20Flowchart.png" width="430" height="940"/>

*Figure 4: Flow Diagram of the English to Binary* 

## Criteria C: Development 

We spent most time working on the development since it is the bulk of the project and the most technically challenging section. We worked on the major functions incrementally, working first on the simpler jobs and then branching into the more difficult. Below is documentation of the process of our device's development.

### Input English and print a messsage 

**Displaing the letters** 

This was the first elementary step we had to take in order to start off our project. We had ideated our initial draft, knowing that the basic function of inputting English would be based on a blinking light and then choosing it based on pressing left or right. The LCD (Liquid Crystal Display), or our screen, can only display two rows of 16 characters, meaning that we had very limited space and could not fit all of our commands at once. We wanted to keep the bottom row for displaying the message, this way the user can see what they are typing. This meant we only had to use the top row for displaying characters. We created the display of characters, or key, by creating a char, or a data type which stores multiple characters. On our code, it would look like this: ```char letters[17] = "ABCDEFGHIJKLMNOP";``` Since C++ is a low-level language, we need to specify the type of variable and also the number of characters. We created a for loop inside our setup which printed every letter inside our 'letters' variable starting from the first row and first column of our display. So whenever you turned on the device, the first thing it would show you the first 16 letters of the alphabet. In order to make a second screen so we could fit the entire alphabet, in addition to a few commands and puncutation symbols, we created a new char: ```char letters2[17] = "QRSTUVWXYZ@!.SAE";```. In order to shift from one screen to another, we created the variable ```switchscreen``` and defined it as 0. Then, we used many if statements. If the switchscreen was set to 0, or the default value we gave it, then the first screen would be shown. After all the letters all blinked, the swtichscreen value would change to 1. If the switchscreen is 1, then the second screen it shown. After all those letters blinked, the switchscreen value changes back to 0, therefore creating a continious cycle.  

For displaying text, you can use some default methods such as: 
- ```lcd.setCursor(0, 0) ```: Starts the text on the first row and first column. The 0,0 in parenthesis marks the location of the character. 
- ```lcd.print()```: Prints the text inside the parenthesis 

Code for displaying the letters: 
```cpp 
char letters[17] = "ABCDEFGHIJKLMNOP";
char letters2[17] = "QRSTUVWXYZ@!.SAE";
int switchscreen = 0; 
void loop() {
  
  if (switchscreen == 0){
    
    lcd.setCursor(0, 0);
    for (int i=0; i<sizeof(letters)-1; i++) {
      lcd.print(letters[i]);
    }
    
    
    if (d%8==0 && d>0){
    	switchscreen = 1;
      	d+=1;
    }
    
    if (it%4 == 0 && it>0) {
        d+=1;
    }
    blinkon();
    blinkoff(); 
    it+=1;
    
  }
  
  else{
    lcd.setCursor(0, 0);
    for (int i=0; i<sizeof(letters2)-1; i++) {
      lcd.print(letters2[i]);
    }
    
    if (d%8==0 && d>0){
    	switchscreen = 0; 
      d+=1;
    }
    
    if (it%4 == 0 && it>0) {
        d+=1;
    }
    blinkon();
    blinkoff2(); 
    it+=1;
  }

``` 

**Blinking letters** 

The next step was to make the letters blink. We chose to make the first letter in the middle blink and then have to letters blink simultaneously, moving towards the edge of the screen. Below is a demonstration on how that would look: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Pictures/ezgif.com-gif-maker.gif" width="184" height="147" /> 

*Note: Example above only demonstrates with four letters, we would apply this concept with all 16 characters* 

In order to do that, we created two seperate functions, one for the blinking off the lights and one for blinking on the lights. This made it easier to follow within our void loop. Since we would have to make two letters blink simultaneously, we created two variables: ```pos_l``` and ```pos_r```. ``Pos_l``, short for position left, would make the left side of the letters blink, while ```pos_r``` would make the right side of the letters blink. Our letters start flashing from the middle of our screen, which means our initial positions are the characters on column 7 and 8. The blinking off function just replaced the character with an empty string, and had a delay of 200 milliseconds. Next, the blink on function would use the variable d (first defined as 0) and find the module of d and 8 and find the next position. It then print the letter again and has another delay of 200 milliseconds. If it were on the left, then it would have to subtract position, and if it were on the right, then it would have to add position. The last step is to bring both functions together in a void loop. If the mod of the iterations of both functions with 6 is 0, then d would increase by 1. The reason why we need to find the mod of iterations with 6 is because it will blink 6 times. 
### FINISH THIS SECTION 

Code for blinking letters: 

```cpp 

int pos_l = 7;
int pos_r = 8;
int d=0;
int it=0;

void blinkoff(){
  	lcd.setCursor(pos_l - (d%8), 0);
  	lcd.print(" ");
  	lcd.setCursor(pos_r + (d%8), 0);
  	lcd.print(" ");
  	delay(200); 
}

void blinkon(){
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

  blinkoff();
  blinkon(); 
  it+=1;
``` 

**Selecting Letters** 

Now that we have both a screen and a way to navigate through the letters, we need a way to select and print a message. This section has two main tasks: printing the message and deleting a letter. One click left selects the left blinking letter, one click right selects the right blinking letter, and a double click right will delete the letter. We will also be using double-left click, but we can ignore that for now since it is not relevant for this section. 

For sending the message, it checks if the button has been pressed twice. If it has been pressed only twice (checked if the variable for button press is larger than 1), then it will recall the double-click function. If not, then it will concatenate (or join) the blinking letter to the message. We first defined the messsage as an empty string, but once it is concatenated with a letter, then it will become a full message. 

If instead the right button has been pressed twice, then it will recall the delete function. The delete function, we use the ```delete()``` method to decrease the length of the message by one letter. Then, we reprint the messsage without the incorrect letter. 

For the commands, we had to be able to create a distinction between the letters "S","A","E" and the commands, "SOS","Acknowledge,"Error." We did this by creating an if statement: if on the second screen, the character "S" is selected, then, the messsage becomes "SOS." The same if statement was applied with the other commands. It was only neccessary to put this code in the right button function because all the commands were placed on the right hand side of the screen, meaning that you only used the right button to select them. 

Code for Selecting Letters: 
```cpp 

}
    
  void L_Button() {
    if (it-last_bpl<=1 && it>0) {
      Serial.print("double click ");
      dcl_L();
    }
      
    else {
      if (switchscreen == 0){
        msg.concat(letters[pos_l-(d%8)]);
        lcd.setCursor(0, 1);
        lcd.print(msg); 
        last_bpl = it;
      }
      else{
        msg.concat(letters2[pos_l-(d%8)]);
        lcd.setCursor(0, 1);
        lcd.print(msg); 
        last_bpl = it;
      }
    }
  }
  
  void R_Button() {
    if (it-last_bpr<=1 && it>0) {
      Serial.print("double click");
      dcl_R();
    }
    
    else {
      if (switchscreen ==0){
    	msg.concat(letters[pos_r+(d%8)]);
    	lcd.setCursor(0, 1);
    	lcd.print(msg);
    	last_bpr = it;
      }
          
      else{
        msg.concat(letters2[pos_r+(d%8)]);
    	lcd.setCursor(0, 1);
        if (msg == "S"){
          msg = "SOS";
            }
        if (msg == "A"){
          msg = "ACKNOWLEDGE";
            }
        if (msg == "E"){
          (msg = "ERROR");
            }
    	lcd.print(msg);
    	last_bpr = it;  
        }
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


```

### Input message and convert to Binary 

The next major function for our device was to convert our English message into binary using an LED. This meant that we had to attach an LED to our breadboard and connect it to our Arduino. The translation from English to binary would occur whenever the user sends a message, meaning that the reciever of the message gets the text in binary and then must translate it using their own device. To make things simpler, we created a function for whenever the right button is clicked twice, which performs the send command by translating the message into binary. 

Inside the function, the first thing is a for loop which converts the message into a character. 

``` for (int i =0; i< msg.length()-1; i++){char msgchar = msg.charAt(i)``` 

Then, once we converted each letter into a character, we used the BIN command, which specifies the format of the text. This then converts the character into binary automatically. The arduino functions using ASCII code (American Standard Code for Information Interchange), which interprets characters as letters. However, this means that the alphabet starts from the number 65 (since 0-65 are allotted for puncutation or other symbols). We thought starting from the number 65 was counter-intuitive for someone trying to decrypt the message, so we subtracted 65 from the ASCII Code number, making the alphabet start from the number 0. This meant that A would mean 0, B would mean 1, etc.. 

``` String binary = String(msgchar-65,BIN)``` 

Next, the device would have to display the binary number using an LED. The way we chose to display this is by representing 0s as LED off for 5 seconds, 1s as LED on for 5 seconds , and change of letter as LED on for 1 second. This way the reciever would not be confused if the LED is off or if it is representing a letter. Using another for loop, it would run through each 1 and 0 inside the binary representation, and then turn on according if it is a 1 or 0 using an if statement. 

```cpp 
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
```

Lastly, we had to make the screen blank and restart the message after it sends. We simply used the ```remove()``` method and made the variable message into an empty string. 

```
  to_send.remove(to_send.length()-1);
  msg = "";
  
  for (int i=0; i<=to_send.length()+1; i++){
    lcd.print(" ");
    lcd.setCursor(0+i, 1);
  	lcd.print(" ");
``` 

Code for imputting English and sending to Binary: 

```cpp
//Double-click right -> Send message
int led = 13;
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
  ``` 
  
### Input Morse code and output English translation 

### Completed Code 

```cpp
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 7, 6, 5, 4);

//char letters_b[17]
String msg = "";
String to_send = "";
char letters[17] = "ABCDEFGHIJKLMNOP";
char letters2[17] = "QRSTUVWXYZ@!.SAE";
int pos_l = 7;
int pos_r = 8;
int time = 0;
int pos = 0;
int d=0;
int it=0;
int last_bpl=0;
int last_bpr=0;
int led = 13; 
int switchscreen = 0; 

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


void blinkoff2(){
  lcd.setCursor(pos_l - (d%8), 0);
  lcd.print(letters2[pos_l - (d%8)]);    
  lcd.setCursor(pos_r + (d%8), 0);
  lcd.print(letters2[pos_r + (d%8)]);
  delay(200);
}
  
void loop() {
  
  if (switchscreen == 0){
    
    lcd.setCursor(0, 0);
    for (int i=0; i<sizeof(letters)-1; i++) {
      lcd.print(letters[i]);
    }
    
    
    if (d%8==0 && d>0){
    	switchscreen = 1;
      	d+=1;
    }
    
    if (it%4 == 0 && it>0) {
        d+=1;
    }
    blinkon();
    blinkoff(); 
    it+=1;
    
  }
  
  else{
    lcd.setCursor(0, 0);
    for (int i=0; i<sizeof(letters2)-1; i++) {
      lcd.print(letters2[i]);
    }
    
    
    if (d%8==0 && d>0){
    	switchscreen = 0; 
      d+=1;
    }
    
    if (it%4 == 0 && it>0) {
        d+=1;
    }
    blinkon();
    blinkoff2(); 
    it+=1;
  }

}
    
  void L_Button() {
    if (it-last_bpl<=1 && it>0) {
      Serial.print("double click ");
      dcl_L();
    }
      
    else {
      if (switchscreen == 0){
        msg.concat(letters[pos_l-(d%8)]);
        lcd.setCursor(0, 1);
        lcd.print(msg); 
        last_bpl = it;
      }
      else{
        msg.concat(letters2[pos_l-(d%8)]);
        lcd.setCursor(0, 1);
        lcd.print(msg); 
        last_bpl = it;
      }
    }
  }
  
  void R_Button() {
    if (it-last_bpr<=1 && it>0) {
      Serial.print("double click");
      dcl_R();
    }
    
    else {
      if (switchscreen ==0){
    	msg.concat(letters[pos_r+(d%8)]);
    	lcd.setCursor(0, 1);
    	lcd.print(msg);
    	last_bpr = it;
      }
          
      else{
        msg.concat(letters2[pos_r+(d%8)]);
    	lcd.setCursor(0, 1);
        if (msg == "S"){
          msg = "SOS";
            }
        if (msg == "A"){
          msg = "ACKNOWLEDGE";
            }
        if (msg == "E"){
          (msg = "ERROR");
            }
    	lcd.print(msg);
    	last_bpr = it;  
        }
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
  		delay(1000); 
  		digitalWrite(led,LOW); 
      	delay(1000); 
        }
      if (binary[x] =='1'){
      	Serial.println("One");
      	digitalWrite(led, HIGH);
 	 	delay(50000); 
  		digitalWrite(led,LOW);
        delay(1000); 
        digitalWrite(led,HIGH); 
  		delay(1000); 
  		digitalWrite(led,LOW); 
      	delay(1000);
       }
  	}
    Serial.println("New letter");
    digitalWrite(led,HIGH); 
    delay(20000); 
    digitalWrite(led,LOW); 
    delay(20000); 
    digitalWrite(led,HIGH); 
    delay(20000); 
    digitalWrite(led,LOW);
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
### Instruction Table for Communication System 

|                                     Command:                                     | Instruction                               | Left Button: | Right Button: |
|:--------------------------------------------------------------------------------:|-------------------------------------------|:------------:|:-------------:|
| Select left blinking letter                                                      | 1 Left press                              |       0     |       X     |
| Select right blinking letter                                                     | 1 Right press                             |       X      |       0       |
| Send Message                                                                     | 2 Right presses                           |       X      |     (2) 0     |
| Delete letter from message                                                       | 2 Left presses                            |     (2) 0    |       X       |
| Change mode of the device (from English input to translate Morse or vice versa ) | 1 Press of both buttons  at the same time |       0      |       0       |
| Input Morse code dot                                                             | 1 Left press under 1  second              | 0 < 1 second |       X       |
| Input Morse code dash                                                            | 1 Left press above 1  1second             | 0 > 1 second |       X       |
| Translate Morse code to English                                                  | 1 Right press                             |       X      |       0       |

**Key for Table:** 
- 0 = Press 
- X = Not presssed 
- (2) = Do this instruction twice 

This is a video

## Criteria E: Evaluation 

### Alpha Testing 

| Test No. | Procedure | Inputs | Expected Output | Success Criteria                                                                |Criteria Met| 
|----------|-----------|--------|-----------------|---------------------------------------------------------------------------------|------------|
| 1        |      Use left and right buttons to select best, and then double press the right button to send message.     |    "Best"    |    "Best" printed on message, and get the numbers 1,5,18,19 blink on the LED light.             | Must allow the user to enter English and output in binary                       |Yes |
| 2        |           |        |                 | Must allow the user to enter either morse code and output to English            |.  |
| 3        |           |        |                 | Must be able to carry out the commands delete, error, acknowledge, send and SOS |.  |
| 4        |           |        |                 | Must be able to send at least 10 words per minute                               |.  |

### Limitations and Further Improvements 

**Limitations** 

**Further Improvements** 
