
# Task 2 calculator project
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error: Cannot divide by zero!"
    return x / y

print("Simple Calculator")
print("Select operation:")
print("1. Addition (+)")
print("2. Subtraction (-)")
print("3. Multiplication (*)")
print("4. Division (/)")

try:
    num1 = float(input("Enter first number: "))
    num2 = float(input("Enter second number: "))
    choice = input("Enter operation (+, -, *, /): ")

    if choice == '+':
        result = add(num1, num2)
    elif choice == '-':
        result = subtract(num1, num2)
    elif choice == '*':
        result = multiply(num1, num2)
    elif choice == '/':
        result = divide(num1, num2)
    else:
        result = "Invalid operation!"

    print("Result:", result)

except ValueError:
    print("Invalid input! Please enter numeric values.")


    
#Task 3 password generator project
import random
import string

def generate_password(length):
    if length < 4:
        return "Password should be at least 4 characters long."

    
    upper = string.ascii_uppercase
    lower = string.ascii_lowercase
    digits = string.digits
    symbols = string.punctuation

    
    all_chars = upper + lower + digits + symbols

    
    password = random.choice(upper) + random.choice(lower) + random.choice(digits) + random.choice(symbols)

    
    password += ''.join(random.choices(all_chars, k=length - 4))

   
    password_list = list(password)
    random.shuffle(password_list)

    return ''.join(password_list)
try:
    user_length = int(input("Enter the desired password length: "))
    password = generate_password(user_length)
    print("Generated Password:", password)
except ValueError:
    print("Invalid input! Please enter a number.")

#task 4 Rock-Paper-Scissors Game
import random
def rock_paper_scissors():
    print("WELCOME TO THE GAME!")
    options = ["rock", "paper", "scissors"]

    your_choice = input("Enter your choice (rock, paper, scissors): ").strip().lower()
    if your_choice not in options:
        print("Invalid choice! Please enter rock, paper, or scissors.")
        return

    my_choice = random.choice(options)
    print("My choice:", my_choice)

    if your_choice == my_choice:
        print("It's a tie!")
    elif (
        (your_choice == "rock" and my_choice == "scissors") or
        (your_choice == "paper" and my_choice == "rock") or
        (your_choice == "scissors" and my_choice == "paper")
    ):
        print("YOU WIN!")
    else:
        print("YOU LOSE!")

rock_paper_scissors()
