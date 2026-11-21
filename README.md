# Detect-the-lines-using-Hough-Transform

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---
##  Instructions

* Fill ONLY in `# Your Code Here` sections
* Do NOT change existing code
* Run step-by-step
* Verify outputs

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Developed By

* **Name:** Dhineshkumar L
* **Register No:** 212224230066

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```python
image = cv2.imread('dk_pic.jpg') 
```

---

###  Step 3: Convert to Grayscale

```python
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 4: Display Images

```python
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```

---

###  Step 5: Grayscale Image

```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

###  Step 6: Canny Edge Detector

```python
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150

# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()
```

---

### Step 7: Result of Hough Transform

```python
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = np.array(line).reshape(-1)
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 5)

# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
plt.show()
```

---



---

##  Expected Output

* Original image


<img width="462" height="841" alt="image" src="https://github.com/user-attachments/assets/924e7b84-8218-42cf-8cfa-4bf5e6985e66" />



* Grayscale image


<img width="442" height="821" alt="image" src="https://github.com/user-attachments/assets/43318aea-36e5-4c74-a7ee-7ac96345141e" />


 * Canny Edge Detector

<img width="443" height="832" alt="image" src="https://github.com/user-attachments/assets/ae8da3cc-a57d-41b5-b8c0-8180b7975655" />


* Result of Hough Transform




<img width="413" height="733" alt="image" src="https://github.com/user-attachments/assets/2ab673e6-7b09-45ea-81df-5e861cc2fc27" />






---



---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---


