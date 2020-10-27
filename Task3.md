## Task 3: Programming Task 
In a game of guessing a number between 1-100 for two players, player A and player B. 
The player A knows the number. 
The player B is trying to guess with the least number of attempts.
Player A can only reply to a guess from the other player B with “low”, “high”, or “That is the number”.

**Your task is to create a computer program for Player B.**

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

