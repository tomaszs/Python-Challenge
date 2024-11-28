# Calculate the Sum of Digits in a String

## The Challenge

Write a Python function that calculates the sum of all numeric digits in a given string.

### Example Input and Output:

- Input: `"abc123"`  
  Output: `6`

- Input: `"a1b2c3d"`  
  Output: `6`

- Input: `"no digits here"`  
  Output: `0`

---

## Tips:

1. **Identify Digits:** Use Python’s `isdigit()` method to check if a character is a digit.  
2. **Convert to Integer:** When you find a digit, convert it from a string to an integer using `int()`.  
3. **Iterate:** Loop through the string and accumulate the sum of all digits.

---

## Solution:

### Using a Loop

```python
def sum_of_digits(s):
    total = 0
    for char in s:
        if char.isdigit():
            total += int(char)
    return total

# Example usage
print(sum_of_digits("abc123"))  # Output: 6
print(sum_of_digits("a1b2c3d"))  # Output: 6
print(sum_of_digits("no digits here"))  # Output: 0
```

---

## Why This Challenge Matters

This problem introduces key Python skills:  
- **Character Inspection:** Using `isdigit()` to identify numeric characters.  
- **Type Conversion:** Understanding how to switch between strings and integers.  
- **Looping Logic:** Applying loops to extract and process specific data.

---

## Challenge Yourself Further

1. Modify the function to return the **product** of all digits instead of the sum.  
2. Extend the function to handle strings with negative numbers (e.g., `"abc-123"` should sum as `6`).  
3. Write a version that works for multilingual strings with numeric Unicode characters.

---

Solving this challenge earns you **1 point**—great work! Keep pushing forward to master Python!

If you spot a mistake in a challenge, please create a merge request to excercise how to use GitHub as well :)
