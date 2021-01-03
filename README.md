# 100-Python-challenging-programming-exercises-for-Python-3.
100+ Python challenging programming exercises for Python 3 with Solutions
### Question 1:
Write a program that calculates and prints the value according to the given formula: Q = Square root of [(2 * C * D)/H] Following are the fixed values of C and H: C is 50. H is 30. D is the variable whose values should be input to your program in a comma-separated sequence. Example Let us assume the following comma separated input sequence is given to the program: 100,150,180 The output of the program should be: 18,22,24
##### Solution
```>>> python
import math
user_input = input("Enter a comma-separated sequence : ").split(",")
result = [str(math.floor(math.sqrt(((2*50*int(x))/30)))) for x in user_input]
print(','.join(result))
````
