# Tuples in Python 3
---
## What are Tuples?
Tuples are an iterable data type in Python. Tuples are...
* Immutable
* Allow different data types as items
* Nestable
## How to use Tuples
* Declared using round brackets
* (50,) is a singleton tuple, the comma is required
## Tuple Operators
* Concatenation: Joining two tuples
* Repetition: Repeating a tuple multiple times
* Membership: Checking if a value exists in a tuple
* Tuples are sliceable, iterable, and indexable

```python
# Concatenation
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print(concat_result)

# Repetition
c = ('Hi!',)
repet_result = c * 3
print(repet_result)

# Membership
d = a + b + c
print(d)
print('Hi!' in d)
print(7 in d)
```
Output:
```python
(1, 2, 3, 4, 5, 6)
('Hi!', 'Hi!', 'Hi!')
(1, 2, 3, 4, 5, 6, 'Hi!')
True
False
```
Built in functions:
* len() - length of tuple
* min() - minimum value in tuple
* max() - maximum value in tuple
* tuple() - converts sequence to tuple
## Tuple Comprehension
```python
even_tup = tuple(i for i in range(1,21) if i % 2 == 0)
print(even_tup)
```
Output: (2, 4, 6, 8, 10, 12, 14, 16, 18, 20)
## Packing and Unpacking
```python
var_1 = 2
var_2 = 3
var_3 = 5

# Example of packing. Creates tuple by combining multiple values.
prime = var_1, var_2, var_3

print(prime)

fib = (0, 1, 1, 2, 3, 5, 8)
# Example of unpacking fib[0] and fib[1] to assign values to variables. 
# Repacks remaining values into new tuples for later use.
fib_0, fib_1, fib_n = fib[0], fib[1], fib[2:]
print(fib_0)
print(fib_1)
print(fib_n)
```
Output: 
```python
(2, 3, 5)
0
1
(1, 2, 3, 5, 8)
```
Packing and unpacking can be useful when combined with variable arguments for function definition and function calls



