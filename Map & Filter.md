# Map & Filter
---
## Map Function
The map function applies a function all items in a iterable data type
Example:
```python
def square(num):
    return num ** 2

array = list(range(1,11))
square_array = list(map(square, array))

print(array)
print(square_array)
```
Output:
```python
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
Note 1:    
   * The map function doesn’t return a specific data type
   * It returns a python iterable data. 
   * After applying the map function, you need to apply a list function to it to convert it back to a list.

Note 2:   
   * You shouldn't use map function for every minor change you want to do to a string
   * Typically you shouldn't use methods with map as their likely is already method which performs the same function
## Filter Function
Used to filter out items from a data set that meets a certain condition.

Format: filter(bool_returning_function, sequence)
* The first parameter is a function
     * Needs to return a boolean value, and take in the values of the list as arguments
* The second parameter can be any iterable datatype

**Example 1**
```python
def isOdd(x):
    return x % 2 != 0

array = list(range(1,21))
odds = list(filter(isOdd, array))

print(odds)
```
Output: 
```[1, 3, 5, 7, 9, 11, 13, 15, 17, 19]```

**Example 2**
```
def isPalindrome(x):
    return x == x[::-1]

array = list(range(1,100))

palindromic_numbers = list(map(int, filter(isPalindrome, map(str, array))))
print(palindromic_numbers)
```
Output: ```[1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 22, 33, 44, 55, 66, 77, 88, 99]```

Analysis:
* ```map(str, array)``` -> converts all the numbers in the array into string value so the isPalindrome function can be used
* ```filter(isPalindrome, map(str, array))``` -> filters out all the values which are not palindromes using the isPalindrome function
* ```map(int, filter(isPalindrome, map(str, array)))``` -> converts the string values back into int values
* ```list(map(int, filter(isPalindrome, map(str, array))))``` -> converts the iterable data into a list
