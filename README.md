# Python Programming Portfolio

**William Hall**
**Bishoo's Stortford College**
**Python for STEM**
**Year 12**

## About Me

Hello, my is Will. I am 16 years old and I was born on the 21st of June 2009. Some of the thins that I enjoy are designing things, skiing, golfing and playign tennis. The A-Level subjects that I take are 3D Design, Maths and Economics

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
- Studen Grade Calculater
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