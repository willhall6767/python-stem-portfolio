# Python Programming Portfolio

**William Hall**
**Bishop's Stortford College**
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
| 1 | [Unit Converter](#Unit-converter-portfolio-projects) | Variables, functions, input/output | ✅ Complete | 
| 2 | [Number Guessing Game](#Number-Guessing-Game-portfolio-projects) | Loops, conditionals, random | ✅ Complete |
| 3 | [To-Do List Manager](#To-do-list-manager-portfolio-projects) | Lists, functions, data structures | ✅ Complete |
| 4 | [Student Grade Calculator](#Student-grade-calculator-portfolio-projects) | Dictionaries, validation, error handling | ✅ Complete |
| 5 | [OOP Bank Account](#OOP-Bank-Account-portfolio-projects) | Classes, OOP principles | ✅ Complete |
| 6 | [Contact book with file saving](#Contact-book-with-file-saving-portfolio-projects) | Jupyter Notebooks, data exploration | ✅ Complete |
| 7 | [Name chooser](#Name-chooser-portfolio-projects) | Entering, analysing, showing | ✅ Complete |
| 8 | [Movie rating list](#Movie-rating-list-portfolio-projects) | Entering, interpreting, showing | ✅ Complete |
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

-  ## Unit Converter |[Portfolio Projects](#Portfolio-projects)
  - **A program that converts between common units. It inlcudes kilometers to miles, miles to kilometers, fahrenheit to degress celcius, degrees celcuis to fahrenheit, kg to pounds, pounds to kg, pints to litres and litres to pints.**
``` Python
def km_to_miles(km):
    return km * 0.621371

def miles_to_km(miles):
    return miles / 0.621371

def c_to_f(c):
    return (c * 9/5) + 32

def f_to_c(f):
    return (f - 32) * 5/9

def kg_to_pounds(kg):
    return kg * 2.20462

def pounds_to_kg(pounds):
    return pounds / 2.20462

def litres_to_pints(litres):
    # UK pints
    return litres * 1.75975

def pints_to_litres(pints):
    return pints / 1.75975


def get_number(prompt):
    """Safely get a numeric input from the user."""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Invalid input. Please enter a number.")


def show_menu():
    print("\n=== Unit Converter ===")
    print("1. Kilometres to Miles")
    print("2. Miles to Kilometres")
    print("3. Celsius to Fahrenheit")
    print("4. Fahrenheit to Celsius")
    print("5. Kilograms to Pounds")
    print("6. Pounds to Kilograms")
    print("7. Litres to Pints")
    print("8. Pints to Litres")
    print("9. Exit")


def main():
    while True:
        show_menu()
        choice = input("Enter your choice (1-9): ")

        if choice == "1":
            km = get_number("Enter kilometres: ")
            print(f"{km} km = {km_to_miles(km):.2f} miles")

        elif choice == "2":
            miles = get_number("Enter miles: ")
            print(f"{miles} miles = {miles_to_km(miles):.2f} km")

        elif choice == "3":
            c = get_number("Enter Celsius: ")
            print(f"{c}°C = {c_to_f(c):.2f}°F")

        elif choice == "4":
            f = get_number("Enter Fahrenheit: ")
            print(f"{f}°F = {f_to_c(f):.2f}°C")

        elif choice == "5":
            kg = get_number("Enter kilograms: ")
            print(f"{kg} kg = {kg_to_pounds(kg):.2f} pounds")

        elif choice == "6":
            pounds = get_number("Enter pounds: ")
            print(f"{pounds} pounds = {pounds_to_kg(pounds):.2f} kg")

        elif choice == "7":
            litres = get_number("Enter litres: ")
            print(f"{litres} litres = {litres_to_pints(litres):.2f} pints")

        elif choice == "8":
            pints = get_number("Enter pints: ")
            print(f"{pints} pints = {pints_to_litres(pints):.2f} litres")

        elif choice == "9":
            print("Goodbye!")
            break

        else:
            print("Invalid choice. Please select 1-9.")


# Run the program
main()
```
What should happen:

<img width="318" height="551" alt="image" src="https://github.com/user-attachments/assets/ffc77db8-852d-4569-881a-97d3abe7a34d" />



-  ## Number Guessing Game |[Portfolio Projects](#Portfolio-projects)
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
What should happen:

<img width="518" height="152" alt="SS1" src="https://github.com/user-attachments/assets/e474027b-24c3-49d9-aa9f-419c79a6663c" />



- ## To-Do List Manager |[Portfolio Projects](#Portfolio-projects)
  - **This is a simple to-do list where the used can enter tasks that they have and the program will record these, the user can also present all of the tasks that the user has entered when asked tro, it can also mark tasks as done once they have been completes and finally it can also remove tasks that the user had previously added which they no longer want.**

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



- ## Student Grade Calculator |[Portfolio Projects](#Portfolio-projects)
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
What should happen:

<img width="447" height="225" alt="image" src="https://github.com/user-attachments/assets/8c955517-5b3f-453f-8c05-44f353e4e0fd" />



- ## OOP Bank Account |[Portfolio Projects](#Portfolio-projects)
  - **This is a simple bank acocunt simulation which initially asks for the bank account holder's name and then also asks for the opening balance. Then out of a menu of 5 options, it will ask you to select one. Once you have selected an option it will then ask you to enter something for this option for example an amount of money. Once this is completed it will then show you your new account balance**

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
What should happen:

<img width="582" height="427" alt="image" src="https://github.com/user-attachments/assets/992e3cec-8f10-4625-bd87-5c06607732a2" />



- ## Contact Book with File Saving |[Portfolio Projects](#Portfolio-projects)
  - **This is a contact book which firstly gives you can option of 3 things. Once you have picked one of these options for example adding a contact, it will ask for the name of this contact and their number. Once you have done this it will record this data. One of the other options is to view contacts. Once you have added multiple contacts if you select the option to view contacts it will display the contacts that you have previously entered.**
```
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
What should happen:

<img width="581" height="473" alt="SS4" src="https://github.com/user-attachments/assets/051942bc-e2a5-4c90-95d5-e4d5b80eee89" />


- ## Name chooser |[Portfolio Projects](#Portfolio-projects)
  - **A piece of code that takes in your name, analysis it and then tells you its opinion on it**
```Python
def namechooser():
    '''selects a name'''
    for i in range(3):
        name = input("Enter a name:")
        if name =="bob":
            print("You are awesome!")
        elif name.lower() =="john":
            print("its alright")
        else: 
            print("boring")
            
#namechooser()
```
What should happen:

<img width="252" height="51" alt="image" src="https://github.com/user-attachments/assets/7ec7cf81-7cbe-40d3-bfc8-b70cea6f48ad" />


- ## Movie rating list |[Portfolio Projects](#Portfolio-projects)
  - **A piece of code which takes in the movie name, date it was made, director, its genre and your personal rating of the movie. Then after you have repeatadly inserted these different stats then it will put these stats into a table and display it**
```Python
import sqlite3

def dbConnection():
    # Create connection to database
    conn = sqlite3.connect('movie_list.db')
    cursor = conn.cursor()

    # Create table
    cursor.execute('''
        CREATE TABLE IF NOT EXISTS movielist (
              item_id INTEGER PRIMARY KEY AUTOINCREMENT,
              item_name TEXT NOT NULL,
              year INTEGER NOT NULL,
              director TEXT, 
              genre TEXT NOT NULL,
              rating INTEGER
        )
    ''')
    conn.commit()
    return conn, cursor


def insertData():
    '''add data to the database table'''
    query = '''INSERT INTO movielist (item_name, year, director, genre, rating)
VALUES ("Waves", 2019, "Trey Edward Shutts", "drama", 10);'''
    conn, cursor = dbConnection()
    cursor.execute(query)
    conn.commit()
    conn.close()


def insertDataWithParameters():
    '''add data to the database table'''
    query = '''INSERT INTO movielist (item_name, year, director, genre, rating)
VALUES (?, ?, ?, ?, ?);'''
    item_name = input('Enter the item name:')
    year = int(input('Enter the year:'))
    director = input('Enter the directors name:')
    genre = input('Enter the genre:')
    rating = int(input('Enter your rating:'))

    conn, cursor = dbConnection()
    cursor.execute(query, (item_name, year, director, genre, rating))
    conn.commit()
    conn.close()
    print("Record was successfully saved")


def readDatabase():
    '''read data from a table'''
    query = """SELECT * FROM movielist"""
    conn, cursor = dbConnection()
    cursor.execute(query)
    results = cursor.fetchall()

    print(f'{"item name":<20} {"Year":<6} {"Director":<25} {"Genre":<20} {"Rating":<6}')
    for row in results:
        print(f'{row[1]:<20} {row[2]:<6} {row[3]:<25} {row[4]:<20} {row[5]:<5}')
    conn.close()


def delete():
    userChange = input('Which item name would you like to delete?: ')
    query = '''DELETE FROM movielist WHERE item_name = ?'''

    conn, cursor = dbConnection()
    cursor.execute(query, (userChange,))
    conn.commit()
    conn.close()
    print("Record deleted (if it existed).")


def menu():
    title = 'Movie List Ratings'
    line = '-'
    menu = '''1. Add item (s)
2. Show items
3. Remove item
4. Update item
5. Quit
'''
    print(f"{title}\n{line*len(title)}")
    print(menu)


def main():
    '''Main user interface'''
    while True:
        menu()
        userChoice = int(input('Choose an option:'))

        if userChoice == 5:
            print('--------------End of program------------')
            break

        elif userChoice == 1:
            insertDataWithParameters()

        elif userChoice == 2:
            readDatabase()

        elif userChoice == 3:
            delete()

        elif userChoice == 4:
            print("Update function not implemented yet.")
```
What should happen:

<img width="939" height="297" alt="image" src="https://github.com/user-attachments/assets/2b158ad6-e580-4335-b707-4d44bf1c0c1a" />




