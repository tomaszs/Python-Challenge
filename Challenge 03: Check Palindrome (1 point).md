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

Solving this challenge earns you 1 point—great work! Ready to tackle the next one? Keep coding and leveling up your Python skills!

If you spot a mistake in a challenge, please create a merge request to excercise how to use GitHub as well :)
