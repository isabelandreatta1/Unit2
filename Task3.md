# Task 3:  Boolean Logic

## Read the Notes for Topic 1.1. Imagine yourself in the developer team behind the 🌟Matrix Reloaded🌟. 
Consider also the previous Matrix. The following is the description of the problem as described by the student that created it 2 years ago:

“Currently, every time students go off-campus we have to sign out by filling out a Google Form. We specify our return date, destination, and other details. When we return back from our outing we sign in by checking our name out of a list of  signed-out people. The form is long (it has around 8 questions), it does not have any default input values (such as the date or destination), and many times the data is the same or unique for each user, for example, the house to which they belong to or their mobile phone. The
“overnight” checkbox is another example of an unnecessary question: this can be calculated by parsing
the input return date.”

### 1. What is the context in which the original Matrix system was designed?
How big did the Matrix system need to be? 
What features were needed?
Who were the intended users of the system?

The Matrix had to include name of students signed out, data of return date and destination, mobile phone numbers imputed, the different house options
Features of the old Matrix system including writing answers for survey and checking boxes, centralising and organising the data (list of signed out people) 
The indeed users of the systems were students and faculty. (Students input their details and faculty used the data) 

### 2. What are some issues that could arise when transitioning from the old sign in/out system based on Google Forms to the dedicated web application Matrix? 

- Need additional training on how to use the new web Matrix application to faculty and students 
- The web application would need to include a lot of more complex features including a personal login 
- Difficulties in moving old data to new web application/losing data 
- Students need sign out while it may still be in transitioning period 

### 3. What would be the advantages and limitations of hosting the Matrix on a local computer versus on the cloud?
**Matrix on a local computer:** 
Advantages of hosting the Matrix on a local computer include accessing information quickly and you have all your data in one centralised server. You can also transfer data more simply. However, it is not very secure (since there is no back-up), and it is not efficient. 

**Matrix on the cloud:** 
Some of the advantages of hosting the Matrix on the cloud is that it runs on a variety of browsers and hardware. Because of this, students can also use inexpensive hardware. Keeping it on the cloud also means that the data can be restored in case of an emergency, and also it is kept secure. Some limitations of hosting the Matrix on the cloud is slower access to data and difficulty in moving old data to the cloud. 


### 4. Describe how would a Direct changeover, Parallel run, an ad phased implementation look like for the Matrix system? 

**Direct changeover:**
A direct changeover from the old matrix system to the new one would look like telling all the students to use the new matrix system and annulling the old one. By having a direct changeover, it would be the easiest to explain to users, however, there would be no certainty if the new matrix system would be better or worse (firstly, if it even works, secondly, if it works easier). Due to this, data will be lost as well as it would be risky to change so abruptly because there it will not be possible to return to the old system. 


**Parallel run:**
A parallel run for the Matrix system would be the safest option, ensuring that the old system is shut off only when there is full certainty the new one works well. However, in the perspective of a user, the process of using both systems is more tedious and confusing. Furthermore, data would not be properly centralised. This is particularly problematic for a signing in/out system since it may need to be used in emergencies. 


**Phased Implementation:** 
A phased implementation would be the most effective type of transition.  A phased implementation would mean that they would gradually reduce the reliance on the old system, meanwhile also increasing the reliance on the new system. The old system would be shut off once all the necessary information is transferred to the new system. For the Matrix, it would mean that it would allow users to get used to the new system, and also many adjustments can be made to the new system in the transition phase. However, since users do need to use two systems for a while, many of the same limitations of a parallel run would occur (tedious and confusing process, and decentralised data). Fortunately, the time duration of using two systems simultaneously would be shorter than a parallel run. 

### 5. What would be the consequences of a deficient transition from the old Google Form system to the Matrix, and to the New Matrix Reloaded? What would be the consequences of data loss?   
- Users stop using the new system because it a. Doesn’t work well b. Not user-friendly
- Can not login (incorrect password) 
- Incorrect contact details 
- Not have full records of the users/accounts

## [HL]
📔A book shop has a computer at each point of sale, and also a central computer. When a customer buys a book in the book shop, the salesperson at the point of sale uses a scanning device to input a barcode from the book. The barcode is sent to the central computer where the barcode of each book and the corresponding price are held in a database on a disk. When the price is found, it is sent to the point of sale computer where all necessary calculations are performed, details of the transaction are stored on a local disk and a receipt is printed out.

### Construct a system flow chart for the system described above. 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/Task3.jpg" width="367" height="159"/>

### At the point of sale there are peripheral devices other than the scanning device and printer.

### Define peripheral devices

A peripheral device is an input/output device which is used either for inputting,  storing or processing information from a computer. There are three types of peripheral devices based on their purpose. The inputting type include mouses and keyboards (they input information to the computer), the storing type include USBs and SATAs (they store computer’s data into external devices), and output type include headphones and printers (they output information from the computer to another device). 

### Outline the purpose of one other possible peripheral device in this scenario.


### The customers can also buy books online. A customer can select a book, and then enter their name, address and credit card number. This data is stored on the book shop’s central computer in a database of customer orders.

### Identify two sources of risk to personal data in this online system. 
 A possible source of risk to personal data would be data loss from incopetent employee. This is because all the information is stored on one central computer, and by accidentally modifying or deleting information, this will permanently change the data without having a way to check the previous data. Another risk would be in the case of a natural disaster, where all data can be deleted. This is because all data is stored on a local computer, and has no restoration or back-up system. 

(Another plausible risk could be malicious activity, meaning a third party attempts to steal or modify the data through hacking, breaking the computer, or using the central computer for nefarious purposes) 

### State two measures that the book shop can take to address the risks identified in part (d)
A measure to address both data loss from a natural disaster and incompetent employees are backups. There are two types of backups the book shop can implement. The first could backup media, in which they store the data on a separate hardware, located in a safe area. They could also perform a cloud-backup, in which all the data is stored on a web-server. This will allow access with any type of hardware/device. The book shop should operate generational backups, therefore always being able to see data’s past history and check for any data transferring errors. 

### Outline the consequences to the customer if their data is not adequately protected. [2]
Some consequences include a failed purchase, either by having the incorrect credit card or item not getting delivered by having the incorrect address. There is also a possibility of identity theft; client’s personal information can be stolen and used for malicious purposes. Lastly, the book shop may also lose information on which books are bought and have false information about their inventory. 




