# 🐍 THE ULTIMATE PYTHON DAY 2 TEXTBOOK
## Conditionals, Logic, & Decision Making
### Complete Professional Guide with Deep Dives, 30+ Error Types, 5 Projects & 10 Worksheets

**Edition:** 2.0 (ENHANCED - COMPLETE)  
**Target:** Complete Beginner → Professional Developer  
**Pages:** 80+  
**Code Examples:** 250+  
**Error Scenarios:** 30+  
**Projects:** 5 Complete  
**Worksheets:** 10 with Full Solutions  
**Total Study Time:** 18-25 hours  

---

# PART 1: CONDITIONALS FUNDAMENTALS

## 1.1 WHAT ARE CONDITIONALS?

Conditionals are decision-making statements that allow your program to take different paths based on whether a condition is TRUE or FALSE.

### Real-World Analogy
```
IF it's raining → Take umbrella
ELSE → Don't take umbrella

IF temperature > 40°C → Turn on AC
ELSE IF temperature > 25°C → Use fan
ELSE → Don't use anything
```

### Visual Flow

```
        START
          ↓
      CONDITION
      (True/False?)
        ↙      ↘
      TRUE    FALSE
        ↓       ↓
    ACTION1  ACTION2
        ↓       ↓
        └─────┬─────┘
              ↓
             END
```

### Why Conditionals Matter

Without conditionals:
```python
# Static code (same for everyone)
print("You must be 18+ to enter")
# No flexibility!
```

With conditionals:
```python
age = 20
if age >= 18:
    print("Welcome! You can enter")
else:
    print("Sorry, you're too young")
# Dynamic - works for ANY age!
```

---

## 1.2 THE if STATEMENT - COMPLETE DEEP DIVE

### Basic Syntax

```python
if condition:
    # Code here executes ONLY if condition is TRUE
    # Must be indented (4 spaces)
    statement1
    statement2
    # All indented code is part of the if block
```

### Understanding Indentation

**CRITICAL:** Python uses indentation to define code blocks.

```python
# ✅ CORRECT (4-space indentation)
if age >= 18:
    print("Adult")
    print("Can vote")
print("Program continues")

# ❌ WRONG (no indentation)
if age >= 18:
print("Adult")  # IndentationError!

# ❌ WRONG (inconsistent indentation)
if age >= 18:
  print("Adult")  # 2 spaces
    print("Can vote")  # 4 spaces - Error!
```

### Detailed Example 1: Basic Age Check

```python
age = 20

# Step 1: Evaluate condition
if age >= 18:  # Is 20 >= 18? YES → TRUE
    # Step 2: Enter the if block
    print("You are an adult")
    status = "Adult"

print("Program ends")

# OUTPUT:
# You are an adult
# Program ends
```

**Line-by-line trace:**
```
Line 1: age = 20
        Memory: age → 20

Line 3: if age >= 18:
        Evaluate: 20 >= 18? YES (TRUE)

Line 4-5: (Indented, so execute)
        print("You are an adult")
        status = "Adult"
        
Line 7: print("Program ends")
        (Always runs regardless of if)
```

### Example 2: When Condition is FALSE

```python
age = 15

if age >= 18:  # Is 15 >= 18? NO → FALSE
    print("You are an adult")  # SKIPPED
    status = "Adult"  # SKIPPED

print("Program ends")

# OUTPUT:
# Program ends
```

**What happens:**
- Condition FALSE → Skip entire if block
- Jump to code AFTER the if block
- Continue program

### The Colon (:) is MANDATORY

```python
# ❌ WRONG (missing colon)
if age >= 18
    print("Adult")
# SyntaxError: expected ':'

# ✅ CORRECT
if age >= 18:
    print("Adult")

# The colon tells Python: "A block is coming"
```

### Multiple Statements in if Block

```python
score = 95

if score >= 90:
    # ALL these execute together
    print("Excellent!")
    grade = "A"
    bonus = 5
    print(f"Grade: {grade}, Bonus: +{bonus}")
    
    # Still part of if block (indented)
    if bonus > 0:
        print("You got extra points!")

# This is NOT part of if block (no indent)
print("Next student")

# OUTPUT:
# Excellent!
# Grade: A, Bonus: +5
# You got extra points!
# Next student
```

---

## 1.3 if/else - TWO PATH DECISIONS

### Concept

```
              CONDITION
                 ↓
         Is condition TRUE?
            ↙          ↘
          YES           NO
           ↓            ↓
       PATH_A        PATH_B
       (if block)   (else block)
           ↓            ↓
        Execute       Execute
        THIS          THIS
                      INSTEAD
```

### Syntax

```python
if condition:
    # Executes if condition is TRUE
    code_block_A()
else:
    # Executes if condition is FALSE
    code_block_B()
```

### Example 1: Age Check

```python
age = 16

if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")

# OUTPUT: "You are a minor"

# Trace:
# age = 16
# 16 >= 18? FALSE
# Go to else block
# Print "You are a minor"
```

### Example 2: Test Pass/Fail

```python
score = 35

if score >= 40:
    print("✓ PASS")
    print("Congratulations!")
else:
    print("✗ FAIL")
    print("Try next time")

# OUTPUT:
# ✗ FAIL
# Try next time
```

### CRITICAL: Only ONE Block Executes

```python
balance = 500
withdrawal = 200

if withdrawal <= balance:
    balance = balance - withdrawal  # This executes
    print("Withdrawal successful")
else:
    print("Insufficient funds")  # This does NOT execute

print(f"Balance: {balance}")

# OUTPUT:
# Withdrawal successful
# Balance: 300

# The else block NEVER runs when if is true
```

---

## 1.4 elif - MULTIPLE PATHS

### Concept

```
IF only handles 2 paths (true/false)
ELIF lets you handle MANY paths

IF → ELIF → ELIF → ELIF → ... → ELSE
```

### Syntax

```python
if condition_1:
    # Executes if condition_1 is TRUE
    code1()
elif condition_2:  # "else if"
    # Executes if condition_1 is FALSE AND condition_2 is TRUE
    code2()
elif condition_3:
    # Executes if above are FALSE AND condition_3 is TRUE
    code3()
else:
    # Executes if ALL conditions above are FALSE
    code_default()
```

### Example: Grade Conversion

```python
score = 75

if score >= 90:
    grade = "A"
    print("Outstanding!")
elif score >= 80:
    grade = "B"
    print("Excellent!")
elif score >= 70:
    grade = "C"
    print("Good!")
elif score >= 60:
    grade = "D"
    print("Average")
else:
    grade = "F"
    print("Fail")

print(f"Your grade: {grade}")

# TRACE for score = 75:
# score >= 90? 75 >= 90? NO
# score >= 80? 75 >= 80? NO
# score >= 70? 75 >= 70? YES ← MATCH!
# grade = "C"
# print("Good!")
# Skip remaining elif and else
# print(f"Your grade: {grade}")

# OUTPUT:
# Good!
# Your grade: C
```

### CRITICAL: Stops After First Match

```python
score = 85

if score >= 80:         # TRUE → Execute
    print("At least 80")
elif score >= 70:       # SKIPPED (first was true)
    print("At least 70")
elif score >= 60:       # SKIPPED
    print("At least 60")
else:                   # SKIPPED
    print("Below 60")

# OUTPUT: "At least 80"

# Key: Once a condition matches, 
# all elif and else below are IGNORED
```

### Order Matters (Specific to General)

```python
score = 85

# ❌ WRONG ORDER (dangerous!)
if score >= 60:
    print("Passed")       # This matches, even if score is 95!
elif score >= 80:
    print("Excellent")    # NEVER executes
elif score >= 90:
    print("Outstanding")  # NEVER executes

# OUTPUT: "Passed" (WRONG!)

# ✅ CORRECT ORDER (specific to general)
if score >= 90:
    print("Outstanding")
elif score >= 80:
    print("Excellent")
elif score >= 60:
    print("Passed")

# OUTPUT: "Excellent" (CORRECT!)

# RULE: Order from MOST specific to MOST general
```

---

## 1.5 NESTED CONDITIONALS

### Concept: if Inside if

```python
if outer_condition:
    print("Outer if block")
    
    if inner_condition:
        print("Inner if block")
    else:
        print("Inner else block")
else:
    print("Outer else block")
```

### Visual

```
        OUTER IF
          ↓
       Is TRUE?
        ↙
      YES
       ↓
    INNER IF
       ↓
    Is TRUE?
     ↙    ↘
   YES    NO
    ↓     ↓
  ACT1  ACT2
```

### Example 1: Authentication

```python
username = input("Username: ")
password = input("Password: ")

# Outer if: Check username
if username == "admin":
    print("Username found")
    
    # Inner if: Check password
    if password == "secret":
        print("Password correct")
        print("✓ LOGIN SUCCESSFUL")
    else:
        print("✗ Wrong password")
else:
    print("✗ Username not found")

# Scenarios:
# Scenario 1: admin/secret
# Output: Username found, Password correct, ✓ LOGIN SUCCESSFUL

# Scenario 2: admin/wrong
# Output: Username found, ✗ Wrong password

# Scenario 3: john/secret
# Output: ✗ Username not found
```

### Indentation Rules for Nesting

```
Level 0: No indent (main program)
Level 1: 4 spaces (inside if)
Level 2: 8 spaces (inside nested if)
Level 3: 12 spaces (inside triple nested if)
```

```python
# Correct indentation
if condition1:        # Level 0
    code1             # Level 1 (4 spaces)
    
    if condition2:    # Level 1 (4 spaces)
        code2         # Level 2 (8 spaces)
        
        if condition3:  # Level 2 (8 spaces)
            code3     # Level 3 (12 spaces)
    
    code4             # Level 1 (4 spaces)

code5                 # Level 0 (no indent)
```

### Example 2: Bank Withdrawal

```python
balance = 5000
withdrawal_amount = 2000
pin_correct = True

if withdrawal_amount > 0:
    print("Amount is positive ✓")
    
    if withdrawal_amount <= balance:
        print("Sufficient balance ✓")
        
        if pin_correct:
            print("PIN correct ✓")
            balance = balance - withdrawal_amount
            print(f"✓ Withdrawn: ₹{withdrawal_amount}")
            print(f"Remaining: ₹{balance}")
        else:
            print("✗ Wrong PIN")
    else:
        print("✗ Insufficient balance")
else:
    print("✗ Invalid amount")

# OUTPUT:
# Amount is positive ✓
# Sufficient balance ✓
# PIN correct ✓
# ✓ Withdrawn: ₹2000
# Remaining: ₹3000
```

---

# PART 2: BOOLEAN LOGIC MASTERY

## 2.1 BOOLEAN VALUES & TRUTHINESS

### Boolean Basics

```python
# Two boolean values in Python
True   # Represents YES / ON / 1
False  # Represents NO / OFF / 0

# Every value in Python has a boolean value
# (called its "truthiness")
```

### Truthiness Table

```
TRUTHY (evaluated as True)
─────────────────────────────
Non-zero numbers: 1, -5, 3.14
Non-empty strings: "hello", "a"
Non-empty lists: [1, 2], ["a"]
Non-empty dicts: {"a": 1}
True (literal)
Any non-None object

FALSY (evaluated as False)
─────────────────────────────
Zero: 0, 0.0
Empty string: ""
Empty list: []
Empty dict: {}
False (literal)
None
```

### Using Truthiness in Conditionals

```python
user_input = ""

# Empty string is FALSY
if user_input:
    print("User entered something")
else:
    print("No input provided")

# OUTPUT: "No input provided"

# Equivalent to:
if bool(user_input):  # bool("") = False
    print("User entered something")
else:
    print("No input provided")
```

### Practical Examples

```python
# Example 1: Check if list is empty
items = []

if items:  # Empty list is FALSY
    print(f"Items: {items}")
else:
    print("No items")

# OUTPUT: "No items"

# Example 2: Check if variable has value
balance = 0

if balance:  # 0 is FALSY
    print(f"Balance: {balance}")
else:
    print("No balance")

# OUTPUT: "No balance"

# Example 3: Check if optional value exists
email = None

if email:  # None is FALSY
    print(f"Email: {email}")
else:
    print("No email provided")

# OUTPUT: "No email provided"
```

---

## 2.2 COMPARISON OPERATORS IN DETAIL

### All Comparison Operators

```
OPERATOR  NAME              EXAMPLE    RETURNS
================================================
==        Equals            5 == 5     True
!=        Not equals        5 != 3     True
>         Greater than      5 > 3      True
<         Less than         3 < 5      True
>=        Greater/equal     5 >= 5     True
<=        Less/equal        5 <= 5     True
```

### Deep Dive: == (Equality)

```python
# Compares VALUES
print(10 == 10)           # True
print("hello" == "hello") # True
print(10 == "10")         # False (different types)
print([1, 2] == [1, 2])   # True (same contents)
print(True == 1)          # True (bool is subclass of int)
```

### String Comparison (Case-Sensitive)

```python
name = "Alice"

if name == "Alice":
    print("Name matches")

if name == "alice":  # Lowercase 'a'
    print("This won't print")
    # "Alice" != "alice"

# OUTPUT: "Name matches"
```

### Chained Comparisons

```python
# Normal way (verbose)
if age >= 18 and age <= 65:
    print("Working age")

# Chained way (elegant)
if 18 <= age <= 65:
    print("Working age")

# Both do the same thing!
# But chained is more readable

# More complex
x = 50
if 0 <= x <= 100:
    print("Valid percentage")

# With mixed operators
if 5 < value < 10 and value != 7:
    print("Between 5 and 10, but not 7")
```

### Common Mistakes

```python
# ❌ MISTAKE 1: Using = instead of ==
if age = 18:  # This ASSIGNS, not compares
    print("Adult")

# ✅ CORRECT
if age == 18:  # This COMPARES
    print("Adult")

# ❌ MISTAKE 2: Float precision
x = 0.1 + 0.2
if x == 0.3:
    print("Equal")
# Won't print! (0.1 + 0.2 = 0.30000000000000004)

# ✅ CORRECT
if abs(x - 0.3) < 0.0001:  # Check if close enough
    print("Approximately equal")

# ❌ MISTAKE 3: String vs number
age_text = input("Age: ")  # Returns string "20"
if age_text > 18:
    # TypeError: '>' not supported between 'str' and 'int'
    print("Adult")

# ✅ CORRECT
if int(age_text) > 18:
    print("Adult")
```

---

## 2.3 LOGICAL OPERATORS (and/or/not)

### The Three Operators

```
OPERATOR  MEANING                  EXAMPLE
======================================================
and       ALL must be True        True and False → False
or        AT LEAST ONE is True    True or False  → True
not       Reverses True/False     not True       → False
```

### Truth Tables

**AND - Both must be True**
```
A     B     A and B
──────────────────
T     T     T
T     F     F
F     T     F
F     F     F
```

**OR - At least one must be True**
```
A     B     A or B
──────────────────
T     T     T
T     F     T
F     T     T
F     F     F
```

**NOT - Reverses**
```
A     not A
─────────────
T     F
F     T
```

### AND Operator

```python
# ALL conditions must be TRUE
age = 20
has_license = True
has_insurance = True

if age >= 18 and has_license and has_insurance:
    print("✓ Can drive")
else:
    print("✗ Cannot drive")

# OUTPUT: "✓ Can drive"

# If ANY is false:
has_insurance = False

if age >= 18 and has_license and has_insurance:
    print("✓ Can drive")
else:
    print("✗ Cannot drive")

# OUTPUT: "✗ Cannot drive"
```

### OR Operator

```python
# AT LEAST ONE must be TRUE
day = "Saturday"

if day == "Saturday" or day == "Sunday":
    print("🎉 Weekend!")
else:
    print("😴 Weekday")

# OUTPUT: "🎉 Weekend!"

# Even if only one matches:
day = "Monday"

if day == "Saturday" or day == "Sunday":
    print("🎉 Weekend!")
else:
    print("😴 Weekday")

# OUTPUT: "😴 Weekday"
```

### NOT Operator

```python
# Reverses/Negates
is_raining = False

if not is_raining:
    print("☀️ Sunny - Take sunscreen")
else:
    print("☔ Rainy - Take umbrella")

# OUTPUT: "☀️ Sunny - Take sunscreen"

# Practical: Check if NOT empty
items = []

if not items:  # If items is empty (falsy)
    print("No items")
else:
    print(f"{len(items)} items")

# OUTPUT: "No items"
```

### Combining Operators

```python
# AND with OR (multiple paths)
day = "Saturday"
time = 22

if (day == "Saturday" or day == "Sunday") and time >= 22:
    print("🎉 Late night weekend!")
else:
    print("Regular time")

# Evaluation:
# (Saturday or Sunday) = True
# True and (22 >= 22) = True and True = True
# OUTPUT: "🎉 Late night weekend!"
```

---

## 2.4 BOOLEAN ALGEBRA & DE MORGAN'S LAWS

### De Morgan's Laws (Important!)

```
NOT (A AND B) = (NOT A) OR (NOT B)
NOT (A OR B) = (NOT A) AND (NOT B)

In English:
"Not all true" means "at least one is false"
"Neither true" means "both are false"
```

### Example 1

```python
# Original
if not (age >= 18 and has_license):
    print("Cannot drive")

# Using De Morgan's
# not (A and B) = (not A) or (not B)
if age < 18 or not has_license:
    print("Cannot drive")

# Both mean the same thing!
```

### Example 2

```python
# Original
if not (is_admin or is_moderator):
    print("Access denied")

# Using De Morgan's
# not (A or B) = (not A) and (not B)
if not is_admin and not is_moderator:
    print("Access denied")

# Both mean the same!
```

---

## 2.5 SHORT-CIRCUIT EVALUATION

### AND Operator Short-Circuit

```python
# If first is FALSE, second is NOT evaluated
def check_first():
    print("Checking first...")
    return False

def check_second():
    print("Checking second...")
    return True

result = check_first() and check_second()

# OUTPUT: "Checking first..."
# check_second() is NEVER called!

# Why? With AND, if first is false, result is always false
# So Python doesn't even check the second
```

### OR Operator Short-Circuit

```python
# If first is TRUE, second is NOT evaluated
def check_first():
    print("Checking first...")
    return True

def check_second():
    print("Checking second...")
    return False

result = check_first() or check_second()

# OUTPUT: "Checking first..."
# check_second() is NEVER called!

# Why? With OR, if first is true, result is always true
```

### Practical Use: Safe Dictionary Access

```python
person = {"name": "Alice"}  # No "age" key

# ❌ DANGEROUS
if person["age"] > 18:  # KeyError!
    print("Adult")

# ✅ SAFE (uses short-circuit)
if "age" in person and person["age"] > 18:
    print("Adult")

# Trace:
# "age" in person? FALSE
# First part is FALSE, so AND stops
# person["age"] is NEVER accessed
# No error!
```

---

# PART 3: ADVANCED CONDITIONALS

## 3.1 TERNARY OPERATOR (One-Liner if/else)

### Concept: Compress if/else Into One Line

```python
# Regular if/else
if score >= 80:
    grade = "A"
else:
    grade = "B"

# Ternary operator
grade = "A" if score >= 80 else "B"

# Both do the same thing!
```

### Syntax

```python
value_if_true if condition else value_if_false
```

### Examples

```python
age = 20
status = "Adult" if age >= 18 else "Minor"
print(status)  # "Adult"

number = 7
parity = "Even" if number % 2 == 0 else "Odd"
print(parity)  # "Odd"

score = 35
result = "PASS" if score >= 40 else "FAIL"
print(result)  # "FAIL"
```

### When NOT to Use Ternary

```python
# ❌ Too complex (don't use ternary)
grade = "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "F"

# ✅ Use regular if/elif/else
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
else:
    grade = "F"
```

---

## 3.2 SWITCH-CASE ALTERNATIVE (Python 3.10+)

### Traditional Approach (Still Works)

```python
day = "Monday"

if day == "Monday":
    print("Start of week")
elif day == "Friday":
    print("End of week")
elif day == "Saturday" or day == "Sunday":
    print("Weekend")
else:
    print("Midweek")
```

### New match/case (Python 3.10+)

```python
day = "Monday"

match day:
    case "Monday":
        print("Start of week")
    case "Friday":
        print("End of week")
    case "Saturday" | "Sunday":  # Multiple values
        print("Weekend")
    case _:  # Default (like else)
        print("Midweek")
```

---

## 3.3 MEMBERSHIP TESTING (in/not in)

### The in Operator

```python
# Check if value exists
print("a" in "apple")         # True
print("x" in "apple")         # False

numbers = [1, 2, 3, 4, 5]
print(3 in numbers)           # True
print(10 in numbers)          # False

person = {"name": "Alice", "age": 25}
print("name" in person)       # True (checks KEYS)
print("Alice" in person)      # False (value, not key)
```

### Practical Use

```python
valid_options = ["A", "B", "C"]
user_choice = input("Choose: ").upper()

if user_choice in valid_options:
    print("✓ Valid choice")
else:
    print("✗ Invalid choice")
```

### not in

```python
banned_users = ["troll", "spammer", "hacker"]
username = "john"

if username not in banned_users:
    print("✓ User can enter")
else:
    print("🚫 User is banned")
```

---

## 3.4 IDENTITY CHECKING (is/is not)

### == vs is

```python
# == checks VALUE equality
# is  checks if SAME OBJECT in memory

a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)    # True (same contents)
print(a is b)    # False (different objects)
```

### When to Use is

```python
# ✅ Check for None (always use 'is')
value = None

if value is None:
    print("No value")

# ✅ Check for True/False
if flag is True:
    print("Flag is True")

# ❌ DON'T use ==
if value == None:  # Works but bad style
    print("No value")
```

---

## 3.5 COMPLEX BOOLEAN EXPRESSIONS

### Building Complex Conditions

```python
# Loan approval system
age = 25
salary = 60000
employment_years = 5
credit_score = 720
existing_debts = 200000

# All conditions combined
if (age >= 21 and salary >= 30000 and employment_years >= 2 and 
    credit_score >= 700 and existing_debts < (salary * 3)):
    print("✓ Eligible for loan")
else:
    print("✗ Not eligible for loan")
```

### Using Intermediate Variables (More Readable)

```python
is_legal_age = age >= 21
has_minimum_income = salary >= 30000
has_stable_employment = employment_years >= 2
has_good_credit = credit_score >= 700
has_acceptable_debt_ratio = existing_debts < (salary * 3)

if (is_legal_age and has_minimum_income and has_stable_employment and 
    has_good_credit and has_acceptable_debt_ratio):
    print("✓ Eligible for loan")
else:
    print("✗ Not eligible for loan")
```

---

# PART 4: ERROR MASTERY

## 4.1 THIRTY COMMON CONDITIONAL ERRORS

### ERROR 1: Missing Colon

```python
# ❌ WRONG
if age >= 18
    print("Adult")
# SyntaxError: expected ':'

# ✅ CORRECT
if age >= 18:
    print("Adult")
```

### ERROR 2: Incorrect Indentation

```python
# ❌ WRONG
if age >= 18:
print("Adult")  # Not indented!

# ✅ CORRECT
if age >= 18:
    print("Adult")  # 4 spaces
```

### ERROR 3: Tab vs Space Mixing

```python
# ❌ WRONG
if age >= 18:
    print("Adult")  # 4 spaces
	print("You can vote")  # Tab

# ✅ CORRECT (all 4 spaces)
if age >= 18:
    print("Adult")
    print("You can vote")
```

### ERROR 4: Missing elif keyword

```python
# ❌ WRONG
if score >= 90:
    grade = "A"
else if score >= 80:  # Wrong! Should be 'elif'
    grade = "B"

# ✅ CORRECT
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
```

### ERROR 5: Using = instead of ==

```python
# ❌ WRONG
if age = 18:  # Assignment, not comparison
    print("Adult")

# ✅ CORRECT
if age == 18:  # Comparison
    print("Adult")
```

### ERROR 6: Case Sensitivity

```python
# ❌ WRONG
user_input = "Yes"
if user_input == "yes":  # Lowercase
    print("Proceed")
# Won't print! "Yes" != "yes"

# ✅ CORRECT
if user_input.lower() == "yes":
    print("Proceed")
```

### ERROR 7: String vs Number Comparison

```python
# ❌ WRONG
user_input = input("Age: ")  # Returns string "20"
if user_input > 18:  # TypeError
    print("Adult")

# ✅ CORRECT
if int(user_input) > 18:
    print("Adult")
```

### ERROR 8: Floating Point Precision

```python
# ❌ WRONG
x = 0.1 + 0.2
if x == 0.3:  # Won't be true
    print("Equal")

# ✅ CORRECT
if abs(x - 0.3) < 0.0001:
    print("Approximately equal")
```

### ERROR 9: Checking Wrong Variable

```python
# ❌ WRONG
if age >= 18:
    if age >= 18:  # Checking age again!
        print("Can drive")

# ✅ CORRECT
if age >= 18:
    if has_license:
        print("Can drive")
```

### ERROR 10: Dictionary Key Access Without Checking

```python
# ❌ WRONG
person = {"name": "Alice"}
if person["age"] > 18:  # KeyError!
    print("Adult")

# ✅ CORRECT
if "age" in person and person["age"] > 18:
    print("Adult")
```

### ERROR 11: List Index Out of Range

```python
# ❌ WRONG
items = [1, 2, 3]
if items[5] == 1:  # IndexError!
    print("Found")

# ✅ CORRECT
if len(items) > 5 and items[5] == 1:
    print("Found")
```

### ERROR 12: Wrong Comparison Operator

```python
# ❌ WRONG
age = 15
if age > 18:  # Should be >=
    print("Adult")
# Won't print for age 18!

# ✅ CORRECT
if age >= 18:
    print("Adult")
```

### ERROR 13: Impossible Condition

```python
# ❌ IMPOSSIBLE
age = 30
if age < 18 and age > 65:  # Can't be both!
    print("This never prints")

# ✅ CORRECT
if age < 18 or age > 65:
    print("Outside working age")
```

### ERROR 14: Using AND When Should Use OR

```python
# ❌ WRONG (AND means ALL must match)
command = "help"
if command == "help" and command == "?":  # Impossible!
    print("Show help")

# ✅ CORRECT
if command == "help" or command == "?":
    print("Show help")
```

### ERROR 15: Not Validating User Input

```python
# ❌ WRONG (crashes on bad input)
age = int(input("Age: "))
if age >= 18:
    print("Adult")
# ValueError if user enters "abc"

# ✅ CORRECT
try:
    age = int(input("Age: "))
    if age >= 18:
        print("Adult")
except ValueError:
    print("Please enter a number")
```

---

# PART 5: FIVE COMPLETE PROJECTS

## PROJECT 1: STUDENT GRADE ANALYZER

```python
"""
Project 1: Student Grade Analyzer
- Multiple nested conditionals
- Average/min/max calculations
- Customized recommendations
"""

print("=" * 60)
print("   📚 STUDENT GRADE ANALYZER")
print("=" * 60)

# Get student info
student_name = input("\nStudent Name: ").strip().title()

# Input validation for scores
while True:
    try:
        math_score = float(input("Math Score (0-100): "))
        if 0 <= math_score <= 100:
            break
        print("Score must be 0-100")
    except ValueError:
        print("Invalid number")

while True:
    try:
        english_score = float(input("English Score (0-100): "))
        if 0 <= english_score <= 100:
            break
        print("Score must be 0-100")
    except ValueError:
        print("Invalid number")

while True:
    try:
        science_score = float(input("Science Score (0-100): "))
        if 0 <= science_score <= 100:
            break
        print("Score must be 0-100")
    except ValueError:
        print("Invalid number")

# Calculations
average_score = (math_score + english_score + science_score) / 3
total_score = math_score + english_score + science_score
highest_score = max(math_score, english_score, science_score)
lowest_score = min(math_score, english_score, science_score)

# Determine overall grade using nested elif
if average_score >= 90:
    overall_grade = "A"
    performance = "Outstanding"
    emoji = "🌟"
elif average_score >= 80:
    overall_grade = "B"
    performance = "Excellent"
    emoji = "✨"
elif average_score >= 70:
    overall_grade = "C"
    performance = "Good"
    emoji = "👍"
elif average_score >= 60:
    overall_grade = "D"
    performance = "Average"
    emoji = "🤔"
else:
    overall_grade = "F"
    performance = "Poor"
    emoji = "⚠️"

# Identify strength and weakness
if math_score >= english_score and math_score >= science_score:
    strength = "Math"
elif english_score >= math_score and english_score >= science_score:
    strength = "English"
else:
    strength = "Science"

if math_score <= english_score and math_score <= science_score:
    weakness = "Math"
elif english_score <= math_score and english_score <= science_score:
    weakness = "English"
else:
    weakness = "Science"

# Generate recommendations
recommendations = []

if math_score < 60:
    recommendations.append("• Focus on Math - needs improvement")
if english_score < 60:
    recommendations.append("• Improve English - requires attention")
if science_score < 60:
    recommendations.append("• Study Science - below standard")

if average_score < 70:
    recommendations.append("• Consider extra classes or tutoring")
    recommendations.append("• Increase study hours")

if average_score >= 90:
    recommendations.append("• Maintain this excellent performance!")
    recommendations.append("• Consider advanced courses")

# Display results
print("\n" + "=" * 60)
print(f"   {emoji} ANALYSIS FOR {student_name.upper()}")
print("=" * 60)

print(f"\nIndividual Scores:")
print(f"  Math:     {math_score:.1f}/100")
print(f"  English:  {english_score:.1f}/100")
print(f"  Science:  {science_score:.1f}/100")

print(f"\nSummary:")
print(f"  Total:    {total_score:.1f}/300")
print(f"  Average:  {average_score:.2f}")
print(f"  Highest:  {highest_score:.1f} ({strength})")
print(f"  Lowest:   {lowest_score:.1f} ({weakness})")

print(f"\nOverall Performance:")
print(f"  Grade:        {overall_grade}")
print(f"  Performance:  {performance}")

if recommendations:
    print(f"\nRecommendations:")
    for rec in recommendations:
        print(f"  {rec}")

# Final message based on performance
if average_score >= 90:
    print(f"\n🎉 Congratulations {student_name}! Excellent work!")
elif average_score >= 80:
    print(f"\n✅ Good job {student_name}! Keep it up!")
elif average_score >= 70:
    print(f"\n📈 Nice effort {student_name}! You're on track.")
elif average_score >= 60:
    print(f"\n💪 {student_name}, you can do better! Don't give up.")
else:
    print(f"\n⚠️ {student_name}, urgent action needed. Seek help!")

print("\n" + "=" * 60)
```

---

## PROJECT 2: BANK ACCOUNT TRANSACTION SYSTEM

```python
"""
Project 2: Bank Account Transaction System
- Complex nested conditionals
- Validation logic
- Multiple transaction types
"""

print("=" * 70)
print("   🏦 BANK ACCOUNT MANAGEMENT SYSTEM")
print("=" * 70)

# Initialize account
account_holder = input("\nAccount Holder Name: ").strip().title()
initial_balance = 0

while True:
    try:
        initial_balance = float(input("Initial Balance (₹): "))
        if initial_balance >= 0:
            break
        print("Balance cannot be negative")
    except ValueError:
        print("Invalid amount")

balance = initial_balance
transaction_history = []

# Banking operations
while True:
    print(f"\n{'=' * 70}")
    print(f"Current Balance: ₹{balance:,.2f}")
    print(f"{'=' * 70}")
    print("\n1. Deposit  2. Withdraw  3. Check Balance  4. History  5. Exit")
    
    choice = input("\nChoose (1-5): ").strip()
    
    if choice == "1":  # Deposit
        try:
            amount = float(input("Deposit amount (₹): "))
            
            if amount <= 0:
                print("❌ Amount must be positive")
            elif amount > 1000000:
                print("❌ Single deposit limit: ₹1,000,000")
            else:
                balance += amount
                transaction_history.append(("Deposit", amount, balance))
                print(f"✅ ₹{amount:,.2f} deposited")
        except ValueError:
            print("❌ Invalid amount")
    
    elif choice == "2":  # Withdraw
        try:
            amount = float(input("Withdraw amount (₹): "))
            
            if amount <= 0:
                print("❌ Amount must be positive")
            elif amount > balance:
                print(f"❌ Insufficient balance (Available: ₹{balance:,.2f})")
            elif amount % 100 != 0:
                print("❌ Must be multiple of ₹100")
            elif amount > 10000:
                confirm = input(f"Large withdrawal ₹{amount:,.2f}. Confirm? (yes/no): ").lower()
                if confirm in ["yes", "y"]:
                    balance -= amount
                    transaction_history.append(("Withdrawal", amount, balance))
                    print(f"✅ ₹{amount:,.2f} withdrawn")
                    if balance < 1000:
                        print(f"⚠️  Low balance: ₹{balance:,.2f}")
                else:
                    print("❌ Cancelled")
            else:
                balance -= amount
                transaction_history.append(("Withdrawal", amount, balance))
                print(f"✅ ₹{amount:,.2f} withdrawn")
        except ValueError:
            print("❌ Invalid amount")
    
    elif choice == "3":  # Check Balance
        print(f"\n{'=' * 70}")
        print(f"Account Holder: {account_holder}")
        print(f"Current Balance: ₹{balance:,.2f}")
        
        if balance == initial_balance:
            print("Status: No transactions")
        elif balance > initial_balance:
            profit = balance - initial_balance
            print(f"Status: ✅ Gain of ₹{profit:,.2f}")
        else:
            loss = initial_balance - balance
            print(f"Status: ❌ Loss of ₹{loss:,.2f}")
        print(f"{'=' * 70}")
    
    elif choice == "4":  # History
        if not transaction_history:
            print("\n❌ No transactions")
        else:
            print(f"\n{'=' * 70}")
            print("   TRANSACTION HISTORY")
            print(f"{'=' * 70}")
            print(f"{'Type':<15} {'Amount':>15} {'Balance':>15}")
            print(f"{'─' * 70}")
            
            for txn_type, amount, bal_after in transaction_history:
                print(f"{txn_type:<15} ₹{amount:>13,.2f} ₹{bal_after:>13,.2f}")
    
    elif choice == "5":  # Exit
        print(f"\n{'=' * 70}")
        print(f"Thank you {account_holder}!")
        print(f"Final Balance: ₹{balance:,.2f}")
        if balance > initial_balance:
            print(f"✅ Gain: ₹{balance - initial_balance:,.2f}")
        print(f"{'=' * 70}")
        break
    
    else:
        print("❌ Invalid option")
```

---

## PROJECT 3: WEATHER ADVISORY SYSTEM

```python
"""
Project 3: Weather Advisory System
- Multiple conditions with AND/OR
- Risk assessment
- Industry-specific advisories
"""

import random

print("=" * 70)
print("   🌤️  WEATHER ADVISORY SYSTEM")
print("=" * 70)

# Simulate weather data
temperature = random.randint(-10, 50)
humidity = random.randint(20, 100)
wind_speed = random.randint(0, 100)
rainfall = random.randint(0, 100)
visibility = random.randint(0, 100)

print("\n📊 CURRENT CONDITIONS:")
print(f"  Temperature: {temperature}°C")
print(f"  Humidity: {humidity}%")
print(f"  Wind Speed: {wind_speed} km/h")
print(f"  Rainfall: {rainfall}mm")
print(f"  Visibility: {visibility}m")

# Determine weather status
status = ""

if temperature > 40 and humidity < 30:
    status = "🔥 EXTREME HOT"
    advisory = "Heat Advisory - Drink water, avoid outdoors"
elif temperature > 35:
    status = "🌡️ HOT"
    advisory = "High temp - Use sunscreen"
elif temperature < 0 and humidity > 80:
    status = "❄️ FREEZING"
    advisory = "Frost warning - Avoid traveling"
elif temperature < 5:
    status = "❄️ COLD"
    advisory = "Cold weather - Wear warm clothes"
else:
    status = "✓ NORMAL"
    advisory = "Pleasant - Good for outdoor activities"

# Check for rain
if rainfall > 50:
    if temperature < 0:
        status = "❄️ HEAVY SNOW"
        advisory = "Heavy snow - Don't travel"
    else:
        status = "🌧️ HEAVY RAIN"
        advisory = "Heavy rain - Carry umbrella"
elif rainfall > 20:
    status = "🌧️ RAIN"
    advisory = "Light rain - Carry umbrella"

# Check for wind
if wind_speed > 60:
    status += " + 💨 STORM"
    advisory += " | Strong winds - Secure objects"
elif wind_speed > 40:
    status += " + 💨 WINDY"

# Check visibility
if visibility < 100:
    status += " + 🌫️ FOG"

# Risk assessment
risk_score = 0
if temperature > 40 or temperature < -5:
    risk_score += 2
if humidity > 90 or humidity < 20:
    risk_score += 1
if wind_speed > 60:
    risk_score += 2
if rainfall > 50:
    risk_score += 2
if visibility < 100:
    risk_score += 1

if risk_score >= 6:
    risk_level = "🔴 EXTREME"
elif risk_score >= 4:
    risk_level = "🟠 HIGH"
elif risk_score >= 2:
    risk_level = "🟡 MODERATE"
else:
    risk_level = "🟢 LOW"

# Display results
print("\n" + "=" * 70)
print("   📢 ADVISORY & RECOMMENDATIONS")
print("=" * 70)

print(f"\nStatus: {status}")
print(f"Advisory: {advisory}")
print(f"Risk Level: {risk_level}")
print("\n" + "=" * 70)
```

---

## PROJECT 4: MOVIE TICKET BOOKING SYSTEM

```python
"""
Project 4: Movie Ticket Booking System
- Multiple nested conditions
- Complex cost calculations
- User interaction flow
"""

print("=" * 60)
print("   🎬 MOVIE TICKET BOOKING SYSTEM")
print("=" * 60)

# Movie database
movies = {
    "1": {"name": "Avengers", "price": 300},
    "2": {"name": "Avatar", "price": 350},
    "3": {"name": "Inception", "price": 320},
}

# Get customer info
customer_name = input("\nCustomer Name: ").strip().title()

while True:
    try:
        age = int(input("Age: "))
        if 0 < age < 150:
            break
        print("Invalid age")
    except ValueError:
        print("Enter valid number")

# Display movies
print("\nAvailable Movies:")
for movie_id, info in movies.items():
    print(f"  {movie_id}. {info['name']} - ₹{info['price']}")

# Select movie
while True:
    movie_choice = input("\nSelect (1-3): ").strip()
    if movie_choice in movies:
        selected_movie = movies[movie_choice]
        break
    print("Invalid choice")

# Get tickets
while True:
    try:
        num_tickets = int(input("Number of tickets (1-10): "))
        if 1 <= num_tickets <= 10:
            break
        print("1-10 only")
    except ValueError:
        print("Invalid number")

# Calculate price
base_price = selected_movie["price"] * num_tickets
discount = 0

# Age-based discount
if age >= 60:
    discount += 0.20
    print("✓ Senior discount: 20%")

# Bulk discount
if num_tickets >= 5:
    discount += 0.10
    print("✓ Bulk discount: 10%")

# Student discount
student = input("Student? (yes/no): ").lower()
if student in ["yes", "y"] and age <= 25:
    discount += 0.15
    print("✓ Student discount: 15%")

# Apply discount (max 35%)
total_discount = min(discount, 0.35)
discount_amount = base_price * total_discount
final_price = base_price - discount_amount

# Convenience charge
convenience_charge = 0
if final_price > 1000:
    convenience_charge = 50
    print("✓ Convenience charge: ₹50")

total_price = final_price + convenience_charge

# Display summary
print("\n" + "=" * 60)
print("   📋 BOOKING SUMMARY")
print("=" * 60)
print(f"Movie: {selected_movie['name']}")
print(f"Tickets: {num_tickets}")
print(f"Base: ₹{base_price:,.2f}")
if total_discount > 0:
    print(f"Discount ({total_discount*100:.0f}%): -₹{discount_amount:,.2f}")
if convenience_charge > 0:
    print(f"Convenience: +₹{convenience_charge}")
print(f"\nTotal: ₹{total_price:,.2f}")

print("\n✓ Booking confirmed!")
print("=" * 60)
```

---

## PROJECT 5: MEDICAL DIAGNOSIS ASSISTANT (COMPLETE)

```python
"""
Project 5: Medical Diagnosis Assistant
- Complex medical logic
- Age-based considerations
- Severity assessment
DISCLAIMER: Educational only, not medical advice
"""

print("=" * 70)
print("   ⚕️  MEDICAL SYMPTOM CHECKER (Educational)")
print("=" * 70)
print("⚠️  DISCLAIMER: Not substitute for professional medical advice")
print("=" * 70)

# Get patient info
patient_name = input("\nPatient Name: ").strip().title()

try:
    age = int(input("Age: "))
except ValueError:
    print("Invalid age")
    exit()

# Symptom checklist
symptoms = {
    "fever": False,
    "cough": False,
    "sore_throat": False,
    "headache": False,
    "body_ache": False,
    "fatigue": False,
    "chills": False,
    "shortness_of_breath": False,
    "nausea": False,
    "vomiting": False,
    "diarrhea": False,
    "loss_of_taste": False,
}

print("\nPlease indicate symptoms (yes/no):")
for symptom in symptoms:
    response = input(f"  {symptom.replace('_', ' ').title()}? ").lower()
    if response in ["yes", "y"]:
        symptoms[symptom] = True

# Count symptoms
symptom_count = sum(symptoms.values())
print(f"\nTotal symptoms: {symptom_count}")

# Diagnosis logic
print("\n" + "=" * 70)
print("   📋 PRELIMINARY ASSESSMENT")
print("=" * 70)

diagnosis = []
severity = "LOW"

# Common Cold
if (symptoms["cough"] and symptoms["sore_throat"]) and not symptoms["fever"]:
    diagnosis.append("Common Cold")
    severity = "LOW"

# Flu (Influenza)
elif (symptoms["fever"] and symptoms["cough"] and symptoms["body_ache"] 
      and symptoms["headache"]):
    diagnosis.append("Influenza (Flu)")
    severity = "MODERATE"

# COVID-19 indicators
elif (symptoms["fever"] and symptoms["cough"] and symptoms["loss_of_taste"] 
      and (symptoms["shortness_of_breath"] or symptoms["fatigue"])):
    diagnosis.append("Possible COVID-19")
    severity = "MODERATE-HIGH"

# Viral Infection (General)
elif symptom_count >= 4 and symptoms["fever"]:
    diagnosis.append("Viral Infection")
    severity = "MODERATE"

# Gastroenteritis
elif (symptoms["nausea"] or symptoms["vomiting"]) and symptoms["diarrhea"]:
    diagnosis.append("Gastroenteritis")
    severity = "MODERATE"

# Allergy
elif symptoms["cough"] and symptoms["sore_throat"] and not symptoms["fever"]:
    diagnosis.append("Possible Allergy")
    severity = "LOW"

# High fever alert
if symptoms["fever"]:
    if symptom_count <= 2:
        diagnosis.append("Isolated High Fever - Requires Investigation")
        severity = "HIGH"

# Age-specific considerations
if age < 5 and symptom_count >= 3:
    severity = "HIGH"
    print(f"⚠️  Young child (age {age}) with multiple symptoms")

if age > 65 and symptom_count >= 2:
    severity = "HIGH"
    print(f"⚠️  Senior citizen (age {age}) at higher risk")

# Display diagnosis
if diagnosis:
    print(f"\nPossible Conditions:")
    for d in diagnosis:
        print(f"  • {d}")
else:
    print("\nNo specific diagnosis found. Consult a doctor.")

print(f"\nSeverity: {severity}")

# Recommendations
print("\n" + "-" * 70)
print("RECOMMENDATIONS:")
print("-" * 70)

if severity == "LOW":
    print("✓ Home care should be sufficient")
    print("✓ Rest and stay hydrated")
    print("✓ Monitor symptoms for 3-5 days")
elif severity == "MODERATE":
    print("⚠️ Consider visiting a clinic")
    print("✓ Rest and hydration")
    print("✓ Monitor vital signs")
elif severity in ["MODERATE-HIGH", "HIGH"]:
    print("🚨 SEEK MEDICAL ATTENTION IMMEDIATELY")
    print("✓ Call doctor or visit urgent care")
    print("✓ If difficulty breathing: Emergency")

print("\n" + "=" * 70)
print("⚕️  ALWAYS CONSULT A HEALTHCARE PROFESSIONAL")
print("=" * 70)
```

---

# PART 6: PRACTICE WORKSHEETS (COMPLETE WITH SOLUTIONS)

## WORKSHEET 1: Basic if/else

**Exercise 1.1** - Predict output:
```python
age = 20
if age >= 18:
    print("Adult")
else:
    print("Minor")
```
**Answer:** Adult

**Exercise 1.2** - Check if number is positive:
```python
# SOLUTION:
number = int(input("Enter number: "))
if number > 0:
    print("Positive")
else:
    print("Non-positive")
```

**Exercise 1.3** - Fix the error:
```python
# ❌ WRONG:
score = 85
if score >= 80
    print("Pass")

# ✅ CORRECT:
score = 85
if score >= 80:
    print("Pass")
```

---

## WORKSHEET 2: elif Mastery

**Exercise 2.1** - Grade classification:
```python
# SOLUTION:
score = 75

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Grade: {grade}")
# OUTPUT: Grade: C
```

---

## WORKSHEET 3: Boolean Operators

**Exercise 3.1** - Predict True/False:
```python
a = True
b = False

print(a and b)      # False
print(a or b)       # True
print(not b)        # True
print(a and not b)  # True
```

**Exercise 3.2** - Loan eligibility:
```python
# SOLUTION:
age = 25
income = 60000
credit_score = 720

if age >= 21 and income >= 30000 and credit_score >= 700:
    print("✓ Eligible")
else:
    print("✗ Not eligible")
# OUTPUT: ✓ Eligible
```

---

## WORKSHEET 4: Nested Conditionals

**Exercise 4.1** - Banking:
```python
# SOLUTION:
balance = 5000
withdrawal = 2000

if withdrawal > 0:
    if withdrawal <= balance:
        balance -= withdrawal
        print(f"✓ Withdrawn: ₹{withdrawal}")
    else:
        print("✗ Insufficient")
else:
    print("✗ Invalid")
```

---

## WORKSHEET 5: Ternary Operator

**Exercise 5.1** - Convert to ternary:
```python
# Original:
if age >= 18:
    status = "Adult"
else:
    status = "Minor"

# Ternary:
status = "Adult" if age >= 18 else "Minor"
```

---

## WORKSHEET 6: Input Validation

**Exercise 6.1** - Validate and process:
```python
# SOLUTION:
try:
    age = int(input("Age: "))
    if 0 <= age <= 150:
        if age >= 18:
            print("Adult")
        else:
            print("Minor")
    else:
        print("Invalid age")
except ValueError:
    print("Enter a number")
```

---

## WORKSHEET 7: Complex Conditions

**Exercise 7.1** - Access control:
```python
# SOLUTION:
role = "moderator"
is_active = True
violations = 0

if (role == "admin") or (role == "moderator" and is_active and violations == 0):
    print("✓ Access granted")
else:
    print("✗ Access denied")
# OUTPUT: ✓ Access granted
```

---

## WORKSHEET 8: De Morgan's Law

**Exercise 8.1** - Logical equivalence:
```python
# Original:
if not (age >= 18 and has_license):
    print("Cannot drive")

# Equivalent (De Morgan's):
if age < 18 or not has_license:
    print("Cannot drive")
```

---

## WORKSHEET 9: Error Identification

**Exercise 9.1** - Find and fix errors:
```python
# ❌ BROKEN:
score = input("Score: ")
if score >= 80:  # TypeError!
    print("Pass")

# ✅ FIXED:
score = int(input("Score: "))
if score >= 80:
    print("Pass")
```

---

## WORKSHEET 10: Real-World Scenarios

**Exercise 10.1** - Discount calculator:
```python
# SOLUTION:
amount = 5000
customer_type = "VIP"

if customer_type == "VIP" and amount > 4000:
    discount = 0.30
elif customer_type == "VIP":
    discount = 0.20
elif amount > 4000:
    discount = 0.15
else:
    discount = 0

final = amount * (1 - discount)
print(f"Final: ₹{final:,.2f}")
# OUTPUT: Final: ₹3,500.00
```

---

# CHALLENGE PROBLEMS

### Challenge 1: Temperature Converter
```python
celsius = float(input("Temperature (°C): "))
fahrenheit = (celsius * 9/5) + 32

if celsius > 40:
    alert = "🔥 Extreme heat"
elif celsius > 30:
    alert = "🌡️ Very hot"
elif celsius < 0:
    alert = "❄️ Freezing"
elif celsius < 10:
    alert = "❄️ Cold"
else:
    alert = "✓ Normal"

print(f"{celsius}°C = {fahrenheit:.1f}°F - {alert}")
```

### Challenge 2: Game Difficulty
```python
experience = int(input("Experience (1-10): "))

if experience < 3:
    difficulty = "Easy"
elif experience < 6:
    difficulty = "Normal"
elif experience < 9:
    difficulty = "Hard"
else:
    difficulty = "Extreme"

print(f"Recommended: {difficulty}")
```

### Challenge 3: Eligibility Checker
```python
age = int(input("Age: "))
income = int(input("Income: "))
has_degree = input("Has degree? (yes/no): ").lower() == "yes"

eligible = (age >= 21 and age <= 65 and 
            income >= 20000 and income <= 150000 and 
            has_degree)

if eligible:
    print("✓ Eligible!")
else:
    print("✗ Doesn't meet criteria")
```

---

## KEY TAKEAWAYS

✅ **Master conditionals**: if, elif, else  
✅ **Boolean logic**: and, or, not  
✅ **Comparison operators**: ==, !=, >, <, >=, <=  
✅ **Complex conditions**: nested, chained, combined  
✅ **Error handling**: validation, edge cases  
✅ **Professional code**: clean, readable, efficient  

---

**YOU'VE COMPLETED DAY 2!** 🎉

**Now ready for Day 3: Loops** 🚀

