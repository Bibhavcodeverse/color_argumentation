# color_argumentation


# Color Augmentation using Torchvision

## Overview
This project applies **color augmentation** to images using `torchvision.transforms`. It modifies image properties such as **brightness, contrast, saturation, hue**, and applies **random grayscale conversion**.

## Features
- Uses **ColorJitter** to adjust brightness, contrast, saturation, and hue.
- Applies **RandomGrayscale** with a configurable probability.
- Displays the **original and augmented images** side by side.

## Dependencies
Ensure you have the following installed:

```bash
pip install torch torchvision pillow matplotlib
```

## How to Run
1. **Load an image**: The script reads an image using PIL.
2. **Apply color augmentation**: Uses `ColorJitter` and `RandomGrayscale` for transformations.
3. **Display results**: Shows the original and augmented images using Matplotlib.

### Example Usage
```python
import torch
from torchvision import transforms
from PIL import Image
import matplotlib.pyplot as plt

# Load Image
image_path = "path/to/image.jpg"  # Replace with the actual image path
image = Image.open(image_path)

# Define Color Transforms
color_transforms = transforms.Compose([
    transforms.ColorJitter(brightness=0.5, contrast=0.5, saturation=0.5, hue=0.2),
    transforms.RandomGrayscale(p=0.2)  # Convert to grayscale with 20% probability
])

# Apply Transformations
augmented_image = color_transforms(image)

# Display Original and Augmented Images
fig, ax = plt.subplots(1, 2, figsize=(10, 5))
ax[0].imshow(image)
ax[0].set_title("Original Image")
ax[0].axis("off")
ax[1].imshow(augmented_image)
ax[1].set_title("Augmented Image")
ax[1].axis("off")
plt.tight_layout()
plt.show()
```

## Expected Output
The script will display:
- The **original image**.
- The **color-augmented version** with modified brightness, contrast, saturation, and hue.


![Screenshot 2025-03-27 003210](https://github.com/user-attachments/assets/57240e76-aa9e-42c3-b9e7-1d853dcb4049)

## Notes
- Adjust the transformation parameters to experiment with different augmentation effects.
- Set the correct **image path** before running the script.

## License
This project is open-source and available under the MIT License.

