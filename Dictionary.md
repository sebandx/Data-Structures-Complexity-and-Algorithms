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
