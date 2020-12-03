# Advent of Code 

## Day 1 
```py. 
n = input("Please put in the numbers: ")
numberList = []
n.split(" ")
for i in range(199):
    numberList.append(n[i])
    i = i+1
    for l in range(199):
        while int(n[i]) + int(n[l+1])!= 200:
            l = i+1
        else:
            print(n[i] * n[l])
``` 
Answer = []

## Day 2 

