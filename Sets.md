# Sets in Python 3
---
* Sets are an unordered collection of items with no duplicates
* Sets are can instantly check if a element exists in the set or not
```python
example_set1 = {1, 2, 3}
singleton_set = {7}
empty_set = set() # this is because {} is reversed for dictionaries Python 3.
```
* len(), min(), max(), repition, and conocotation can all be used with sets
* You can convert iterable datatypes to sets
## Membership Operators
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
## Sets - Adding and Removing Values
* .add() - adds element
* .remove() - removes element, will not raise error if it isn't found
* .discard() - removes element, will raise an error if it isn't found
* .pop() - removes element and returns the value. Not recommended
* .clear() - empties a set
Note:
```python
groups = ["lesserafilm", "txt", "new jeans"]
groups.clear()
print(groups)
```
Output: ```set()```
## Set Operators
**Union** - combines 2 sets ('|' symbol)
```python
set1 = set('hello')
set2 = set('world')

result = set1 | set2
print(result)
```
Output: {'h', 'w', 'e', 'r', 'l', 'd', 'o'}
* Note as a set cannot contain duplicates, any duplicate letters will be removed when merging the sets
**Intersection** - members that only exist in both sets ('&' symbol)
```python
set1 = set('hello')
set2 = set('world')

result = set1 & set2
print(result)
```
Output: {'o', 'l'}
**Difference** - members that exist in **the first set** but not the **second set**
```python
set1 = set('hello')
set2 = set('world')

result1 = set1 - set2 
result2 = set2 - set1 #

print(result1)
print(result2)
```
Output:
```python
{'e', 'h'}
{'w', 'd', 'r'}
```

**Symetric Difference** - Members that exists one or the other set, but not both ('^' symbol)
```python
set1 = set('hello')
set2 = set('world')

result = set1 ^ set2 
print(result)
```
Output:  {'e', 'h', 'w', 'd', 'r'}
Proper subset - boolean operator ('<' symbol)
* Returns true that A is a proper subset of B if all members of A is found in B, but **A can't be identical to B**
```python
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print(set1 < set2)
print(set1 < set3)
print(set1 < set4)
```
Output:
```python
True
False
False
```
**Subset** - Boolean Operator ('<=' symbol)
* Same as proper subset, but **A can be identical to B**
```python
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print(set1 <= set2) 
print(set1 <= set3) 
print(set1 <= set4)
```
Output: 
```python
True
True
False
```
**Proper Superset** - Boolean operator ('>' symbol)
* A is a proper superset of B if A has all the values of B **and more**, however **they are not identical**
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print(set1 > set2)
print(set1 > set3)
print(set1 > set4)
```
Output:
```python
False
True
False
```
**Superset** - Boolean Operator ('>=' symbol)
* Same as superset. However **A can equal to B**
```python
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print(set1 >= set2)
print(set1 >= set3)
print(set1 >= set4)
```
Output:
```python
True
True
False
```
## Disjoint:
* Two sets are considered disjointed if they do not share a common value
* This can be checked using the isdisjoint() method
```python
set1 = {1,2,3,4}
set2 = {5,6,7}
set3 = {1,2,3,4,5}

print(set1.isdisjoint(set2))
print(set2.isdisjoint(set3))
```
Output:
```python
True
False
```
## Set Operators as Methods
* .union()
* .interesection()
* .difference()
* .symmetric_difference()
* .issubset()
* .issuperset()
* .copy()
* Their are no proper super / subset methods
* The reasons we have set methods and opertaors is because methods can mutate / add on to the set, while opertaors generate new set
## Assignment Operations
* Performs the set operation and assigns the result o the left operand
* These are the same as set operators as methods
```python
a = set('abracadabra')
b = set('alacazam')

a |= b 
print('Union Update:', a)

a = set('abracadabra')
b = set('alacazam')

a &= b 
print('Intersection Update:', a)

a = set('abracadabra')
b = set('alacazam')

a -= b # same as: a.difference_update(b)
print('Difference Update:', a)

a = set('abracadabra')
b = set('alacazam')

a ^= b # same as: a.symmetric_difference_update(b)
print('Symmeteric Difference Update:', a)
```
Output:
```python
Union Update: {'b', 'a', 'z', 'r', 'l', 'm', 'd', 'c'}
Intersection Update: {'c', 'a'}
Difference Update: {'b', 'r', 'd'}
Symmeteric Difference Update: {'b', 'z', 'r', 'l', 'm', 'd'}
```
## Set Comprehension
* Sets support list comprehension as well
```python
def isPalindrome(x):
    return x == x[::-1]

nums = list(range(1,100))
palindromic_set = {num for num in nums if isPalindrome(str(num))}

print(palindromic_set)
```
Output:
{1, 2, 3, 4, 5, 6, 7, 8, 9, 33, 11, 44, 66, 77, 99, 22, 55, 88}
