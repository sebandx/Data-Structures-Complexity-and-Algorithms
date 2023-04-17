# Matrices & List Comprehension 
---
## Matrices in Python 3
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
## List Comprehension Python 3
It is a concise method to create a list. It is typically used when the list is...
* The result of an operation applied to all the terms
* Made from another sequence
* A member of another sequence that satisfies a certain condition
**Example 1:**
```python
squares = [i**2 for i in range(10)]

print(squares)
```
Output:
```[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]```

List Comprehension Contains:
1. Square Bracket containing an expression that descirbes the list
2. One or more for clause(s) to explain its members
3. Zero or more if clause(s) depending on the complexity of the list
Explaination:
* ```i**2``` describes the operation preformed on each i value
* ```for i in range(10)``` describes where i comes from

**Example 2:**
```python
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result)
```
Output:
```[[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]```
* ```[x,y]``` describes each item of the list
* ```for x in a for y in b``` 
     * Loops through all the values in a
     * Then for every value in a it will loop through all the values in b
* ```x != y``` adds them to the list as long as x isn't equal to y

**Example 3:**
```python
vec = [[1,2,3], [4,5,6], [7,8,9]]

result = [value for row in vec for value in row]
print(result)
```
* value describes each item in the list
* ```for row in vec``` iterates through every item in the vec
* ```for value in row``` for every item in vec it iterates through every value in row
     * It also describes where value comes from

Output: 
```[1, 2, 3, 4, 5, 6, 7, 8, 9]```
