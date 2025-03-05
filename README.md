import cv2
from google.colab.patches import cv2_imshow

# Load the image
image = cv2.imread("download.png")

if image is None:
    print("/content/download.png")
else:
    # Convert to grayscale
    gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    blurred = cv2.GaussianBlur(gray, (5, 5), 0)
    edges = cv2.Canny(blurred, 50, 150)
    print("Original Image-Aashish:")
    cv2_imshow(image)
    print("Grayscale Image-Aashish:")
    cv2_imshow(gray)
    print("Blurred Image-Aashish:")
    cv2_imshow(blurred)
    print("Edge Detected Image-Aashish:")
    cv2_imshow(edges)
    cv2.imwrite("grayscale.jpg", gray)
    cv2.imwrite("blurred.jpg", blurred)
    cv2.imwrite("edges.jpg", edges)
    print("Processing complete. Images saved.")
