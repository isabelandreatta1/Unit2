# Advent of Code 

## Day 1 
```py. 
n = open('Day1.txt','r').readlines()
numberList = []

for i in range(len(n)):
    n[i] = int(n[i])

for i in range(199):
    numberList.append(n[i])
    for l in range(199):
        if n[i] + n[l+1]== 2020:
            print(n[i] * n[l+1])
            exit()
``` 
Answer to part 1: 444019
Answer to part 2: 29212176




## Day 2 

