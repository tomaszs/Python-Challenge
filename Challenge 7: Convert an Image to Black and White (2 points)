# Convert an Image to Black and White

## The Challenge

Write a Python script that takes an input image file and saves a new version of the image in black and white.

### Example:

- Input: A color image (e.g., `input.jpg`).  
- Output: A black and white version of the image (e.g., `output.jpg`).

---

## Tips:

1. **Use the PIL Library:** Python's Pillow library (`PIL`) makes it easy to manipulate images.  
2. **Convert to Grayscale:** Use the `convert("L")` method in PIL to turn the image into black and white.  
3. **Save the Result:** Save the new image using the `save()` method.

---

## Solution:

### Install Pillow

If you don’t already have Pillow installed, use the following command:

```bash
pip install pillow
```

### Complete Code

```python
from PIL import Image

def convert_to_black_and_white(input_file, output_file):
    try:
        # Open the image file
        img = Image.open(input_file)
        # Convert the image to grayscale
        bw_img = img.convert("L")
        # Save the black and white image
        bw_img.save(output_file)
        print(f"Black and white image saved as {output_file}.")
    except Exception as e:
        print(f"An error occurred: {e}")

# Example usage
convert_to_black_and_white("input.jpg", "output.jpg")
```

---

## Walkthrough: How the Script Works

1. **Import the Required Library:**  
   The script starts by importing the `Image` class from the Pillow library. This class provides the tools needed to open, manipulate, and save images.

2. **Define the Function:**  
   The function `convert_to_black_and_white()` takes two arguments:
   - `input_file`: The file path of the image to be converted.
   - `output_file`: The file path where the black-and-white image will be saved.

3. **Open the Image:**  
   The `Image.open(input_file)` method loads the image file into memory for processing.

4. **Convert to Black and White:**  
   The `convert("L")` method is called on the loaded image. Here’s what happens:
   - `"L"` is a mode in Pillow that represents grayscale (black and white). Each pixel in the image is converted to a single intensity value, removing all color information.

5. **Save the New Image:**  
   The `save(output_file)` method writes the processed image to the specified file.

6. **Error Handling:**  
   The `try-except` block ensures that if any error occurs (e.g., the input file doesn’t exist), the program doesn’t crash and instead prints a helpful error message.

7. **Run the Function:**  
   In the example usage, the function is called with `"input.jpg"` as the source image and `"output.jpg"` as the destination.

---

## Why This Challenge Matters

This task introduces you to image processing, a key skill in Python programming. You'll learn:  
- **File Handling:** Open and save files with the Pillow library.  
- **Image Manipulation:** Understand how to work with pixel data and color modes.  
- **Error Handling:** Deal with potential file or library issues.

---

## Challenge Yourself Further

1. Extend the script to allow batch processing of multiple images in a folder.  
2. Add a command-line interface (CLI) using Python's `argparse` module to specify input and output files.  
3. Create an option to apply a sepia tone effect instead of black and white.

---

Solving this challenge earns you **2 points**—excellent work! Ready to explore more creative tasks? Keep coding and expanding your skills!
