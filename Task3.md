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

