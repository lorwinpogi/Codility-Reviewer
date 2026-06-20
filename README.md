# Codility Reviewer


---

# 🐍 Python Functions

## def

Used to define a function.

```python
def add(a, b):
    return a + b
```

### Common Mistake

❌ Missing colon

```python
def add(a, b)
```

✅ Correct

```python
def add(a, b):
```

---

## return

Returns a value from a function.

```python
def square(x):
    return x * x
```

### Common Mistake

❌ Using print instead of return

```python
def square(x):
    print(x * x)
```

✅ Correct

```python
def square(x):
    return x * x
```

---

## Parameters

```python
def greet(name):
    return f"Hello {name}"
```

Output:

```text
Hello Ana
```

---

## Positional Arguments

```python
def divide(a, b):
    return a / b

divide(10, 2)
```

---

## Keyword Arguments

```python
def divide(a, b):
    return a / b

divide(b=2, a=10)
```

---

## Default Arguments

```python
def power(base, exp=2):
    return base ** exp

power(3)
```

Output:

```text
9
```

---

## *args

Accept unlimited positional arguments.

```python
def total(*args):
    return sum(args)

print(total(1, 2, 3))
```

Output:

```text
6
```

---

## **kwargs

Accept unlimited keyword arguments.

```python
def info(**kwargs):
    return kwargs

print(info(name="Ana", age=20))
```

Output:

```python
{'name': 'Ana', 'age': 20}
```

---

## lambda

Anonymous one-line function.

```python
square = lambda x: x * x

print(square(5))
```

Output:

```text
25
```

Common use:

```python
sorted(data, key=lambda x: x[1])
```

---

# 🔥 Most Important Python Built-ins

## len()

```python
len([1, 2, 3])
```

Output:

```text
3
```

---

## sum()

```python
sum([1, 2, 3])
```

Output:

```text
6
```

---

## min()

```python
min([4, 1, 7])
```

Output:

```text
1
```

---

## max()

```python
max([4, 1, 7])
```

Output:

```text
7
```

---

## enumerate()

Returns index and value together.

```python
names = ["Ana", "Bob"]

for i, name in enumerate(names):
    print(i, name)
```

Output:

```text
0 Ana
1 Bob
```

---

## zip()

Loops through multiple lists simultaneously.

```python
a = [1, 2]
b = [3, 4]

for x, y in zip(a, b):
    print(x, y)
```

Output:

```text
1 3
2 4
```

---

## List Comprehension

```python
squares = [x*x for x in range(5)]
```

Output:

```python
[0, 1, 4, 9, 16]
```

---

## any()

```python
any(x > 0 for x in [-1, -2, 3])
```

Output:

```text
True
```

---

## all()

```python
all(x > 0 for x in [1, 2, 3])
```

Output:

```text
True
```

---

# 🐼 Pandas

## Import

```python
import pandas as pd
```

---

## Series

```python
s = pd.Series([10, 20, 30])
```

---

## DataFrame

```python
df = pd.DataFrame({
    "a": [1, 2],
    "b": [3, 4]
})
```

---

## read_csv()

```python
df = pd.read_csv("data.csv")
```

---

## drop_duplicates()

```python
df = df.drop_duplicates()
```

---

## dropna()

```python
df = df.dropna()
```

---

## rename()

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
df["Department"] = (
    df["Department"]
    .astype("category")
)
```

---

## Create New Column

```python
df["Full_Name"] = (
    df["First_Name"] +
    " " +
    df["Last_Name"]
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

# 🗄️ SQL Fundamentals

## SELECT

Retrieve data.

```sql
SELECT *
FROM employees;
```

---

## DISTINCT

Remove duplicates.

```sql
SELECT DISTINCT department
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

## ORDER BY

Sort results.

```sql
SELECT *
FROM employees
ORDER BY salary DESC;
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

Filter grouped records.

```sql
SELECT department,
       COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
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

## COUNT

```sql
SELECT COUNT(*)
FROM employees;
```

---

## SUM

```sql
SELECT SUM(salary)
FROM employees;
```

---

## AVG

```sql
SELECT AVG(salary)
FROM employees;
```

---

## MIN

```sql
SELECT MIN(salary)
FROM employees;
```

---

## MAX

```sql
SELECT MAX(salary)
FROM employees;
```

---

## WITH (CTE)

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

# 🎯 SQL Codility Patterns

## Find Duplicates

```sql
SELECT email,
       COUNT(*) AS cnt
FROM users
GROUP BY email
HAVING COUNT(*) > 1;
```

---

## Second Highest Value

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

## Nth Highest Value

```sql
SELECT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET N-1;
```

---

## Count Records Per Group

```sql
SELECT department,
       COUNT(*)
FROM employees
GROUP BY department;
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

# ⚡ Last-Minute Exam Tips

## Python

Know these without notes:

- `def`
- `return`
- `lambda`
- `enumerate()`
- `zip()`
- `sorted(..., key=...)`
- List comprehension
- `any()`
- `all()`
- `min()`
- `max()`
- `sum()`
- `len()`

---

## Pandas

Know these without notes:

- `read_csv()`
- `drop_duplicates()`
- `dropna()`
- `rename()`
- filtering rows
- `astype("category")`
- create new column
- reorder columns
- `return df`

---

## SQL

Know these without notes:

- `SELECT`
- `DISTINCT`
- `WHERE`
- `JOIN`
- `GROUP BY`
- `HAVING`
- `COUNT`
- `SUM`
- `AVG`
- `MIN`
- `MAX`
- `WITH`
- aliases

---

# ✅ Final Exam Checklist

## Python

- [ ] Functions
- [ ] Parameters
- [ ] *args
- [ ] **kwargs
- [ ] return
- [ ] lambda
- [ ] enumerate()
- [ ] zip()
- [ ] list comprehension
- [ ] any()
- [ ] all()
- [ ] min()
- [ ] max()
- [ ] sum()
- [ ] len()

## Pandas

- [ ] Series
- [ ] DataFrame
- [ ] read_csv()
- [ ] drop_duplicates()
- [ ] dropna()
- [ ] rename()
- [ ] filtering
- [ ] astype("category")
- [ ] new column
- [ ] reorder columns
- [ ] return df

## SQL

- [ ] SELECT
- [ ] DISTINCT
- [ ] WHERE
- [ ] JOIN
- [ ] GROUP BY
- [ ] HAVING
- [ ] COUNT
- [ ] SUM
- [ ] AVG
- [ ] MIN
- [ ] MAX
- [ ] WITH (CTE)
- [ ] Aliases
- [ ] Find Duplicates
- [ ] Second Highest Value
- [ ] Above Average Salary
