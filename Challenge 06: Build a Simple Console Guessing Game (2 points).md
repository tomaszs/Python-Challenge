# Build a Simple Console Guessing Game

## The Challenge

Create a Python program where the computer selects a random number between 1 and 100, and the player has to guess it. The program should provide hints such as "Too high" or "Too low" until the player guesses correctly.

### Example Interaction:

```
Welcome to the Guessing Game!
I have selected a number between 1 and 100. Try to guess it.

Enter your guess: 50
Too high! Try again.

Enter your guess: 25
Too low! Try again.

Enter your guess: 30
Congratulations! You guessed the number in 3 tries!
```

---

## Tips:

1. **Generate a Random Number:** Use Python's `random.randint()` function to select a number between 1 and 100.  
2. **Take Input from the Player:** Use `input()` to get the player's guess.  
3. **Provide Feedback:** Use conditional statements (`if`, `elif`, `else`) to check if the guess is too high, too low, or correct.  
4. **Count Attempts:** Keep track of how many attempts the player takes to guess the number.

---

## Solution:

### Complete Code

```python
import random

def guessing_game():
    print("Welcome to the Guessing Game!")
    print("I have selected a number between 1 and 100. Try to guess it.
")
    
    number_to_guess = random.randint(1, 100)
    attempts = 0

    while True:
        try:
            guess = int(input("Enter your guess: "))
            attempts += 1
            if guess < number_to_guess:
                print("Too low! Try again.
")
            elif guess > number_to_guess:
                print("Too high! Try again.
")
            else:
                print(f"Congratulations! You guessed the number in {attempts} tries!")
                break
        except ValueError:
            print("Please enter a valid number.
")

# Run the game
guessing_game()
```

---

## Why This Challenge Matters

This task combines fundamental Python concepts into a fun, interactive project:
- **Random Numbers:** Learn how to generate random numbers with `random.randint()`.
- **Input Handling:** Practice taking and processing user input.
- **Conditional Logic:** Reinforce the use of `if-else` statements for decision-making.
- **Loops:** Use a `while` loop to create a game loop that repeats until the correct guess is made.

---

## Challenge Yourself Further

1. Add difficulty levels:  
   - Easy: Unlimited guesses.  
   - Medium: Maximum of 10 guesses.  
   - Hard: Maximum of 5 guesses.

2. Keep track of the player's best score across multiple games.

3. Add a feature where the player can quit by typing "exit".

---

Solving this challenge earns you **2 points**—great job! Ready for the next level? Build on this game and explore more possibilities!

If you spot a mistake in a challenge, please create a merge request to excercise how to use GitHub as well :)
