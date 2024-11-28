# Check Palindrome

Write a Python function that checks if a string is a palindrome.

### Example Input and Output:

- Input: `"radar"`  
  Output: `True`

- Input: `"hello"`  
  Output: `False`

---

### Tips:

1. **Definition of Palindrome:** A palindrome reads the same backward as forward.
2. **Ignore Case:** Convert the string to lowercase to ensure case insensitivity.

---

### Solution:

```python
def is_palindrome(s):
    s = s.lower()
    return s == s[::-1]

# Example usage
print(is_palindrome("radar"))  # Output: True
print(is_palindrome("hello"))  # Output: False
```
