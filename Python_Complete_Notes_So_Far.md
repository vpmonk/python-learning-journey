# Python Learning Notes — Complete So Far

> A single-file revision guide for everything studied so far.
> Focus: understanding the concept, remembering the syntax/template, and writing code independently.

---

# 1. Variables

## What I learned

A variable stores a value so we can use it later.

## Template

```python
variable_name = value
```

## Example

```python
name = "Vishnu"
age = 24
salary = 50000
is_working = True

print(name)
print(age)
```

## Important

Python is dynamically typed. We do not need to declare the type manually.

```python
x = 10
x = "Python"
```

---

# 2. Data Types

Common Python data types:

```python
age = 24                 # int
salary = 50000.50        # float
name = "Vishnu"          # str
is_active = True         # bool
value = None             # NoneType
```

## Check type

```python
print(type(age))
print(type(name))
```

---

# 3. Input and Output

## Template

```python
value = input("Enter something: ")
print(value)
```

## Important

`input()` always returns a string.

```python
age = input("Enter age: ")

print(type(age))   # str
```

Convert it when necessary:

```python
age = int(input("Enter age: "))
```

---

# 4. Type Conversion

```python
age = int("24")
salary = float("50000.5")
number = str(100)
```

Common conversions:

```text
int()
float()
str()
bool()
```

---

# 5. Operators

## Arithmetic

```python
a = 10
b = 3

print(a + b)    # addition
print(a - b)    # subtraction
print(a * b)    # multiplication
print(a / b)    # division
print(a // b)   # floor division
print(a % b)    # remainder
print(a ** b)   # power
```

## Comparison

```python
a == b
a != b
a > b
a < b
a >= b
a <= b
```

## Logical

```python
and
or
not
```

Example:

```python
age = 25

if age >= 18 and age <= 60:
    print("Working age")
```

---

# 6. Conditions

## Template

```python
if condition:
    ...
elif condition:
    ...
else:
    ...
```

## Example

```python
score = 85

if score >= 90:
    print("A")
elif score >= 75:
    print("B")
else:
    print("C")
```

---

# 7. For Loop

A `for` loop processes items one by one.

## Template

```python
for item in iterable:
    # code
```

## Example

```python
movies = ["Leo", "Vikram", "Kaithi"]

for movie in movies:
    print(movie)
```

Output:

```text
Leo
Vikram
Kaithi
```

---

# 8. range()

Used frequently with loops.

```python
range(5)
```

Produces:

```text
0 1 2 3 4
```

Examples:

```python
for i in range(5):
    print(i)

for i in range(1, 6):
    print(i)

for i in range(0, 10, 2):
    print(i)
```

---

# 9. While Loop

Repeats while a condition remains true.

## Template

```python
while condition:
    # code
```

## Example

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Be careful with infinite loops:

```python
# Dangerous if count never changes
while count <= 5:
    print(count)
```

---

# 10. break

Stops the loop completely.

```python
for i in range(10):
    if i == 5:
        break

    print(i)
```

Output:

```text
0
1
2
3
4
```

---

# 11. continue

Skips the current iteration.

```python
for i in range(5):
    if i == 2:
        continue

    print(i)
```

Output:

```text
0
1
3
4
```

---

# 12. Lists

Lists store multiple values.

```python
numbers = [10, 20, 30, 40]
```

Lists are ordered and mutable.

## Access

```python
print(numbers[0])
print(numbers[-1])
```

## Change

```python
numbers[0] = 100
```

---

# 13. List Slicing

## Template

```python
list[start:stop:step]
```

Example:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
print(numbers[:3])
print(numbers[2:])
print(numbers[::-1])
```

Remember:

`stop` is excluded.

---

# 14. List Methods

## append()

Adds one item.

```python
numbers.append(60)
```

## remove()

Removes a value.

```python
numbers.remove(30)
```

## pop()

Removes by index and returns the value.

```python
value = numbers.pop()
```

## sort()

```python
numbers.sort()
```

Descending:

```python
numbers.sort(reverse=True)
```

## reverse()

```python
numbers.reverse()
```

---

# 15. Tuples

Tuples are ordered but immutable.

```python
person = ("Vishnu", 24, "India")
```

Access:

```python
print(person[0])
```

You cannot normally change an element:

```python
# person[0] = "Alex"  # Error
```

Use tuples when the collection should not be modified.

---

# 16. Sets

Sets store unique values.

```python
numbers = {1, 2, 3, 3, 4}

print(numbers)
```

Result contains each value once.

## Membership

```python
if 3 in numbers:
    print("Found")
```

This is extremely useful for DSA.

## Duplicate removal

```python
numbers = [1, 2, 2, 3, 3, 4]

unique = set(numbers)

print(unique)
```

---

# 17. Dictionaries

Dictionaries store key-value pairs.

```python
person = {
    "name": "Vishnu",
    "age": 24,
    "city": "Chennai"
}
```

## Access

```python
print(person["name"])
```

## get()

Safer when a key may not exist.

```python
print(person.get("salary"))
```

## Add / update

```python
person["salary"] = 50000
```

## keys()

```python
print(person.keys())
```

## values()

```python
print(person.values())
```

## items()

```python
for key, value in person.items():
    print(key, value)
```

---

# 18. Functions

Functions package reusable logic.

## Template

```python
def function_name(parameters):
    # logic
    return result
```

## Example

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

## Why functions matter

Instead of repeating:

```python
print(10 + 20)
print(30 + 40)
print(50 + 60)
```

we write reusable logic:

```python
def add(a, b):
    return a + b
```

---

# 19. return vs print

`print()` displays something.

`return` sends a value back to the caller.

```python
def square(number):
    return number * number

result = square(5)

print(result)
```

This distinction becomes very important in DSA.

---

# 20. List Comprehension

A compact way to create lists.

## Normal

```python
squares = []

for number in range(5):
    squares.append(number * number)
```

## Comprehension

```python
squares = [number * number for number in range(5)]
```

## With condition

```python
even_numbers = [
    number
    for number in range(10)
    if number % 2 == 0
]
```

Mental template:

```python
[result for item in iterable if condition]
```

---

# 21. enumerate()

Use `enumerate()` when we need both index and value.

```python
movies = ["Leo", "Vikram", "Kaithi"]

for index, movie in enumerate(movies):
    print(index, movie)
```

Output:

```text
0 Leo
1 Vikram
2 Kaithi
```

Template:

```python
for index, value in enumerate(iterable):
    ...
```

---

# 22. zip()

Combines values from multiple iterables.

```python
names = ["Vijay", "Ajith", "Dhanush"]
movies = ["Leo", "Mankatha", "Raayan"]

for name, movie in zip(names, movies):
    print(name, movie)
```

Template:

```python
for a, b in zip(list1, list2):
    ...
```

---

# 23. map()

Applies a function to every item.

```python
numbers = [1, 2, 3, 4]

result = list(map(lambda x: x * 2, numbers))

print(result)
```

Output:

```text
[2, 4, 6, 8]
```

Template:

```python
result = list(map(function, iterable))
```

---

# 24. filter()

Keeps items that satisfy a condition.

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = list(
    filter(lambda x: x % 2 == 0, numbers)
)

print(even_numbers)
```

Output:

```text
[2, 4, 6]
```

Template:

```python
result = list(filter(condition_function, iterable))
```

---

# 25. lambda

A small anonymous function.

```python
square = lambda x: x * x

print(square(5))
```

Equivalent normal function:

```python
def square(x):
    return x * x
```

Lambda is especially common with:

```python
map()
filter()
sorted()
```

---

# 26. Nested Loops

A loop inside another loop.

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

Useful for:

- Matrix problems
- Pair comparisons
- Combinations
- 2D arrays

---

# 27. Nested Data

Real-world data is often nested.

Example:

```python
employees = [
    {"name": "Arun", "salary": 50000},
    {"name": "Bala", "salary": 60000},
    {"name": "Cathy", "salary": 70000}
]
```

Access:

```python
print(employees[0]["name"])
```

Loop:

```python
for employee in employees:
    print(employee["name"], employee["salary"])
```

Filter:

```python
for employee in employees:
    if employee["salary"] > 55000:
        print(employee["name"])
```

This is important for JSON/API/data-engineering work.

---

# 28. Strings

Strings are sequences of characters.

```python
name = "Python"
```

## Indexing

```python
print(name[0])
print(name[-1])
```

## Slicing

```python
print(name[1:4])
print(name[::-1])
```

---

# 29. String Methods

```python
text = "  Python Data Engineering  "

print(text.upper())
print(text.lower())
print(text.strip())
print(text.replace("Python", "SQL"))
```

## split()

```python
text = "Python SQL PySpark"

words = text.split()

print(words)
```

## join()

```python
words = ["Python", "SQL", "PySpark"]

result = " | ".join(words)

print(result)
```

## startswith / endswith

```python
filename = "sales.csv"

print(filename.endswith(".csv"))
```

## find()

```python
text = "Python"

print(text.find("th"))
```

---

# 30. Basic Exception Handling

Exceptions prevent a program from crashing unexpectedly when we can handle the error.

## Template

```python
try:
    # risky code
except SomeError:
    # recovery / handling
```

## Example

```python
try:
    age = int(input("Enter age: "))
    print(age)
except ValueError:
    print("Please enter a valid number.")
```

Current level: basic `try` / `except`.

Advanced exceptions are still pending:

- `else`
- `finally`
- `raise`
- Custom exceptions

---

# 31. Generators

A generator produces values lazily instead of creating everything at once.

## Template

```python
def generator_function():
    yield value
```

## Example

```python
def numbers():
    yield 1
    yield 2
    yield 3

gen = numbers()

print(next(gen))
print(next(gen))
print(next(gen))
```

Output:

```text
1
2
3
```

---

# 32. yield

`yield` pauses a generator and remembers its state.

Example:

```python
def count():
    yield 1
    yield 2
    yield 3
```

When:

```python
gen = count()
```

the function does not immediately produce all values.

When:

```python
next(gen)
```

it resumes until the next `yield`.

---

# 33. Generator Expressions

List comprehension:

```python
numbers = [x * x for x in range(1000000)]
```

This creates the list immediately.

Generator:

```python
numbers = (x * x for x in range(1000000))
```

This produces values lazily.

Use generators when processing large data streams or files where loading everything into memory is undesirable.

---

# 34. Basic OOP

OOP organizes code using objects containing data and behavior.

## Class

A class is a blueprint.

```python
class Player:
    pass
```

## Object

An object is an instance of a class.

```python
player1 = Player()
```

---

# 35. __init__()

`__init__()` initializes an object.

```python
class Player:

    def __init__(self, name, health, coins):
        self.name = name
        self.health = health
        self.coins = coins
```

Create an object:

```python
player1 = Player("Vijay", 100, 500)

print(player1.name)
print(player1.health)
```

---

# 36. self

`self` refers to the current object.

```python
class Player:

    def __init__(self, name):
        self.name = name
```

When:

```python
player1 = Player("Vijay")
```

`self` refers to `player1`.

---

# 37. Methods

Methods are functions defined inside a class.

```python
class Player:

    def __init__(self, name, health, coins):
        self.name = name
        self.health = health
        self.coins = coins

    def take_damage(self, damage):
        self.health -= damage

    def add_coins(self, coins):
        self.coins += coins
```

Use:

```python
player = Player("Vijay", 100, 500)

player.take_damage(20)
player.add_coins(100)

print(player.health)
print(player.coins)
```

---

# 38. Problem-Solving Patterns

These are the first DSA patterns practiced in Python.

---

## 38.1 Traversal

Visit every element.

```python
numbers = [10, 20, 30, 40]

for num in numbers:
    print(num)
```

---

## 38.2 Index Traversal

Use the index when position matters.

```python
numbers = [10, 20, 30]

for i in range(len(numbers)):
    print(i, numbers[i])
```

---

## 38.3 Accumulator

Use a variable to build a result.

```python
numbers = [10, 20, 30]

total = 0

for num in numbers:
    total += num

print(total)
```

Template:

```python
result = initial_value

for item in data:
    result = update(result, item)
```

---

## 38.4 Counting

Count elements satisfying a condition.

```python
numbers = [10, 15, 20, 25, 30]

count = 0

for num in numbers:
    if num > 20:
        count += 1

print(count)
```

---

## 38.5 Maximum

```python
numbers = [10, 45, 22, 90, 31]

maximum = numbers[0]

for num in numbers:
    if num > maximum:
        maximum = num

print(maximum)
```

---

## 38.6 Minimum

```python
numbers = [10, 45, 22, 90, 31]

minimum = numbers[0]

for num in numbers:
    if num < minimum:
        minimum = num

print(minimum)
```

---

## 38.7 Searching

```python
numbers = [10, 20, 30, 40]

target = 30
found = False

for num in numbers:
    if num == target:
        found = True
        break

print(found)
```

---

## 38.8 Filtering

```python
numbers = [10, 15, 20, 25, 30]

result = []

for num in numbers:
    if num % 2 == 0:
        result.append(num)

print(result)
```

---

## 38.9 Transformation

Change every element.

```python
numbers = [1, 2, 3, 4]

result = []

for num in numbers:
    result.append(num * num)

print(result)
```

---

# 39. Frequency Counting

Frequency counting is one of the most important DSA patterns.

Use a dictionary to store:

```text
value → number of occurrences
```

## Template

```python
freq = {}

for item in data:
    if item in freq:
        freq[item] += 1
    else:
        freq[item] = 1
```

## Example

```python
nums = [2, 3, 2, 5, 3, 2]

freq = {}

for num in nums:
    if num in freq:
        freq[num] += 1
    else:
        freq[num] = 1

print(freq)
```

Output:

```text
{2: 3, 3: 2, 5: 1}
```

---

# 40. Most Frequent Element

```python
nums = [2, 3, 2, 5, 3, 2]

freq = {}

for num in nums:
    if num in freq:
        freq[num] += 1
    else:
        freq[num] = 1

most_frequent = None
highest_count = 0

for num, count in freq.items():
    if count > highest_count:
        highest_count = count
        most_frequent = num

print(most_frequent)
```

---

# 41. Find Elements Appearing Exactly Once

```python
nums = [2, 3, 2, 5, 3, 7]

freq = {}

for num in nums:
    if num in freq:
        freq[num] += 1
    else:
        freq[num] = 1

for num, count in freq.items():
    if count == 1:
        print(num)
```

---

# 42. Current DSA Progress

## Arrays

Learned patterns:

- Basic traversal
- Index traversal
- Accumulator
- Counting
- Maximum
- Minimum
- Searching
- Filtering
- Transformation
- Frequency counting
- Most frequent element
- Exactly once

## Current Hashing Concepts

Hashing is mainly about fast lookup.

### Set

Use when the question is:

> "Have I seen this?"

```python
seen = set()

for num in nums:
    if num in seen:
        print("Duplicate")
    seen.add(num)
```

### Dictionary

Use when the question is:

> "How many?" or "What value belongs to this key?"

```python
freq = {}

for num in nums:
    freq[num] = freq.get(num, 0) + 1
```

Important hashing patterns still to practice:

- Duplicate detection
- Frequency counting
- Most frequent element
- Unique elements
- Two Sum
- Grouping
- Intersection
- Difference
- Prefix sum + hashmap

---

# 43. Python Concepts Still Pending

These have not yet been properly covered and should NOT be marked as completed.

## Files

```python
with open("data.txt", "r") as file:
    content = file.read()
```

To learn:
- Reading
- Writing
- `with`
- `pathlib`
- Large files

## CSV

```python
import csv

with open("sales.csv", newline="") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row)
```

## JSON

```python
import json

with open("data.json") as file:
    data = json.load(file)
```

## Advanced Exceptions

```python
try:
    ...
except ValueError:
    ...
else:
    ...
finally:
    ...
```

Also:

```python
raise ValueError("Invalid value")
```

## Modules and Packages

```python
import math
from pathlib import Path
```

To learn:
- Creating modules
- Imports
- Packages
- `__init__.py`

## Virtual Environments

```bash
python -m venv .venv
```

Activate the environment and manage packages using `pip`.

## APIs

Expected future pattern:

```python
import requests

response = requests.get(
    "https://api.example.com/data",
    timeout=10
)

data = response.json()
```

To learn:
- GET
- POST
- Parameters
- Headers
- Authentication
- JSON
- Status codes
- Timeouts
- Retries
- Pagination

## Database Connectivity

Future goal:

```text
Python
   ↓
Database connection
   ↓
SQL query
   ↓
Fetch / transform data
   ↓
Load data
```

## Logging

```python
import logging

logging.basicConfig(level=logging.INFO)

logging.info("Pipeline started")
logging.warning("Missing value")
logging.error("Pipeline failed")
```

## pytest

Future pattern:

```python
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5
```

## Type Hints

```python
def add(a: int, b: int) -> int:
    return a + b
```

## Dataclasses

```python
from dataclasses import dataclass

@dataclass
class Employee:
    name: str
    salary: int
```

## Advanced OOP

Still to learn:

- Inheritance
- Composition
- Encapsulation
- Class methods
- Static methods
- Properties
- Dataclasses
- Abstract classes / interfaces concepts

---

# 44. Learning Rule

The objective is NOT:

```text
Watch course
↓
Copy code
↓
Finish course
```

The objective is:

```text
Understand
↓
Write without AI
↓
Run
↓
Debug
↓
Explain
↓
Solve unfamiliar problem
↓
Build
↓
Deploy
```

A topic is considered genuinely learned only when I can use it independently.

---

# 45. Current Python Target

Build enough Python skill to independently handle:

```text
Python
├── DSA
├── Data Engineering
├── Backend
├── APIs
├── ETL
├── Database interaction
├── Automation
├── GenAI
└── Technical interviews
```

---

# 46. Revision Checklist

- [x] Variables
- [x] Data types
- [x] Input / Output
- [x] Type conversion
- [x] Operators
- [x] Conditions
- [x] for loop
- [x] while loop
- [x] range()
- [x] break / continue
- [x] Lists
- [x] List slicing
- [x] List methods
- [x] Tuples
- [x] Sets
- [x] Dictionaries
- [x] Functions
- [x] List comprehensions
- [x] enumerate()
- [x] zip()
- [x] map()
- [x] filter()
- [x] lambda
- [x] Nested loops
- [x] Nested data
- [x] Strings
- [x] Basic exceptions
- [x] Generators
- [x] Generator expressions
- [x] Basic OOP
- [x] Basic DSA patterns
- [x] Basic hashing concepts

## Not Yet Completed

- [ ] File handling
- [ ] CSV
- [ ] JSON
- [ ] Advanced exceptions
- [ ] Modules / packages
- [ ] venv / pip
- [ ] APIs
- [ ] Database connectivity
- [ ] Logging
- [ ] pytest
- [ ] Type hints
- [ ] Dataclasses
- [ ] Advanced OOP
- [ ] Production Python
- [ ] Python ETL
- [ ] Large-file processing
- [ ] Production API ingestion
- [ ] Python database pipelines
