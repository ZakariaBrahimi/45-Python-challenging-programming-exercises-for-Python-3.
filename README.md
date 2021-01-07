# 100-Python-challenging-programming-exercises-for-Python-3.
100+ Python challenging programming exercises for Python 3 with Solutions
### Question 1:
Write a program that calculates and prints the value according to the given formula: Q = Square root of [(2 * C * D)/H] Following are the fixed values of C and H: C is 50. H is 30. D is the variable whose values should be input to your program in a comma-separated sequence. Example Let us assume the following comma separated input sequence is given to the program: 100,150,180 The output of the program should be: 18,22,24
##### Solution
```python
>>>import math
user_input = input("Enter a comma-separated sequence : ").split(",")
result = [str(math.round(math.sqrt(((2*50*float(x))/30)))) for x in user_input]
print(','.join(result))
````
### Question 2:
Write a program which takes 2 digits, X,Y as input and generates a 2-dimensional array. The element value in the i-th row and j-th column of the array should be i*j. Note: i=0,1.., X-1; j=0,1,¡­Y-1. Example Suppose the following inputs are given to the program: 3,5 Then, the output of the program should be: [[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8]]
##### Solution
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
##### Solution
```python
user_input = input("Enter a comma separated sequence of words : ").split(",")
user_input.sort()
print(",".join(user_input))
```
### Question 4:
Question£º Write a program that accepts sequence of lines as input and prints the lines after making all characters in the sentence capitalized. Suppose the following input is supplied to the program: Hello world Practice makes perfect Then, the output should be: HELLO WORLD PRACTICE MAKES PERFECT
##### Solution
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
