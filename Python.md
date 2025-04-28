Checking types of variables
	name = "Mateo"
	type(name)
	answer: String
	

Taking characters and letters in a string
	example: name = "Mateo"
	name[3]
	answer: "e"

"hello"[0]
answer: "h"

"hello"[-1]
answer: o  - Starts from last character and goes back(if it was -2 it would have been l)

Type None (Null in other languages)
user = None - (it represents nothingless, for example if we have active_user variable, we can set it to none because there noa ctive user atm but when someone loggs in then we have it. Its a way to set variable before we get value on it later)


SLICES
-A **slice** is a way to extract a **subsequence** (subset) from sequences like:

- `str` (strings)
    
- `list`
    
- `tuple`
    
- `bytes`, `bytearray`, `range`
    

You use the **colon (`:`)** syntax to specify which part of the sequence to extract.

## 2. Basic Syntax

python

`sequence[start:stop:step]`

- **start**: index to begin (inclusive)
    
- **stop**: index to end (exclusive)
    
- **step**: how much to move forward each time (default: `1`)
    

All three are optional.

we can do for example without step
sequence[start:stop]

this is short for 
sequence[start:stop:1]
So it moves **one step at a time**, from `start` to just before `stop`.
s = "Python"

print(s[1:4])   # 'yth'   → characters at index 1, 2, 3
print(s[:3])    # 'Pyt'   → from beginning to index 2
print(s[2:])    # 'thon'  → from index 2 to end
print(s[:])     # 'Python' → full string (copy)


## 3. Slice Examples (From Simple to Advanced)
Basic
s = "abcdefg"
s[1:4]     # 'bcd'
s[:4]      # 'abcd'
s[2:]      # 'cdefg'
s[:]       # 'abcdefg' (full copy)

With Step
s[::2]     # 'aceg'
s[1::2]    # 'bdf'
s[::-1]    # 'gfedcba' (reverse)

Negative Indices:
s[-3:]     # 'efg'
s[:-2]     # 'abcde'
s[-4:-1]   # 'def'

4. Out-of-Range Slicing
5. s = 'abc'
s[0:10]   # 'abc'
s[10:20]  # '' (empty string)


## 7. Real-World Use Cases

### ✅ Reverse a string or list:

python

`s[::-1]`

### ✅ Copy a list:

python

`copy = original[:]`

### ✅ Rotate list left by n:

n = 2
lst = [1, 2, 3, 4, 5]
rotated = lst[n:] + lst[:n]  # [3, 4, 5, 1, 2]

### Get every nth element:

python

`lst[::3]  # every 3rd item`

### ✅ Trim leading and trailing characters:
s = "[[hello]]"
s = s[2:-2]  # 'hello'

## 8. Tips & Gotchas

**Default values**:
s[start:]  == s[start:len(s)]
s[:stop]   == s[0:stop]
s[:]       == s[0:len(s):1]

**Negative steps** go backward:
s[::-1]  # reverse
s[-2::-1]  # from second-last, going backward

**Don't use `step=0`** – it's invalid:
s[::0]  # ValueError: slice step cannot be zero

Slicing returns a **new object**, not a reference (for immutable types):
a = "hello"
b = a[:]
a is b  # True (strings are interned)

For lists, slicing creates a **shallow copy**:
lst = [[1], [2]]
copy = lst[:]
copy[0][0] = 100
print(lst)  # [[100], [2]] — inner lists are shared!


## 9. Summary Table

|Syntax|Meaning|
|---|---|
|`s[a:b]`|From index a to b (exclusive)|
|`s[:b]`|From start to b|
|`s[a:]`|From a to end|
|`s[:]`|Full sequence|
|`s[::n]`|Every nth element|
|`s[::-1]`|Reverse sequence|
|`del s[a:b]`|Delete slice from a to b|
|`s[a:b] = X`|Replace slice with X|

## 1. What is an Escape Character?

- In Python, a **backslash (`\`)** is used as an **escape character**.
    
- It lets you insert **special characters** inside strings that would normally cause problems or that cannot be typed directly.
    

**Example:**

python

`print("Hello\nWorld")`

**Output:**

nginx

`Hello World`

Here, `\n` means "newline" — it doesn't print `\n`, but **moves to a new line**.

---

## 2. Why Use Escape Characters?

✅ To insert things like **quotes inside quotes**  
✅ To create **newlines**, **tabs**, **special Unicode characters**  
✅ To include **special control characters** (like backspace)

Without escape characters, you'd get **errors** or **weird behavior**.

---

## 3. Common Python Escape Characters

|Escape Sequence|Meaning|Example|Output|
|---|---|---|---|
|`\\`|Backslash (`\`)|`"a\\b"`|`a\b`|
|`\'`|Single Quote (`'`) inside string|`'It\'s nice'`|`It's nice`|
|`\"`|Double Quote (`"`) inside string|`"She said \"Hello\""`|`She said "Hello"`|
|`\n`|Newline|`"Hello\nWorld"`|(New line)|
|`\t`|Tab (horizontal tab)|`"Hello\tWorld"`|(Tab space)|
|`\r`|Carriage return|`"Hello\rWorld"`|(Overwrites "Hello" with "World")|
|`\b`|Backspace|`"Hello\bWorld"`|`HellWorld`|
|`\f`|Form feed (new page, rarely used)|`"Hello\fWorld"`|(Page break)|
|`\v`|Vertical tab (rare)|`"Hello\vWorld"`|(Vertical tab)|
|`\ooo`|Octal value (rare)|`"\101"`|`A`|
|`\xhh`|Hexadecimal value|`"\x41"`|`A`|
|`\N{name}`|Unicode character by name|`"\N{COPYRIGHT SIGN}"`|`©`|
|`\uXXXX`|Unicode character (16-bit hex)|`"\u00A9"`|`©`|
|`\UXXXXXXXX`|Unicode character (32-bit hex)|`"\U0001F600"`|😀 (emoji)|

---

## 4. Special Notes

### **Double Quotes and Single Quotes**

You can use single quotes `'` inside double-quoted strings, and vice versa without needing escape:

python

`print("It's sunny")   # OK print('He said "Hi"') # OK`

But if you want to use **the same type** inside:

python

`print('It\'s sunny')  # Escape needed print("He said \"Hi\"")  # Escape needed`

---

### **Raw Strings: `r""`**

If you want Python **NOT to treat `\` as escape**, use a **raw string**:

python

`print(r"Hello\nWorld")`

**Output:**

`Hello\nWorld`

`r` tells Python to treat the string _literally_, no escaping.

✅ Great for regular expressions, file paths, etc.

---

### **Unicode Escapes**

You can insert special symbols like:

python

`print("\u03A9")   # Ω (Greek Omega) print("\N{HEAVY BLACK HEART}") # ❤️`

---

### **Carriage Return `\r`**

Carriage return (`\r`) **returns the cursor to the beginning of the line** and **overwrites**:

python

`print("12345\rabc")`

**Output:**

nginx

`abc45`

(`123` gets overwritten by `abc`.)

---

### **Backspace `\b`**

`\b` **erases** the character **before**:

python

`print("Hello\bWorld")`

**Output:**

nginx

`HellWorld`

---

## 5. Escape Characters Summary

|Escape|Description|
|---|---|
|`\\`|Backslash|
|`\'`|Single Quote|
|`\"`|Double Quote|
|`\n`|Newline|
|`\t`|Horizontal Tab|
|`\r`|Carriage Return|
|`\b`|Backspace|
|`\f`|Form Feed|
|`\v`|Vertical Tab|
|`\ooo`|Octal Value|
|`\xhh`|Hexadecimal Value|
|`\N{}`|Unicode by Name|
|`\uXXXX`|Unicode (16-bit hex)|
|`\UXXXXXXXX`|Unicode (32-bit hex)|

---

# ✅ Key Tips:

- **Backslash (`\`) starts an escape.**
    
- **Use `r""` raw strings** if you want to avoid escapes.
    
- **Common ones** you use all the time: `\n`, `\t`, `\\`, `\'`, `\"`.
    
- **Advanced ones** like `\u`, `\U`, `\N{}` are useful for **Unicode emojis** or **symbols**.
    
- **Always escape properly** to avoid syntax errors.


Triple """ is being used for multiple line strings

example: """ John
is being
a bad
boy
"""
this works whlie having multiple line strings with only "" or `` doesnt...gives an error

