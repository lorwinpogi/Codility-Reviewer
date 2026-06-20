# 🚀 Codility Reviewer (Python, Pandas, SQL)

> Quick-review guide for common Codility assessments.


# 🐍 Python

## Functions

### Definition
A function is a reusable block of code that performs a specific task.

### Syntax

```python
def function_name():
    pass
```

### Example

```python
def greet():
    print("Hello")

greet()
```

Output:

```text
Hello
```

### Parameters

```python
def greet(name):
    print("Hello", name)

greet("John")
```

Output:

```text
Hello John
```

### Return Values

```python
def add(a, b):
    return a + b

result = add(5, 3)

print(result)
```

Output:

```text
8
```

### ⚠️ Common Codility Mistake

❌ Wrong

```python
def solution(a, b):
    print(a + b)
```

✅ Correct

```python
def solution(a, b):
    return a + b
```

---

## For Loops

### Basic Loop

```python
for i in range(5):
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

### Loop Through List

```python
names = ["John", "Jane", "Mark"]

for name in names:
    print(name)
```

### Loop With Index

```python
names = ["John", "Jane"]

for i in range(len(names)):
    print(i, names[i])
```

### ⚠️ Common Mistake

❌ Wrong

```python
for i in range(len(numbers)+1):
```

✅ Correct

```python
for i in range(len(numbers)):
```

---

## If / Else Conditions

### Basic If

```python
age = 18

if age >= 18:
    print("Adult")
```

### If Else

```python
age = 18

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### If Elif Else

```python
score = 85

if score >= 90:
    print("A")
elif score >= 80:
    print("B")
else:
    print("C")
```

---

## Lists

### Create List

```python
numbers = [1, 2, 3, 4]
```

### Access Elements

```python
print(numbers[0])
```

Output:

```text
1
```

### Useful Operations

```python
numbers.append(5)

numbers.remove(2)

len(numbers)

max(numbers)

min(numbers)
```

### Loop Through List

```python
for num in numbers:
    print(num)
```

---

## Strings

### lower()

Convert text to lowercase.

```python
text = "HELLO"

print(text.lower())
```

Output:

```text
hello
```

---

### split()

Convert string → list.

```python
text = "apple,banana,orange"

result = text.split(",")
```

Output:

```python
['apple', 'banana', 'orange']
```

---

### replace()

```python
text = "Hello World"

print(text.replace("World", "Python"))
```

Output:

```text
Hello Python
```

---

### join()

Convert list → string.

```python
fruits = ["apple", "banana", "orange"]

result = ",".join(fruits)
```

Output:

```text
apple,banana,orange
```

---

## Dictionaries & Counting

### Dictionary

```python
student = {
    "name": "John",
    "age": 20
}
```

### Access Value

```python
print(student["name"])
```

Output:

```text
John
```

---

### Frequency Counting

```python
words = ["apple", "banana", "apple"]

count = {}

for word in words:

    if word in count:
        count[word] += 1

    else:
        count[word] = 1

print(count)
```

Output:

```python
{
    "apple": 2,
    "banana": 1
}
```

---

### Faster Method

```python
from collections import Counter

words = ["apple", "banana", "apple"]

print(Counter(words))
```

Output:

```python
Counter({'apple': 2, 'banana': 1})
```

---

## Max / Min Logic

### Maximum

```python
numbers = [10, 5, 20, 8]

print(max(numbers))
```

Output:

```text
20
```

### Minimum

```python
print(min(numbers))
```

Output:

```text
5
```

### Manual Maximum

```python
numbers = [10, 5, 20, 8]

largest = numbers[0]

for num in numbers:

    if num > largest:
        largest = num

print(largest)
```

---

## Date / Month Handling

### Extract Year

```python
date = "2024-05-12"

year = date.split("-")[0]

print(year)
```

Output:

```text
2024
```

### Extract Month

```python
date = "2024-05-12"

month = date.split("-")[1]

print(month)
```

Output:

```text
05
```

### Month Conversion

```python
months = {
    "01": "January",
    "02": "February",
    "03": "March",
    "04": "April",
    "05": "May"
}

print(months["05"])
```

Output:

```text
May
```

---

## Edge Cases

Always test:

### Empty List

```python
[]
```

### One Element

```python
[5]
```

### Duplicate Values

```python
[1, 1, 1]
```

### Negative Numbers

```python
[-5, -10, -1]
```

### Empty String

```python
""
```

### Large Input

```python
range(100000)
```

### Safe Max Example

❌ Wrong

```python
max([])
```

Raises:

```text
ValueError
```

✅ Correct

```python
if numbers:
    print(max(numbers))
```

---

# 🐼 Pandas

## Import

```python
import pandas as pd
```

---

## drop_duplicates()

Remove duplicate rows.

```python
df = df.drop_duplicates()
```

---

## dropna()

Remove rows with missing values.

```python
df = df.dropna()
```

---

## rename()

Rename columns.

```python
df = df.rename(
    columns={
        "Name": "Full_Name"
    }
)
```

---

## Filtering Rows

```python
df = df[df["Age"] > 18]
```

---

## astype("category")

```python
df["Department"] = df["Department"].astype("category")
```

---

## Create New Column

```python
df["Full_Name"] = (
    df["First_Name"]
    + " "
    + df["Last_Name"]
)
```

---

## Reorder Columns

```python
df = df[
    ["Name", "Age", "ID"]
]
```

---

## Return DataFrame

```python
return df
```

---

## Common Codility Template

```python
import pandas as pd

def solution(df):

    df = df.drop_duplicates()

    df = df.dropna()

    df = df.rename(
        columns={
            "Name": "Full_Name"
        }
    )

    return df
```

---

# 🗄️ SQL

## SELECT

Retrieve columns.

```sql
SELECT *
FROM employees;
```

---

## WHERE

Filter rows.

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

---

## JOIN

Combine tables.

```sql
SELECT e.name,
       d.department
FROM employees e
JOIN departments d
ON e.employee_id = d.employee_id;
```

---

## GROUP BY

Group records.

```sql
SELECT department,
       COUNT(*)
FROM employees
GROUP BY department;
```

---

## HAVING

Filter grouped results.

```sql
SELECT department,
       COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

---

## Aggregation Functions

### COUNT

```sql
SELECT COUNT(*)
FROM employees;
```

### SUM

```sql
SELECT SUM(salary)
FROM employees;
```

### AVG

```sql
SELECT AVG(salary)
FROM employees;
```

### MIN

```sql
SELECT MIN(salary)
FROM employees;
```

### MAX

```sql
SELECT MAX(salary)
FROM employees;
```

---

## CTE (WITH Clause)

```sql
WITH avg_salary AS (

    SELECT AVG(salary) AS avg_sal
    FROM employees

)

SELECT *
FROM employees
WHERE salary >
(
    SELECT avg_sal
    FROM avg_salary
);
```

---

## Aliases

### Column Alias

```sql
SELECT salary AS employee_salary
FROM employees;
```

### Table Alias

```sql
SELECT e.name
FROM employees e;
```

---
