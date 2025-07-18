# 🧠 Python Regex Basics and Best Practices

---

## 📌 What is Regex?

**Regex (Regular Expression)** is a powerful tool for **searching**, **matching**, and **extracting patterns** in text. It's commonly used to find:
- Emails
- Dates
- Headings
- Phone numbers
- Custom patterns in documents

---

## ✅ Python Regex Module: `re`

### 🔹 1. Import the Module

```python
import re
```

---

### 🔹 2. Common Functions

| Function         | Description                          |
|------------------|--------------------------------------|
| `re.search()`    | Finds **first match** in a string    |
| `re.findall()`   | Returns **all matches** as a list    |
| `re.match()`     | Matches pattern **only at the start**|
| `re.sub()`       | **Replaces** matched pattern         |
| `re.split()`     | **Splits** string by regex pattern   |
| `re.compile()`   | **Precompiles** a regex pattern      |

---

### 🔹 3. Common Regex Patterns

| Pattern    | Meaning                              | Example Match          |
|------------|--------------------------------------|-------------------------|
| `.`        | Any character (except newline)       | `a`, `1`, `%`           |
| `\d`      | Digit (0–9)                          | `5`, `2`                |
| `\D`      | Not a digit                          | `a`, `!`                |
| `\w`      | Word character (a–z, A–Z, 0–9, _)    | `name_123`              |
| `\W`      | Not a word character                 | `@`, `#`                |
| `\s`      | Whitespace                           | space, tab              |
| `\S`      | Not whitespace                       | `a`, `1`                |
| `^`        | Start of string                      | `^Hello`                |
| `$`        | End of string                        | `world$`                |
| `*`        | 0 or more times                      | `go*gle` → `ggle`       |
| `+`        | 1 or more times                      | `go+gle` → `gogle`      |
| `?`        | 0 or 1 times (optional)              | `colou?r`               |
| `{m,n}`    | Between m and n repetitions          | `a{2,4}` → `aaa`        |
| `[...]`    | Match any character in brackets      | `[aeiou]`               |
| `[^...]`   | Match any character *not* in brackets| `[^0-9]`                |
| `|`        | OR                                   | `apple|banana`          |
| `(...)`    | Group                                | `(Mr|Ms)\. \w+`       |

---

## 🧪 Examples

### ✅ Match Markdown Headings

```python
re.match(r'^(#{1,6})\s+(.*)', line)
```
Breakdown:
- `^` = start of line  
- `#{1,6}` = 1 to 6 `#` symbols  
- `\s+` = at least one space  
- `(.*)` = rest of the line (heading text)

---

### ✅ Extract Emails

```python
re.findall(r'\b[\w.-]+@[\w.-]+\.\w{2,4}\b', text)
```

---

### ✅ Find All Numbers

```python
re.findall(r'\d+', "AWS cost: 250 USD in 2024")
# Output: ['250', '2024']
```

---

## 🛠 Best Practices

- ✅ Use **raw strings**: `r"pattern"` to avoid escaping backslashes.
- ✅ **Break down complex regex** into simpler parts and test step-by-step.
- ✅ Use `re.compile()` for reuse.
- ✅ Test on [regex101.com](https://regex101.com/) (great explanations).
- ✅ Use **named groups** for better readability:
  ```python
  re.match(r'(?P<level>#{1,6}) (?P<text>.+)', line)
  ```
