# Python Programming Portfolio

**William Hall**
**Bishoo's Stortford College**
**Python for STEM**
**Year 12**

## About Me

Hello, my is Will. I am 16 years old and I was born on the 21st of June 2009. Some of the things that I enjoy are designing things, skiing, golfing and playign tennis. The A-Level subjects that I take are 3D Design, Maths and Economics

---

## Course Overview

This portfolio documents my progress through a Python programming course designed for students preparing for STEM pathays at university. The course covers:

- Python fundamentals (variables, input/output, data type)
- Control sutrctures (loops and conditional)
- Functions and modular code
- Data structures (lists, discitonaries, tuples, sets)
- Validation and error handling
- File handling
- Object-Orientated Perogramming (OOP)
- version control with Git and Github
- Work with Jupyter Notebooks

---

## Portfolio Projects

| # | Project | Key Skills | Status |
|---|---|---|---|
| 1 | [Unit Converter](#) | Variables, functions, input/output | ✅ Complete | 
| 2 | [Number Guessing Game](#) | Loops, conditionals, random | ✅ Complete |
| 3 | [To-Do List](#) | Lists, functions, data structures | ✅ Complete |
| 4 | [Student Grade Calculator](#) | Dictionaries, validation, error handling | ✅ Complete |
| 5 | [OOP Bank Account](#) | Classes, OOP principles | ✅ Complete |
| 6 | [Data Analysis Notebook](#) | Jupyter Notebooks, data exploration | ✅ Complete |

---

## Skills I Have Developed 

**Progromming Concepts**
- Writing clean, wells-commented Python code
- Using functions to organise and reuse code
- Handling user input safely with validation

**Tools and Technologies**
- Python 3 (Thonny IDE)
- Jupyter Notebooks
- Git version control
- GitHub for code sharing and portfolio management
- Markdown for documentation

---

## Contact

- **GitHub:** willhall6767
- **Email:** wh09606@gmail.com

---

## Project Codes
- Converter
``` Python
def FTempConverter():
    '''Tem converter'''
    temp = float(input(" Enter Celcius temp: "))
    f = (temp*9)/5+32
    print(f"{temp} C is {f} F")
FTempConverter()
```
- Number Guessing Game
  - **For this project I have programmed a code which will firstly tell you that it is thinking of a number from 1-100 and ask you for your first guess. Once you put you guess in it will tell you if you guessed too high, too low or correct. If you guessed too high or too low it will ask you again for your guess again and it will repeat this process untill you guess correctly. Finally, it will tell you how many attempts it took for you to guess the number it was thinking of.**
``` Python
import random

def play_game():
    """Play one round of the guessing game."""
    secret = random.randint(1, 100)
    attempts = 0
    
    print("I'm thinking of a number between 1 and 100.")
    
    while True:
        guess = int(input("Your guess: "))
        attempts += 1
        
        if guess < secret:
            print("Too low! Try again.")
        elif guess > secret:
            print("Too high! Try again.")
        else:
            print(f"Correct! You got it in {attempts} attempts.")
            break  # Exit the loop
```
#### What should happen:
```
<img width="492" height="147" alt="{BD09105D-CC7C-4C2E-B27D-609CFCD0662E}" src="https://github.com/user-attachments/assets/c1be5c96-631f-4fae-ade5-c1505f0cf46b" />
```
- To-Do List Manager
  - **A simple to-do list where the user can add tasks, view all tasks, mark a task as done, and remove tasks.**
``` Python
def show_tasks(tasks):
    """Display all tasks with their numbers."""
    if len(tasks) == 0:
        print("No tasks yet!")
        return
    
    print("\n=== Your Tasks ===")
    for i, task in enumerate(tasks, start=1):
        print(f"{i}. {task}")
    print()

def add_task(tasks):
    """Add a new task to the list."""
    new_task = input("Enter task: ")
    tasks.append(new_task)
    print(f"Added: '{new_task}'")

def remove_task(tasks):
    """Remove a task by number."""
    show_tasks(tasks)
    number = int(input("Enter task number to remove: "))
    if 1 <= number <= len(tasks):
        removed = tasks.pop(number - 1)
        print(f"Removed: '{removed}'")
    else:
        print("Invalid number.")

def main():
    tasks = []
    
    while True:
        print("=== To-Do List ===")
        print("1. View tasks")
        print("2. Add task")
        print("3. Remove task")
        print("4. Quit")
        
        choice = input("Choose: ")
        
        if choice == "1":
            show_tasks(tasks)
        elif choice == "2":
            add_task(tasks)
        elif choice == "3":
            remove_task(tasks)
        elif choice == "4":
            print("Goodbye!")
            break

main()
```
What should happen:

<img width="719" height="797" alt="{D22EC756-BBF7-4E40-9FAF-93BB3456B56B}" src="https://github.com/user-attachments/assets/5e43b9ec-bbe5-4f1e-b6ca-f058e682b646" />
```
- Student Grade Calculater
  - **For this project I programmed a code which will firstly ask your for your name, it will then ask you to put in the scores you got for each subject - maths, english and science - then it will calculate the percentages you got for each of these subjects and also give you a grade.**
``` Python
def get_grade(average):
    """Return a letter grade based on average percentage."""
    if average >= 70:
        return "A"
    elif average >= 60:
        return "B"
    elif average >= 50:
        return "C"
    elif average >= 40:
        return "D"
    else:
        return "U"

def get_valid_score(subject):
    """Ask for a score and keep asking until a valid number is entered."""
    while True:
        try:
            score = float(input(f"Enter score for {subject} (0-100): "))
            if 0 <= score <= 100:
                return score
            else:
                print("Score must be between 0 and 100.")
        except ValueError:
            print("Please enter a number.")

def calculate_results():
    """Collect scores and display results."""
    name = input("Student name: ")
    subjects = ["Maths", "English", "Science"]
    scores = {}
    
    for subject in subjects:
        scores[subject] = get_valid_score(subject)
    
    average = sum(scores.values()) / len(scores)
    grade = get_grade(average)
    
    print(f"\n=== Results for {name} ===")
    for subject, score in scores.items():
        print(f"  {subject}: {score:.1f}")
    print(f"Average: {average:.1f}%")
    print(f"Grade: {grade}")

calculate_results()
```
- OOP Bank Account
  - **A simple bank account simulation using a class. The user can deposit money, withdraw money (with a check for sufficient funds), and check their balance.**
``` Python
class BankAccount:
    """A simple bank account class."""
    
    def __init__(self, owner, initial_balance=0):
        """Set up the account with an owner name and starting balance."""
        self.owner = owner
        self.balance = initial_balance
        self.transactions = []
    
    def deposit(self, amount):
        """Add money to the account."""
        if amount > 0:
            self.balance += amount
            self.transactions.append(f"Deposit: +£{amount:.2f}")
            print(f"Deposited £{amount:.2f}. New balance: £{self.balance:.2f}")
        else:
            print("Deposit amount must be positive.")
    
    def withdraw(self, amount):
        """Remove money from the account if funds are available."""
        if amount <= 0:
            print("Withdrawal amount must be positive.")
        elif amount > self.balance:
            print(f"Insufficient funds. Balance is only £{self.balance:.2f}")
        else:
            self.balance -= amount
            self.transactions.append(f"Withdrawal: -£{amount:.2f}")
            print(f"Withdrew £{amount:.2f}. New balance: £{self.balance:.2f}")
    
    def show_balance(self):
        """Display the current balance."""
        print(f"\nAccount holder: {self.owner}")
        print(f"Current balance: £{self.balance:.2f}")
    
    def show_history(self):
        """Display all transactions."""
        print(f"\n=== Transaction History for {self.owner} ===")
        for t in self.transactions:
            print(f"  {t}")
        print(f"  Current balance: £{self.balance:.2f}")


# --- Using the class ---
def main():
    name = input("Enter account holder name: ")
    opening = float(input("Enter opening balance: £"))
    
    account = BankAccount(name, opening)
    
    while True:
        print("\n1. Deposit")
        print("2. Withdraw")
        print("3. Check balance")
        print("4. View history")
        print("5. Exit")
        
        choice = input("Choose: ")
        
        if choice == "1":
            amount = float(input("Amount to deposit: £"))
            account.deposit(amount)
        elif choice == "2":
            amount = float(input("Amount to withdraw: £"))
            account.withdraw(amount)
        elif choice == "3":
            account.show_balance()
        elif choice == "4":
            account.show_history()
        elif choice == "5":
            print("Thank you for banking with us.")
            break

main()
```
- Contact Book with File Saving
  - **A contact book that saves names and phone numbers to a text file. Each time you run the program, it loads existing contacts from the file.**
``` Python
import os

FILENAME = "contacts.txt"

def load_contacts():
    """Load contacts from file. Return empty list if file doesn't exist."""
    contacts = []
    if os.path.exists(FILENAME):
        with open(FILENAME, "r") as f:
            for line in f:
                parts = line.strip().split(",")
                if len(parts) == 2:
                    contacts.append({"name": parts[0], "phone": parts[1]})
    return contacts

def save_contacts(contacts):
    """Save all contacts to file."""
    with open(FILENAME, "w") as f:
        for c in contacts:
            f.write(f"{c['name']},{c['phone']}\n")
    print("Contacts saved.")

def add_contact(contacts):
    name = input("Name: ")
    phone = input("Phone: ")
    contacts.append({"name": name, "phone": phone})
    save_contacts(contacts)

def view_contacts(contacts):
    if not contacts:
        print("No contacts saved.")
        return
    print("\n=== Contacts ===")
    for i, c in enumerate(contacts, 1):
        print(f"{i}. {c['name']} — {c['phone']}")

def main():
    contacts = load_contacts()
    print(f"Loaded {len(contacts)} contact(s).")
    
    while True:
        print("\n1. View contacts  2. Add contact  3. Exit")
        choice = input("Choose: ")
        if choice == "1":
            view_contacts(contacts)
        elif choice == "2":
            add_contact(contacts)
        elif choice == "3":
            break

main()
```
