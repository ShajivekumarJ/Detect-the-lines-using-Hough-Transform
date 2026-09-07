
#  Lane Detection
##  Developed By

* **Name:** SHAJIVE KUMAR J 
* **Register No:** 212225230258

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

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

1.Read the input image using OpenCV and convert it from BGR to grayscale.

2.Apply the Canny edge detection technique to identify edges in the road image.

3.Apply the Probabilistic Hough Line Transform (HoughLinesP) to detect straight lane lines from the detected edges.

4.Draw the detected lane lines on the original image using cv2.line() and display the final lane detection result.


###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```python
image = cv2.imread('Qn_7_.jpg')  # Replace 'image.jpg' with your image path

```

---

###  Step 3: Convert to Grayscale

```python
# Convert to grayscale.
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 4: Display Images

```python
plt.figure(figsize=(10,5))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 5: Edge Detection (Canny)

```python
# Perform Edge Detection
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---

###  Step 6: Hough Transform

```python
# Detect lines using Hough Transform

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2

# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

---

##  Expected Output

* Original image
<img width="766" height="466" alt="Screenshot 2026-08-27 111311" src="https://github.com/user-attachments/assets/b0d00151-ce62-4e6e-b20a-288f68c6fc67" />

* Grayscale image
<img width="743" height="481" alt="Screenshot 2026-08-27 111316" src="https://github.com/user-attachments/assets/33f98e86-6d2e-485a-b757-8ac5e80dd574" />


* Edge detected image
<img width="638" height="447" alt="Screenshot 2026-08-27 111323" src="https://github.com/user-attachments/assets/c554d860-750b-46ca-a524-ec587612452f" />

* Final lane detection output
<img width="677" height="476" alt="Screenshot 2026-08-27 111328" src="https://github.com/user-attachments/assets/972e1c0f-c9c8-49b7-b29b-f133c83d4d96" />

---

##  Instructions

* Fill ONLY in `# Your Code Here` sections
* Do NOT change existing code
* Run step-by-step
* Verify outputs

---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
  
