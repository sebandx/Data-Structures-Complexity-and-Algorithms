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
