# Shape Detection with OpenCV

This project demonstrates a simple shape detection system using OpenCV. The script processes an image to detect and label geometric shapes like triangles, quadrilaterals, pentagons, hexagons, and circles.

## Requirements

- Python 3.x
- OpenCV

## Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/your-username/your-repository-name.git
    ```

2. Navigate to the project directory:

    ```bash
    cd your-repository-name
    ```

3. Install the required packages:

    ```bash
    pip install opencv-python
    ```

## Usage

1. Place your image file (`shapes.png` or any other image file) in the project directory.
2. Run the script:

    ```bash
    python shape_detection.py
    ```

## Script Explanation

The script reads an image file and detects geometric shapes based on the contours in the image. It labels the shapes directly on the image.

- `cv2.imread("shapes.png")`: Reads the image file.
- `cv2.cvtColor(img, cv2.COLOR_RGB2GRAY)`: Converts the image to grayscale.
- `cv2.threshold(imgGray, 127, 255, cv2.THRESH_BINARY)`: Applies a binary threshold to the grayscale image.
- `cv2.findContours(thresh, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)`: Finds contours in the thresholded image.
- `cv2.approxPolyDP(contour, 0.01*cv2.arcLength(contour, True), True)`: Approximates the contour to a polygon.
- `cv2.drawContours(img, [contour], 0, (0, 255, 0), 5)`: Draws the contours on the image.
- `cv2.putText(img, "Shape", (x, y), cv2.FONT_HERSHEY_SIMPLEX, 0.6, (0, 255, 255), 2)`: Labels the shape on the image.

## Acknowledgements

This project uses OpenCV, an open-source computer vision and machine learning software library.
