# Count Vowels in a String

Write a Python function that counts the number of vowels in a given string.

### Example Input and Output:

- Input: `"hello"`  
  Output: `2`

- Input: `"Python"`  
  Output: `1`

---

### Tips:

1. **Identify Vowels:** Create a list or string containing all vowels: `['a', 'e', 'i', 'o', 'u']`.
2. **Case Insensitivity:** Convert the string to lowercase to avoid missing uppercase vowels.
3. **Iterate and Count:** Loop through the string and check if each character is a vowel.

---

### Solution:

```python
def count_vowels(s):
    vowels = "aeiou"
    count = 0
    for char in s.lower():
        if char in vowels:
            count += 1
    return count

# Example usage
print(count_vowels("hello"))  # Output: 2
print(count_vowels("Python"))  # Output: 1
```
Solving this challenge earns you 1 point—great work! Ready to tackle the next one? Keep coding and leveling up your Python skills!

If you spot a mistake in a challenge, please create a merge request to excercise how to use GitHub as well :)
