# Snakify 


## Sum of ten numbers - For Loop 
10 numbers are given in the input. Read them and print their sum. Use as few variables as you can.
```py
numberList = []
total = 0
for i in range(10):
    number = int(input())
    numberList.append(number)
    total = total + numberList[i]
print(total)
```

## List of Squares - While Loop 
For a given integer N, print all the squares of integer numbers where the square is less than or equal to N, in ascending order.
```py
n = int(input())
s = 1 
while s **2 <= n: 
    print(s**2)
    s = s+1
``` 
## Least divisor
Given an integer not less than 2. Print its smallest integer divisor greater than 1.
```py
n = int(input())
i = 2 
while n%i != 0: 
     i = i+1 
print(i)
```
## Morning jog
As a future athlete you just started your practice for an upcoming event. Given that on the first day you run x miles, and by the event you must be able to run y miles.
Calculate the number of days required for you to finally reach the required distance for the event, if you increases your distance each day by 10% from the previous day.

Print one integer representing the number of days to reach the required distance.
```py
FirstRun = int(input())
FinalRun = int(input())
days = 1
while FirstRun < FinalRun:
    FirstRun = FirstRun * 1.1
    days = days + 1
print(days)
``` 
## The sum of the sequence
Determine the sum of all elements in the sequence, ending with the number 0.
```py
total = 0
while True:
    n = int(input())
    if n != 0:
        total = total + n
    else:
        print(total)
        break
 ``` 
## The average of the sequence
Determine the average of all elements of the sequence ending with the number 0.
```py
count = 0
total = 0

while True:
    n = int(input())
    if n != 0:
        count = count + 1
        total = total + n
    else:
        finaltotal = total/count
        print(finaltotal)
        break
  ``` 
  ## The maximum of the sequence
  A sequence consists of integer numbers and ends with the number 0. Determine the largest element of the sequence.
  ```py 
 numbersList = []
while True:
    n = int(input())
    if n !=0: 
        numbersList.append(n)
    else: 
        break
print(max(numbersList))
```
