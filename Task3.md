## Task 3: Programming Task 
In a game of guessing a number between 1-100 for two players, player A and player B. 
The player A knows the number. 
The player B is trying to guess with the least number of attempts.
Player A can only reply to a guess from the other player B with “low”, “high”, or “That is the number”.

**Your task is to create a computer program for Player B.**
```py.
import random
number = random.randint(1,100)
number = 42
def program():
    count = 0
    print("I have chosen a number, please pick a number between 1 -100")
    low = 0
    high = 100
    mid = round((low + high)/2)
    correct = "that is correct"
    print(mid)
    while True:
        answer = input("Player A")
        if mid == number:
            print(mid)
            print("That is the number. You complete in {} trials".format(count))
            break
        elif mid < number:
            print("{} = low ".format(mid))
            count = count + 1
            low = mid
            mid = round((low + high) / 2)
        else:
            count = count + 1
            print('{} = high'.format(mid))
            print(answer)
            high = mid
            mid = round((low + high)/2)
program()

```

**Computer program for Player A** 
```py.
import random
number = random.randint(1,100)
count = 0
print("I have chosen a number, please pick a number between 1 -100")
while True:
    guess = int(input())
    if guess > number:
        print("high")
        count = count + 1
    elif guess < number:
        print('low')
        count = count+1
    else:
        print("That is the number. You took {} tries".format(count))
        break
``` 

