# Unit 2: Arduino LED Dipslay 
## Criteria A: Planning

### Context of the problem 
The customer is looking for an LED display which will count from 0-9. However, there are certain limitations regarding this display: it must use a maximum of 4 buttons and 7 LED lights, using a different dipslay than the typical 7-segment display (which has an 8-like pattern) used in, for example, digital clocks. 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Seven_segment_01_Pengo.jpg" width="150" height="150"/>
*Figure 1. Example of the typical 7-segment dipslay* 

### Justification of the solution 


<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Sketches.jpg" width="350" height="500"/>

*Figure 2. Sketches of possible displays* 


### Criteria for success
1. The display should count from 0-9 
1. A table showing each number number 0-9 and corresponding LEDs are included 
1. Information indicating what the buttons do is included
1. The display uses maximum 7 LEDs and 4 buttons 

## Criteria B: Design 
![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/IMG_2759.JPG)

*Figure 3 System Diagram* 

### Record of Tasks
| Task No. | Planned Action                                                                          | Planned Outcome                                        | Time Estimated | Target Completion Date | Criterion |
|----------|-----------------------------------------------------------------------------------------|--------------------------------------------------------|----------------|------------------------|-----------|
| 1.       | Planning: Create draft sketches for display.                                            | 3 or more sketches of display options                  |                |                        |           |
| 2.       | Planning: Modify and finalise the display                                               | Final display labelled with figure of counting system  |                |                        |           |
| 3.       | Planning: Create a digital circuit on Tinkercad  of the Arduino with some of the coding |                                                        |                |                        |           |
| 3.       | Planning: Create a '' table for the LED lights                                          |                                                        |                |                        |           |
| 4.       | Planning: Create K-maps and equations for each LED lights (a-e)                         | 5 K-maps and boolean equations for LEDs                |                |                        |           |
| 5.       | Planning: Create a flowchart and truthtable  for the LEDs                               | 5 flowcharts and truth tables                          |                |                        |           |
| 6.       | Development: Finish the code for the Arduino and  test it on the Tinkercad simulation   |                                                        |                |                        |           |
| 7.       | Development: Create the box for the display                                             |                                                        |                |                        |           |
| 8.       | Development: Connect all the wires                                                      |                                                        |                |                        |           |
| 9.       | Development: Write the code on the Arduino                                              |                                                        |                |                        |           |

### Testing Plan  

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

## Criteria D: Functionality 

## Criteria E: Evaluation 
