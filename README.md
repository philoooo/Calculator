<h1 align="center"> Python Calculator</h1>

<p>&nbsp;</p>
I made a simple calcuator with python that the user can interact with to calcuate numbers using addition, subtraction, multiplication, division.

<p>&nbsp;</p>

1. Here, I imported a python file to provide to enhance user experience with ascii art and defined my operator functions.
```
import art
print(art.logo)


def add(n1, n2):
    return n1 + n2

def subtract(n1, n2):
    return n1 - n2

def multiply(n1, n2):
    return n1 * n2

def divide(n1, n2):
    return n1 / n2
```

2. I added my functions into a dictinary as values using +, -. * and / as keys.
```
operators = {
    "+": add,
    "-": subtract,
    "*": multiply,
    "/": divide
}
```
3. I used recursion to restart the calculator whenever the user chooses to start a new calculation. Instead of ending the program, I called the calculator() function again, which resets all variables and starts the process from the beginning.
```
def calculator():
    should_accumulate = True
    num1 = float(input("Please type the first number: "))

    while should_accumulate:
        for symbol in operators:
            print(symbol)
        operator_type = input("Pick an operation: ")
        num2 = float(input("What is the next number: "))

        # Use dictionary and key index to call user input
        result = (operators[operator_type](num1, num2))
        print(f"{num1} {operator_type} {num2} = {result}")

        if_continue = input(f"Type 'y' to continue calculating with {result}, or type 'n' to start a new calculation: ")

        if if_continue == 'y':
            num1 = result
        else:
            should_accumulate = False
            print("\n" * 20)
            calculator()

calculator()
```
4. This is a test case to display the user experience, from my editor:
```
 _____________________
|  _________________  |
| | Pythonista   0. | |  .----------------.  .----------------.  .----------------.  .----------------. 
| |_________________| | | .--------------. || .--------------. || .--------------. || .--------------. |
|  ___ ___ ___   ___  | | |     ______   | || |      __      | || |   _____      | || |     ______   | |
| | 7 | 8 | 9 | | + | | | |   .' ___  |  | || |     /  \     | || |  |_   _|     | || |   .' ___  |  | |
| |___|___|___| |___| | | |  / .'   \_|  | || |    / /\ \    | || |    | |       | || |  / .'   \_|  | |
| | 4 | 5 | 6 | | - | | | |  | |         | || |   / ____ \   | || |    | |   _   | || |  | |         | |
| |___|___|___| |___| | | |  \ `.___.'\  | || | _/ /    \ \_ | || |   _| |__/ |  | || |  \ `.___.'\  | |
| | 1 | 2 | 3 | | x | | | |   `._____.'  | || ||____|  |____|| || |  |________|  | || |   `._____.'  | |
| |___|___|___| |___| | | |              | || |              | || |              | || |              | |
| | . | 0 | = | | / | | | '--------------' || '--------------' || '--------------' || '--------------' |
| |___|___|___| |___| |  '----------------'  '----------------'  '----------------'  '----------------' 
|_____________________|

Please type the first number: 16
+
-
*
/
Pick an operation: /
What is the next number: 3
16.0 / 3.0 = 5.333333333333333
Type 'y' to continue calculating with 5.333333333333333, or type 'n' to start a new calculation: y
+
-
*
/
Pick an operation: *
What is the next number: 3
5.333333333333333 * 3.0 = 16.0
Type 'y' to continue calculating with 16.0, or type 'n' to start a new calculation: n





















Please type the first number: 5
+
-
*
/
Pick an operation: -
What is the next number: 40
5.0 - 40.0 = -35.0
Type 'y' to continue calculating with -35.0, or type 'n' to start a new calculation:
```
