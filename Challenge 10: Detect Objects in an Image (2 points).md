# Detect Objects in an Image

## The Challenge

Write a Python script that detects and labels objects in an image using a pre-trained machine learning model. The script should display the detected objects and their confidence scores.

### Example Interaction:

```
Enter the path to an image: input.jpg
Detected objects:
- Cat (95.5%)
- Couch (89.2%)
```

---

## Tips:

1. **Use a Pre-Trained Model or API:**
   - You can use Google's **Cloud Vision API**, **Hugging Face's transformers**, or pre-trained TensorFlow models.

2. **Install Required Libraries:**
   - For Hugging Face: `pip install transformers pillow`
   - For TensorFlow: `pip install tensorflow pillow`

3. **Process the Image:** Load and preprocess the image to make it compatible with the chosen model or API.

4. **Display Results:** Parse the output and print detected objects and confidence scores.

---

## Solution:

### Using Hugging Face's `transformers` Library

```python
from transformers import pipeline
from PIL import Image

def detect_objects(image_path):
    try:
        # Load the pre-trained image classification pipeline
        classifier = pipeline("image-classification", model="google/vit-base-patch16-224")
        
        # Open the image
        img = Image.open(image_path)
        
        # Perform object detection
        results = classifier(img)

        # Display the results
        print("Detected objects:")
        for result in results:
            print(f"- {result['label']} ({result['score'] * 100:.1f}%)")
    except Exception as e:
        print(f"An error occurred: {e}")

# Example usage
image_path = input("Enter the path to an image: ")
detect_objects(image_path)
```

---

## Walkthrough: How the Script Works

1. **Install Libraries:**
   - Install Hugging Face's `transformers` library using:  
     `pip install transformers pillow`.

2. **Pre-Trained Model:**
   - The script uses a pre-trained **Vision Transformer (ViT)** model for image classification.

3. **Load the Image:**
   - Use Python's `Pillow` library to open and process the image.

4. **Perform Object Detection:**
   - The `pipeline` object applies the pre-trained model to the input image and returns predictions.

5. **Display Results:**
   - The predictions include labels and confidence scores, which are printed in a readable format.

---

## Why This Challenge Matters

This task introduces you to:
- **Image Processing:** Learn how to preprocess and work with images in Python.
- **Machine Learning Models:** Use pre-trained models to perform complex tasks easily.
- **Real-World Applications:** Object detection is widely used in fields like robotics, security, and automation.

---

## Challenge Yourself Further

1. Extend the script to draw bounding boxes around detected objects on the image.  
2. Save the detection results in a JSON or CSV file for later analysis.  
3. Allow the script to process multiple images in a batch.  
4. Integrate the script with a simple web interface using Flask or Streamlit.

---

Solving this challenge earns you **2 points**—great work! Ready to explore more advanced image processing tasks? Keep coding and experimenting!

If you spot a mistake in a challenge, please create a merge request to excercise how to use GitHub as well :)
