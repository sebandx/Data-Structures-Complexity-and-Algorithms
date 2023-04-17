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
## Sets in Python 3
* Unordered collection with no duplicate elements
```python
example_set1 = {1, 2, 3}
singleton_set = {7}
empty_set = set() # this is because {} is reversed for a different feature in python 3.
```
* len(), min(), max(), repition, and conocotation can all be used with sets
* Lists and other iterable datatypes can also be converted to sets
Example:
```python
array = [1, 2, 3, 4]
set1 = set(array)
```
### Membership Operators
in and not in
Example:
```python
set1 = {1, 2, 3, 4}
print(1 in set1)
print(5 in set1)
```
Output:
True
False
* As a set is unordered, you cannot index or slice a set. However, a set is iterable.
### Sets - Adding and Removing Values
* .add() - adds element
* .remove() - removes element, will not raise error if it isn't found
* .discard() - removes element, will raise an error if it isn't found
* .pop() - removes element and returns the value. Not recommended
* .clear() - empties a set
Example:
```python
groups = ["lesserafilm", "txt", "new jeans"]
groups.add("g(i)dle")
groups.discard("lesserafilm")
groups.remove("mamooo") # no error
groups.discard("mamoo") # will raise error
groups.clear()
print(groups) # an empty set will output set()
```
Output: set()
## Set Operators
Union - combines 2 sets
```python
set1 = set('hello')
set2 = set('world')

result = set1 | set2
print(result)
```
Output: {'h', 'w', 'e', 'r', 'l', 'd', 'o'}
Intersection - members that only exist in both sets
```python
set1 = set('hello')
set2 = set('world')

result = set1 & set2
print(result)
```
Output: {'o', 'l'}
Difference - members that exist in first set but not second set
```python
set1 = set('hello')
set2 = set('world')

result1 = set1 - set2 # set1 difference set2
result2 = set2 - set1 # set2 difference set1

print('set1 - set2:', result1)
print('set2 - set1:', result2)
```
Output:
set1 - set2: {'e', 'h'}
set2 - set1: {'w', 'd', 'r'}

Symetric Difference - Members that exists one or the other set, but not both
```python
set1 = set('hello')
set2 = set('world')

result = set1 ^ set2 
```
Output:  {'e', 'h', 'w', 'd', 'r'}
Proper subset - boolean operator
* Returns true that A is a proper subset of B if all members of A is found in B, but A can't be identical to B
```python
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper subset of set2?:', set1 < set2) # < is the proper subset operator
print('Is set1 proper subset of set3?:', set1 < set3)
print('Is set1 proper subset of set4?:', set1 < set4)
```
Output:
Is set1 proper subset of set2?: True
Is set1 proper subset of set3?: False
Is set1 proper subset of set4?: False
Subset - Boolean Operator
* Same as proper subset, but A can be identical to B
```python
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 a subset of set2?:', set1 <= set2) # <= is the subset operator
print('Is set1 a subset of set3?:', set1 <= set3) # Notice the difference in value here
print('Is set1 a subset of set4?:', set1 <= set4)
```
Output: 
Is set1 a subset of set2?: True
Is set1 a subset of set3?: True
Is set1 a subset of set4?: False
Proper Superset - Boolean operator
* A is a proper superset of B if A has all the values of B and more, however they are not identical
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper superset of set2?:', set1 > set2) # > is the proper superset operator
print('Is set1 proper superset of set3?:', set1 > set3)
print('Is set1 proper superset of set4?:', set1 > set4)
```
Output:
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper superset of set2?:', set1 > set2) # > is the proper superset operator
print('Is set1 proper superset of set3?:', set1 > set3)
print('Is set1 proper superset of set4?:', set1 > set4)

Superset - Boolean Operator
* Same as superset. However A can be equal to B
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 superset of set2?:', set1 >= set2) # >= is the proper superset operator
print('Is set1 superset of set3?:', set1 >= set3)
print('Is set1 superset of set4?:', set1 >= set4)

```
Output:
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 superset of set2?:', set1 >= set2) # >= is the proper superset operator
print('Is set1 superset of set3?:', set1 >= set3)
print('Is set1 superset of set4?:', set1 >= set4)

Disjoint:
* Two sets are considered disjointed if they do not share a common value
* This can be checked using the isdisjoint() method
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 superset of set2?:', set1 >= set2) # >= is the proper superset operator
print('Is set1 superset of set3?:', set1 >= set3)
print('Is set1 superset of set4?:', set1 >= set4)

```
## Set Operators as Methods
```python
a = set('abracadabra')
b = set('alacazam')
a.union(b)
a.intersection(b)
a.difference(b)
a.symmetric_difference(b)
a.issubset(b)
a.issuperset(b)
# Their are no proper super / subset methods
r = a.copy()
```
### Assignment Operations
* Allows you to apply a set operator with an original and second set, and assign it to the original set 
```python
a = set('abracadabra')
b = set('alacazam')

a |= b # same as: a.update(b)
print('Union Update:', a)

# Intersection and Update --> Update the set, keeping only elements found in it and all others.
a = set('abracadabra')
b = set('alacazam')

a &= b # same as: a.intersection_update(b)
print('Intersection Update:', a)

# Difference and Update --> Update the set, removing elements found in others.
a = set('abracadabra')
b = set('alacazam')

a -= b # same as: a.difference_update(b)
print('Difference Update:', a)

# Symmetric Difference and Update --> Update the set, keeping only elements found in either set, but not in both.
a = set('abracadabra')
b = set('alacazam')

a ^= b # same as: a.symmetric_difference_update(b)
print('Symmeteric Difference Update:', a)
```
Output:
Union Update: {'b', 'a', 'z', 'r', 'l', 'm', 'd', 'c'}
Intersection Update: {'c', 'a'}
Difference Update: {'b', 'r', 'd'}
Symmeteric Difference Update: {'b', 'z', 'r', 'l', 'm', 'd'}
### Set Comprehension
* Sets support list comprehension as well
```python
def isPalindrome(x):
    ''' isPalindrome() returns True if string X is a palindrome '''
    return x == x[::-1]

nums = list(range(1,100))
palindromic_set = {num for num in nums if isPalindrome(str(num))}

print('Palindromic Numbers Set from 1 to 100:')
print(palindromic_set)
```
Output:
{1, 2, 3, 4, 5, 6, 7, 8, 9, 33, 11, 44, 66, 77, 99, 22, 55, 88}
Note that the output is in no particular order
## Dictionary in Python 3
* Data type that stores collection of key value pairs, such that each possible key appears at most once in the collection. 
Dictionary Operators
* Adding a pair
* Removing a pair
* Modifying a existing pair
* Lookup of an value associated with a key
* Dictionaries are defined using {}
* Each item in the dictionary is a key value pair
Example
```python
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}
```
### Keys
* Unique adresses for a dictionary value's location
* Must be immutable
* Must be unique
     * If a new pair is initialized with the existing key, it supercides the previous declaration
### Values
* Can be any data-type
### Updating a Dictionary
* Modify existing value by refrencing key
* Add new values by creating new key
* Overwrite existing value by refrencing key and reassigning value
Example:
```python
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy['followers'] += 10 # We are adding 10 to the value located at key: 'followers'
sammy['verified'] = True # We added a new value at a new key: 'verified'
sammy['username'] = 'SammySammy'

print('Sammy Dict:', sammy)
```
### Deletion With Dictionaries
* We can delete the key and susequently delete the value
* Empty a entire dictionary
* Delete the dictionary
```python
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

del sammy['followers'] # del is a keyword used to help us to execute a removal
print('followers key deleted:', sammy)

sammy.clear() # {} is considered an empty dict
print('emptying out a dictionary', sammy)
print('--\n\n')

del sammy
```
Output:
followers key deleted: {'username': 'sammy', 'online': True}
emptying out a dictionary {}
NameError: name 'sammy' is not defined
### Membership operators can be used to check membership
in and not in operators can be used to check if key is a member of a dictionary
### Built in Functions
* len() 
* max() 
* min() 
* str() 
* list()
Example:
```python
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

print('Dict to string:', str(sammy))
print('Dict to list:', list(sammy))
```
Output:
Dict to string: {'username': 'sammy', 'online': True, 'followers': 42}
Dict to list: ['username', 'online', 'followers']
### Duplicate a Dictionary and Copy Keys Only
``` python
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy_copy1 = sammy.copy()
sammy_copy2 = sammy

sammy['verified'] = True

print('sammy_copy1:', sammy_copy1)
print('sammy_copy2:', sammy_copy2)
print('--')

# Duplicate keys only

tammy = tammy.fromkeys(sammy) # Notice that all key's values are None ... aka empty

print('tammy dict:', tammy)
```
Output:
sammy_copy1: {'username': 'sammy', 'online': True, 'followers': 42}
sammy_copy2: {'username': 'sammy', 'online': True, 'followers': 42, 'verified': True}
tammy dict: {'username': None, 'online': None, 'followers': None, 'verified': None}
### Dictionary Methods
* A.keys() –> Returns a sequence of keys/addresses in A
* A.values() –> Returns a sequence of item values in A
* A.items() –> Returns a sequence of key,item pairs in A
* A.get(address) –> Returns the item value at address
* A.update(B) –> Extends A with the dictionary of key,value pairs of B
### Iterating through a dictionary
There are 3 iterations methods
1. Iterating keys
2. Iterating values
3. Iterating key value pairs then upacking
Example:
```python
# Iteration Example 1: Keys
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

for k in sammy.keys():
    print('Current key:', k)
print('--\n')

# Iteration Example 2: Values

for v in sammy.values():
    print('Current value:', v)
print('--\n')

# Iteration Example 3: Key, Value Pair

for k, v in sammy.items():
    print('Current Key:', k)
    print('Current Value:', v)
    print()
```
### dict() Constrcutor Dictionary Comprehension
We can turn other data types to dictionaries.
Also similar to lists, tuples, and sets, dictionaries also support comprehension.
Note:
We must specify where the keys are and where the values.
```python
# dict() Example

example_data = [
    ('one', 3),
    ('two', 3),
    ('three', 5)
]

data_dict = dict(example_data)
print('data_dict:', data_dict)
print('--')

# Dictionary Comprehension
# Goal: Take string numerals and assign them with their integer square
# - keys : string numerals
# - values: integer squares

example_data2 = ['1', '2', '3', '4', '5']

data2_dict = {x : int(x)**2 for x in example_data2}

print('data2_dict:', data2_dict)
```
Output:
data_dict: {'one': 3, 'two': 3, 'three': 5}
data2_dict: {'1': 1, '2': 4, '3': 9, '4': 16, '5': 25}
