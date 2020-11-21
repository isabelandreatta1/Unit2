# Unit 2: Arduino LED Dipslay 
## Criteria A: Planning

### Context of the problem 
The customer is looking for an LED display which will count from 0-9. However, there are certain limitations regarding this display: it must use a maximum of 4 buttons and 7 LED lights, and it must have a different dipslay than the typical 7-segment display (which has an 8-like pattern) used in, for example, digital clocks. 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Seven_segment_01_Pengo.jpg" width="150" height="150"/>
*Figure 1. Example of the typical 7-segment dipslay* 

### Justification of the solution 
We are using an Arduino Uno R3 in order to create the LED and button circuit, 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Sketches.jpg" width="350" height="500"/>

*Figure 2. Sketches of possible displays* 


### Criteria for success
1. The display should count from 0-9 
1. A table showing each number number 0-9 and corresponding LEDs are included 
1. Information indicating what the buttons do is included
1. The display uses maximum 7 LEDs and 4 buttons 

## Criteria B: Design 
![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/IMG_2759.JPG)

*Figure 3. System Diagram* 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/TRUTH_TABLE.png" width="450" height="300"/>

*Figure 4. Truth Table* 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/LED_LIGHT_DIAGRAM.png" width="300" height="200"/>
                                                                                                            
*Figure 5. LED-Lights Diagram* 

### Record of Tasks  
| Task No. | Planned Action                                                                        | Planned Outcome                                                                | Time Estimated | Target Completion Date | Criterion |
|----------|---------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|----------------|------------------------|-----------|
| 1.       | Planning: Create draft sketches for display.                                          | 3 or more sketches of display options                                          | 30 minutes     | 2nd November           | A         |
| 2.       | Planning: Modify and finalise the display                                             | Final display labelled with figure of counting system                          | 15 minutes     | 3rd November           | A         |
| 3.       | Design: Create a digital circuit on Tinkercad  of the Arduino with some of the coding | Draft of code on Tinkercad                                                     | 20 minutes     | 6th November           | B         |
| 3.       | Design: Create a truth table for the LED lights                                       | Truth Table                                                                    | 10 minutes     | 6th November           | B         |
| 4.       | Design: Create K-maps and equations for each LED lights (a-e)                         | 5 K-maps and boolean equations for LEDs                                        | 15 minutes     | 7th November           | B         |
| 5.       | Design: Create a flowchart for the code                                               | 5 flowcharts and truth tables                                                  | 25 minutes     | 8th November           | B         |
| 6.       | Development: Finish the code for the Arduino and  test it on the Tinkercad simulation | Completed Code in C++ for Arduino which programs the light and button circuit  | 30 minutes     | 9th November           | C         |
| 7.       | Development: Create the box for the display                                           | A painted standing up display                                                  | 45 minutes     | 10th November          | C         |
| 8.       | Development: Connect all the wires                                                    | A functioning circuit                                                          | 45 minutes     | 10th November          | C         |
| 9.       | Development: Write the code on the Arduino                                            | Arduino and circuit that are connected, with a code that works as planned      | 25 minutes     | 13th November          | C         |


## Criteria C: Development 


```cpp
int led_a = 13; 
int led_b = 12;
int led_c = 11; 
int led_d = 10; 
int led_e = 9; 
int btn_x = 8; 
int btn_y = 7; 

int btn_w = 6; 
int btn_z = 5; 
int val_x = 0; 
int val_y = 0; 
int val_w = 0; 
int val_z = 0; 

void setup()
{
  pinMode(led_a, OUTPUT); 
  pinMode(led_b, OUTPUT); 
  pinMode(led_c, OUTPUT); 
  pinMode(led_d, OUTPUT); 
  pinMode(led_e, OUTPUT); 
  Serial.begin(9600); 
}

    
void loop()
{
  val_x = digitalRead(btn_x);
  val_y = digitalRead(btn_y);
  val_w = digitalRead(btn_w);
  val_z = digitalRead(btn_z);

  int a = (!val_z) && (!val_w) && val_y || (!val_z) && (!val_w) && val_x || (!val_x) && (!val_y) && (!val_z) && val_w || val_z && val_w && val_y || val_x && val_y && val_z && (!val_x) && (!val_y) && val_z && (!val_w); 
  digitalWrite(led_a,a);  
  int b =  (!val_x) && val_y && (!val_z) && (!val_w) ||  (!val_x) && (!val_y) && (!val_z) && val_w || (!val_x) && val_y && (!val_z) && val_w || (!val_x) && (!val_y) && val_z && (!val_w) || val_x && val_y && val_z && (!val_w); 
  digitalWrite(led_b,b); 
  int c = (!val_x) && (!val_y) && (!val_z) && (val_w) || val_y && val_z && val_w || (!val_x) && (!val_y) && val_z && (!val_w) ; 
  digitalWrite(led_c,c); 
  int d = val_x && val_y && (!val_z) && (!val_w) || val_x && (!val_y) && (!val_z) && val_w ||  val_y && val_x & val_z || val_x && val_y && val_z ; 
  digitalWrite(led_d,d); 
  digitalWrite(led_e,d);  
}
```

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/DipslayBack.JPG" width="380" height="220"/>

*Display Circuit* 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Display%20Front%20View.jpg" width="341" height="187"/>

*Front of Display* 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/DisplaySide.jpg" width="254" height="264"/>

*Side of Display 1* 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/DisplaySide2.jpg" width="232" height="194"/>

*Side of Display 2* 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Button_Instrunctions.jpg" width="250" height="250"/>

*Button Instrunctions* 

## Criteria D: Functionality 

### Testing Plan  

## Criteria E: Evaluation 
