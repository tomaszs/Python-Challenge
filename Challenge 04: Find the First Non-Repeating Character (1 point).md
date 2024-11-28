# Find the First Non-Repeating Character

## The Challenge

Write a Python function that finds the first character in a string that does not repeat.

### Example Input and Output:

- Input: `"swiss"`  
  Output: `"w"`

- Input: `"aabbccdd"`  
  Output: `None`

---

## Tips:

1. **Iterate with a Plan:** Loop through the string and keep track of character counts.  
2. **Data Structure Help:** Use a dictionary to store the frequency of each character.  
3. **Order Matters:** After counting, iterate through the string again to find the first character with a count of 1.

---

## Solution:

### Using a Dictionary

```python
def first_non_repeating_char(s):
    # Count character frequencies
    char_count = {}
    for char in s:
        char_count[char] = char_count.get(char, 0) + 1
    
    # Find the first non-repeating character
    for char in s:
        if char_count[char] == 1:
            return char
    return None

# Example usage
print(first_non_repeating_char("swiss"))  # Output: "w"
print(first_non_repeating_char("aabbccdd"))  # Output: None
```

---

## Why This Challenge Matters

This problem introduces you to concepts of:  
- **Frequency Counting:** A common algorithmic technique.  
- **Dictionary Usage:** Leveraging dictionaries for efficient lookups.  
- **Iterative Logic:** Breaking problems into multiple passes for clarity.

---

## Challenge Yourself Further

1. Handle case insensitivity (e.g., `"Swiss"` should output `"w"`).  
2. Extend the function to return all non-repeating characters in order of appearance.  

---

Solving this challenge earns you **1 point**—great work! Ready for the next? Keep going and sharpen your Python skills!
