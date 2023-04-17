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
