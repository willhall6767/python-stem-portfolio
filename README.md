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
[- Converter](https://github.com/willhall6767/Python-Award-Option/blob/main/Week1/week1challenges.ipynb)
``` Python
def FTempConverter():
    '''Tem converter'''
    temp = float(input(" Enter Celcius temp: "))
    f = (temp*9)/5+32
    print(f"{temp} C is {f} F")
FTempConverter()
```
[- Number Guessing Game]
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

