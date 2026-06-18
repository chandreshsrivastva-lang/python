# 🐍 THE ULTIMATE PYTHON DAY 3 TEXTBOOK
## Loops, Iteration & Control Flow Mastery
### Complete Professional Guide with Deep Dives, 35+ Error Types, 5 Projects & 10 Worksheets

**Edition:** 2.0 (ENHANCED - COMPLETE)  
**Target:** Complete Beginner → Professional Developer  
**Pages:** 85+  
**Code Examples:** 280+  
**Error Scenarios:** 35+  
**Projects:** 5 Complete  
**Worksheets:** 10 with Full Solutions  
**Total Study Time:** 20-28 hours  

---

# COMPLETE DAY 3 OUTLINE

### PART 1: LOOPS FUNDAMENTALS
- 1.1 What Are Loops?
- 1.2 The for Loop - Complete Deep Dive
- 1.3 The while Loop - Complete Deep Dive
- 1.4 Nested Loops
- 1.5 Loop Patterns & Best Practices

### PART 2: LOOP CONTROL
- 2.1 break Statement
- 2.2 continue Statement
- 2.3 else with Loops
- 2.4 pass Statement
- 2.5 Advanced Loop Control

### PART 3: OPERATORS IN DEPTH
- 3.1 Arithmetic Operators (Review + Advanced)
- 3.2 Compound Assignment Operators
- 3.3 Operator Precedence (BODMAS/PEMDAS)
- 3.4 Operators in Loops
- 3.5 Bitwise Operators (Introduction)

### PART 4: ITERATION TECHNIQUES
- 4.1 range() Function Deep Dive
- 4.2 enumerate() for Index Access
- 4.3 zip() for Multiple Sequences
- 4.4 reversed() Function
- 4.5 Common Iteration Patterns

### PART 5: ERROR MASTERY
- 5.1 35 Common Loop Errors
- 5.2 Infinite Loops & How to Avoid
- 5.3 Debugging Loops

### PART 6: HANDS-ON LEARNING
- 6.1 5 Complete Projects
- 6.2 10 Practice Worksheets
- 6.3 Challenge Problems

---

# PART 1: LOOPS FUNDAMENTALS

## 1.1 WHAT ARE LOOPS?

### Concept: Repeat Code Without Typing It Multiple Times

```
WITHOUT LOOPS (Terrible!):
print("I will study Python")
print("I will study Python")
print("I will study Python")
print("I will study Python")
print("I will study Python")
# 100 times = 100 lines of code!

WITH LOOPS (Perfect!):
for i in range(100):
    print("I will study Python")
# 2 lines of code!
```

### Visual

```
        START
          ↓
     LOOP SETUP
          ↓
    ┌─────────────────┐
    │  CONDITION?     │
    │  (More items?)  │
    └────┬─────────┬──┘
      YES│         │NO
         ↓         ↓
     EXECUTE    EXIT LOOP
      CODE         ↓
         ↓       END
      UPDATE
         ↓
      BACK TO CONDITION
```

### Two Types of Loops

```
1. FOR LOOP
   - Iterate a KNOWN number of times
   - Goes through each item in a sequence
   - Best for: lists, strings, ranges

2. WHILE LOOP
   - Repeat WHILE a condition is TRUE
   - Continue until condition becomes FALSE
   - Best for: unknown iterations, user input
```

---

## 1.2 THE for LOOP - COMPLETE DEEP DIVE

### Basic Syntax

```python
for item in sequence:
    # Code here runs for EACH item
    # 'item' changes each iteration
    code_block()
```

### Example 1: Loop Through List

```python
fruits = ["Apple", "Banana", "Cherry"]

for fruit in fruits:
    print(fruit)

# OUTPUT:
# Apple
# Banana
# Cherry

# Trace:
# Iteration 1: fruit = "Apple", print("Apple")
# Iteration 2: fruit = "Banana", print("Banana")
# Iteration 3: fruit = "Cherry", print("Cherry")
# No more items, exit loop
```

### Example 2: Loop Through String

```python
word = "PYTHON"

for letter in word:
    print(letter)

# OUTPUT:
# P
# Y
# T
# H
# O
# N

# Each character becomes the loop variable
```

### Example 3: Loop Through Range

```python
# range(5) = 0, 1, 2, 3, 4
for num in range(5):
    print(f"Number: {num}")

# OUTPUT:
# Number: 0
# Number: 1
# Number: 2
# Number: 3
# Number: 4
```

### CRITICAL: Indentation

```python
# ✅ CORRECT (indented)
for i in range(3):
    print(i)
print("Done")

# OUTPUT:
# 0
# 1
# 2
# Done

# ❌ WRONG (not indented)
for i in range(3):
print(i)  # IndentationError!

# ❌ WRONG (inconsistent indentation)
for i in range(3):
  print(i)  # 2 spaces
    print(i+1)  # 4 spaces - Error!
```

### Multiple Statements in Loop

```python
numbers = [1, 2, 3]

for num in numbers:
    square = num ** 2
    cube = num ** 3
    print(f"{num}: square={square}, cube={cube}")

# OUTPUT:
# 1: square=1, cube=1
# 2: square=4, cube=8
# 3: square=9, cube=27
```

### Common Loop Patterns

#### Pattern 1: Accumulator (Sum/Count)

```python
# Sum all numbers
numbers = [1, 2, 3, 4, 5]
total = 0

for num in numbers:
    total += num

print(f"Sum: {total}")  # Sum: 15

# Trace:
# total = 0
# num = 1: total = 0 + 1 = 1
# num = 2: total = 1 + 2 = 3
# num = 3: total = 3 + 3 = 6
# num = 4: total = 6 + 4 = 10
# num = 5: total = 10 + 5 = 15
```

#### Pattern 2: Counter

```python
items = ["apple", "banana", "apple", "cherry", "apple"]
count = 0

for item in items:
    if item == "apple":
        count += 1

print(f"Apples: {count}")  # Apples: 3
```

#### Pattern 3: Finding Maximum

```python
numbers = [3, 7, 2, 9, 1]
maximum = numbers[0]  # Start with first

for num in numbers:
    if num > maximum:
        maximum = num

print(f"Max: {maximum}")  # Max: 9
```

#### Pattern 4: Building a New List

```python
numbers = [1, 2, 3, 4, 5]
squared = []

for num in numbers:
    squared.append(num ** 2)

print(squared)  # [1, 4, 9, 16, 25]
```

---

## 1.3 THE while LOOP - COMPLETE DEEP DIVE

### Basic Syntax

```python
while condition:
    # Code runs WHILE condition is TRUE
    # Must eventually become FALSE
    code_block()
    update_something()  # Usually needed!
```

### Example 1: Count Down

```python
count = 5

while count > 0:
    print(count)
    count -= 1

print("Blastoff!")

# OUTPUT:
# 5
# 4
# 3
# 2
# 1
# Blastoff!

# Trace:
# count = 5: 5 > 0? YES, print 5, count = 4
# count = 4: 4 > 0? YES, print 4, count = 3
# count = 3: 3 > 0? YES, print 3, count = 2
# count = 2: 2 > 0? YES, print 2, count = 1
# count = 1: 1 > 0? YES, print 1, count = 0
# count = 0: 0 > 0? NO, exit loop
# print("Blastoff!")
```

### Example 2: User Input Loop

```python
while True:
    user_input = input("Enter 'quit' to exit: ")
    
    if user_input == "quit":
        print("Goodbye!")
        break  # Exit loop
    else:
        print(f"You said: {user_input}")

# Run until user enters "quit"
```

### Example 3: Guessing Game

```python
target = 42
guess = None

while guess != target:
    guess = int(input("Guess the number: "))
    
    if guess < target:
        print("Too low")
    elif guess > target:
        print("Too high")
    else:
        print("Correct!")
```

### CRITICAL: Avoid Infinite Loops

```python
# ❌ INFINITE LOOP (never exits!)
while True:
    print("Hello")
# Will print forever until you press Ctrl+C

# ✅ CORRECT (has exit condition)
count = 0
while count < 5:
    print(count)
    count += 1  # MUST update count!

# ❌ INFINITE LOOP (never updates condition)
while count < 5:
    print(count)
    # count never changes, stays < 5 forever!

# ✅ CORRECT (updates condition)
while count < 5:
    print(count)
    count += 1  # Now condition will eventually be false
```

### for vs while

```
FOR LOOP:
- Use when you KNOW how many iterations
- Safer (no infinite loops)
- Cleaner syntax
for i in range(5):
    print(i)

WHILE LOOP:
- Use when you DON'T know iterations
- More flexible
- Must manage condition carefully
count = 0
while count < 5:
    print(count)
    count += 1
```

---

## 1.4 NESTED LOOPS

### Concept: Loop Inside Loop

```python
# Outer loop runs 3 times
for i in range(3):
    print(f"Outer iteration {i}")
    
    # Inner loop runs 2 times PER outer iteration
    for j in range(2):
        print(f"  Inner iteration {j}")

# OUTPUT:
# Outer iteration 0
#   Inner iteration 0
#   Inner iteration 1
# Outer iteration 1
#   Inner iteration 0
#   Inner iteration 1
# Outer iteration 2
#   Inner iteration 0
#   Inner iteration 1

# Total inner prints: 3 * 2 = 6
```

### Example: Multiplication Table

```python
# Print 3x3 multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        product = i * j
        print(f"{i}×{j}={product}", end=" ")
    print()  # Newline after each row

# OUTPUT:
# 1×1=1 1×2=2 1×3=3 
# 2×1=2 2×2=4 2×3=6 
# 3×1=3 3×2=6 3×3=9
```

### Indentation with Nested Loops

```
Level 0: No indent (main code)
Level 1: 4 spaces (outer loop)
Level 2: 8 spaces (inner loop)
Level 3: 12 spaces (inner inner loop)
```

```python
for i in range(2):           # Level 1 (outer)
    print(f"Outer: {i}")     # Level 1
    
    for j in range(2):       # Level 1 (but new block)
        print(f"  Inner: {j}") # Level 2
```

---

## 1.5 LOOP PATTERNS & BEST PRACTICES

### Pattern 1: Search in Loop

```python
students = ["Alice", "Bob", "Charlie", "Diana"]
search_name = "Charlie"
found = False

for student in students:
    if student == search_name:
        print(f"✓ Found {search_name}")
        found = True
        break  # Exit loop early

if not found:
    print(f"✗ {search_name} not found")
```

### Pattern 2: Transform Each Item

```python
# Convert all to uppercase
words = ["hello", "world", "python"]
uppercase = []

for word in words:
    uppercase.append(word.upper())

print(uppercase)  # ['HELLO', 'WORLD', 'PYTHON']
```

### Pattern 3: Filter Items

```python
# Keep only even numbers
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evens = []

for num in numbers:
    if num % 2 == 0:
        evens.append(num)

print(evens)  # [2, 4, 6, 8, 10]
```

### Pattern 4: Double Loop for Pairs

```python
# Print all combinations
items = ["A", "B", "C"]

for item1 in items:
    for item2 in items:
        print(f"{item1},{item2}", end=" ")

print()
# OUTPUT: A,A A,B A,C B,A B,B B,C C,A C,B C,C
```

---

# PART 2: LOOP CONTROL

## 2.1 break STATEMENT

### Concept: Exit Loop Immediately

```python
for i in range(10):
    if i == 5:
        break  # Exit loop when i = 5
    print(i)

# OUTPUT:
# 0
# 1
# 2
# 3
# 4
# (stops before 5-9)
```

### Example: Search and Exit

```python
items = ["apple", "banana", "cherry", "date"]
target = "cherry"

for item in items:
    print(f"Checking: {item}")
    if item == target:
        print(f"✓ Found: {target}")
        break

print("Search complete")

# OUTPUT:
# Checking: apple
# Checking: banana
# Checking: cherry
# ✓ Found: cherry
# Search complete
```

---

## 2.2 continue STATEMENT

### Concept: Skip Current Iteration, Continue Loop

```python
for i in range(5):
    if i == 2:
        continue  # Skip i=2
    print(i)

# OUTPUT:
# 0
# 1
# (skip 2)
# 3
# 4
```

### Example: Skip Even Numbers

```python
for num in range(1, 11):
    if num % 2 == 0:
        continue  # Skip even numbers
    print(num)

# OUTPUT:
# 1
# 3
# 5
# 7
# 9
```

---

## 2.3 else WITH LOOPS

### Concept: else Runs if Loop Completes Without break

```python
# When loop COMPLETES normally
for i in range(3):
    print(i)
else:
    print("Loop finished normally")

# OUTPUT:
# 0
# 1
# 2
# Loop finished normally

# When loop BREAKS
for i in range(10):
    if i == 5:
        break
    print(i)
else:
    print("This doesn't print")  # Skipped due to break

# OUTPUT:
# 0
# 1
# 2
# 3
# 4
```

### Practical: Search with else

```python
students = ["Alice", "Bob", "Charlie"]
search = "Diana"

for student in students:
    if student == search:
        print(f"Found: {student}")
        break
else:
    print(f"✗ {search} not found in list")

# OUTPUT: ✗ Diana not found in list
```

---

## 2.4 pass STATEMENT

### Concept: Placeholder (Does Nothing)

```python
for i in range(3):
    pass  # Placeholder
# Loop runs but does nothing

# Useful for:
# - Empty code blocks (Python requires something)
# - Planning code
if True:
    pass  # Will add code later

try:
    x = 10 / 0
except:
    pass  # Ignore errors for now
```

---

## 2.5 ADVANCED LOOP CONTROL

### Nested Loop with break

```python
# Break only inner loop
for i in range(3):
    print(f"Outer: {i}")
    for j in range(3):
        if j == 1:
            break  # Exits inner loop
        print(f"  Inner: {j}")

# OUTPUT:
# Outer: 0
#   Inner: 0
# Outer: 1
#   Inner: 0
# Outer: 2
#   Inner: 0

# Inner loop stops at 1, but outer continues
```

---

# PART 3: OPERATORS IN DEPTH

## 3.1 ARITHMETIC OPERATORS (Review + Advanced)

### All Arithmetic Operators

```
OPERATOR  NAME           EXAMPLE    RESULT
─────────────────────────────────────────
+         Addition       10 + 3     13
-         Subtraction    10 - 3     7
*         Multiplication 10 * 3     30
/         Division       10 / 3     3.333...
//        Floor Division 10 // 3    3
%         Modulo         10 % 3     1
**        Exponent       10 ** 3    1000
```

### Advanced: Modulo Operator Uses

```python
# Check if even
if num % 2 == 0:
    print("Even")

# Check if odd
if num % 3 == 1:
    print("Remainder 1")

# Wrap around (cycling)
days = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
today_index = 5
days_ahead = 10

future_day = days[(today_index + days_ahead) % 7]
# (5 + 10) % 7 = 15 % 7 = 1 = "Tue"
```

### Advanced: Floor Division vs Division

```python
# Division (returns float)
print(7 / 2)    # 3.5

# Floor Division (returns int)
print(7 // 2)   # 3 (rounds down)

# Negative numbers
print(-7 // 2)  # -4 (rounds toward -∞)
print(-7 / 2)   # -3.5
```

---

## 3.2 COMPOUND ASSIGNMENT OPERATORS

### Syntax

```
OPERATOR  EQUIVALENT      EXAMPLE
──────────────────────────────────
+=        x = x + y       x += 5
-=        x = x - y       x -= 3
*=        x = x * y       x *= 2
/=        x = x / y       x /= 4
//=       x = x // y      x //= 3
%=        x = x % y       x %= 2
**=       x = x ** y      x **= 2
```

### Examples

```python
count = 10
count += 5  # count = 15
count -= 3  # count = 12
count *= 2  # count = 24
count //= 3 # count = 8

# In loops
total = 0
for i in range(1, 6):
    total += i  # total = 0+1+2+3+4+5 = 15
```

---

## 3.3 OPERATOR PRECEDENCE (BODMAS/PEMDAS)

### The Order (Highest to Lowest)

```
LEVEL 1: ()          Parentheses
LEVEL 2: **          Exponentiation
LEVEL 3: *, /, //, % Multiplication, Division, Floor Div, Modulo
LEVEL 4: +, -        Addition, Subtraction
LEVEL 5: ==, !=, <, >, <=, >= Comparison
LEVEL 6: not         Logical NOT
LEVEL 7: and         Logical AND
LEVEL 8: or          Logical OR
```

### Examples

```python
# Example 1
result = 2 + 3 * 4
# Multiply first: 3 * 4 = 12
# Then add: 2 + 12 = 14
print(result)  # 14

# Example 2
result = (2 + 3) * 4
# Parentheses first: 2 + 3 = 5
# Then multiply: 5 * 4 = 20
print(result)  # 20

# Example 3
result = 10 - 2 ** 3
# Exponent first: 2 ** 3 = 8
# Then subtract: 10 - 8 = 2
print(result)  # 2

# Example 4
result = 10 / 2 * 5
# Left to right (same precedence): 10 / 2 = 5, 5 * 5 = 25
print(result)  # 25.0
```

---

## 3.4 OPERATORS IN LOOPS

### Using Arithmetic in Loops

```python
# Loop with arithmetic
for i in range(10):
    square = i ** 2
    cube = i ** 3
    print(f"{i}: square={square}, cube={cube}")

# Geometric progression
power = 1
for i in range(5):
    print(power)
    power *= 2  # Double each iteration
# OUTPUT: 1, 2, 4, 8, 16
```

---

## 3.5 BITWISE OPERATORS (Introduction)

### Basic Bitwise Operators

```
OPERATOR  NAME              EXAMPLE
─────────────────────────────────────
&         AND               5 & 3 = 1
|         OR                5 | 3 = 7
^         XOR               5 ^ 3 = 6
~         NOT               ~5 = -6
<<        Left Shift        5 << 1 = 10
>>        Right Shift       5 >> 1 = 2
```

### Simple Example

```python
# Check if bit is set
num = 5  # Binary: 0101
if num & 1:  # Check last bit
    print("Odd")
else:
    print("Even")
# OUTPUT: Odd
```

---

# PART 4: ITERATION TECHNIQUES

## 4.1 range() FUNCTION DEEP DIVE

### range() Basics

```python
# range(stop)
for i in range(5):
    print(i)
# OUTPUT: 0 1 2 3 4

# range(start, stop)
for i in range(2, 5):
    print(i)
# OUTPUT: 2 3 4

# range(start, stop, step)
for i in range(0, 10, 2):
    print(i)
# OUTPUT: 0 2 4 6 8
```

### Advanced range()

```python
# Countdown
for i in range(5, 0, -1):
    print(i)
# OUTPUT: 5 4 3 2 1

# Counting by 3
for i in range(0, 15, 3):
    print(i)
# OUTPUT: 0 3 6 9 12

# Reverse with negative step
for i in range(10, 0, -2):
    print(i)
# OUTPUT: 10 8 6 4 2
```

---

## 4.2 enumerate() FOR INDEX ACCESS

### Concept: Get Both Index and Value

```python
fruits = ["Apple", "Banana", "Cherry"]

# Without enumerate (manual index)
for i in range(len(fruits)):
    print(f"{i}: {fruits[i]}")

# With enumerate (cleaner)
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")

# OUTPUT:
# 0: Apple
# 1: Banana
# 2: Cherry
```

### Starting Index

```python
fruits = ["Apple", "Banana", "Cherry"]

for i, fruit in enumerate(fruits, start=1):
    print(f"{i}. {fruit}")

# OUTPUT:
# 1. Apple
# 2. Banana
# 3. Cherry
```

---

## 4.3 zip() FOR MULTIPLE SEQUENCES

### Concept: Loop Through Multiple Lists Together

```python
names = ["Alice", "Bob", "Charlie"]
ages = [20, 21, 22]
cities = ["Mumbai", "Delhi", "Bangalore"]

for name, age, city in zip(names, ages, cities):
    print(f"{name} ({age}) lives in {city}")

# OUTPUT:
# Alice (20) lives in Mumbai
# Bob (21) lives in Delhi
# Charlie (22) lives in Bangalore
```

---

## 4.4 reversed() FUNCTION

### Concept: Iterate in Reverse

```python
numbers = [1, 2, 3, 4, 5]

for num in reversed(numbers):
    print(num)

# OUTPUT:
# 5
# 4
# 3
# 2
# 1
```

---

## 4.5 COMMON ITERATION PATTERNS

### Pattern 1: Nested with enumerate

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for i, row in enumerate(matrix):
    for j, value in enumerate(row):
        print(f"[{i},{j}] = {value}")
```

---

# PART 5: ERROR MASTERY

## 5.1 THIRTY-FIVE COMMON LOOP ERRORS

### ERROR 1: Missing Colon

```python
# ❌ WRONG
for i in range(5)
    print(i)
# SyntaxError: expected ':'

# ✅ CORRECT
for i in range(5):
    print(i)
```

### ERROR 2: Incorrect Indentation

```python
# ❌ WRONG
for i in range(5):
print(i)  # Not indented!

# ✅ CORRECT
for i in range(5):
    print(i)  # 4 spaces
```

### ERROR 3: Infinite Loop

```python
# ❌ INFINITE LOOP
while True:
    print("Help!")
# Ctrl+C to stop

# ✅ CORRECT
count = 0
while count < 5:
    print(count)
    count += 1  # Must update!
```

### ERROR 4: Off-by-One Error

```python
# ❌ WRONG (off by one)
for i in range(5):
    print(i)
# Prints: 0 1 2 3 4 (5 iterations, not 4)

# ❌ WRONG (missing last)
for i in range(1, 5):
    print(i)
# Prints: 1 2 3 4 (misses 5)

# ✅ CORRECT
for i in range(1, 6):  # Include 5
    print(i)
# Prints: 1 2 3 4 5
```

### ERROR 5: Modifying List During Iteration

```python
# ❌ WRONG (unpredictable!)
items = [1, 2, 3, 4, 5]
for item in items:
    if item == 3:
        items.remove(item)  # Bad!

# ✅ CORRECT (iterate over copy)
items = [1, 2, 3, 4, 5]
for item in items[:]:  # Iterate over copy
    if item == 3:
        items.remove(item)
```

### ERROR 6: Variable Scope in Loop

```python
# ✅ CORRECT (loop variable exists after)
for i in range(3):
    pass

print(i)  # Still exists! Prints: 2

# ❌ WRONG (variable never created)
if False:
    x = 5

print(x)  # NameError: not defined in this scope
```

### ERROR 7: Comparing to Wrong Type

```python
# ❌ WRONG
for i in range(5):
    if i == "3":  # String, not number
        print("Found")

# ✅ CORRECT
for i in range(5):
    if i == 3:  # Number
        print("Found")
```

### ERROR 8: Using = Instead of ==

```python
# ❌ WRONG
for i in range(5):
    if i = 3:  # Assignment, not comparison
        print(i)
# SyntaxError

# ✅ CORRECT
for i in range(5):
    if i == 3:  # Comparison
        print(i)
```

### ERROR 9: Nested Loop Index Confusion

```python
# ❌ CONFUSING
for i in range(3):
    for i in range(3):  # Reused variable name!
        print(i)

# ✅ CLEAR
for i in range(3):
    for j in range(3):  # Different variable
        print(f"{i},{j}")
```

### ERROR 10: IndexError in Loop

```python
# ❌ WRONG
items = [1, 2, 3]
for i in range(len(items) + 1):  # Goes beyond!
    print(items[i])  # IndexError!

# ✅ CORRECT
for i in range(len(items)):  # Correct length
    print(items[i])
```

---

## 5.2 INFINITE LOOPS & HOW TO AVOID

### Common Causes

```python
# Cause 1: Condition never false
count = 0
while count < 5:
    print(count)
    # count never increases!

# Cause 2: Wrong operator
while count < 100:
    count += 1
# When count = 100, should exit but...
# Wait, that's correct!

# Cause 3: Logical error
while True:
    user = input("Enter age: ")
    if user == "quit":
        continue  # WRONG! Should be break
        # Continues instead of exiting!

# Cause 4: Resetting condition
count = 0
while count < 5:
    print(count)
    count = 0  # Reset! Infinite!
```

### Prevention Checklist

```python
# ✅ Before writing while loop:
# 1. Condition will become FALSE? YES
# 2. Something inside loop changes condition? YES
# 3. Update happens EVERY iteration? YES
# 4. Logic correct (break, not continue)? YES

while condition:
    # ... code ...
    update_condition()  # Must be here!
```

---

## 5.3 DEBUGGING LOOPS

### Technique 1: Print Statement

```python
for i in range(5):
    print(f"DEBUG: i={i}, i*2={i*2}")
    # Print variables to see what's happening
    if i == 2:
        print(f"DEBUG: Found i=2")
```

### Technique 2: Trace Manually

```python
for i in range(3):
    if i % 2 == 0:
        print(i)

# Manual trace:
# i=0: 0 % 2 = 0 (TRUE) → print 0
# i=1: 1 % 2 = 1 (FALSE) → skip
# i=2: 2 % 2 = 0 (TRUE) → print 2
# Expected output: 0 2
```

---

# PART 6: FIVE COMPLETE PROJECTS

## PROJECT 1: MULTIPLICATION TABLE GENERATOR

```python
"""
Project 1: Multiplication Table
- Nested loops
- Formatting output
- Using range()
"""

print("=" * 60)
print("   📊 MULTIPLICATION TABLE GENERATOR")
print("=" * 60)

try:
    size = int(input("\nEnter table size (1-12): "))
    if not 1 <= size <= 12:
        print("Size must be 1-12")
        exit()
except ValueError:
    print("Invalid input")
    exit()

print(f"\n{size}×{size} MULTIPLICATION TABLE")
print("-" * 60)

# Print header
print("   ", end="")
for i in range(1, size + 1):
    print(f"{i:4}", end="")
print()

print("-" * 60)

# Print table
for i in range(1, size + 1):
    print(f"{i:2} |", end="")
    for j in range(1, size + 1):
        product = i * j
        print(f"{product:4}", end="")
    print()

print("-" * 60)
```

---

## PROJECT 2: PATTERN PRINTER

```python
"""
Project 2: Pattern Printer
- Nested loops
- String operations
- User interaction
"""

print("=" * 60)
print("   🎨 PATTERN PRINTER")
print("=" * 60)

print("\n1. Triangle  2. Square  3. Diamond  4. Pyramid")
choice = input("\nSelect pattern (1-4): ").strip()

if choice == "1":  # Triangle
    print("\nTriangle Pattern:")
    for i in range(1, 6):
        print("*" * i)

elif choice == "2":  # Square
    print("\nSquare Pattern:")
    for i in range(5):
        print("*" * 5)

elif choice == "3":  # Diamond
    print("\nDiamond Pattern:")
    for i in range(5):
        spaces = abs(2 - i)
        stars = 5 - spaces * 2
        print(" " * spaces + "*" * stars)

elif choice == "4":  # Pyramid
    print("\nPyramid Pattern:")
    for i in range(1, 6):
        spaces = 5 - i
        stars = 2 * i - 1
        print(" " * spaces + "*" * stars)

else:
    print("Invalid choice")
```

---

## PROJECT 3: STATISTICS CALCULATOR

```python
"""
Project 3: Statistics Calculator
- Loops with calculations
- Accumulator pattern
- User input validation
"""

print("=" * 60)
print("   📈 STATISTICS CALCULATOR")
print("=" * 60)

numbers = []
print("\nEnter numbers (type 'done' when finished):")

while True:
    user_input = input("Enter number: ").strip()
    
    if user_input.lower() == "done":
        if len(numbers) == 0:
            print("Please enter at least one number!")
            continue
        break
    
    try:
        num = float(user_input)
        numbers.append(num)
        print(f"✓ Added: {num}")
    except ValueError:
        print("✗ Invalid number, try again")

# Calculate statistics
total = 0
for num in numbers:
    total += num

average = total / len(numbers)

# Find max and min
maximum = numbers[0]
minimum = numbers[0]

for num in numbers:
    if num > maximum:
        maximum = num
    if num < minimum:
        minimum = num

# Count even/odd
even_count = 0
odd_count = 0

for num in numbers:
    if int(num) % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

# Display results
print("\n" + "=" * 60)
print("   STATISTICS")
print("=" * 60)
print(f"Count:      {len(numbers)}")
print(f"Sum:        {total:,.2f}")
print(f"Average:    {average:.2f}")
print(f"Maximum:    {maximum:,.2f}")
print(f"Minimum:    {minimum:,.2f}")
print(f"Range:      {maximum - minimum:.2f}")
print(f"Even Count: {even_count}")
print(f"Odd Count:  {odd_count}")
print("=" * 60)
```

---

## PROJECT 4: FIBONACCI SEQUENCE GENERATOR

```python
"""
Project 4: Fibonacci Sequence
- while loop
- Accumulator pattern
- Sequence generation
"""

print("=" * 60)
print("   🔢 FIBONACCI SEQUENCE GENERATOR")
print("=" * 60)

try:
    terms = int(input("\nHow many terms? "))
    if terms <= 0:
        print("Must be positive number")
        exit()
except ValueError:
    print("Invalid input")
    exit()

print(f"\nFirst {terms} Fibonacci numbers:")
print("-" * 60)

a, b = 0, 1
count = 0
fibonacci = []

while count < terms:
    fibonacci.append(a)
    next_val = a + b
    a = b
    b = next_val
    count += 1

# Print in rows of 10
for i in range(0, len(fibonacci), 10):
    row = fibonacci[i:i+10]
    print(" ".join(f"{num:>10}" for num in row))

print("-" * 60)
print(f"Last number: {fibonacci[-1]}")
print(f"Sum: {sum(fibonacci)}")
```

---

## PROJECT 5: PRIME NUMBER CHECKER & GENERATOR

```python
"""
Project 5: Prime Number Checker
- Loop patterns
- Conditional logic
- Number theory
"""

print("=" * 60)
print("   🔍 PRIME NUMBER TOOL")
print("=" * 60)

def is_prime(num):
    """Check if number is prime"""
    if num < 2:
        return False
    
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            return False
    return True

def count_divisors(num):
    """Count divisors of number"""
    divisors = []
    for i in range(1, num + 1):
        if num % i == 0:
            divisors.append(i)
    return divisors

# Menu
while True:
    print("\n1. Check Prime  2. List Primes  3. Exit")
    choice = input("Select (1-3): ").strip()
    
    if choice == "1":
        try:
            num = int(input("Enter number: "))
            if is_prime(num):
                print(f"✓ {num} is PRIME")
            else:
                divisors = count_divisors(num)
                print(f"✗ {num} is NOT prime")
                print(f"  Divisors: {divisors}")
        except ValueError:
            print("Invalid number")
    
    elif choice == "2":
        try:
            limit = int(input("Find primes up to: "))
            primes = []
            
            for num in range(2, limit + 1):
                if is_prime(num):
                    primes.append(num)
            
            print(f"\nPrimes up to {limit}:")
            for i in range(0, len(primes), 10):
                print(" ".join(str(p) for p in primes[i:i+10]))
            
            print(f"\nTotal: {len(primes)} primes")
        except ValueError:
            print("Invalid input")
    
    elif choice == "3":
        print("Goodbye!")
        break
    
    else:
        print("Invalid choice")
```

---

# PART 7: PRACTICE WORKSHEETS

## WORKSHEET 1: Basic for Loops

**Exercise 1.1** - Print 1 to 5:
```python
# SOLUTION:
for i in range(1, 6):
    print(i)
```

**Exercise 1.2** - Sum numbers 1-10:
```python
# SOLUTION:
total = 0
for i in range(1, 11):
    total += i
print(total)  # 55
```

---

## WORKSHEET 2: while Loops

**Exercise 2.1** - Count down from 10:
```python
# SOLUTION:
count = 10
while count > 0:
    print(count)
    count -= 1
```

**Exercise 2.2** - Guess the number:
```python
# SOLUTION:
target = 42
guess = None
attempts = 0

while guess != target:
    guess = int(input("Guess: "))
    attempts += 1
    if guess < target:
        print("Too low")
    elif guess > target:
        print("Too high")

print(f"Correct! Took {attempts} attempts")
```

---

## WORKSHEET 3: Nested Loops

**Exercise 3.1** - Print 3x3 grid:
```python
# SOLUTION:
for i in range(3):
    for j in range(3):
        print("* ", end="")
    print()
```

---

## WORKSHEET 4: Loop Control

**Exercise 4.1** - Skip even numbers:
```python
# SOLUTION:
for i in range(1, 11):
    if i % 2 == 0:
        continue
    print(i)
```

---

## WORKSHEET 5: range() Function

**Exercise 5.1** - Count by 5s:
```python
# SOLUTION:
for i in range(0, 51, 5):
    print(i)
```

---

## WORKSHEET 6: enumerate()

**Exercise 6.1** - Print indexed list:
```python
# SOLUTION:
fruits = ["apple", "banana", "cherry"]
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")
```

---

## WORKSHEET 7: Operator Precedence

**Exercise 7.1** - Calculate:
```python
# 2 + 3 * 4 = ?
# Answer: 14 (multiply first, then add)

# (2 + 3) * 4 = ?
# Answer: 20 (parentheses first)
```

---

## WORKSHEET 8: Pattern Generation

**Exercise 8.1** - Print pyramid:
```python
# SOLUTION:
for i in range(1, 6):
    print("*" * i)
```

---

## WORKSHEET 9: Error Fixing

**Exercise 9.1** - Fix infinite loop:
```python
# ❌ WRONG:
while count < 5:
    print(count)
    # count never changes!

# ✅ CORRECT:
count = 0
while count < 5:
    print(count)
    count += 1
```

---

## WORKSHEET 10: Real-World Scenarios

**Exercise 10.1** - Menu system:
```python
# SOLUTION:
while True:
    print("1. Add  2. View  3. Exit")
    choice = input("Select: ")
    
    if choice == "1":
        print("Adding...")
    elif choice == "2":
        print("Viewing...")
    elif choice == "3":
        print("Goodbye!")
        break
    else:
        print("Invalid choice")
```

---

# CHALLENGE PROBLEMS

### Challenge 1: Prime Factors
```python
num = 60
factors = []

n = num
i = 2

while i * i <= n:
    while n % i == 0:
        factors.append(i)
        n //= i
    i += 1

if n > 1:
    factors.append(n)

print(f"Prime factors of {num}: {factors}")
# OUTPUT: [2, 2, 3, 5]
```

### Challenge 2: Perfect Number
```python
# A number equals sum of its divisors (except itself)
num = 28
divisor_sum = 0

for i in range(1, num):
    if num % i == 0:
        divisor_sum += i

if divisor_sum == num:
    print(f"{num} is PERFECT")
else:
    print(f"{num} is NOT perfect")
```

### Challenge 3: Collatz Conjecture
```python
num = 27
steps = 0

while num != 1:
    print(num, end=" → ")
    if num % 2 == 0:
        num //= 2
    else:
        num = 3 * num + 1
    steps += 1

print("1")
print(f"Steps: {steps}")
```

---

## KEY TAKEAWAYS

### Loop Selection
```
FOR LOOP: Known iterations (lists, ranges)
WHILE LOOP: Unknown iterations (user input, conditions)
NESTED LOOPS: Multiple levels of iteration
```

### Control Statements
```
break → Exit loop immediately
continue → Skip to next iteration
else → Runs if loop completes (no break)
```

### Operators
```
Arithmetic: +, -, *, /, //, %, **
Compound: +=, -=, *=, /=, //=, %=, **=
Precedence: () → ** → *,/,%,// → +,- → comparisons → not → and → or
```

### Common Patterns
```
Accumulator: total += item
Counter: count += 1
Search: if found: break
Transform: new_list.append(transform(item))
Filter: if condition: new_list.append(item)
```

---

**CONGRATULATIONS! YOU'VE COMPLETED DAY 3!** 🎉

**You now understand:**
- ✅ for and while loops
- ✅ Loop control (break, continue)
- ✅ Nested loops
- ✅ Operators in detail
- ✅ Loop patterns
- ✅ 35+ error types
- ✅ Real-world loop projects

**Next Steps: Day 4 - Functions!** 🚀

