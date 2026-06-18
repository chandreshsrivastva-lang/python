# 🐍 THE ULTIMATE PYTHON DAY 2 TEXTBOOK
## Conditionals, Logic, & Decision Making
### Complete Professional Guide with Deep Dives, 30+ Error Types, 5 Projects & 10 Worksheets

**Edition:** 2.0 (ENHANCED)  
**Target:** Complete Beginner → Professional Developer  
**Pages:** 50+  
**Code Examples:** 250+  
**Error Scenarios:** 30+  
**Projects:** 5 Complete  
**Worksheets:** 10 with Solutions  
**Total Study Time:** 18-25 hours  

---

## COMPLETE DAY 2 OUTLINE

### PART 1: CONDITIONALS FUNDAMENTALS
- 1.1 What Are Conditionals?
- 1.2 The if Statement - Complete Deep Dive
- 1.3 if/else - Two Path Decisions
- 1.4 elif - Multiple Paths
- 1.5 Nested Conditionals

### PART 2: BOOLEAN LOGIC MASTERY
- 2.1 Boolean Values & Truthiness
- 2.2 Comparison Operators in Detail
- 2.3 Logical Operators (and/or/not)
- 2.4 Boolean Algebra & De Morgan's Laws
- 2.5 Short-Circuit Evaluation

### PART 3: ADVANCED CONDITIONALS
- 3.1 Ternary Operator (One-Liner if/else)
- 3.2 Switch-Case Alternative (Python 3.10+)
- 3.3 Membership Testing (in/not in)
- 3.4 Identity Checking (is/is not)
- 3.5 Complex Boolean Expressions

### PART 4: ERROR MASTERY
- 4.1 30 Common Conditional Errors
- 4.2 Logic Errors vs Syntax Errors
- 4.3 Debugging Conditionals

### PART 5: PROFESSIONAL PRACTICES
- 5.1 Writing Clean Conditionals
- 5.2 Performance & Optimization
- 5.3 Real-World Patterns

### PART 6: HANDS-ON LEARNING
- 6.1 5 Complete Projects
- 6.2 10 Practice Worksheets
- 6.3 Challenge Problems

---

## PROJECT 5: MEDICAL DIAGNOSIS ASSISTANT (CONTINUED)

```python
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

print("\nPlease indicate which symptoms you have (yes/no):")
for symptom in symptoms:
    response = input(f"  {symptom.replace('_', ' ').title()}? ").lower()
    if response in ["yes", "y"]:
        symptoms[symptom] = True

# Count symptoms
symptom_count = sum(symptoms.values())
print(f"\nTotal symptoms reported: {symptom_count}")

# Diagnosis logic based on symptoms
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
    severity = "HIGH"  # Young children need special attention
    print(f"⚠️  Age: {age} - Young child with multiple symptoms")

if age > 65 and symptom_count >= 2:
    severity = "HIGH"  # Elderly at higher risk
    print(f"⚠️  Age: {age} - Senior citizen with symptoms")

# Display diagnosis
if diagnosis:
    print(f"\nPossible Conditions:")
    for d in diagnosis:
        print(f"  • {d}")
else:
    print("\nNo specific diagnosis found. Please consult a doctor.")

print(f"\nSeverity Level: {severity}")

# Recommendations
print("\n" + "-" * 70)
print("RECOMMENDATIONS:")
print("-" * 70)

if severity == "LOW":
    print("✓ Home care should be sufficient")
    print("✓ Get adequate rest and hydration")
    print("✓ Monitor symptoms for 3-5 days")
    
elif severity == "MODERATE":
    print("⚠️ Consider visiting a local clinic")
    print("✓ Get rest and stay hydrated")
    print("✓ Monitor vital signs")
    print("✓ Use over-the-counter remedies if appropriate")
    
elif severity in ["MODERATE-HIGH", "HIGH"]:
    print("🚨 SEEK MEDICAL ATTENTION IMMEDIATELY")
    print("✓ Call a doctor or visit urgent care")
    print("✓ If difficulty breathing: Call emergency services")
    print("✓ Get tested if COVID suspected")

# Prevention tips
print("\n" + "-" * 70)
print("PREVENTION TIPS:")
print("-" * 70)

if symptoms["cough"] or symptoms["sore_throat"]:
    print("• Cover mouth when coughing/sneezing")
    print("• Wear mask if going out")

if symptoms["fever"] or symptoms["body_ache"]:
    print("• Isolate to avoid spreading to others")
    print("• Maintain distance from vulnerable people")

print("• Wash hands frequently")
print("• Disinfect commonly touched surfaces")
print("• Maintain proper nutrition")
print("• Get adequate sleep")

print("\n" + "=" * 70)
print("⚕️  ALWAYS CONSULT A HEALTHCARE PROFESSIONAL FOR DIAGNOSIS")
print("=" * 70)
```

---

## PART 6: PRACTICE WORKSHEETS

### WORKSHEET 1: Basic if/else

**Exercise 1.1** - Predict the output:
```python
age = 20
if age >= 18:
    print("Adult")
else:
    print("Minor")
```
**Answer:** Adult

**Exercise 1.2** - Write code to check if a number is positive or non-positive:
```python
# SOLUTION:
number = int(input("Enter a number: "))
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

### WORKSHEET 2: elif Mastery

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
```

**Exercise 2.2** - Trace the execution:
```python
x = 15

if x < 10:
    print("Small")
elif x < 20:
    print("Medium")
elif x < 30:
    print("Large")
else:
    print("Very Large")

# Answer: Medium
```

---

### WORKSHEET 3: Boolean Operators

**Exercise 3.1** - Predict True/False:
```python
a = True
b = False

print(a and b)      # False
print(a or b)       # True
print(not b)        # True
print(a and not b)  # True
```

**Exercise 3.2** - Write a loan eligibility checker:
```python
# SOLUTION:
age = 25
income = 60000
credit_score = 720

if age >= 21 and income >= 30000 and credit_score >= 700:
    print("✓ Eligible for loan")
else:
    print("✗ Not eligible")
```

---

### WORKSHEET 4: Nested Conditionals

**Exercise 4.1** - Banking system:
```python
# SOLUTION:
balance = 5000
withdrawal_amount = 2000

if withdrawal_amount > 0:
    if withdrawal_amount <= balance:
        balance -= withdrawal_amount
        print(f"✓ Withdrawn: ₹{withdrawal_amount}")
        print(f"Remaining: ₹{balance}")
    else:
        print("✗ Insufficient balance")
else:
    print("✗ Invalid amount")
```

---

### WORKSHEET 5: Ternary Operator

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

**Exercise 5.2** - Max of two numbers:
```python
# SOLUTION:
a = 10
b = 20
max_value = a if a > b else b
print(max_value)  # 20
```

---

### WORKSHEET 6: Input Validation

**Exercise 6.1** - Validate and process input:
```python
# SOLUTION:
try:
    age = int(input("Enter age: "))
    if 0 <= age <= 150:
        if age >= 18:
            print("Adult")
        else:
            print("Minor")
    else:
        print("Invalid age")
except ValueError:
    print("Please enter a number")
```

---

### WORKSHEET 7: Complex Conditions

**Exercise 7.1** - User access control:
```python
# SOLUTION:
role = "moderator"
is_active = True
violations = 0

if (role == "admin") or (role == "moderator" and is_active and violations == 0):
    print("✓ Access granted")
else:
    print("✗ Access denied")
```

---

### WORKSHEET 8: Logical Equivalence

**Exercise 8.1** - Using De Morgan's Law:
```python
# Original:
if not (age >= 18 and has_license):
    print("Cannot drive")

# Equivalent (using De Morgan's):
if age < 18 or not has_license:
    print("Cannot drive")
```

---

### WORKSHEET 9: Error Identification

**Exercise 9.1** - Find and fix 5 errors:
```python
# ❌ BROKEN:
score = input("Score: ")
if score >= 80:  # TypeError: string >= int
    print("Pass")

# ✅ FIXED:
score = int(input("Score: "))
if score >= 80:
    print("Pass")
```

---

### WORKSHEET 10: Real-World Scenarios

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
```

---

## CHALLENGE PROBLEMS

### Challenge 1: Temperature Converter with Alerts
```python
# Convert and classify temperature
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

print(f"{celsius}°C = {fahrenheit}°F - {alert}")
```

### Challenge 2: Game Difficulty Selector
```python
# Select game difficulty based on experience
experience = int(input("Experience (1-10): "))

if experience < 3:
    difficulty = "Easy"
elif experience < 6:
    difficulty = "Normal"
elif experience < 9:
    difficulty = "Hard"
else:
    difficulty = "Extreme"

print(f"Recommended difficulty: {difficulty}")
```

### Challenge 3: Eligibility Checker
```python
# Check eligibility for special program
age = int(input("Age: "))
income = int(input("Income: "))
has_degree = input("Has degree? (yes/no): ").lower() == "yes"

eligible = (age >= 21 and age <= 65 and 
            income >= 20000 and income <= 150000 and 
            has_degree)

if eligible:
    print("✓ You are eligible!")
else:
    print("✗ You don't meet the criteria")
```

---

## KEY TAKEAWAYS

### Conditionals Hierarchy
```
if (must be first)
  ↓
elif (optional, multiple allowed)
  ↓
else (optional, must be last)
```

### Boolean Operators Priority
```
Highest: not
Middle:  and
Lowest:  or
```

### Common Mistakes to Avoid
1. ❌ Using `=` instead of `==` in conditions
2. ❌ Forgetting `:` after if/elif/else
3. ❌ Wrong indentation (not 4 spaces)
4. ❌ Not checking boundaries
5. ❌ Comparing different types (string vs int)
6. ❌ Missing elif when needed
7. ❌ Wrong order in chained comparisons
8. ❌ Not validating user input

### Best Practices
✅ Use descriptive variable names  
✅ Break complex conditions into parts  
✅ Validate input before using it  
✅ Use early returns to avoid deep nesting  
✅ Test edge cases  
✅ Comment complex logic  
✅ Order conditions from specific to general  

---

## NEXT STEPS

**Day 3 Topics:**
- Loops (for, while)
- Loop control (break, continue)
- Loop patterns
- Common loop errors
- Real-world loop projects

**Preparation for Day 3:**
- Review Day 2 all concepts
- Complete all worksheets
- Build at least 2 projects from scratch
- Practice debugging with print statements

---

**CONGRATULATIONS ON COMPLETING DAY 2!** 🎉

You now understand:
- ✅ All conditional statements (if/elif/else)
- ✅ Boolean logic and operators
- ✅ Complex conditions and nesting
- ✅ 30+ error types and solutions
- ✅ Professional coding practices
- ✅ Real-world applications

**Time to move to Day 3: Loops!** 🚀

