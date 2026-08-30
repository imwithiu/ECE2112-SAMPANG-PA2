# ECE-2112-PA-1

**Made by: Zechariah Sampang | 2ECE-C**

The content of this repository contains the Programming Assignment 1 for our course "Advance Computer Programming" this S.Y. 2026-2027. This project covers three python problems pertaining to Module 1 - Base Computing with Python.

# **A. Word Rotation Problem**

Create a function named `rotate_word()` that accepts a non-empty string. Move the first character of the string to the end while keeping all remaining characters in their original order. Preserve the capitalization of every character.

Example: `rotate_word("Code")` --> "odeC"

The following methods were used in this problem:
- `text[1:]` - a string slicing method that extracts all characters starting from index 1 through the end of the string. The colon `:` at the end of the index 0 signifies that it extracts through the end.
- `text[0]` - an initial character of the string that gets extracted.
- `+` - the string concatenation operator used to join the substring `text[1:]` and the extracted character of the string `text[0]`.


These combined methods effectively defined the function `rotate_word(text)` to move the initial character of the string to the end of the substring.
The final function for this problem is as follows;


```python
def rotate_word(text):
    return text[1:] + text[0]
```

# **B. Username Builder Program**

Create a function named `make_username()` that accepts two strings: first_name and last_name.
The function must:
1. convert all letters to lowercase;
2. remove all spaces from the first name;
3. remove all spaces from the last name; and
4. join the processed first and last names using one period (.).

Example
`make_username("Ana Maria", "De Leon")` --> "anamaria.deleon"

The following functions and methods were used in this problem:
- `.lower()` - A built-in string method that convert all letters to lowercase.
- `.replace(" ", "")` - A built-in string method that replaces all spaces in the strings with an empty string.
- `+ "." +` - the string concatenation operator used to combine the processed first name, a period, and the processed last name.
- Variable Assignment - a method that reassigns the modified string back to the variable.


Combining them all, the final function for this problem is as follows;


```python
def make_username(first_name, last_name):
    first_name = first_name.lower().replace(" ", "")
    last_name = last_name.lower().replace(" ", "")
    return first_name + "." + last_name
```


# **C. Bookend Swap Problem**

Create a function named swap_bookends() that accepts a list containing at least two elements. Unpack the list into three variables:
- first – the first element;
- middle – a list containing everything between the first and last elements; and
- last – the last element.
Using these variables, return a new list in which the first and last elements have exchanged positions.
The elements in middle must remain in their original order. Do not modify the input list.

Example
`swap_bookends([1, 2, 3, 4, 5, 6])` --> "[6, 2, 3, 4, 5, 1]"

The following functions and methods were used in this problem:
- `first, *middle, last = items`- An extended sequence unpacking used to extract the first element, the middle elements as a list, and the last element. Note that the asterisk `*` before the variable `middle` collects those middle elements into a single sublist.
- `last, *middle, first` - A list unpacking used to construct and return a new list with the swapped bookends.


Combining them all, the final function for this problem is as follows;


```python
def swap_bookends(items):
    first, *middle, last = items
    return [last, *middle, first]
```


Thank you for reading! 

To see the main python program for Programming Assignment 1, click this [link](https://github.com/imwithiu/SAMPANG-2ECE-C/blob/main/%5BSAMPANG%5D2ECE-C.ipynb) and download. Open on Jupyter Notebook, then run all cells.
