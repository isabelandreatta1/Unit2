# Quizzes homework
Solve them again, program them, draw flow diagram, test them. Add it to your repo for Unit 2

## Quiz 1 
Given 2 numbers, A and B, Output TRUE if one if them is 10 or if their sum is 10.

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
Test: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%201.png" width="264" height="278"/>

### Flow Chart 
![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/FlowChart%201.png) 

## Quiz 2
Given three int values, A, B, and C, output the largest.

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
Test: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%202.png" width="300" height="320"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%202.png) 

## Quiz 3
Given an integer N, print all the integers from 0 to N. 

[HL] show also the addition of the numbers.

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
def rangeN(N):
    count = 0
    for i in range(N+1):
        print(i)
        count += i
    return(count)

print(rangeN(N = 6))
```
Test: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%203.png" width="366" height="290"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%203.png)

## Quiz 4
Given an integer N, show all its factors. 

[HL] show also the addition of the factors show if the result is the same as N

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
def perfectN(N):
    count = 0
    for i in range(1,N):
        if 6%i == 0:
            print(i)
            count += i
    return("Sum of factors is:" ,count , "," , count== N)

print(perfectN(N = 6))
```
Test: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%204.png" width="432" height="162"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%204.png)

## Quiz 5
Given an integer N, show the multiplication table. 

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
def TableN(N):
    for i in range(1,10):
        multiplication = N * i
        return(N,"x",i,"=", multiplication)
print(TableN(N = 2))
```
Test: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%205.png" width="364" height="318"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%205.png)

## Quiz 6
Output TRUE if the given string begins with 'mix', except the 'm' can be anything, so 'pix', '9ix'..all count.

### Pseudo Code 
```
Function MixStart(string) 
print(string[1] == 'i' and string[2] == 'x) 
end function 
```
### Python Code 

```py
def MixStart(string):
    if(string[1] == 'i' and string[2] == 'x'):
        return True
    else:
        return False

print(MixStart(string = "mix snacks"))
```
Test: 

<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%206.png" width="464" height="192"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%206.png)

## Quiz 7
Given a string, output each letter with its index:

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
def letters(strings):
    for i in range(len(strings)):
        return(i, "->", strings[i])

print(letters(strings = ['hello']))
letters()
```
Test: 
<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%207.png" width="296" height="188"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%207.png)

## Quiz 8
Given an array of integers, find the largest absolute value.  Tip: you can use the abs() function.

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
def maxAbs(array):
    largestnumber = 0
    for i in range(len(array)):
        if abs(int(array[i])) > largestnumber:
            largestnumber = abs(int(array[i]))
    return(largestnumber)

print(maxAbs(array = [-4,5,6,-7]))
```
Test: 
<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%208.png" width="512" height="184"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%208.png)

## Quiz 9
Given an array of sorted integers, find the missing number.

### Pseudo Code 
```
Function missingNumber(array) 
correctnumber = 0 
loop i from 0 to length.array-1
	number = array[i]
	if number == correctnumber:
		correctnumber += 1
	else:
		print(correctnumber)
		break
end loop
end function 
```
### Python Code 
```py. 
def MissingNumber(array):
    correctnumber = array[0]
    for i in range(len(array)):
        number = array[i]
        if number == correctnumber:
            correctnumber += 1
        else:
            return(correctnumber)
            break

print(MissingNumber(array = [1,2,3,5,6,7,8,9]))
print(MissingNumber(array = [4,5,6,8,9,10]))
print(MissingNumber(array = [73,74,75,76,78,79]))
``` 
Test: 
<img src="https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Test%209.png" width="722" height="240"/>

### Flow Chart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Flowchart%209.png)

## Quiz 10

### Pseudo Code 
``` 
Function BigNeighbour(numbers)
largestdifference = 0 
loop i from 0 to numbers.length-1:
	difference = abs(numnbers[i] - numbers[i+1]) 
	if difference > largestdifference:
		largestdifference = difference 
		end loop 
return(largestdifference) 
end Function 
```
### Python 
```py
def BigNeighbour(numbers):
    largestdifference = 0
    for i in range(0, len(numbers)-1):
        difference = abs(numbers[i] - numbers[i + 1])
        if difference > largestdifference:
            largestdifference = difference
    return largestdifference

print(BigNeighbour(numbers = [1,2,3,4,5,7]))
```

Test: 
![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Quiz10test.png) 

### Flowchart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Quiz%2010.png)

## Quiz 11 

### Pseudo Code 
```
Function SameFirstLast(array):
firstelement = array[0] 
lastelement = array[array.length-1] 
if firstelement == lastelement and array.length >= 1:
	return True
else:
	return False 
end Function 
``` 
### Python 
```py.
def SameFirstLast(array): 
	firstelement = array[0] 
	lastelement = array[len(array)-1] 
	if firstelement == lastelement and len(array)>=1:
		return True
	else: 
		return False 
print(SameFirstLast(array = [1,2,3])) 
print(SameFirstLast(array = [1,2,3,1]) 
print(SameFirstLast(array = [1,2,1])) 
```
Test: 
![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Quiz11Test.png) 

### Flowchart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Quiz%2011.png)

## Quiz 12 
Given an array of words, find the average word length.

### Pseudo Code 
``` 
Function wordcounter(array): 
wordcounter = 0 
lettercounter = 0 
loop i from 0 to array.length-1:
	wordcounter += 1 
	loop n from 0 to array[1].length-1:
	lettercounter += 0 
	end loop 
end loop 
return(lettercounter/wordcounter) 
end Function 
```

### Python 
```py.
def wordlength(array):
	wordcounter = 0
	lettercounter = 0
	for i in range(len(array)):
		wordcounter += 1
		for n in range(len(array[i])):
		    lettercounter +=1
	return(lettercounter/wordcounter)

print(wordlength(array = ["home","car","travel","beach"]))
print(wordlength(array = ["sun","sat","cut","can"]))
print(wordlength(array = ["police","abacus"]))
``` 
Test: 
![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Quiz12Test.png)

### Flowchart 

![Diagram](https://github.com/isabelandreatta1/Unit2/blob/main/QuizTestPics/Blank%20diagram.png)


