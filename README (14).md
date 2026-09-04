# Canny Edge Detection using OpenCV

## Aim

To implement the **Canny Edge Detection algorithm** on a sample image using Python and OpenCV to detect the edges present in the image.

## Objective

* Read a sample image.
* Reduce image noise using Gaussian Blur.
* Apply the Canny Edge Detection algorithm.
* Display the original, blurred, and edge-detected images.

## Requirements

### Software

* Python 3.x
* OpenCV
* NumPy
* Matplotlib
* Jupyter Notebook / VS Code / Google Colab

### Installation

Install the required libraries using:

```bash
pip install opencv-python matplotlib numpy
```

## Algorithm

The Canny Edge Detection process consists of the following major steps:

1. **Noise Reduction**

    Gaussian Blur is applied to reduce unwanted noise and small variations in the image.

3. **Gradient Calculation**

   The intensity gradients of the image are calculated to identify areas with significant intensity changes.

5. **Non-Maximum Suppression**

   Unnecessary pixels are removed to obtain thin and precise edges.

7. **Double Thresholding**

   Two threshold values are used to classify pixels as strong, weak, or non-edge pixels.

9. **Edge Tracking by Hysteresis**

   Weak edges connected to strong edges are retained, while isolated weak edges are removed.

## Implementation

```
import cv2
import matplotlib.pyplot as plt

# Read the sample image
image = cv2.imread("sample.jpg")

# Apply Gaussian Blur to reduce noise
blurred = cv2.GaussianBlur(image, (5, 5), 1.4)

# Apply Canny Edge Detection
edges = cv2.Canny(blurred, threshold1 = 180, threshold2 = 200)

# Display the images
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(image[:,:,::-1])
plt.title("Original Image")

plt.subplot(1, 3, 2)
plt.imshow(blurred[:,:,::-1], cmap="gray")
plt.title("Gaussian Blurred")

plt.subplot(1, 3, 3)
plt.imshow(edges, cmap="gray")
plt.title("Canny Edge Detection")
plt.axis("off")

plt.tight_layout()
plt.show()
```

## Parameters Used

| Parameter       |    Value | Description                        |
| --------------- | -------: | ---------------------------------- |
| Gaussian Kernel | `(5, 5)` | Kernel used for noise reduction    |
| Sigma           |    `1.4` | Gaussian smoothing parameter       |
| Lower Threshold |    `180` | Lower threshold for edge detection |
| Upper Threshold |    `200` | Upper threshold for edge detection |

## Input

A sample image named:

```text
sample.jpg
```

Place the image in the same directory as the Python program or Jupyter Notebook.

## Output

The program displays:

1. **Original Image**
2. **Gaussian Blurred Image**
3. **Canny Edge Detection Output**

The final output highlights the important boundaries and structures in the image as edges.

## Project Structure

```text
Canny-Edge-Detection/
│
├── sample.jpg
├── canny_edge_detection.py
└── README.md
```

## Result

The Canny Edge Detection algorithm was successfully implemented using OpenCV. The significant edges present in the sample image were detected after reducing image noise using Gaussian Blur.
