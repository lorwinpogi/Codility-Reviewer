# Codility Reviewer
> Complete Python, Pandas, and SQL Reviewer for Coding Assessments


# 🐍 Python

## Functions

### Definition

A function is a reusable block of code.

### Syntax

```python
def function_name(parameters):
    return value
```

### Example

```python
def add(a, b):
    return a + b

print(add(5, 3))
```

Output:

```text
8
```

### When to Use

- Reuse code
- Organize logic
- Avoid repetition

### Common Mistakes

❌ Using print instead of return

```python
def add(a, b):
    print(a + b)
```

✅ Correct

```python
def add(a, b):
    return a + b
```

---

## For Loops

### Definition

Repeats code multiple times.

### Syntax

```python
for item in iterable:
    # code
```

### Example

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

### Common Mistakes

❌

```python
for i in range(len(numbers)+1):
```

✅

```python
for i in range(len(numbers)):
```

---

## Conditions

### if

```python
age = 18

if age >= 18:
    print("Adult")
```

### if / else

```python
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### if / elif / else

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

### Definition

Stores multiple values.

### Example

```python
numbers = [1, 2, 3, 4]
```

### Common Operations

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

### split()

Converts string → list

```python
text = "apple,banana,orange"

result = text.split(",")
```

Output:

```python
['apple', 'banana', 'orange']
```

---

### lower()

```python
text = "HELLO"

print(text.lower())
```

Output:

```text
hello
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

Converts list → string

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

### Counter

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
largest = numbers[0]

for num in numbers:

    if num > largest:
        largest = num
```

---

## Date & Month Handling

### Extract Year

```python
date = "2024-05-12"

year = date.split("-")[0]
```

Output:

```text
2024
```

---

### Extract Month

```python
month = date.split("-")[1]
```

Output:

```text
05
```

---

### Convert Month Number to Name

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

```python
[]
```

Empty List

```python
[5]
```

One Element

```python
[1,1,1]
```

Duplicates

```python
[-5,-10,-1]
```

Negative Numbers

```python
""
```

Empty String

```python
range(100000)
```

Large Input

---

# 🐼 Pandas

## Import

```python
import pandas as pd
```

---

## drop_duplicates()

### Definition

Removes duplicate rows.

### Syntax

```python
df.drop_duplicates()
```

### Example

```python
df = df.drop_duplicates()
```

### Common Mistake

❌

```python
df.drop_duplicates()
```

✅

```python
df = df.drop_duplicates()
```

---

## rename()

### Definition

Renames columns.

### Syntax

```python
df.rename(columns={})
```

### Example

```python
df = df.rename(
    columns={
        "Name": "Full_Name"
    }
)
```

---

## dropna()

### Definition

Removes rows with missing values.

### Example

```python
df = df.dropna()
```

---

## Filtering Rows

### Example

```python
df = df[df["Age"] > 18]
```

---

## astype("category")

### Example

```python
df["Department"] = (
    df["Department"]
    .astype("category")
)
```

---

## Create New Column

### Example

```python
df["Full_Name"] = (
    df["First_Name"]
    + " "
    + df["Last_Name"]
)
```

---

## Reorder Columns

### Example

```python
df = df[
    ["Name", "Age", "ID"]
]
```

---

## Return DataFrame

### Example

```python
return df
```

---

# 🗄️ SQL

# Data Retrieval

## SELECT

### Definition

Retrieves columns from a table.

### Syntax

```sql
SELECT column1, column2
FROM table_name;
```

### Example

```sql
SELECT name, salary
FROM employees;
```

### When to Use

- Retrieve data
- Reporting
- Analytics

### Common Mistakes

❌

```sql
SELECT *
FROM employees;
```

When only a few columns are needed.

---

## DISTINCT

### Definition

Removes duplicate rows.

### Syntax

```sql
SELECT DISTINCT column
FROM table;
```

### Example

```sql
SELECT DISTINCT department
FROM employees;
```

### Notes

Checks uniqueness of the entire selected combination.

---

# Filtering

## WHERE

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

Used before grouping.

---

## AND

```sql
SELECT *
FROM employees
WHERE salary > 50000
AND department = 'IT';
```

All conditions must be true.

---

## OR

```sql
SELECT *
FROM employees
WHERE department = 'IT'
OR department = 'HR';
```

At least one condition must be true.

---

## IN

```sql
SELECT *
FROM employees
WHERE department IN ('IT','HR');
```

Cleaner than multiple OR statements.

---

## NOT IN

```sql
SELECT *
FROM employees
WHERE department NOT IN ('IT','HR');
```

⚠️ Beware NULL values.

---

## BETWEEN

```sql
SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 60000;
```

Inclusive range.

---

## LIKE

```sql
SELECT *
FROM employees
WHERE name LIKE 'A%';
```

Wildcards:

```text
% = many characters
_ = one character
```

---

## IS NULL

```sql
SELECT *
FROM employees
WHERE manager_id IS NULL;
```

---

## IS NOT NULL

```sql
SELECT *
FROM employees
WHERE manager_id IS NOT NULL;
```

---

# Sorting

## ORDER BY

```sql
SELECT *
FROM employees
ORDER BY salary;
```

---

## ASC

```sql
ORDER BY salary ASC;
```

Default sort order.

---

## DESC

```sql
ORDER BY salary DESC;
```

Highest to lowest.

---

## LIMIT

```sql
SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;
```

Top 5 records.

---

# Aggregations

## COUNT()

```sql
SELECT COUNT(*)
FROM employees;
```

Counts rows.

---

## SUM()

```sql
SELECT SUM(salary)
FROM employees;
```

Total value.

---

## AVG()

```sql
SELECT AVG(salary)
FROM employees;
```

Average value.

---

## MIN()

```sql
SELECT MIN(salary)
FROM employees;
```

Smallest value.

---

## MAX()

```sql
SELECT MAX(salary)
FROM employees;
```

Largest value.

---

# Grouping

## GROUP BY

```sql
SELECT department,
       COUNT(*)
FROM employees
GROUP BY department;
```

Groups records.

---

## HAVING

```sql
SELECT department,
       COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

Filters groups.

---

# Conditional Logic

## CASE

```sql
SELECT name,
CASE
    WHEN salary > 50000
    THEN 'High'
    ELSE 'Low'
END AS tier
FROM employees;
```

SQL equivalent of if/else.

---

# Joins

## INNER JOIN

```sql
SELECT *
FROM employees e
INNER JOIN departments d
ON e.dept_id = d.id;
```

Matching rows only.

---

## LEFT JOIN

```sql
SELECT *
FROM employees e
LEFT JOIN departments d
ON e.dept_id = d.id;
```

Keep all left rows.

---

## RIGHT JOIN

```sql
SELECT *
FROM employees e
RIGHT JOIN departments d
ON e.dept_id = d.id;
```

Keep all right rows.

---

## FULL JOIN

```sql
SELECT *
FROM employees e
FULL JOIN departments d
ON e.dept_id = d.id;
```

Keep all rows from both tables.

---

# Set Operations

## UNION

```sql
SELECT name
FROM employees

UNION

SELECT name
FROM contractors;
```

Removes duplicates.

---

## UNION ALL

```sql
SELECT name
FROM employees

UNION ALL

SELECT name
FROM contractors;
```

Keeps duplicates.

---

# Subqueries

## Single Row Subquery

```sql
SELECT name
FROM employees
WHERE salary =
(
    SELECT MAX(salary)
    FROM employees
);
```

---

## Multi Row Subquery

```sql
SELECT name
FROM employees
WHERE dept_id IN
(
    SELECT id
    FROM departments
    WHERE location = 'NY'
);
```

---

# 🎯 Codility Patterns

## Find Duplicates

```sql
SELECT email,
       COUNT(*)
FROM users
GROUP BY email
HAVING COUNT(*) > 1;
```

---

## Second Highest Salary

```sql
SELECT MAX(salary)
FROM employees
WHERE salary <
(
    SELECT MAX(salary)
    FROM employees
);
```

---

## Above Average Salary

```sql
SELECT *
FROM employees
WHERE salary >
(
    SELECT AVG(salary)
    FROM employees
);
```

---

## Top N Records

```sql
SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;
```

---



