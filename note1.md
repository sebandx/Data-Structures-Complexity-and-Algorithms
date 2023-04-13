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
Looking at the Previous Code:
* i**2 for i in range(10) --> is the expression that describe the list
* i**2 describes each item in the list
* i is taken from the for clause
* or i in range(10) describes where i comes from
