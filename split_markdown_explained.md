# 🧠 Understanding `md_text.split('\n')` in Python

This guide is for beginners who are trying to understand how to process Markdown text in Python.

---

## 🔹 What is `md_text`?

`md_text` is a variable that holds the **entire content of a Markdown file or string**.

Example:

```python
md_text = """# AWS Cloud
This is a cloud platform.
## Features
- Scalable
- Secure"""
```

---

## 🔹 What does `.split('\n')` mean?

It means: **split the text wherever there is a newline character** (`\n`).

This turns one long string into a **list of lines**.

---

## 🧪 Example:

### ✅ Code:
```python
md_text = "# Heading 1\nThis is a paragraph.\n## Heading 2\nAnother line."
data = md_text.split('\n')
```

### ✅ Output:
```python
[
  "# Heading 1",
  "This is a paragraph.",
  "## Heading 2",
  "Another line."
]
```

---

## 📋 Visual Breakdown of Each Line

| Line Number | Markdown Line                |
|-------------|------------------------------|
| 1           | `# AWS Cloud`                |
| 2           | `This is a cloud platform.`  |
| 3           | `## Features`                |
| 4           | `- Scalable`                 |
| 5           | `- Secure`                   |

---

## ✅ Why Use This?

Splitting by `\n` lets you:
- Examine Markdown **line by line**
- Detect **headings**, **lists**, **code blocks**
- Build your own Markdown parser!
