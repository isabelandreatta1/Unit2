# Quizzes homework
Solve them again, program them, draw flow diagram, test them. Add it to your repo for Unit 2

## Quiz 1 

### Pseudo Code 
```
Function Makes10 (A,B) 
print(A + B == 10 or A == 10 or B == 10) 
end function
```
### Python Code 
```py
def Makes10():
    A = int(input("Please input A"))
    B = int(input("Please input B"))
    print(A + B == 10 or A == 10 or B == 10)

Makes10()
```
### Flow Chart 

## Quiz 2

### Pseudo Code 
```
Function intMax (A,B,C)
if A<B:
	if B>C:
		print(B)
	else:
		print(C)
else:
	if A>C:
		print(A)
	else:
		print(C) 
end function 
```
### Python Code 
```py
def intMax():
    A = int(input("Please input A "))
    B = int(input("Please input B "))
    C = int(input("Please input C "))
    if A<B:
        if B>C:
            print(B)
        else:
            print(C)
    else:
        if A>C:
            print(A)
        else:
            print(C)
    intMax()
```

### Flow Chart 

## Quiz 3

### Pseudo Code 
```
Function rangeN(N) 
	count = 0 
	loop i from 0 to N:
		print(i)
		count += i 
	print(count) 
	end loop 
end function 
```
### Python Code 

```py
def rangeN():
    N = int(input("Please input int N "))
    count = 0
    for i in range(N+1):
        print(i)
        count += i
    print(count)

rangeN()
```
### Flow Chart 

## Quiz 4

### Pseudo Code 
```
Function perfectN(N) 
count = 0 
	loop i from 0 to N:
		if 6 mod i == 0:
			print(i)
			count += i
	print("Sum of factors is:" + "count" + "," + count == N) 
	end loop 
end function 
```
### Python Code 
```py
def perfectN():
    N = int(input("Please input int N "))
    count = 0
    for i in range(1,N):
        if 6%i == 0:
            print(i)
            count += i
    print("Sum of factors is:", count , ",", count == N)
perfectN()
```
### Flow Chart 

## Quiz 5

### Pseudo Code 
```
Function TableN(N)
	loop i from 1 to 9:
		multiplication = N * i 
		print(N + "x" + i + "=" + multiplication) 
	end loop 
end function 
```
### Python Code 
```py
def TableN():
    N = int(input("Please input N "))
    for i in range(1,10):
        multiplication = N * i
        print(N,"x",i,"=", multiplication)
TableN()
```
### Flow Chart 

## Quiz 6

### Pseudo Code 
```
Function MixStart(string) 
print(string[1] == 'i' and string[2] == 'x) 
end function 
```
### Python Code 

```py
def MixStart():
    string = input("Please input string ")
    print(string[1] == 'i' and string[2] == 'x')
    
MixStart()
```
### Flow Chart 

## Quiz 7

### Pseudo Code 
```
Function letters(string) 
loop i from 0 to (length.string - 1):
	print(i,"->", string[i]) 
end loop 
end function 
```
### Python Code 
```py
def letters():
    string = input("Please input string ")
    for i in range(len(string)):
        print(i, "->", string[i])

letters()
```
### Flow Chart 

## Quiz 8

### Pseudo Code 
```
Function maxAbs(array) 
largestnumber = 0 
	loop i from 0 to length.array - 1:
		if abs(array[i]) > largestnumber:
			largestnumber = abs(array[i]) 
	end loop 
	print("max absolute is" + largestnumber) 
end function 
```
### Python Code 

```py
def maxAbs():
    largestnumber = 0
    stringinput = input("Please input array ")
    array = list(map(int, stringinput.split(' ')))
    for i in range(len(array)):
        if abs(int(array[i])) > largestnumber:
            largestnumber = abs(int(array[i]))
    print("max absolute is", largestnumber)

maxAbs()
```

### Flow Chart 

## Quiz 9

### Pseudo Code 
```
Function missingNumber(array) 
correctnumber = 0 
loop i from 0 to length.array-1
	if number == correctnumber:
		correctnumber += 1
	else:
		print(correctnumber)
		break
end loop
end function 
```
### Python Code 

```py
def missingNumber():
    stringinput = input("Please input array ")
    array = list(map(int, stringinput.split(' ')))
    correctnumber = array[0]
    for i in range(len(array)):
        number = array[i]
        if number == correctnumber:
            correctnumber += 1
        else:
            print(correctnumber)
            break

    missingNumber()
```

### Flow Chart 
