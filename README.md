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
'''python
raww = int(input("Enter The First Number : "))
column = int(input("Enter The second Number : "))
multilist = [[0 for col in range(column)] for raw in range(raww)]
for i in range(raww):
    for j in range(column):
        multilist[i][j] = i*j
print(multilist)

'''
