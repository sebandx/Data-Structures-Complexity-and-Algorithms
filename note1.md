# Data Structure Notes
---
## Matrices in Python 3
* In mathematics, a matrix is a representation of numbers, symbols, or expressions in a 2D Array.
* In Python, their is no Matrix data structure. Instead, we use a 2D list with the rules of a normal matrix
    * All rows must have the same number of values
    * All items in the 2D list must have the same data type

Example:
```python
matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]
```
## List Comprehension Pythn 3
* A concise method to create a list in Python 3
List Comprehension is Typically Used When:
* List is result of some operation applied to all the terms
* Made from another sequence/iterable data
* List is a member of another list/sequence/iteraBle data that satisfies some condition
If so, we can use a Lambda Functions, however we will learn another method
Old Method:
```python
squares = []
for i in range(10):
    squares.append(i ** 2)

print('Our result: %s' % squares)

# Our result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
List Comprehension
```python
squares = [i**2 for i in range(10)]

print('Our new result: %s' % squares)
# Our new result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
List Comprehension Contains:
* Square Bracket containing an expression that descirbes the list
* One or more For clauses to explain its members
* A zero or more if clauses depending on the complexity of the list
### Example 1:
```i**2 for i in range(10)```
* ```i**2``` describes each item in the list
* ```for i in range(10)``` describes where i comes from
### Example 2:
```python
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result)
```
* ```[x,y]``` describes each item of the list
* '''for x in a for y in b''' means that it will loop through all the values in a
* and for every value in a it will loop through all the values in b
* and add them to the list as long as x != y\
Output:
```[[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]```

### Example 3:
```python
vec = [[1,2,3], [4,5,6], [7,8,9]]

result = [value for row in vec for value in row]
print('Vec as a single list of values: %s' % result)
```
* value describes each item in the list
* ```for row in vec``` iterates through every item in the vec
* ```for value in row``` iterates through every in row and describes what value is

Output: ```Vec as a single list of values: [1, 2, 3, 4, 5, 6, 7, 8, 9]```
## Map Function In Python 3
The map function applies a function all items in a iterable datatype
Format
```map(function_name, sequence)```
```python
def square(num):
    ''' squares the given num argument '''
    return num ** 2
# end of square

array = list(range(1,11))
square_array = list(map(square, array))

print('Original Array:', array)
print('Array Squared:', square_array)
```
Output:
Original Array: ```[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]```
Array Squared: ```[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]```
Note: the map function is that it doesn’t return a specific data type, but an python iterable data. This means after applying the map function, we just execute a list function on it.
* You shouldn't use map function for every minor change you want to do to a string
* Typically you shouldn't use methods with map as their likely is already method which performs the same function
## Filter Function
The filter function is to filter out items from a data set that meets a certain condition.
Format:
```filter(bool_returning_function, sequence)```
* The function needs to return a boolean value, and take in the values of the list as arguments
* The sequence can be any iterable datatype
```python
def isOdd(x):
    ''' isOdd() returns True if x is odd.'''
    return x % 2 != 0

array = list(range(1,21))
odds = list(filter(isOdd, array))

print('Odd Numbers from 1 to 20:', odds)
```
Output: 
```Odd Numbers from 1 to 20: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]```
### Example - List of Palindromes
```
def isPalindrome(x):
    ''' isPalindrome returns True if string X is a palindrome.'''
    return x == x[::-1]

array = list(range(1,10000))

palindromic_numbers = list(map(int, filter(isPalindrome, map(str, array))))
print('Palindromic Numbers from 1 to 10,000', palindromicNumbers)
```
Code Analysis
* ```map(str, array)``` converts all the numbers in the array into string value so the isPalindrome function can be used
* ```filter(isPalindrome, map(str, array))``` filters out all the values which are not palidromes
* ```map(int, filter(isPalindrome, map(str, array)))``` converts the string values back into int values
* ```list(map(int, filter(isPalindrome, map(str, array))))``` converts the iterable data into a list
