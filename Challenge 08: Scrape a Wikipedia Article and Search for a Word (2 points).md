# Scrape a Wikipedia Article and Search for a Word

## The Challenge

Write a Python script that scrapes the content of a specified Wikipedia article and checks if a given word exists within the text.

### Example Interaction:

```
Enter the Wikipedia article URL: https://en.wikipedia.org/wiki/Python_(programming_language)
Enter the word to search for: Guido
The word "Guido" appears in the article!
```

---

## Tips:

1. **Use Requests and BeautifulSoup:** These libraries make it easy to fetch web pages and parse HTML content.  
2. **Handle the HTML:** Extract only the main content of the article (e.g., text within `<p>` tags).  
3. **Make It Dynamic:** Let the user provide the URL and word as input.

---

## Solution:

### Install Required Libraries

If you don’t already have the necessary libraries installed, use the following commands:

```bash
pip install requests beautifulsoup4
```

### Complete Code

```python
import requests
from bs4 import BeautifulSoup

def scrape_and_search_wikipedia(url, word):
    try:
        # Fetch the Wikipedia page
        response = requests.get(url)
        response.raise_for_status()  # Check for HTTP request errors
        
        # Parse the HTML content
        soup = BeautifulSoup(response.text, 'html.parser')
        
        # Extract all paragraphs
        paragraphs = soup.find_all('p')
        article_text = " ".join(p.get_text() for p in paragraphs)
        
        # Check if the word exists in the article
        if word.lower() in article_text.lower():
            print(f'The word "{word}" appears in the article!')
        else:
            print(f'The word "{word}" does not appear in the article.')
    except Exception as e:
        print(f"An error occurred: {e}")

# Example usage
url = input("Enter the Wikipedia article URL: ")
word = input("Enter the word to search for: ")
scrape_and_search_wikipedia(url, word)
```

---

## Walkthrough: How the Script Works

1. **Import Required Libraries:**  
   - `requests` fetches the HTML content of the Wikipedia page.
   - `BeautifulSoup` parses the HTML, allowing you to extract relevant parts of the page.

2. **Fetch the Wikipedia Page:**  
   - Use `requests.get(url)` to retrieve the page content.  
   - Use `raise_for_status()` to ensure there are no HTTP errors.

3. **Parse the HTML Content:**  
   - Create a `BeautifulSoup` object to parse the HTML.  
   - Use the `find_all('p')` method to extract all `<p>` tags (the main content of the article).  
   - Concatenate the text from all paragraphs into a single string.

4. **Search for the Word:**  
   - Convert both the article text and the search word to lowercase to ensure case insensitivity.  
   - Check if the word is a substring of the article text using the `in` keyword.

5. **Provide Feedback:**  
   - If the word is found, print a success message. Otherwise, inform the user that the word is not present.

6. **Error Handling:**  
   - Use a `try-except` block to gracefully handle issues like invalid URLs or network errors.

---

## Why This Challenge Matters

This task introduces you to:
- **Web Scraping:** Learn how to fetch and process web content dynamically.  
- **String Matching:** Apply basic text processing techniques to search for specific terms.  
- **Error Handling:** Develop robust scripts that handle common issues gracefully.

---

## Challenge Yourself Further

1. Extend the script to count how many times the word appears in the article.  
2. Allow searching for multiple words at once.  
3. Save the scraped article text to a file for offline analysis.  
4. Add a feature to scrape links to other Wikipedia articles from the page.

---

Solving this challenge earns you **2 points**—excellent work! Ready for the next challenge? Keep pushing your Python skills further!

If you spot a mistake in a challenge, please create a merge request to excercise how to use GitHub as well :)
