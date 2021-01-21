# 100-Python-challenging-programming-exercises-for-Python-3.
100+ Python challenging programming exercises for Python 3 with Solutions
### Question 1:
Write a program that calculates and prints the value according to the given formula: Q = Square root of [(2 * C * D)/H] Following are the fixed values of C and H: C is 50. H is 30. D is the variable whose values should be input to your program in a comma-separated sequence. Example Let us assume the following comma separated input sequence is given to the program: 100,150,180 The output of the program should be: 18,22,24
#### Solution
```python
>>>import math
user_input = input("Enter a comma-separated sequence : ").split(",")
result = [str(math.round(math.sqrt(((2*50*float(x))/30)))) for x in user_input]
print(','.join(result))
````
### Question 2:
Write a program which takes 2 digits, X,Y as input and generates a 2-dimensional array. The element value in the i-th row and j-th column of the array should be i*j. Note: i=0,1.., X-1; j=0,1,¡­Y-1. Example Suppose the following inputs are given to the program: 3,5 Then, the output of the program should be: [[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8]]
#### Solution
```python
demensions = input().split(",")
column = int(demensions[0])
raw = int(demensions[1])
multilist = [[0 for raww in range(raw)] for col in range(column)]
for i in range(column):
    for j in range(raw):
        multilist[i][j] = i*j
print(multilist)
```
### Question 3:
Write a program that accepts a comma separated sequence of words as input and prints the words in a comma-separated sequence after sorting them alphabetically. Suppose the following input is supplied to the program: without,hello,bag,world Then, the output should be: bag,hello,without,world
#### Solution
```python
user_input = input("Enter a comma separated sequence of words : ").split(",")
user_input.sort()
print(",".join(user_input))
```
### Question 4:
Question£º Write a program that accepts sequence of lines as input and prints the lines after making all characters in the sentence capitalized. Suppose the following input is supplied to the program: Hello world Practice makes perfect Then, the output should be: HELLO WORLD PRACTICE MAKES PERFECT
#### Solution
```python
lines = list()
i = 1
print("______Press Enter to Exit.______")
print("")
while True:
    user_input = input(f"Enter line number {i} : ")
    i += 1
    if user_input:
        lines.append(user_input.upper())
    else:
        break
for k in range(len(lines)):
    print(lines[k])
```
### Question 5:
Write a program that accepts a sequence of whitespace separated words as input and prints the words after removing all duplicate words and sorting them alphanumerically. Suppose the following input is supplied to the program: hello world and practice makes perfect and hello world again Then, the output should be: again and hello makes perfect practice world
#### Solution
```python
user_input = list(set(input('Enter a sequence of whitespace separated words : ').split(" ")))
print(' '.join(sorted(user_input)))
```
### Question 6:
Write a program which accepts a sequence of comma separated 4 digit binary numbers as its input and then check whether they are divisible by 5 or not. The numbers that are divisible by 5 are to be printed in a comma separated sequence. Example: 0100,0011,1010,1001 Then the output should be: 1010 Notes: Assume the data is input by console.
#### Solution
```python
user_input = [x for x in input("Enter a sequence of comma separated 4 digit binary numbers : ").split(",")]
result = list()
for element in user_input:
    if (int(element, 2)) % 5 == 0:
        result.append(element)
print(",".join(result))
```
### Question 7:
Write a program, which will find all such numbers between 1000 and 3000 (both included) such that each digit of the number is an even number. The numbers obtained should be printed in a comma-separated sequence on a single line.
#### Solution
```python
result = list()
for element in range(1000, 3001):
    to_string = str(element)
    if (int(to_string[0]) % 2 == 0 and int(to_string[1]) % 2 == 0 and int(to_string[2]) % 2 == 0 and int(to_string[3]) % 2 == 0):
        result.append(to_string)
print(",".join(result))
```
### Question 8:
Write a program that accepts a sentence and calculate the number of letters and digits. Suppose the following input is supplied to the program: hello world! 123 Then, the output should be: LETTERS 10 DIGITS 3
#### Solution
```python
user_input = input("Enter a sentence : ")
letter_length = 0
digit_length = 0
for character in user_input:
    if character.isdigit():
        digit_length += 1
    if character.isalpha():
        letter_length += 1
    else:
        pass
print(f"LETTERS : {letter_length}\nDIGITS : {digit_length}")
```
### Question 9:
Write a program that accepts a sentence and calculate the number of upper case letters and lower case letters. Suppose the following input is supplied to the program: Hello world! Then, the output should be: UPPER CASE 1 LOWER CASE 9
#### Solution
```python
user_input = input("Enter a sentence : ")
upper_letters = 0
lower_letters = 0
dict_result = {"upper_letters" : 0, "lower_letters" : 0}
for character in user_input:
    if character.isupper():
        dict_result["upper_letters"] += 1
    if character.islower():
        dict_result["lower_letters"] += 1
    else:
        pass
print(f"Uper case letters : {dict_result['upper_letters']}\nlower case letters : {dict_result['lower_letters']}")
```
### Question 10:
Write a program that computes the value of a+aa+aaa+aaaa with a given digit as the value of a. Suppose the following input is supplied to the program: 9 Then, the output should be: 11106
#### Solution
```python
user_input = input("Enter a Number (1-9) : ")
items_list = [user_input, user_input+user_input, user_input+user_input+user_input, user_input+user_input+user_input+user_input]
result = 0
for i in items_list:
    result += int(i)
print(result)
```
### Question 11:
Use a list comprehension to square each odd number in a list. The list is input by a sequence of comma-separated numbers. Suppose the following input is supplied to the program: 1,2,3,4,5,6,7,8,9 Then, the output should be: 1,3,5,7,9
#### Solution
```python
num_list = input("Enter a sequence of comma-separated numbers : ").split(",")
result = [x for x in num_list if int(x)%2==1]
print(",".join(result))
```
### Question 12:
Write a program that computes the net amount of a bank account based a transaction log from console input. The transaction log format is shown as following: D 100 W 200
D means deposit while W means withdrawal. Suppose the following input is supplied to the program: D 300 D 300 W 200 D 100 Then, the output should be: 500
#### Solution
```python
# Try : ===>> D 300 D 300 W 200 D 100
user_input = input().split(" ")
account_balance = 0
for i in range(0, len(user_input),2):
    if (user_input[i] == "D"):
        account_balance += int(user_input[i+1])
    elif (user_input[i] == "W"):
        account_balance -= int(user_input[i+1])
print(f"Your Account Balance : {account_balance}")
```
### Question 13:
A website requires the users to input username and password to register. Write a program to check the validity of password input by users. Following are the criteria for checking the password:

At least 1 letter between [a-z]
At least 1 number between [0-9]
At least 1 letter between [A-Z]
At least 1 character from [$#@]
Minimum length of transaction password: 6
Maximum length of transaction password: 12
Your program should accept a sequence of comma separated passwords and will check them according to the above criteria. Passwords that match the criteria are to be printed, each separated by a comma. Example If the following passwords are given as input to the program: ABd1234@1,a F1#,2w3E*,2We3345 Then, the output of the program should be: ABd1234@1
```python
# Almost Done
import re
user_input = input("Enter a sequence of comma separated passwords : ").split(",")
pattern = r"[a-zA-Z0-9]{6,12}" # here is the problem ====>> [$#@]
# m = r"^.*(?=.{8,})(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[@#$%^&+=]).*$"
for password in user_input:
    if re.search(pattern, password):
        print(password)
    else:
        pass
```
### Question 14:
You are required to write a program to sort the (name, age, height) tuples by ascending order where name is string, age and height are numbers. The tuples are input by console. The sort criteria is: 1: Sort based on name; 2: Then sort based on age; 3: Then sort by score. The priority is that name > age > score. If the following tuples are given as input to the program: Tom,19,80 John,20,90 Jony,17,91 Jony,17,93 Json,21,85 Then, the output of the program should be: [('John', '20', '90'), ('Jony', '17', '91'), ('Jony', '17', '93'), ('Json', '21', '85'), ('Tom', '19', '80')]
#### Solution
```python
result = list()
while True:
    user_input = input("Enter the (name, age, height) : ")
    if user_input:
        result.append(tuple(user_input.split(",")))
    else:
        break
print(sorted(result))
```
### Question 15:
Define a class with a generator which can iterate the numbers, which are divisible by 7, between a given range 0 and n.
- To learn more about Python Generators : - [Introduction To python Generators](https://realpython.com/introduction-to-python-generators/)
                                          - [Expert Python Tutorial #5 - Generators](https://www.youtube.com/watch?fbclid=IwAR0S5T8bCwG3T4hJ1vupogRUanhb917pVXDQY2rDu53j5EtY8Zb4MZeloSM&v=2eiFCQ-YAf4&feature=youtu.be)
#### Solution
```python
user_input = int(input("Enter a Number : "))
#using a Normal Python Generators
def generator(n):
    for i in range(n):
        if i % 7 == 0:
            yield i
# g = generator(user_input)
# for i in g:
#     print(i)
#using generator expression (also called a generator comprehension)
result = (x for x in range(user_input) if x % 7 == 0)
for i in result:
    print(i)
```
### Question 16:
A robot moves in a plane starting from the original point (0,0). The robot can move toward UP, DOWN, LEFT and RIGHT with a given steps. The trace of robot movement is shown as the following: UP 5 DOWN 3 LEFT 3 RIGHT 2, The numbers after the direction are steps. Please write a program to compute the distance from current position after a sequence of movement and original point. If the distance is a float, then just print the nearest integer. Example: If the following are given as input to the program: UP 5 DOWN 3 LEFT 3 RIGHT 2 Then, the output of the program should be: 2
#### Solution
```python
import math
up = int(input("UP : "))
down = int(input("DOWN : "))
left = int(input("LEFT : "))
right = int(input("RIGHT : "))
position = [right-left, up-down]
print(position)
print(round(math.sqrt(position[0]**2 + position[1]**2)))
```
### Question 17:
Write a program to compute the frequency of the words from the input. The output should output after sorting the key alphanumerically. Suppose the following input is supplied to the program: New to Python or choosing between Python 2 and Python 3? Read Python 2 or Python 3. Then, the output should be: 2:2 3.:1 3?:1 New:1 Python:5 Read:1 and:1 between:1 choosing:1 or:2 to:1
#### Solution
```python
user_input = input().split(" ")
dic = dict()
result = dict()
for item in user_input:
    frequency = user_input.count(item)
    dic[item] = frequency
sorted_keys = sorted(dic.keys())
for key in sorted_keys:
    result[key] = dic[key]
print(result)
```
### Question 18:
Write a method which can calculate square value of number
#### Solution
```python
def square(n):
    return n**2
value = int(input("Enter a Number : "))
print(square(value))
```
### Question 19:
Python has many built-in functions, and if you do not know how to use it, you can read document online or find some books. But Python has a built-in document function for every built-in functions.

Please write a program to print some Python built-in functions documents, such as abs(), int(), raw_input()

And add document for your own function Hints: The built-in document method is doc
#### Solution
```python
from pydoc import doc
print(doc(int()))
class FuncDoc:
    """
    hi there i hope you are doing great :D
    """
    result = 0
    def my_func():
        """
        this is my function, so please don't touch it again
        """
print(doc(FuncDoc()))
```
### Question 20:
Define a class, which have a class parameter and have a same instance parameter.
**Hints**: Define a instance parameter, need add it in init method You can init a object with construct parameter or set the value later
#### Solution
```python
class MyClass:
    #class parameter 
    number = 0
    def __init__(self, number):
        # instance parameter
        self.number = number
print(f"Class parameter : {MyClass.number}")
obj = MyClass(30)
print(f"Instance parameter : {obj.number}")
```
### Question 21:
Define a class, which have a class parameter and have a same instance parameter.
#### Solution 
```python
def sum_of_two_num(a, b):
    return a+b
print(sum_of_two_num(2, 4))
```
### Question 22:
Define a function that can convert a integer into a string and print it in console.
#### Solution
```python
def int_to_str(n):
    return str(n)
print(int_to_str(5)+"5")
print(type(int_to_str(3)))
```
### Question 23:
Define a function that can receive two integral numbers in string form and compute their sum and then print it in console.
#### Solution
```python
def sum_two_str(n, m):
    print(int(n) + int(m))
sum_two_str("5", "5")
```
### Question 24:
Define a function that can accept two strings as input and concatenate them and then print it in console.
#### Solution
```python
def concatenate_two_str(n, m):
    print(n+m)
str_1 = input("Enter first String : ")
str_2 = input("Enter second String : ")
concatenate_two_str(str_1, str_2)
```
### Question 25:
Define a function that can accept two strings as input and print the string with maximum length in console. If two strings have the same length, then the function should print all strings line by line.
#### Solution
```python
def max_length(n, m):
    if (len(n) > len(m)):
        print(n)
    elif (len(n) == len(m)):
        print(f'{n}\n{m}')
    else:
        print(m)
max_length('3000','50000')
```
### Question 26:
Define a function that can accept an integer number as input and print the "It is an even number" if the number is even, otherwise print "It is an odd number".
#### Solution
```python
def even_or_odd(n):
    if (n % 2 == 0):
        print("It's Even.")
    else:
        print("It's Odd.")
even_or_odd(4)
even_or_odd(5)
```
### Question 27:
Define a function which can print a dictionary where the keys are numbers between 1 and 3 (both included) and the values are square of keys.
#### Solution
```python
def square_dictionary():
    my_dictionary = {1:1, 2:4, 3:9}
    m = dict()
    for (key, value) in my_dictionary.items():
        print(f'{key} : {value}')
square_dictionary()
```
### Question 28:
Define a function which can print a dictionary where the keys are numbers between 1 and 20 (both included) and the values are square of keys.
#### Solution
```python
def square_dictionary():
    my_dictionary = dict()
    for element in range(1, 21):
        my_dictionary[element] = element**2
    for (key, value) in my_dictionary.items():
        print(f'{key} : {value}')
square_dictionary()
```
### Question 29:
Define a function which can generate a dictionary where the keys are numbers between 1 and 20 (both included) and the values are square of keys. The function should just print the values only.
#### Solution
```python
def square_dictionary():
	dictionary=dict()
	for key in range(1,21):
		dictionary[key] = key**2
	for (key,value) in dictionary.items():	
		print(value)
square_dictionary()
```
### Question 30:
Define a function which can generate and print a list where the values are square of numbers between 1 and 20 (both included).
#### Solution
``` python
def print_sqrt_number():
    result = []
    for i in range(1, 21):
        result.append(i**2)
    print(result)
print_sqrt_number()
```
### Question 31:
Define a function which can generate a list where the values are square of numbers between 1 and 20 (both included). Then the function needs to print the first 5 elements in the list.
#### Solution
```python
def print_sqrt_number():
    result = []
    for i in range(1, 21):
        result.append(i**2)
    print(result[:5])
print_sqrt_number()
```
### Question 32:
Define a function which can generate a list where the values are square of numbers between 1 and 20 (both included). Then the function needs to print the last 5 elements in the list.
#### Solution
```python
def print_sqrt_number():
    result = []
    for i in range(1, 21):
        result.append(i**2)
    print(result[-5:])
print_sqrt_number()
```
### Question 32:
Define a function which can generate a list where the values are square of numbers between 1 and 20 (both included). Then the function needs to print all values except the first 5 elements in the list.
#### Solution
```python
def print_sqrt_number():
    result = []
    for i in range(1, 21):
        result.append(i**2)
    print(result[5:])
print_sqrt_number()
```
### Question 33:
Define a function which can generate and print a tuple where the value are square of numbers between 1 and 20 (both included).
#### Solution
```python
def print_sqrt_number():
    result = []
    for i in range(1, 21):
        result.append(i**2)
    print(tuple(result))
print_sqrt_number()
```
### Question 34:
With a given tuple (1,2,3,4,5,6,7,8,9,10), write a program to print the first half values in one line and the last half values in one line.
#### Solution
```python
tpl = (1,2,3,4,5,6,7,8,9,10)
print(tpl[:5])
print(tpl[5:])
```
### Question 35:
Write a program which accepts a string as input to print "Yes" if the string is "yes" or "YES" or "Yes", otherwise print "No".
```python
user_input = input()
if user_input.lower() == "yes":
    print("Yes")
else:
    print("No")
```
