## Problem Statement

Guess My Number

I am thinking of a number between 0 and 99...
Enter a guess: 50
Your guess is too high

Enter a new number: 25
Your guess is too low

Enter a new number: 40
Your guess is too low

Enter a new number: 45
Your guess is too low

Enter a new number: 48
Congrats! The number was: 48

## Solution

```bash
import random

def main():
        secret_number: int = random.randint(1, 99)
        print("I am thinking of a number between 1 and 99...")

        # Get user's guess with error handling
        while True:
            try:
                guess = int(input("Enter a guess: "))
            except ValueError:
                print("Invalid input! Please enter a number.")
                continue  # Loop ko dobara start karta hai taake valid input liya ja sake
            
            # Check if the guess is correct
            if guess < secret_number:
                print("Your guess is too low")
            elif guess > secret_number:
                print("Your guess is too high")
            else:
                print("Congrats! The number was:", secret_number)
                break  # Loop ko end karta hai jab sahi guess ho jata hai
main()

```