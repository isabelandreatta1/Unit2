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

```py.
allpasswords = open('Day2.txt','r').readlines()
validpasswordcounter = 0

for line in allpasswords:
    line.split()
    #if lowerboundary has two digits
    if  line[1].isnumeric():
        emptyrange1 = (line[0], line[1])
        range1 = int(''.join(map(str,emptyrange1)))
        emptyrange2a = (line[3],line[4])
        range2 = int(''.join(map(str,emptyrange2a)))
        wantedletter = line[6]
    #if lowerboundary has one digit
    else:
        range1 = line[0]
        #if upperboundary has two digits
        if line[3].isnumeric():
            emptyrange2b = (line[2],line[3])
            range2 = int(''.join(map(str,emptyrange2b)))
            wantedletter = line[5]
        #if upperboundary has one digits
        else:
            range2 = line[2]
            wantedletter = line[4]

    elementcounter = 0
    #check if the wanted letter frequency is in range
    for element in line:
        if element == wantedletter:
            elementcounter = elementcounter + 1

    if (elementcounter - 1) in range(int(range1), int(range2)+1):
        validpasswordcounter = validpasswordcounter + 1

print(validpasswordcounter)
```
Answer to part 1: 418 
```py.
    range1 = int((range1))-1
    range2 = int((range2))-1
    position1 = (startofpassword + range1)
    position2 = (startofpassword + range2)
    #check if the wanted letter is in one of the right positions
    elementcounter = 0
    if (line[position1] == wantedletter and not line[position2] == wantedletter):
        validpasswordcounter = validpasswordcounter + 1
    if (line[position2] == wantedletter and not line[position1] == wantedletter):
        validpasswordcounter = validpasswordcounter +1


    print(line[position1], line[position2], wantedletter,line[position1] == wantedletter and not line[position2] == wantedletter) or (line[position2] == wantedletter and not line[position2])
    print('line[position1], line[position2], wantedletter, elementcounter')

print(validpasswordcounter)
``` 
Answer to part 2: 626


