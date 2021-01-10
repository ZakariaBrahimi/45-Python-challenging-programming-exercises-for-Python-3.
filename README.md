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
