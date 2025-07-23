## 🔍 What is Regex?

**Regex (Regular Expression)** is a way to **describe patterns in text**. It's used to **search**, **validate**, or **replace** parts of a string.

Think of regex like a **detective with a magnifying glass**, looking for very specific patterns in a sea of text.

---
## 📚 Basic Syntax

### 1. **Literal Characters**

```regex
house
```
Matches exactly "house".

---

### 2. **Metacharacters**

Special characters with specific meanings:

| Symbol | Meaning                        | Example          | Matches                     |
| ------ | ------------------------------ | ---------------- | --------------------------- |
| `.`    | Any character (except newline) | `c.t`            | cat, cut, c9t               |
| `^`    | Start of line                  | `^a`             | lines starting with "a"     |
| `$`    | End of line                    | `a$`             | lines ending with "a"       |
| `[]`   | Character set                  | `[aeiou]`        | any vowel                   |
| `[^]`  | Negated set                    | `[^0-9]`         | anything **except** a digit |
| `\`    | Escape character               | `\.`             | literal dot (.)             |
| `      | `                              | OR (alternation) | `house                      |

---

### 3. **Quantifiers**

Tell how **many times** something should appear.

| Symbol  | Meaning               | Example  | Matches          |
| ------- | --------------------- | -------- | ---------------- |
| `*`     | 0 or more             | `ca*`    | c, ca, caa, caaa |
| `+`     | 1 or more             | `ca+`    | ca, caa, caaa    |
| `?`     | 0 or 1                | `ca?`    | c, ca            |
| `{n}`   | Exactly n times       | `a{3}`   | aaa              |
| `{n,}`  | At least n times      | `a{2,}`  | aa, aaa, aaaa    |
| `{n,m}` | Between n and m times | `a{2,4}` | aa, aaa, aaaa    |

---

### 4. **Groups and Capturing**

Group parts of the pattern using parentheses:

```regex
(ab)+
```

Matches "ab", "abab", "ababab", etc.

---

### 5. **Predefined Character Classes**

|Class|Meaning|
|---|---|
|`\d`|Digit (0–9)|
|`\D`|Non-digit|
|`\w`|Word character (letters, digits, underscore)|
|`\W`|Non-word character|
|`\s`|Whitespace (space, tab, newline)|
|`\S`|Non-whitespace|

---

## 🧪 Practical Examples

### 1. **Validate a Brazilian ZIP code**

regex

CopyEdit

`^\d{5}-?\d{3}$`

Explanation:

- `^` start of line
- `\d{5}` five digits
- `-?` optional dash
- `\d{3}` three digits
- `$` end of line

---

### 2. **Extract email addresses**

```regex
[\w.-]+@[\w.-]+\.\w+`
```
Matches typical emails like: `john.doe@example.com`

---

### 3. **Replace all spaces with dashes**

```js
`str.replace(/\s+/g, "-")`
```

---

## 💡 Pro Tip: Use Online Tools

Try [regex101.com](https://regex101.com) — it gives live explanations and lets you test your patterns in real time.