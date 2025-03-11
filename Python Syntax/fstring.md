How to use f-strings in Python
To create an f-string, prefix the string with the letter “ f ”. The string itself can be formatted in much the same way that you would with str.format(). F-strings provide a concise and convenient way to embed Python expressions inside string literals for formatting. 

Print Variables using f-string in Python
In the below example, we have used the f-string inside a print() method to print a string. We use curly braces to use a variable value inside f-strings, so we define a variable ‘val’ with ‘Geeks’ and use this inside as seen in the code below ‘val’ with ‘Geeks’. Similarly, we use the ‘name’ and the variable inside a second print statement.

# Python3 program introducing f-string
val = 'Geeks'
print(f"{val}for{val} is a portal for {val}.")


name = 'Om'
age = 22
print(f"Hello, My name is {name} and I'm {age} years old.")
Output

GeeksforGeeks is a portal for Geeks.
Hello, My name is Om and I'm 22 years old.


Print date using f-string in Python
In this example, we have printed today’s date using the datetime module in Python with f-string. For that firstly, we import the datetime module after that we print the date using f-sting. Inside f-string ‘today’ assigned the current date and %B, %d, and %Y represents the full month, day of month, and year respectively.

# Prints today's date with help
# of datetime library
import datetime

today = datetime.datetime.today()
print(f"{today:%B %d, %Y}")
Output

May 23, 2024
Note: F-strings are faster than the two most commonly used string formatting mechanisms, which are % formatting and str.format(). 

Quotation Marks in f-string in Python
To use any type of quotation marks with the f-string in Python we have to make sure that the quotation marks used inside the expression are not the same as quotation marks used with the f-string.


print(f"'GeeksforGeeks'")

print(f"""Geeks"for"Geeks""")

print(f'''Geeks'for'Geeks''')
Output

'GeeksforGeeks'
Geeks"for"Geeks
Geeks'for'Geeks
Evaluate Expressions with f-Strings in Python
We can also evaluate expressions with f-strings in Python. To do so we have to write the expression inside the curly braces in f-string and the evaluated result will be printed as shown in the below code’s output.



english = 78
maths = 56
hindi = 85

print(f"Ram got total marks {english + maths + hindi} out of 300")
Output

Ram got total marks 219 out of 300
Errors while using f-string in Python
Backslashes in f-string in Python
In Python f-string, Backslash Cannot be used in format string directly.



f"newline: {ord('\n')"
Output

Hangup (SIGHUP)
  File "Solution.py", line 1
    f"newline: {ord('\n')"
    ^
SyntaxError: f-string expression part cannot include a backslash
However, we can put the backslash into a variable as a workaround though :


newline = ord('\n')

print(f"newline: {newline}")
Output

newline: 10
Inline comments in f-string in Python
We cannot use comments inside F-string expressions. It will give an error:


f"GeeksforGeeks is {5*2 + 3 #geeks-5} characters."
Output:

Hangup (SIGHUP)
  File "Solution.py", line 1
    f"GeeksforGeeks is {5*2 + 3 #geeks-5} characters."
    ^
SyntaxError: f-string expression part cannot include '#'
Printing Braces using f-string in Python
If we want to show curly braces in the f-string’s output then we have to use double curly braces in the f-string. Note that for each single pair of braces, we need to type double braces as seen in the below code.


# Printing single braces
print(f"{{Hello, Geek}}")

# Printing double braces
print(f"{{{{Hello, Geek}}}}")
Output

{Hello, Geek}
{{Hello, Geek}}


## Printing Dictionaries key-value using f-string in Python
While working with dictionaries, we have to make sure that if we are using double quotes (“) with the f-string then we have to use single quote (‘) for keys inside the f-string in Python and vice-versa. Otherwise, it will throw a syntax error.


Geek = { 'Id': 112,
         'Name': 'Harsh'}

print(f"Id of {Geek["Name"]} is {Geek["Id"]}")
Output

Hangup (SIGHUP)
  File "Solution.py", line 4
    print(f"Id of {Geek["Name"]} is {Geek["Id"]}")
                            ^
SyntaxError: invalid syntax
Using the same type of quotes for f-string and key


Geek = { 'Id': 100,
         'Name': 'Om'}

print(f"Id of {Geek['Name']} is {Geek['Id']}")
Output

Id of Om is 100



## Formatting number
Left Padding With Zeros
Now, let’s add zeros to the left. This is very useful when we need to create customized formats using numbers.

Say we want to obtain the following format: YYYYMMDD, and we have regular numbers from one-to-nine. In this case, we’ll need to add zeros to the left of the month and day.

Here are the two ways to do this with f-string.

year = 2022
month = 1
day = 5

# YYYYMMDD
>>> print(f'{year}{month:0>2}{day:0>2}')
20220105
>>> print(f'{year}{month:02d}{day:02d}')
20220105


## Round Float to “n” Decimals
When it comes to rounding float numbers to “n” decimals, it’s more practical to use the .precision with f type.

Let’s round the number below to one decimal.

x = 20.123
>>> print(f'{x:.1f}')
20.1

## Format Float to Percentages
Now, let’s round the number and add the % sign.

x = 20.123
>>> print(f'{x:.1f}%')
20.1%

## Use Commas as Thousands Separator
We can also add a comma as a thousands separator. We only need to add ,.

x = 1000000
>>> print(f'{x:,}')
1,000,000