## Break Points

```py

raise SystemExit('can put string in here')

```

## Variables

Case sensitive, can use underscores, must start with a letter

## Functions

`def` is used to declare a function definition

```py

def division(num1, num2):
    result = num1 / num2
    return result

```

Call the function and save the result to a variable:

```py

result = division(20,10)

```

## Import function from another module within another file

Note: modules and files are normally called the same

```py

import divide

divide.division(10,5)

```

## Data Types

![data_types](https://user-images.githubusercontent.com/73107656/118349861-3c133b00-b54b-11eb-8525-325faed1d372.png)

`type()` can be used to check the data type of an object

```py
print(type("Hello, World!"))
print(type(42))
print(type(3.145))
print(type(1j))
print(type(["egg", "bacon", "spam"]))
print(type(("egg", "bacon", "spam")))
print(type(range(6)))
print(type({"name" : "John", "age" : 80}))
print(type({"egg", "bacon", "spam"}))
print(type(True))
print(isinstance(3.14, int))


<class 'str'>
<class 'int'>
<class 'float'>
<class 'complex'>
<class 'list'>
<class 'tuple'>
<class 'range'>
<class 'dict'>
<class 'set'>
<class 'bool'>
False

```

## Stings

Multi line strings can be wrapped in **triple quotes**

# Transform data types ------------------------------------------------

Using the functions `float()`, `int()`, `str()` etc..can convert a data type

![data_type_convertor_functions](https://user-images.githubusercontent.com/73107656/118350768-7206ee00-b550-11eb-9c2e-44b6c1a2a67d.png)

## input() function

The input function takes in a string, we can wrap it in one of the above convertors to work with different data type:

```py

first_number = int(input("Input your first number:"))
second_number = int(input("Input your second number:"))

print(first_number + second_number)

```

## Operators

![operators](https://user-images.githubusercontent.com/73107656/118351297-17bb5c80-b553-11eb-8825-3ae54bd5e508.png)

The `division` operator always returns a `float` even if it is a whole number!

To divide something and get an `int` we would use the `//` floor division operator instead, which rounds down to the nearest whole number.

PEMDAS applies: parentheses > exponents > multiplication & division > addition & subtraction

## Incrementing & Decrementing

![incrementing_decrementing](https://user-images.githubusercontent.com/73107656/118351959-b6958800-b556-11eb-844e-aec06c975ece.png)

## f-string: f'{variable}'

Like JavaScript interpolation we can dynamically inject string variables using an f-string:

```py
print(f"Hello {name}, you are {age} years old")

```

Example:

```py
name = "Igor"
age = 35

concat_string = name + ' is ' + str(age)
f_string = f"{name} is {age}"


print(concat_string)

print(f_string)

```

# String Methods --------------------------------------------------------

<img src="https://user-images.githubusercontent.com/73107656/118352565-117cae80-b55a-11eb-98f5-a27a435ad747.png" width="100%">

Examples:

```py

my_string = "HELLO WORLD"
my_string_lower_case = my_string.lower()

print(my_string_lower_case)

my_string_2 = "hElLo WorLD"
my_string_2_upper_case = my_string_2.upper()

print (my_string_2_upper_case)
print (my_string.isalpha())

greetings = my_string.replace("WORLD", "Dave")
print(greetings)

motion = ("jump", "walk", "run")
new_string = "ing ".join(motion)
print(new_string)

print(my_string_2.split(" "))

spaced_string = "     42       "
print(spaced_string.strip())

-------------------------------------------------------

hello world
HELLO WORLD
False
HELLO Dave
jumping walking run
['hElLo', 'WorLD']
42

```

Example 2:

```py

dwarves = "Grumpy, Dopey, Doc, Happy, Bashful, Sneezy, Sleepy"
print(dwarves)

lowercase_string = dwarves.lower()
print(lowercase_string)

commas_removed = lowercase_string.replace(',', '')
print(commas_removed)

split_list = commas_removed.split(' ')
print(split_list)

```

## Working with String

The below techniques do not mutate the original variable.

`variable[0]` Grabs the first letter in the string

`variable[-1]` Grabs the last element in the string

`Variable[0:3]` Slices the string from index 0 to index 3 (exclusive) so 0-2 is grabbed.

# and | or | not ----------------------------------------------------------

```py
print(True and True)
print(True and False)
print(True or False)
print(not (4 < 5 and 4 < 10))

a =10
b =5
result_one = a>b and a>10
result_two = a==5 or b<5
result_three = not(result_two)

```

# Truthy | Falsy ----------------------------------------------------

```py
print(bool(variable))

```

# Identity Operators

```py
a=1
b=1.0
print(a==b)
print(a is b)
print(id(a))
print(id(b))
# a and b have the same numeric value but a different type
c=b
print(b==c)
print(b is c)
print(id(b))
print(id(c))
# b and c are equal in value and identity


True
False
9784896
140094029824688
True
True
140094029824688
140094029824688

```

# Containment operator

```py
print('Program' in 'Programming')
print('spam' in ['spam', 'egg'])
print('sausage' not in ['spam', 'egg'])

```

# conditional

```py
number = int(input("Please enter a number:"))

if number == 5:
    print(f"{number} is equal to 5")
else:
    print(f"{number} is not equal to 5")

# -------------------------------------------------------

a = 10
b = 20
result = None

if a == b:
    result = 'a has the same value as b'
else:
    result = 'a has not got the same value as b'

print(result);


# Ternary Boolean ---------------------------------------

my_boolean = False

my_string = "Hello" if my_boolean else "World"

```

![fizzBuzz](https://user-images.githubusercontent.com/73107656/118421205-9087f900-b6b8-11eb-9dbc-693dccec4849.png)

# if / elif ------------------------------------------------------------------

```py

day = 'Friday'

if day == 'Monday':
    print('Meeting at 9:00')
elif day == 'Wednesday':
    print('Meeting at 2:00')
elif day == 'Friday':
    print('Meeting at 4:00')
else:
    print('No meetings today')


#  Nested

exit_program = True
manual_override = False
critical_systems_shutdown = False

if not exit_program and not critical_systems_shutdown:
    if manual_override:
        print("Shutting system down manually")
    else:
        print("This program will not exit just yet")
elif exit_program and critical_systems_shutdown is not True:
    print("Critical systems must be safely shut down before exiting the program")
else:
    print("This program will now be terminated...")

```

# Iteration ------------------------------------------------------------

Can use a standard for loop to loop through **lists** and **strings**

```py
languages = ["HTML", "CSS", "JavaScript"]
for language in languages:
  print(language)


for character in "Python":
  print(character)

```

## Range(start, stop, increment) -------------------------------------------------------

**Start** index from inclusive

**Stop** index to exclusive

Can use variables to make this a dynamic loop

```py

for i in range(1,5,1):

# Looping through the index using the list length -----------------------

foods = ['bacon', 'sausage', 'egg', 'spam']

for ind in range(len(foods)):
	# In this example only the index is iterated over not the value
    print(ind, foods[ind])

0 bacon
1 sausage
2 egg
3 spam

```

<img src="https://user-images.githubusercontent.com/73107656/118469668-d4512180-b6fd-11eb-9c83-17eafa7ca8c4.png" width="50%" style="margin-left: 25%">

The above is an example of mutating the original list.

## While loop ---------------------------------------------------------------------

```py
play_game = True

while play_game:
    continue_playing = input("Would you like to continue playing the game? y/n ")

    if continue_playing.lower() == "y":
        print("You have decided to continue playing the game.")
    elif continue_playing.lower() == "n":
        print("Now closing the game...")
        play_game = False
    else:
        print("That is not a valid option. Please try again.")

print("Thanks for playing")

```

## Break - Continue - Pass ------------------------------------------------------

Continue skips the code for that iteration and continues the loop
