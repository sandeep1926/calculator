# calculator
 scientific calculator
import math

def add(x, y):
    return x+y

def subtraction(x, y):
    return x-y

def multiply(x, y):
    return x*y

def division(x, y):
    return x/y

def mod(x, y):
    return x%y

def exp(x, y):
    return x**y

operations={
    "+":add,
    "-":subtraction,
    "*":multiply,
    "/":division,
    "**":exp,
    "%":mod
}

def calculator():
    num1=float(input("Enter first Number: "))
    for symbol in operations:
        print(symbol)

        should_continue=True
        while should_continue:
            operation_symbol=input("Choose an Operation: ")
            num2=float(input("Enter second Number: "))

            calculator_function=operations[operation_symbol]

            answer=calculator_function(num1,num2)
            print(f"{num1}{operation_symbol}{num2}={answer}")
            decision=input(f"Type Y to continue calculating with {answer},type E to end the calculation,or type N to start a new calculation:\n").lower()

            if decision == "Y":
                num1=answer
            elif decision == "E":
                break
            else:
                should_continue=False
                calculator()


calculator()


print("THANK YOU")
