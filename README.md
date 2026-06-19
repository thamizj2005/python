# 🐍 Python Complete Revision Guide

> A single-file reference covering Fundamentals → Advanced Python.
> Every topic includes: **Definition**, **Syntax**, **3 worked examples with output**, and **⚠️ Beginner Mistakes to Avoid**.
> Built for fast revision before interviews — search (Ctrl+F) the topic name when you need it.

---

## 📑 Table of Contents

1. [Python Fundamentals](#1-python-fundamentals)
   - 1.1 [Variables](#11-variables)
   - 1.2 [Input / Output](#12-input--output)
   - 1.3 [Type Casting](#13-type-casting)
   - 1.4 [Data Types](#14-data-types)
   - 1.5 [Operators](#15-operators)
2. [Control Flow](#2-control-flow)
   - 2.1 [if / if-else / if-elif-else / Nested if](#21-if--if-else--if-elif-else--nested-if)
   - 2.2 [for loop & range()](#22-for-loop--range)
   - 2.3 [while loop](#23-while-loop)
   - 2.4 [break & continue](#24-break--continue)
3. [Strings](#3-strings)
   - 3.1 [Indexing & Slicing](#31-indexing--slicing)
   - 3.2 [String Methods](#32-string-methods)
   - 3.3 [String Programs (Reverse, Palindrome, Vowel/Consonant)](#33-string-programs)
4. [Collections](#4-collections)
   - 4.1 [Lists](#41-lists)
   - 4.2 [Nested Lists & List Traversal](#42-nested-lists--list-traversal)
   - 4.3 [Tuples](#43-tuples)
   - 4.4 [Sets](#44-sets)
   - 4.5 [Dictionaries](#45-dictionaries)
   - 4.6 [Nested Dictionary](#46-nested-dictionary)
5. [Functions](#5-functions)
   - 5.1 [Function Basics](#51-function-basics)
   - 5.2 [*args and **kwargs](#52-args-and-kwargs)
6. [Modules](#6-modules)
   - 6.1 [import / from-import / Creating Modules](#61-import--from-import--creating-modules)
7. [File Handling](#7-file-handling)
   - 7.1 [open(), Modes, read/write, with open()](#71-open-modes-readwrite-with-open)
8. [Exception Handling](#8-exception-handling)
   - 8.1 [try / except / finally](#81-try--except--finally)
9. [OOP (Object-Oriented Programming)](#9-oop)
   - 9.1 [Core OOP](#91-core-oop)
   - 9.2 [Inheritance](#92-inheritance)
   - 9.3 [Encapsulation](#93-encapsulation)
   - 9.4 [Polymorphism](#94-polymorphism)
   - 9.5 [Abstraction](#95-abstraction)
   - 9.6 [Advanced OOP](#96-advanced-oop)
   - 9.7 [Decorators](#97-decorators)
   - 9.8 [Property (@property / @setter)](#98-property)
10. [JSON](#10-json)
    - 10.1 [JSON Basics, dumps/loads, dump/load, Nested, Pretty Print](#101-json-basics)
11. [Pythonic Features](#11-pythonic-features)
    - 11.1 [List Comprehension](#111-list-comprehension)
    - 11.2 [Dictionary Comprehension](#112-dictionary-comprehension)
    - 11.3 [Lambda](#113-lambda)
    - 11.4 [map() & filter()](#114-map--filter)
    - 11.5 [zip() & enumerate()](#115-zip--enumerate)
12. [Advanced Python](#12-advanced-python)
    - 12.1 [Generators](#121-generators)
    - 12.2 [Iterators](#122-iterators)

---

## 1. Python Fundamentals

### 1.1 Variables

**Definition:**
A variable is a named reference to a value stored in memory. Python is dynamically typed — you don't declare a type; it's inferred from the value assigned.

**Syntax:**
```python
variable_name = value
```

**Example 1 — Basic assignment**
```python
name = "Thamizh"
age = 23
print(name)
print(age)
```
**Output:**
```
Thamizh
23
```

**Example 2 — Multiple assignment in one line**
```python
a, b, c = 10, 20, 30
print(a, b, c)
```
**Output:**
```
10 20 30
```

**Example 3 — Dynamic typing (reassigning a variable to a different type)**
```python
x = 5
print(type(x))
x = "now a string"
print(type(x))
```
**Output:**
```
<class 'int'>
<class 'str'>
```

**⚠️ Beginner Mistakes to Avoid**
- Using Python keywords as variable names (`class = 5`) → `SyntaxError`.
- Starting a variable name with a digit (`1value = 10`) → `SyntaxError`.
- Confusing `=` (assignment) with `==` (comparison).
- Forgetting variable names are case-sensitive (`Name` and `name` are different variables).

---

### 1.2 Input / Output

**Definition:**
`input()` reads a line of text typed by the user and **always returns a string**. `print()` writes output to the console, with optional `sep` and `end` formatting.

**Syntax:**
```python
variable = input("Prompt text: ")
print(value1, value2, sep=" ", end="\n")
```

**Example 1 — Basic input and output**
```python
name = input("Enter your name: ")
print("Hello,", name)
```
**Output (when user types `Thamizh`):**
```
Enter your name: Thamizh
Hello, Thamizh
```

**Example 2 — input() always returns a string**
```python
age = input("Enter age: ")
print(type(age))
print(age + "5")   # string concatenation, not addition
```
**Output (when user types `23`):**
```
Enter age: 23
<class 'str'>
235
```

**Example 3 — Controlling print() formatting**
```python
print("Python", "AI", "CV", sep=" | ", end=" -- Done\n")
print("Next line starts here")
```
**Output:**
```
Python | AI | CV -- Done
Next line starts here
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `input()` returns a string and trying `input() + 5` directly → `TypeError`.
- Not converting numeric input using `int()`/`float()` before doing math.
- Assuming `print()`'s `end` parameter is empty by default — it's actually `"\n"`.

---

### 1.3 Type Casting

**Definition:**
Type casting is converting a value from one data type to another using functions like `int()`, `float()`, `str()`, `bool()`.

**Syntax:**
```python
int(x)
float(x)
str(x)
bool(x)
```

**Example 1 — String to int and back**
```python
a = "100"
b = int(a)
print(b + 50)
print(type(b))
```
**Output:**
```
150
<class 'int'>
```

**Example 2 — Casting in real calculations**
```python
price = "499.99"
price_f = float(price)
print(price_f * 2)

num = 42
print("Value: " + str(num))
```
**Output:**
```
999.98
Value: 42
```

**Example 3 — bool() casting rules**
```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("hello"))
print(bool("False"))   # tricky!
```
**Output:**
```
False
True
False
True
True
```

**⚠️ Beginner Mistakes to Avoid**
- Calling `int("12.5")` directly → `ValueError` (must cast to `float` first, then `int`).
- Assuming `bool("False")` is `False` — any **non-empty string** is truthy, including the text `"False"`.
- Forgetting casting creates a **new value**; the original variable doesn't change unless reassigned.

---

### 1.4 Data Types

**Definition:**
Python's core built-in types: `int` (whole numbers), `float` (decimals), `str` (text), `bool` (True/False).

**Syntax:**
```python
x = 10        # int
y = 10.5      # float
s = "hello"   # str
flag = True   # bool
```

**Example 1 — Checking types**
```python
a = 10
b = 3.14
c = "Python"
d = True
print(type(a), type(b), type(c), type(d))
```
**Output:**
```
<class 'int'> <class 'float'> <class 'str'> <class 'bool'>
```

**Example 2 — Division behavior between int and float**
```python
x = 7
y = 2.0
print(x / y)
print(x // y)
```
**Output:**
```
3.5
3.0
```

**Example 3 — bool is a subclass of int**
```python
print(True + True)
print(False * 10)
print(isinstance(True, int))
```
**Output:**
```
2
0
True
```

**⚠️ Beginner Mistakes to Avoid**
- Confusing `/` (true division → always float) with `//` (floor division → rounds down).
- Forgetting strings are **immutable**: `s[0] = 'P'` raises `TypeError`.
- Thinking `bool` is unrelated to `int` — it is actually a subclass, so `True == 1` is `True`.

---

### 1.5 Operators

**Definition:**
- **Arithmetic:** `+ - * / // % **`
- **Comparison:** `== != > < >= <=`
- **Logical:** `and or not`
- **Assignment:** `= += -= *= /= //= %= **=`

**Syntax:**
```python
result = a + b
result = a == b
result = a and b
a += 1
```

**Example 1 — Arithmetic operators**
```python
a, b = 10, 3
print(a + b, a - b, a * b)
print(a / b, a // b, a % b, a ** b)
```
**Output:**
```
13 7 30
3.3333333333333335 3 1 1000
```

**Example 2 — Comparison and logical operators**
```python
x, y = 5, 10
print(x < y and y > 0)
print(x > y or y > 0)
print(not (x == y))
```
**Output:**
```
True
True
True
```

**Example 3 — Assignment (compound) operators**
```python
count = 5
count += 3
print(count)
count *= 2
print(count)
count //= 4
print(count)
```
**Output:**
```
8
16
4
```

**⚠️ Beginner Mistakes to Avoid**
- Using `=` instead of `==` inside an `if` condition → `SyntaxError` in Python (good — it protects you).
- Forgetting operator precedence: `not` > `and` > `or`.
- Confusing `%` (remainder) with `//` (quotient rounded down) — they answer different questions.

---

## 2. Control Flow

### 2.1 if / if-else / if-elif-else / Nested if

**Definition:**
Conditional statements let a program choose different paths based on whether a condition is `True` or `False`. `elif` checks multiple conditions in sequence; nested `if` places one `if` block inside another.

**Syntax:**
```python
if condition:
    # code
elif another_condition:
    # code
else:
    # code
```

**Example 1 — Simple if-else**
```python
age = 20
if age >= 18:
    print("Eligible to vote")
else:
    print("Not eligible")
```
**Output:**
```
Eligible to vote
```

**Example 2 — if-elif-else (grading system)**
```python
marks = 76
if marks >= 90:
    grade = "A"
elif marks >= 75:
    grade = "B"
elif marks >= 60:
    grade = "C"
else:
    grade = "D"
print("Grade:", grade)
```
**Output:**
```
Grade: B
```

**Example 3 — Nested if (login + role check)**
```python
is_logged_in = True
role = "admin"

if is_logged_in:
    if role == "admin":
        print("Welcome, Admin Dashboard")
    else:
        print("Welcome, User Dashboard")
else:
    print("Please log in")
```
**Output:**
```
Welcome, Admin Dashboard
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting the colon `:` at the end of `if`/`elif`/`else` → `SyntaxError`.
- Inconsistent indentation (mixing tabs and spaces) → `IndentationError`.
- Writing `elif` as `else if` (that's not valid Python syntax).
- Over-nesting `if` statements when `elif` or `and`/`or` would be cleaner.

---

### 2.2 for loop & range()

**Definition:**
A `for` loop iterates over a sequence (list, string, range, etc.). `range(start, stop, step)` generates a sequence of numbers, commonly used to control loop iterations.

**Syntax:**
```python
for item in sequence:
    # code

for i in range(start, stop, step):
    # code
```

**Example 1 — Looping through a list**
```python
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)
```
**Output:**
```
apple
banana
mango
```

**Example 2 — range() with start, stop, step**
```python
for i in range(2, 11, 2):
    print(i, end=" ")
```
**Output:**
```
2 4 6 8 10 
```

**Example 3 — Looping with index using range(len())**
```python
names = ["Ravi", "Anu", "Kiran"]
for i in range(len(names)):
    print(i, "->", names[i])
```
**Output:**
```
0 -> Ravi
1 -> Anu
2 -> Kiran
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `range(stop)` excludes the `stop` value (`range(5)` gives `0,1,2,3,4`, not `5`).
- Using `range(len(list))` when simply looping `for item in list` is cleaner and more Pythonic.
- Modifying a list while iterating over it directly — causes skipped elements or bugs.

---

### 2.3 while loop

**Definition:**
A `while` loop repeats a block of code as long as a condition remains `True`. Useful when the number of iterations isn't known beforehand.

**Syntax:**
```python
while condition:
    # code
```

**Example 1 — Basic counter**
```python
i = 1
while i <= 5:
    print(i)
    i += 1
```
**Output:**
```
1
2
3
4
5
```

**Example 2 — while with user-style condition (sentinel value)**
```python
total = 0
numbers = [4, 7, 2, 9, -1, 5]   # -1 simulates "stop" input
i = 0
while numbers[i] != -1:
    total += numbers[i]
    i += 1
print("Sum until stop:", total)
```
**Output:**
```
Sum until stop: 22
```

**Example 3 — while True with a break condition**
```python
count = 0
while True:
    count += 1
    if count == 3:
        break
print("Loop stopped at:", count)
```
**Output:**
```
Loop stopped at: 3
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting to update the loop variable inside the loop → **infinite loop**.
- Using `while True` without a guaranteed `break` path.
- Off-by-one errors in the loop condition (`<=` vs `<`).

---

### 2.4 break & continue

**Definition:**
`break` exits the loop entirely. `continue` skips the rest of the current iteration and moves to the next one.

**Syntax:**
```python
for item in sequence:
    if condition:
        break       # or continue
```

**Example 1 — break on finding a target**
```python
numbers = [4, 8, 15, 16, 23, 42]
for num in numbers:
    if num == 15:
        print("Found 15, stopping search")
        break
    print("Checked:", num)
```
**Output:**
```
Checked: 4
Checked: 8
Found 15, stopping search
```

**Example 2 — continue to skip even numbers**
```python
for i in range(1, 10):
    if i % 2 == 0:
        continue
    print(i, end=" ")
```
**Output:**
```
1 3 5 7 9 
```

**Example 3 — break and continue together**
```python
for i in range(1, 20):
    if i % 2 != 0:
        continue
    if i > 10:
        break
    print(i, end=" ")
```
**Output:**
```
2 4 6 8 10 
```

**⚠️ Beginner Mistakes to Avoid**
- Confusing `break` (exits the loop) with `continue` (skips just this iteration).
- Using `break`/`continue` outside a loop → `SyntaxError`.
- Forgetting `break`/`continue` inside nested loops only affects the **innermost** loop.

---

## 3. Strings

### 3.1 Indexing & Slicing

**Definition:**
Strings are sequences of characters. **Indexing** accesses a single character by position (0-based, negative indices count from the end). **Slicing** extracts a substring using `[start:stop:step]`.

**Syntax:**
```python
s[index]
s[start:stop:step]
```

**Example 1 — Basic indexing**
```python
word = "Python"
print(word[0])
print(word[5])
print(word[-1])
```
**Output:**
```
P
n
n
```

**Example 2 — Slicing**
```python
text = "Computer Vision"
print(text[0:8])
print(text[9:])
print(text[:8])
```
**Output:**
```
Computer
Vision
Computer
```

**Example 3 — Slicing with step (including reverse)**
```python
s = "ABCDEFGH"
print(s[::2])
print(s[::-1])
print(s[1:6:2])
```
**Output:**
```
ACEG
HGFEDCBA
BDF
```

**⚠️ Beginner Mistakes to Avoid**
- Trying `s[0] = 'X'` to modify a character — strings are **immutable**, this raises `TypeError`.
- Off-by-one confusion: `s[start:stop]` excludes `stop`.
- Forgetting negative indices start at `-1` (not `-0`) for the last character.

---

### 3.2 String Methods

**Definition:**
Built-in functions that operate on strings: `upper()`, `lower()`, `replace()`, `split()`, `strip()` are among the most used.

**Syntax:**
```python
s.upper()
s.lower()
s.replace(old, new)
s.split(separator)
s.strip()
```

**Example 1 — Case conversion**
```python
name = "Thamizh"
print(name.upper())
print(name.lower())
```
**Output:**
```
THAMIZH
thamizh
```

**Example 2 — replace() and split()**
```python
sentence = "I love Java programming"
fixed = sentence.replace("Java", "Python")
print(fixed)

words = fixed.split(" ")
print(words)
```
**Output:**
```
I love Python programming
['I', 'love', 'Python', 'programming']
```

**Example 3 — strip() for cleaning input**
```python
raw = "   hello world   "
print("[" + raw.strip() + "]")
print("[" + raw.lstrip() + "]")
print("[" + raw.rstrip() + "]")
```
**Output:**
```
[hello world]
[hello world   ]
[   hello world]
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting string methods return a **new string** — they don't modify the original (`name.upper()` alone changes nothing unless reassigned).
- Using `strip()` expecting it to remove spaces from the **middle** of a string — it only removes from the ends.
- Calling `split()` without realizing default behavior splits on **any whitespace** when no argument is given.

---

### 3.3 String Programs

**Definition:**
Classic interview programs built using string indexing/slicing and loops: reversing a string, checking palindromes, and counting vowels/consonants.

**Syntax:**
```python
s[::-1]                 # reverse
s == s[::-1]             # palindrome check
```

**Example 1 — Reverse a string**
```python
text = "Chennai"
reversed_text = text[::-1]
print(reversed_text)
```
**Output:**
```
iannehC
```

**Example 2 — Palindrome check**
```python
def is_palindrome(s):
    s = s.lower().replace(" ", "")
    return s == s[::-1]

print(is_palindrome("Madam"))
print(is_palindrome("Python"))
```
**Output:**
```
True
False
```

**Example 3 — Count vowels and consonants**
```python
text = "Computer Vision"
vowels = "aeiouAEIOU"
v_count = c_count = 0

for ch in text:
    if ch.isalpha():
        if ch in vowels:
            v_count += 1
        else:
            c_count += 1

print("Vowels:", v_count)
print("Consonants:", c_count)
```
**Output:**
```
Vowels: 6
Consonants: 8
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting to lowercase the string before comparing in a palindrome check — `"Madam"` won't equal `"madaM"`.
- Counting spaces or punctuation as consonants — always check `ch.isalpha()` first.
- Using a manual loop to reverse a string instead of the simple `s[::-1]` idiom.

---

## 4. Collections

### 4.1 Lists

**Definition:**
A list is an **ordered, mutable** collection that can hold items of mixed types. Supports indexing, slicing, and many built-in methods: `append()`, `insert()`, `remove()`, `pop()`, `sort()`, `reverse()`, `count()`, `index()`.

**Syntax:**
```python
my_list = [item1, item2, item3]
my_list.append(item)
my_list.insert(index, item)
my_list.remove(item)
my_list.pop(index)
my_list.sort()
my_list.reverse()
my_list.count(item)
my_list.index(item)
```

**Example 1 — Create, index, slice**
```python
detections = ["car", "person", "bike", "truck"]
print(detections[0])
print(detections[1:3])
print(detections[-1])
```
**Output:**
```
car
['person', 'bike']
truck
```

**Example 2 — append, insert, remove, pop**
```python
nums = [10, 20, 30]
nums.append(40)
nums.insert(1, 15)
nums.remove(30)
popped = nums.pop()
print(nums)
print("Popped:", popped)
```
**Output:**
```
[10, 15, 20]
Popped: 40
```

**Example 3 — sort, reverse, count, index**
```python
scores = [88, 45, 95, 45, 70]
scores.sort()
print(scores)
scores.reverse()
print(scores)
print("Count of 45:", scores.count(45))
print("Index of 70:", scores.index(70))
```
**Output:**
```
[45, 45, 70, 88, 95]
[95, 88, 70, 45, 45]
Count of 45: 2
Index of 70: 2
```

**⚠️ Beginner Mistakes to Avoid**
- Confusing `remove(value)` (removes by **value**) with `pop(index)` (removes by **position**).
- Calling `.sort()` and expecting it to return the sorted list — it sorts **in place** and returns `None`. Use `sorted(list)` if you need a new sorted copy.
- Forgetting `index()` raises `ValueError` if the item isn't found.
- Copying a list with `list2 = list1` — this only copies the **reference**; use `list1.copy()` or `list1[:]` for an independent copy.

---

### 4.2 Nested Lists & List Traversal

**Definition:**
A nested list is a list containing other lists (commonly used for matrices/grids). Traversal means looping through all elements, including inner lists.

**Syntax:**
```python
matrix = [[1, 2], [3, 4]]
for row in matrix:
    for item in row:
        ...
```

**Example 1 — Creating and accessing a nested list**
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(matrix[1])
print(matrix[1][2])
```
**Output:**
```
[4, 5, 6]
6
```

**Example 2 — Traversing a nested list with nested for loops**
```python
matrix = [[1, 2], [3, 4], [5, 6]]
for row in matrix:
    for val in row:
        print(val, end=" ")
print()
```
**Output:**
```
1 2 3 4 5 6 
```

**Example 3 — Bounding box style nested list (CV use case)**
```python
boxes = [["car", 0.95], ["person", 0.88], ["bike", 0.76]]
for label, confidence in boxes:
    print(f"{label}: {confidence*100:.1f}%")
```
**Output:**
```
car: 95.0%
person: 88.0%
bike: 76.0%
```

**⚠️ Beginner Mistakes to Avoid**
- Creating a nested list with `[[0]*3]*3` — this duplicates **references** to the same inner list, so editing one row changes all rows.
- Forgetting nested lists need nested loops (or list comprehensions) to fully traverse.
- Mixing up row/column indices: `matrix[row][col]`, not `matrix[col][row]`.

---

### 4.3 Tuples

**Definition:**
A tuple is an **ordered, immutable** collection. Once created, its elements cannot be changed — useful for fixed data like coordinates.

**Syntax:**
```python
my_tuple = (item1, item2, item3)
```

**Example 1 — Tuple basics**
```python
point = (10, 20)
print(point)
print(type(point))
```
**Output:**
```
(10, 20)
<class 'tuple'>
```

**Example 2 — Accessing elements**
```python
rgb = (255, 0, 128)
print(rgb[0])
print(rgb[-1])
r, g, b = rgb
print(r, g, b)
```
**Output:**
```
255
128
255 0 128
```

**Example 3 — Immutability in action**
```python
coords = (4, 5)
try:
    coords[0] = 10
except TypeError as e:
    print("Error:", e)
```
**Output:**
```
Error: 'tuple' object does not support item assignment
```

**⚠️ Beginner Mistakes to Avoid**
- Trying to modify a tuple element directly → `TypeError`.
- Forgetting a single-item tuple needs a trailing comma: `(5)` is just an `int`, `(5,)` is a tuple.
- Using a tuple when you actually need a mutable structure (use a list instead).

---

### 4.4 Sets

**Definition:**
A set is an **unordered collection of unique elements** — no duplicates allowed. Supports mathematical operations like union and intersection.

**Syntax:**
```python
my_set = {item1, item2}
my_set.add(item)
my_set.remove(item)
set1.union(set2)
set1.intersection(set2)
```

**Example 1 — Set basics (auto-removes duplicates)**
```python
labels = {"car", "person", "car", "bike"}
print(labels)
print(len(labels))
```
**Output (exact order may vary — sets are unordered):**
```
{'car', 'person', 'bike'}
3
```

**Example 2 — add() and remove()**
```python
fruits = {"apple", "mango"}
fruits.add("banana")
fruits.remove("apple")
print(fruits)
```
**Output (exact order may vary — sets are unordered):**
```
{'mango', 'banana'}
```

**Example 3 — union() and intersection()**
```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}
print(set_a.union(set_b))
print(set_a.intersection(set_b))
```
**Output:**
```
{1, 2, 3, 4, 5, 6}
{3, 4}
```

**⚠️ Beginner Mistakes to Avoid**
- Sets have **no defined order** — never rely on a fixed print order or index into a set.
- Calling `remove()` on a value that doesn't exist → `KeyError` (use `.discard()` if you want no error).
- Creating an empty set with `{}` — this actually creates an empty **dictionary**; use `set()` instead.

---

### 4.5 Dictionaries

**Definition:**
A dictionary stores data as **key-value pairs**. Keys must be unique and immutable (e.g., strings, numbers, tuples); values can be anything.

**Syntax:**
```python
my_dict = {"key1": value1, "key2": value2}
my_dict.items()
my_dict.keys()
my_dict.values()
```

**Example 1 — Create and access values**
```python
student = {"name": "Thamizh", "course": "AI & DS", "year": 2026}
print(student["name"])
print(student.get("course"))
```
**Output:**
```
Thamizh
AI & DS
```

**Example 2 — items(), keys(), values()**
```python
model_info = {"name": "YOLOv8", "type": "segmentation", "mAP": 0.91}
print(model_info.keys())
print(model_info.values())
for k, v in model_info.items():
    print(k, "->", v)
```
**Output:**
```
dict_keys(['name', 'type', 'mAP'])
dict_values(['YOLOv8', 'segmentation', 0.91])
name -> YOLOv8
type -> segmentation
mAP -> 0.91
```

**Example 3 — Updating and adding keys**
```python
config = {"epochs": 50, "batch_size": 16}
config["epochs"] = 100          # update
config["lr"] = 0.001            # add new key
print(config)
```
**Output:**
```
{'epochs': 100, 'batch_size': 16, 'lr': 0.001}
```

**⚠️ Beginner Mistakes to Avoid**
- Accessing a missing key with `dict["key"]` → `KeyError`. Use `.get("key")` to safely return `None` (or a default) instead.
- Trying to use a mutable type (like a list) as a dictionary key → `TypeError: unhashable type`.
- Forgetting dictionaries (Python 3.7+) preserve **insertion order**, but you still shouldn't rely on numeric indexing — there's no `dict[0]`.

---

### 4.6 Nested Dictionary

**Definition:**
A dictionary where values themselves are dictionaries (or lists) — useful for representing structured/hierarchical data like JSON.

**Syntax:**
```python
nested = {
    "key1": {"inner_key": value},
    "key2": {"inner_key": value}
}
```

**Example 1 — Create and access a nested dictionary**
```python
employees = {
    "emp1": {"name": "Ravi", "dept": "AI"},
    "emp2": {"name": "Anu", "dept": "Vision"}
}
print(employees["emp1"]["name"])
print(employees["emp2"]["dept"])
```
**Output:**
```
Ravi
Vision
```

**Example 2 — Updating a value inside a nested dictionary**
```python
employees = {
    "emp1": {"name": "Ravi", "dept": "AI"},
    "emp2": {"name": "Anu", "dept": "Vision"}
}
employees["emp1"]["dept"] = "Computer Vision"
print(employees["emp1"])
```
**Output:**
```
{'name': 'Ravi', 'dept': 'Computer Vision'}
```

**Example 3 — Traversing a nested dictionary**
```python
camera_config = {
    "cam1": {"resolution": "1080p", "fps": 30},
    "cam2": {"resolution": "4K", "fps": 60}
}
for cam, settings in camera_config.items():
    print(cam, "->", settings)
    for key, val in settings.items():
        print("   ", key, ":", val)
```
**Output:**
```
cam1 -> {'resolution': '1080p', 'fps': 30}
    resolution : 1080p
    fps : 30
cam2 -> {'resolution': '4K', 'fps': 60}
    resolution : 4K
    fps : 60
```

**⚠️ Beginner Mistakes to Avoid**
- Trying to access a deeply nested key without checking each level exists first → `KeyError`.
- Confusing nested dictionaries with nested lists when designing data structures (use dicts for named fields, lists for ordered collections).
- Forgetting `.get("key", {})` is a safe way to avoid `KeyError` while still allowing further chained access.

---

## 5. Functions

### 5.1 Function Basics

**Definition:**
A function is a reusable block of code defined with `def`. **Parameters** are placeholders in the definition; **arguments** are actual values passed in. `return` sends a value back to the caller. **Scope** determines where a variable is accessible (local vs global).

**Syntax:**
```python
def function_name(param1, param2):
    # code
    return result
```

**Example 1 — Function with parameters, arguments, and return**
```python
def calculate_iou(box1_area, box2_area, intersection):
    union = box1_area + box2_area - intersection
    return intersection / union

result = calculate_iou(100, 80, 40)
print(round(result, 2))
```
**Output:**
```
0.29
```

**Example 2 — Default parameter values**
```python
def greet(name, msg="Welcome"):
    print(f"{msg}, {name}!")

greet("Thamizh")
greet("Anu", "Good morning")
```
**Output:**
```
Welcome, Thamizh!
Good morning, Anu!
```

**Example 3 — Local vs global scope**
```python
threshold = 0.5   # global

def update_threshold():
    threshold = 0.8   # local, shadows global
    print("Inside function:", threshold)

update_threshold()
print("Outside function:", threshold)
```
**Output:**
```
Inside function: 0.8
Outside function: 0.5
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `return` — without it, a function returns `None` by default.
- Assuming a variable changed inside a function automatically updates the global variable — it doesn't unless you use the `global` keyword.
- Using a **mutable default argument** like `def f(items=[])` — the same list object is reused across calls and silently accumulates data.

---

### 5.2 *args and **kwargs

**Definition:**
`*args` collects extra **positional** arguments into a tuple. `**kwargs` collects extra **keyword** arguments into a dictionary. Used when the number of arguments isn't fixed.

**Syntax:**
```python
def func(*args, **kwargs):
    # args is a tuple
    # kwargs is a dictionary
```

**Example 1 — *args**
```python
def total_detections(*args):
    return sum(args)

print(total_detections(5, 3, 8))
print(total_detections(10, 20))
```
**Output:**
```
16
30
```

**Example 2 — **kwargs**
```python
def show_config(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

show_config(model="YOLOv8", epochs=50, batch_size=16)
```
**Output:**
```
model: YOLOv8
epochs: 50
batch_size: 16
```

**Example 3 — Combining normal args, *args, and **kwargs**
```python
def train_model(model_name, *metrics, **settings):
    print("Model:", model_name)
    print("Metrics:", metrics)
    print("Settings:", settings)

train_model("ResNet18", 0.95, 0.89, lr=0.001, epochs=30)
```
**Output:**
```
Model: ResNet18
Metrics: (0.95, 0.89)
Settings: {'lr': 0.001, 'epochs': 30}
```

**⚠️ Beginner Mistakes to Avoid**
- Wrong ordering — the correct parameter order is `def f(normal, *args, **kwargs)`. Putting `**kwargs` before `*args` → `SyntaxError`.
- Forgetting `*args` is a **tuple** (immutable) and `**kwargs` is a **dictionary**.
- Calling a function with keyword arguments out of order incorrectly mixed with positional ones (positional args must come first).

---

## 6. Modules

### 6.1 import / from-import / Creating Modules

**Definition:**
A module is simply a `.py` file containing reusable code. `import` brings in an entire module; `from module import name` brings in specific items directly.

**Syntax:**
```python
import module_name
from module_name import function_name
```

**Example 1 — Importing a built-in module**
```python
import math
print(math.sqrt(16))
print(math.pi)
```
**Output:**
```
4.0
3.141592653589793
```

**Example 2 — from-import for specific functions**
```python
from random import randint, choice
print(randint(1, 10))
print(choice(["car", "bike", "truck"]))
```
**Output (sample — random output, will vary):**
```
7
bike
```

**Example 3 — Creating and using your own module**
```python
# File: cv_utils.py
def calculate_area(width, height):
    return width * height

# File: main.py
import cv_utils
print(cv_utils.calculate_area(640, 480))
```
**Output:**
```
307200
```

**⚠️ Beginner Mistakes to Avoid**
- Using `from module import *` — pollutes the namespace and makes it unclear where a function came from.
- Naming your own file the same as a built-in module (e.g., `random.py`) — causes import conflicts.
- Forgetting that a custom module must be in the same directory (or on the Python path) to be importable.

---

## 7. File Handling

### 7.1 open(), Modes, read/write, with open()

**Definition:**
File handling lets a program read from and write to files on disk. `open()` opens a file in a given **mode**: `r` (read), `w` (write — overwrites), `a` (append). `with open()` automatically closes the file even if an error occurs.

**Syntax:**
```python
f = open("file.txt", "r")
f.read()
f.readline()
f.readlines()
f.write("text")
f.close()

with open("file.txt", "r") as f:
    data = f.read()
```

**Example 1 — Writing to a file with mode "w"**
```python
with open("notes.txt", "w") as f:
    f.write("Python Revision\n")
    f.write("File Handling Topic\n")
print("File written successfully")
```
**Output:**
```
File written successfully
```

**Example 2 — Reading with read(), readline(), readlines()**
```python
with open("notes.txt", "r") as f:
    print(f.read())

with open("notes.txt", "r") as f:
    print(f.readline())

with open("notes.txt", "r") as f:
    print(f.readlines())
```
**Output:**
```
Python Revision
File Handling Topic

Python Revision

['Python Revision\n', 'File Handling Topic\n']
```

**Example 3 — Appending with mode "a"**
```python
with open("notes.txt", "a") as f:
    f.write("Appended line\n")

with open("notes.txt", "r") as f:
    print(f.read())
```
**Output:**
```
Python Revision
File Handling Topic
Appended line
```

**⚠️ Beginner Mistakes to Avoid**
- Using mode `"w"` when you meant `"a"` — `"w"` **erases** existing file content before writing.
- Forgetting to close a file when not using `with open()` — can lead to data not being saved/flushed properly.
- Trying to read a file that doesn't exist in mode `"r"` → `FileNotFoundError`.
- Forgetting `readlines()` returns a list of strings, each still containing the trailing `\n`.

---

## 8. Exception Handling

### 8.1 try / except / finally

**Definition:**
Exception handling lets a program respond gracefully to runtime errors instead of crashing. `try` contains risky code, `except` catches and handles specific errors, `finally` always runs regardless of whether an error occurred.

**Syntax:**
```python
try:
    # risky code
except SomeError:
    # handle error
finally:
    # always runs
```

**Example 1 — Catching ValueError**
```python
try:
    age = int(input("Enter age: "))
    print("Age is:", age)
except ValueError:
    print("Invalid input — please enter a number")
```
**Output (when user types `abc`):**
```
Enter age: abc
Invalid input — please enter a number
```

**Example 2 — Catching ZeroDivisionError**
```python
def safe_divide(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        return "Cannot divide by zero"

print(safe_divide(10, 2))
print(safe_divide(10, 0))
```
**Output:**
```
5.0
Cannot divide by zero
```

**Example 3 — try/except/finally together**
```python
try:
    numbers = [1, 2, 3]
    print(numbers[5])
except IndexError as e:
    print("Error caught:", e)
finally:
    print("Execution completed")
```
**Output:**
```
Error caught: list index out of range
Execution completed
```

**⚠️ Beginner Mistakes to Avoid**
- Using a bare `except:` that catches **everything**, hiding real bugs — always catch specific exceptions when possible.
- Forgetting `finally` runs **even if** an exception was caught or even if there's a `return` in the `try` block.
- Putting too much code inside `try` — only wrap the line(s) that can actually raise the error.

---

## 9. OOP

### 9.1 Core OOP

**Definition:**
- **Class:** a blueprint for creating objects.
- **Object:** an instance of a class.
- **Attribute:** a variable that belongs to an object.
- **Method:** a function that belongs to a class.
- **self:** refers to the current instance inside a method.
- **Constructor (`__init__`):** a special method called automatically when an object is created, used to initialize attributes.

**Syntax:**
```python
class ClassName:
    def __init__(self, param):
        self.attribute = param

    def method(self):
        # code
```

**Example 1 — Defining a class and creating an object**
```python
class Detector:
    def __init__(self, model_name, confidence):
        self.model_name = model_name
        self.confidence = confidence

    def show_info(self):
        print(f"Model: {self.model_name}, Confidence: {self.confidence}")

d1 = Detector("YOLOv8", 0.91)
d1.show_info()
```
**Output:**
```
Model: YOLOv8, Confidence: 0.91
```

**Example 2 — Multiple objects with independent attributes**
```python
class Detector:
    def __init__(self, model_name, confidence):
        self.model_name = model_name
        self.confidence = confidence

d1 = Detector("YOLOv8", 0.91)
d2 = Detector("ResNet18", 0.85)
print(d1.model_name, d2.model_name)
```
**Output:**
```
YOLOv8 ResNet18
```

**Example 3 — Updating an attribute via a method**
```python
class Counter:
    def __init__(self):
        self.count = 0

    def increment(self):
        self.count += 1

c = Counter()
c.increment()
c.increment()
c.increment()
print(c.count)
```
**Output:**
```
3
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `self` as the first parameter in instance methods → `TypeError` when calling the method.
- Confusing a **class** (blueprint) with an **object** (actual instance built from it).
- Defining attributes outside `__init__` inconsistently, leading to `AttributeError` if a method runs before the attribute is set.

---

### 9.2 Inheritance

**Definition:**
Inheritance allows a **child class** to reuse and extend the functionality of a **parent class**. `super()` calls the parent class's methods from within the child. **Method overriding** lets a child redefine a parent's method.

**Syntax:**
```python
class Parent:
    def method(self):
        ...

class Child(Parent):
    def method(self):
        super().method()
        ...
```

**Example 1 — Basic inheritance**
```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

    def info(self):
        print(f"Brand: {self.brand}")

class Car(Vehicle):
    pass

c = Car("Toyota")
c.info()
```
**Output:**
```
Brand: Toyota
```

**Example 2 — Method overriding**
```python
class Animal:
    def sound(self):
        print("Some generic sound")

class Dog(Animal):
    def sound(self):
        print("Bark")

a = Animal()
d = Dog()
a.sound()
d.sound()
```
**Output:**
```
Some generic sound
Bark
```

**Example 3 — Using super() to extend parent behavior**
```python
class Employee:
    def __init__(self, name):
        self.name = name

class Engineer(Employee):
    def __init__(self, name, skill):
        super().__init__(name)
        self.skill = skill

    def show(self):
        print(f"{self.name} specializes in {self.skill}")

e = Engineer("Thamizh", "Computer Vision")
e.show()
```
**Output:**
```
Thamizh specializes in Computer Vision
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `super().__init__()` in the child's constructor — the parent's attributes never get set.
- Overriding a method but accidentally changing its expected behavior/signature, breaking code that relies on the parent's contract.
- Confusing "is-a" (inheritance) relationships with "has-a" (composition) relationships.

---

### 9.3 Encapsulation

**Definition:**
Encapsulation restricts direct access to an object's internal data. Python uses naming conventions: **public** (`name`), **protected** (`_name`, convention only), **private** (`__name`, name-mangled). **Getters/setters** control access and allow validation.

**Syntax:**
```python
class Example:
    def __init__(self):
        self.public_var = 1
        self._protected_var = 2
        self.__private_var = 3
```

**Example 1 — Public, protected, private variables**
```python
class Account:
    def __init__(self, balance):
        self.owner = "Public"          # public
        self._bank_code = "Protected"  # protected
        self.__balance = balance       # private

acc = Account(5000)
print(acc.owner)
print(acc._bank_code)
print(acc._Account__balance)  # name-mangled access
```
**Output:**
```
Public
Protected
5000
```

**Example 2 — Getter and setter methods**
```python
class Account:
    def __init__(self, balance):
        self.__balance = balance

    def get_balance(self):
        return self.__balance

    def set_balance(self, amount):
        self.__balance = amount

acc = Account(1000)
print(acc.get_balance())
acc.set_balance(2000)
print(acc.get_balance())
```
**Output:**
```
1000
2000
```

**Example 3 — Validation inside a setter**
```python
class Account:
    def __init__(self, balance):
        self.__balance = balance

    def set_balance(self, amount):
        if amount < 0:
            print("Balance cannot be negative")
        else:
            self.__balance = amount

    def get_balance(self):
        return self.__balance

acc = Account(500)
acc.set_balance(-100)
print(acc.get_balance())
```
**Output:**
```
Balance cannot be negative
500
```

**⚠️ Beginner Mistakes to Avoid**
- Thinking `__private` variables are truly inaccessible — Python only **name-mangles** them (`_ClassName__var`); it's a convention, not real security.
- Accessing private/protected attributes directly from outside the class instead of using getters/setters — breaks encapsulation's purpose.
- Forgetting to validate input inside setters, defeating the point of encapsulation.

---

### 9.4 Polymorphism

**Definition:**
Polymorphism means the same method name behaves differently depending on the object calling it ("many forms"). Commonly achieved through method overriding.

**Syntax:**
```python
class A:
    def speak(self): ...
class B:
    def speak(self): ...
```

**Example 1 — Method overriding as polymorphism**
```python
class Shape:
    def area(self):
        print("Area not defined")

class Circle(Shape):
    def area(self):
        print("Area = pi * r^2")

class Square(Shape):
    def area(self):
        print("Area = side^2")

for shape in [Circle(), Square()]:
    shape.area()
```
**Output:**
```
Area = pi * r^2
Area = side^2
```

**Example 2 — Same method name, different behavior (no inheritance needed)**
```python
class Cat:
    def sound(self):
        print("Meow")

class Cow:
    def sound(self):
        print("Moo")

for animal in [Cat(), Cow()]:
    animal.sound()
```
**Output:**
```
Meow
Moo
```

**Example 3 — Built-in polymorphism (len() works differently per type)**
```python
print(len("Python"))
print(len([1, 2, 3, 4]))
print(len({"a": 1, "b": 2}))
```
**Output:**
```
6
4
2
```

**⚠️ Beginner Mistakes to Avoid**
- Thinking polymorphism requires inheritance — it doesn't; two unrelated classes with the same method name also demonstrate it (duck typing).
- Forgetting that calling a method on the wrong object type may raise `AttributeError` if that object doesn't implement the method.
- Overcomplicating simple cases — sometimes a plain `if/elif` is clearer than forcing polymorphism.

---

### 9.5 Abstraction

**Definition:**
Abstraction means hiding internal implementation complexity and exposing only the necessary functionality to the user, often using the `abc` module to define abstract base classes.

**Syntax:**
```python
from abc import ABC, abstractmethod

class Base(ABC):
    @abstractmethod
    def method(self):
        pass
```

**Example 1 — Defining an abstract class**
```python
from abc import ABC, abstractmethod

class Model(ABC):
    @abstractmethod
    def predict(self):
        pass

try:
    m = Model()
except TypeError as e:
    print("Error:", e)
```
**Output (exact wording varies slightly by Python version):**
```
Error: Can't instantiate abstract class Model without an implementation for abstract method 'predict'
```

**Example 2 — Implementing the abstract method in a child class**
```python
from abc import ABC, abstractmethod

class Model(ABC):
    @abstractmethod
    def predict(self):
        pass

class YOLOModel(Model):
    def predict(self):
        print("Running YOLO inference...")

m = YOLOModel()
m.predict()
```
**Output:**
```
Running YOLO inference...
```

**Example 3 — Hiding complexity behind a simple interface**
```python
class CameraSystem:
    def _connect_to_plc(self):
        print("Connecting to PLC over Modbus TCP...")

    def _load_model(self):
        print("Loading YOLOv8 weights...")

    def start(self):
        self._connect_to_plc()
        self._load_model()
        print("System ready")

cam = CameraSystem()
cam.start()
```
**Output:**
```
Connecting to PLC over Modbus TCP...
Loading YOLOv8 weights...
System ready
```

**⚠️ Beginner Mistakes to Avoid**
- Trying to instantiate an abstract class directly → `TypeError`.
- Forgetting to implement **all** abstract methods in a child class — it remains abstract and can't be instantiated either.
- Confusing abstraction (hiding complexity) with encapsulation (restricting access) — they're related but distinct concepts.

---

### 9.6 Advanced OOP

**Definition:**
- **Class variables:** shared across all instances of a class (defined directly in the class body).
- **Class methods (`@classmethod`):** operate on the class itself, take `cls` as the first parameter.
- **Static methods (`@staticmethod`):** don't access instance or class data; behave like a regular function grouped inside a class.
- **Composition:** building a class using other class objects as attributes ("has-a" relationship).

**Syntax:**
```python
class Example:
    class_var = 0

    @classmethod
    def class_method(cls): ...

    @staticmethod
    def static_method(): ...
```

**Example 1 — Class variable shared across instances**
```python
class Model:
    total_models = 0

    def __init__(self, name):
        self.name = name
        Model.total_models += 1

m1 = Model("YOLOv8")
m2 = Model("ResNet18")
print(Model.total_models)
```
**Output:**
```
2
```

**Example 2 — classmethod and staticmethod**
```python
class MathUtils:
    @staticmethod
    def add(a, b):
        return a + b

    @classmethod
    def class_name(cls):
        return cls.__name__

print(MathUtils.add(5, 3))
print(MathUtils.class_name())
```
**Output:**
```
8
MathUtils
```

**Example 3 — Composition ("has-a" relationship)**
```python
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self):
        self.engine = Engine()   # Car HAS-A Engine

    def drive(self):
        self.engine.start()
        print("Car is moving")

c = Car()
c.drive()
```
**Output:**
```
Engine started
Car is moving
```

**⚠️ Beginner Mistakes to Avoid**
- Modifying a class variable through an instance (`m1.total_models = 5`) — this creates a new **instance** variable instead of updating the shared class variable.
- Forgetting `@staticmethod` doesn't receive `self` or `cls` — it can't access instance or class data directly.
- Choosing inheritance when composition is more appropriate (prefer composition when the relationship isn't truly "is-a").

---

### 9.7 Decorators

**Definition:**
A decorator is a function that wraps another function to extend or modify its behavior without changing its source code, applied using the `@decorator_name` syntax.

**Syntax:**
```python
def decorator(func):
    def wrapper(*args, **kwargs):
        # before
        result = func(*args, **kwargs)
        # after
        return result
    return wrapper

@decorator
def my_function():
    ...
```

**Example 1 — Basic decorator**
```python
def log_call(func):
    def wrapper():
        print(f"Calling {func.__name__}")
        func()
    return wrapper

@log_call
def run_inference():
    print("Running inference...")

run_inference()
```
**Output:**
```
Calling run_inference
Running inference...
```

**Example 2 — Decorator with arguments via *args/**kwargs**
```python
def timer_log(func):
    def wrapper(*args, **kwargs):
        print("Starting timer...")
        result = func(*args, **kwargs)
        print("Finished")
        return result
    return wrapper

@timer_log
def process_frame(frame_id):
    print(f"Processing frame {frame_id}")

process_frame(101)
```
**Output:**
```
Starting timer...
Processing frame 101
Finished
```

**Example 3 — Decorator that modifies the return value**
```python
def to_uppercase(func):
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        return result.upper()
    return wrapper

@to_uppercase
def get_label():
    return "car detected"

print(get_label())
```
**Output:**
```
CAR DETECTED
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting the inner `wrapper` function must `return` the original function's result, or the decorated function silently returns `None`.
- Not using `*args, **kwargs` in `wrapper()` — breaks the decorator for any function that takes arguments.
- Stacking multiple decorators without understanding they apply **bottom-up** (closest to the function runs first).

---

### 9.8 Property

**Definition:**
`@property` lets a method be accessed like an attribute (no parentheses needed). `@<property>.setter` lets you define controlled, validated assignment for that same property.

**Syntax:**
```python
class Example:
    @property
    def value(self):
        return self._value

    @value.setter
    def value(self, new_value):
        self._value = new_value
```

**Example 1 — Basic @property (read like an attribute)**
```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    @property
    def area(self):
        return self.width * self.height

r = Rectangle(5, 4)
print(r.area)   # no parentheses needed
```
**Output:**
```
20
```

**Example 2 — @property.setter with validation**
```python
class Confidence:
    def __init__(self, value):
        self._value = value

    @property
    def value(self):
        return self._value

    @value.setter
    def value(self, new_value):
        if 0 <= new_value <= 1:
            self._value = new_value
        else:
            print("Confidence must be between 0 and 1")

c = Confidence(0.5)
c.value = 0.9
print(c.value)
c.value = 1.5
print(c.value)
```
**Output:**
```
0.9
Confidence must be between 0 and 1
0.9
```

**Example 3 — Computed property that stays in sync**
```python
class BoundingBox:
    def __init__(self, x1, y1, x2, y2):
        self.x1, self.y1, self.x2, self.y2 = x1, y1, x2, y2

    @property
    def width(self):
        return self.x2 - self.x1

    @property
    def height(self):
        return self.y2 - self.y1

box = BoundingBox(10, 10, 110, 60)
print(box.width, box.height)
```
**Output:**
```
100 50
```

**⚠️ Beginner Mistakes to Avoid**
- Calling a property with parentheses (`r.area()`) — `@property` methods are accessed **without** `()`.
- Defining a setter without a matching `@property` getter of the same name first → `AttributeError`.
- Forgetting that without a `.setter`, a `@property` is **read-only**; trying to assign to it raises `AttributeError`.

---

## 10. JSON

### 10.1 JSON Basics

**Definition:**
JSON (JavaScript Object Notation) is a lightweight text format for storing/exchanging structured data — very similar to a Python dictionary but it's a **string** when stored/transmitted. `json.dumps()`/`json.loads()` convert between Python objects and JSON **strings**; `json.dump()`/`json.load()` work directly with **files**.

**Syntax:**
```python
import json
json.dumps(python_obj)        # Python -> JSON string
json.loads(json_string)       # JSON string -> Python
json.dump(python_obj, file)   # Python -> JSON file
json.load(file)               # JSON file -> Python
```

**Example 1 — JSON vs Dictionary, dumps() and loads()**
```python
import json

data = {"model": "YOLOv8", "accuracy": 0.91, "active": True}
json_string = json.dumps(data)
print(type(data), type(json_string))
print(json_string)

parsed_back = json.loads(json_string)
print(type(parsed_back))
print(parsed_back["model"])
```
**Output:**
```
<class 'dict'> <class 'str'>
{"model": "YOLOv8", "accuracy": 0.91, "active": true}
<class 'dict'>
YOLOv8
```

**Example 2 — dump() and load() with a file**
```python
import json

config = {"epochs": 50, "lr": 0.001}

with open("config.json", "w") as f:
    json.dump(config, f)

with open("config.json", "r") as f:
    loaded = json.load(f)

print(loaded)
```
**Output:**
```
{'epochs': 50, 'lr': 0.001}
```

**Example 3 — Nested JSON and pretty print**
```python
import json

report = {
    "model": "YOLOv8",
    "metrics": {"precision": 0.92, "recall": 0.88},
    "classes": ["car", "person", "bike"]
}

pretty = json.dumps(report, indent=4)
print(pretty)
```
**Output:**
```
{
    "model": "YOLOv8",
    "metrics": {
        "precision": 0.92,
        "recall": 0.88
    },
    "classes": [
        "car",
        "person",
        "bike"
    ]
}
```

**⚠️ Beginner Mistakes to Avoid**
- Confusing a JSON **string** with a Python **dict** — `json.dumps()` output is text and must be parsed with `json.loads()` before dict-style access.
- JSON uses `true`/`false`/`null`; Python uses `True`/`False`/`None` — the `json` module converts automatically, but don't write raw JSON text using Python casing.
- Forgetting `indent=4` (or any number) is needed for pretty printing — without it, `dumps()` produces a single compact line.
- Trying to `json.dump()` an object with non-serializable types (like a custom class instance) → `TypeError`.

---

## 11. Pythonic Features

### 11.1 List Comprehension

**Definition:**
A concise way to build a new list in a single line, optionally with filtering and transformation, instead of writing a full `for` loop with `.append()`.

**Syntax:**
```python
[expression for item in iterable if condition]
```

**Example 1 — Basic list comprehension**
```python
squares = [x**2 for x in range(1, 6)]
print(squares)
```
**Output:**
```
[1, 4, 9, 16, 25]
```

**Example 2 — Filtering with a condition**
```python
nums = [4, 7, 12, 9, 22, 3]
even_nums = [n for n in nums if n % 2 == 0]
print(even_nums)
```
**Output:**
```
[4, 12, 22]
```

**Example 3 — Transformation combined with filtering**
```python
labels = ["car", "person", "bike", "truck"]
short_upper = [label.upper() for label in labels if len(label) <= 4]
print(short_upper)
```
**Output:**
```
['CAR', 'BIKE']
```

**⚠️ Beginner Mistakes to Avoid**
- Writing overly complex logic inside a comprehension, hurting readability — if it needs multiple conditions and nested loops, a regular `for` loop is often clearer.
- Forgetting the `if` in a list comprehension goes **after** the `for`, while a conditional **expression** (ternary) goes **before** it: `[x if cond else y for x in iterable]`.
- Accidentally creating a generator instead of a list by using `()` instead of `[]`.

---

### 11.2 Dictionary Comprehension

**Definition:**
Like list comprehension, but builds a dictionary in one line using `key: value` pairs.

**Syntax:**
```python
{key_expr: value_expr for item in iterable if condition}
```

**Example 1 — Basic dictionary comprehension**
```python
squares = {x: x**2 for x in range(1, 6)}
print(squares)
```
**Output:**
```
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

**Example 2 — Filtering**
```python
scores = {"Ravi": 45, "Anu": 88, "Kiran": 92, "Devi": 38}
passed = {name: score for name, score in scores.items() if score >= 50}
print(passed)
```
**Output:**
```
{'Anu': 88, 'Kiran': 92}
```

**Example 3 — Transformation**
```python
labels = ["car", "person", "bike"]
label_lengths = {label: len(label) for label in labels}
print(label_lengths)
```
**Output:**
```
{'car': 3, 'person': 6, 'bike': 4}
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting the `key: value` syntax (with a colon) — using just `value for item` builds a **set**, not a dict.
- Using a duplicate key expression — later duplicates silently overwrite earlier ones.
- Trying to comprehend over a dict without using `.items()` when you need both key and value.

---

### 11.3 Lambda

**Definition:**
A lambda is a small, anonymous, single-expression function, often used inline where a full `def` would be overkill — commonly with `map()`, `filter()`, and `sorted()`.

**Syntax:**
```python
lambda arguments: expression
```

**Example 1 — Basic lambda**
```python
square = lambda x: x ** 2
print(square(6))
```
**Output:**
```
36
```

**Example 2 — Lambda with multiple arguments**
```python
add = lambda a, b: a + b
print(add(10, 20))
```
**Output:**
```
30
```

**Example 3 — Conditional (ternary) lambda**
```python
classify = lambda score: "Pass" if score >= 50 else "Fail"
print(classify(72))
print(classify(35))
```
**Output:**
```
Pass
Fail
```

**⚠️ Beginner Mistakes to Avoid**
- Trying to write multiple statements inside a lambda — it only supports a **single expression**.
- Overusing lambdas for complex logic, making code hard to read — use a named `def` function instead when logic grows.
- Forgetting a lambda's conditional form is `value_if_true if condition else value_if_false`, not standard `if/else` block syntax.

---

### 11.4 map() & filter()

**Definition:**
`map(function, iterable)` applies a function to every item in an iterable and returns a map object (transform). `filter(function, iterable)` keeps only items where the function returns `True` (selection). Both are typically wrapped in `list()` to view results.

**Syntax:**
```python
map(function, iterable)
filter(function, iterable)
```

**Example 1 — map() to transform values**
```python
nums = [1, 2, 3, 4, 5]
doubled = list(map(lambda x: x * 2, nums))
print(doubled)
```
**Output:**
```
[2, 4, 6, 8, 10]
```

**Example 2 — filter() to select values**
```python
nums = [10, 15, 22, 33, 40, 7]
evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)
```
**Output:**
```
[10, 22, 40]
```

**Example 3 — Combining map() and filter()**
```python
confidences = [0.45, 0.92, 0.61, 0.30, 0.88]
high_conf_percent = list(map(lambda x: x * 100, filter(lambda x: x >= 0.5, confidences)))
print(high_conf_percent)
```
**Output:**
```
[92.0, 61.0, 88.0]
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `map()`/`filter()` return **iterator objects** in Python 3, not lists — you must wrap with `list()` to see/use them as a list.
- Using `filter()` with a function that doesn't return a boolean-like value — leads to confusing inclusion/exclusion.
- Choosing `map()`/`filter()` + `lambda` when a list comprehension would be more readable (a common style preference in real-world code).

---

### 11.5 zip() & enumerate()

**Definition:**
`zip()` combines multiple iterables element-wise into tuples. `enumerate()` adds an automatic index counter while looping over an iterable.

**Syntax:**
```python
zip(iterable1, iterable2)
enumerate(iterable, start=0)
```

**Example 1 — zip() to pair two lists**
```python
labels = ["car", "person", "bike"]
confidences = [0.95, 0.88, 0.76]
paired = list(zip(labels, confidences))
print(paired)
```
**Output:**
```
[('car', 0.95), ('person', 0.88), ('bike', 0.76)]
```

**Example 2 — Looping with zip() directly**
```python
names = ["Ravi", "Anu"]
scores = [88, 92]
for name, score in zip(names, scores):
    print(f"{name}: {score}")
```
**Output:**
```
Ravi: 88
Anu: 92
```

**Example 3 — enumerate() for index + value**
```python
classes = ["car", "person", "bike", "truck"]
for index, cls in enumerate(classes, start=1):
    print(index, "->", cls)
```
**Output:**
```
1 -> car
2 -> person
3 -> bike
4 -> truck
```

**⚠️ Beginner Mistakes to Avoid**
- Forgetting `zip()` stops at the **shortest** iterable if lengths differ — extra items in the longer list are silently dropped.
- Using `range(len(list))` plus manual indexing instead of the cleaner `enumerate(list)`.
- Forgetting `enumerate()`'s `start` parameter defaults to `0`, not `1`.

---

## 12. Advanced Python

### 12.1 Generators

**Definition:**
A generator is a function that produces a sequence of values **lazily** (one at a time, on demand) using `yield` instead of `return`. This saves memory compared to building a full list upfront. Call `next()` to get the next value.

**Syntax:**
```python
def generator_function():
    yield value1
    yield value2

gen = generator_function()
next(gen)
```

**Example 1 — Basic generator with yield**
```python
def count_up_to(n):
    i = 1
    while i <= n:
        yield i
        i += 1

gen = count_up_to(3)
print(next(gen))
print(next(gen))
print(next(gen))
```
**Output:**
```
1
2
3
```

**Example 2 — Looping directly over a generator function**
```python
def frame_ids(total):
    for i in range(total):
        yield f"frame_{i}"

for fid in frame_ids(4):
    print(fid)
```
**Output:**
```
frame_0
frame_1
frame_2
frame_3
```

**Example 3 — Generator for memory-efficient large-data processing**
```python
def squares_up_to(n):
    for i in range(1, n + 1):
        yield i ** 2

gen = squares_up_to(5)
print(list(gen))
print(sum(squares_up_to(5)))
```
**Output:**
```
[1, 4, 9, 16, 25]
55
```

**⚠️ Beginner Mistakes to Avoid**
- Calling `next()` on an exhausted generator → raises `StopIteration` (handled automatically by `for` loops, but crashes manual `next()` calls).
- Trying to reuse a generator after it's been fully consumed — generators run **once**; you must create a new one to iterate again.
- Confusing `yield` with `return` — `return` ends the function immediately; `yield` pauses it and resumes from that point on the next call.

---

### 12.2 Iterators

**Definition:**
An iterator is an object that implements `__iter__()` and `__next__()`, allowing sequential access to elements via `next()`. `iter()` converts an iterable into an iterator. `StopIteration` is raised automatically when there are no more items. **A generator is itself a type of iterator.**

**Syntax:**
```python
it = iter(iterable)
next(it)   # raises StopIteration when exhausted
```

**Example 1 — iter() and next() on a list**
```python
nums = [10, 20, 30]
it = iter(nums)
print(next(it))
print(next(it))
print(next(it))
```
**Output:**
```
10
20
30
```

**Example 2 — Handling StopIteration manually**
```python
nums = [1, 2]
it = iter(nums)
try:
    print(next(it))
    print(next(it))
    print(next(it))   # nothing left
except StopIteration:
    print("No more items left")
```
**Output:**
```
1
2
No more items left
```

**Example 3 — Confirming a generator is an iterator**
```python
def gen_func():
    yield 1
    yield 2

g = gen_func()
print(hasattr(g, "__next__"))
print(hasattr(g, "__iter__"))
print(iter(g) is g)   # a generator is its own iterator
```
**Output:**
```
True
True
True
```

**⚠️ Beginner Mistakes to Avoid**
- Confusing an **iterable** (something you *can* loop over, like a list) with an **iterator** (the object actually doing the stepping, produced by `iter()`).
- Forgetting `next()` on an exhausted iterator always raises `StopIteration` — must be handled with `try/except` if used manually outside a `for` loop.
- Assuming every iterable is also directly an iterator — a plain `list` is iterable but is **not** itself an iterator (it has no `__next__`).

---

## ✅ Revision Checklist

Use this as a quick self-test before interviews — if you can explain + code each one from memory, you're solid:

- [ ] Variables, I/O, Type Casting, Data Types, Operators
- [ ] if/elif/else, Nested if, for + range(), while, break/continue
- [ ] String indexing/slicing, String methods, Reverse/Palindrome/Vowel programs
- [ ] List methods, Nested lists, Tuples, Sets, Dictionaries, Nested dictionaries
- [ ] Functions, scope, *args/**kwargs
- [ ] Modules (import / from-import / custom modules)
- [ ] File handling (modes, read/write, with open())
- [ ] Exception handling (try/except/finally, ValueError, ZeroDivisionError)
- [ ] OOP: Class/Object, Inheritance, Encapsulation, Polymorphism, Abstraction
- [ ] Advanced OOP: Class/Static methods, Composition, Decorators, @property
- [ ] JSON: dumps/loads, dump/load, nested, pretty print
- [ ] List & dict comprehension, Lambda, map()/filter(), zip()/enumerate()
- [ ] Generators (yield), Iterators (iter/next/StopIteration)

---

*Last updated: June 2026 — maintained by Thamizh as a personal interview-prep reference.*
