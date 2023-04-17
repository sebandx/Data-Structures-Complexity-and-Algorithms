## Tuples in Python 3
Tuples are a basic iterable data type that is...
* Immutable
* Allow different datatypes as items
* Iterable
* Nestable
### How to use Tuples in Python 3
* Declared using round brackets
* (50,) is a singleton tuple, the comma is required
* Tuples are sliceable
### Tuple Operators
* Concatenation: Joining two tuples
* Repition: Repeating a tuple multiple times
* Membership: Checking if a value exists in a tuple
```python
# Concatenation
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print('a+b:', concat_result)

# Repetition
c = ('Hi!',)
repet_result = c * 3
print('c*3', repet_result)

# Membership
d = a + b + c
print('d:', d)
print('\'Hi!\' in d:', 'Hi!' in d)
print('7 in d:', 7 in d)
```
Tuples are also iterable, indexable, and slicable
Built in functions with tuples:
* len() - length of tuple
* min() - minimum value in tuple
* max() - maximum value in tuple
* tuple() - converts sequence to tuple
### Tuple Comprehension
```python
even_tup = tuple(i for i in range(1,21) if i % 2 == 0)
print(even_tup)
```
Output: (2, 4, 6, 8, 10, 12, 14, 16, 18, 20)
### Tuple & Python: Packing and Unpacking
```python
var_1 = 2
var_2 = 3
var_3 = 5

# Example of packing. Creates tuple by combining multiple values.
prime = var_1, var_2, var_3

print('Packed prime values:', prime)

fib = (0, 1, 1, 2, 3, 5, 8)
Example of unpacking fib[0] and fib[1] to assign values to variables. Repacks remaining values into new tuple for later use.
fib_0, fib_1, fib_n = fib[0], fib[1], fib[2:]
print('fib_0:', fib_0)
print('fib_1:', fib_1)
print('fib_n:', fib_n)
```
Output: 
Packed prime values: (2, 3, 5)
fib_0: 0
fib_1: 1
fib_n: (1, 2, 3, 5, 8)
Useful when combined with variable arguments for function definition and function calls
