# 🧠 **Complete Python Regex Guide**

---

## 🔹 What is Regex?

Regex stands for **Regular Expression**, a sequence of characters that forms a **search pattern**. It’s used to **match, search, extract, or replace** patterns in text.

---

## 🔹 Python Regex Module

To use regex in Python:

```python
import re
```

---

## 🔹 Basic Regex Functions

| Function | Description |
|----------|-------------|
| `re.findall()` | Returns all matches as a list |
| `re.search()` | Returns first match object |
| `re.match()` | Checks match only at beginning |
| `re.sub()` | Replaces matches with given string |
| `re.split()` | Splits a string at each match |

---

## 🔹 Most Useful Metacharacters

| Metacharacter | Meaning | Example | Matches |
|---------------|---------|---------|---------|
| `.` | Any character except newline | `a.b` | `acb`, `a9b`, not `ab` |
| `^` | Start of string | `^Hello` | Matches if string starts with "Hello" |
| `$` | End of string | `world$` | Matches if string ends with "world" |
| `*` | 0 or more repetitions | `ab*` | `a`, `ab`, `abb` |
| `+` | 1 or more repetitions | `ab+` | `ab`, `abb` |
| `?` | 0 or 1 repetition | `ab?` | `a`, `ab` |
| `{n}` | Exactly n times | `a{3}` | `aaa` |
| `{n,}` | At least n times | `a{2,}` | `aa`, `aaa`, ... |
| `{n,m}` | Between n and m | `a{2,4}` | `aa`, `aaa`, `aaaa` |
| `[]` | Any one char in set | `[aeiou]` | `a`, `e`, `i` |
| `[^]` | Not in set | `[^aeiou]` | Any non-vowel |
| `|` | OR | `cat|dog` | `cat` or `dog` |
| `()` | Grouping | `(abc)+` | `abc`, `abcabc` |

---

## 🔹 Special Sequences (Shorthand)

| Sequence | Meaning | Example | Matches |
|----------|---------|---------|---------|
| `\d` | Digit (0-9) | `\d+` | `123`, `42` |
| `\D` | Non-digit | `\D+` | `abc`, `@!` |
| `\w` | Word char (a-z, A-Z, 0-9, _) | `\w+` | `hello`, `abc123` |
| `\W` | Non-word char | `\W+` | `@#! ` |
| `\s` | Whitespace | `\s+` | Space, `\t`, `\n` |
| `\S` | Non-whitespace | `\S+` | `word`, `abc` |
| `\b` | Word boundary | `\bI\b` | Matches "I" alone |
| `\B` | Not a word boundary | `\BI` | "Input", "Into", not just "I" |

---

## 🔹 Examples

### ✅ Find All Words
```python
re.findall(r'\w+', 'My email is test@gmail.com')  
# ['My', 'email', 'is', 'test', 'gmail', 'com']
```

### ✅ Find Numbers Only
```python
re.findall(r'\d+', 'There are 3 apples and 12 bananas')  
# ['3', '12']
```

### ✅ Validate Email
```python
re.match(r'\w+@\w+\.\w+', 'test123@gmail.com')  
# Match object (if valid)
```

---

## 🔹 Useful Regex Scenarios

### ✅ Match Phone Number (Indian)
```python
re.findall(r'[789]\d{9}', 'Call me at 9876543210')  
# ['9876543210']
```

### ✅ Extract Domain from Email
```python
re.findall(r'@(\w+\.\w+)', 'email is manas@gmail.com')  
# ['gmail.com']
```

### ✅ Replace Digits with X
```python
re.sub(r'\d', 'X', 'My number is 123456')  
# 'My number is XXXXXX'
```

### ✅ Split on Space or Comma
```python
re.split(r'[ ,]+', 'apple, banana orange')  
# ['apple', 'banana', 'orange']
```

---

## 🔹 Flags (Modifiers)

| Flag | Description |
|------|-------------|
| `re.I` | Ignore case |
| `re.M` | Multiline (`^` and `$` match line start/end) |
| `re.S` | Dot matches newline too |
| `re.X` | Ignore whitespace and comments in pattern |

### Example:
```python
re.findall(r'hello', 'Hello', re.I)  # ['Hello']
```

---

## 🔹 Grouping and Backreference

```python
match = re.search(r'(\d{4})-(\d{2})-(\d{2})', 'Date: 2024-04-08')
match.group(0)  # '2024-04-08'
match.group(1)  # '2024'
match.group(2)  # '04'
match.group(3)  # '08'
```

---
