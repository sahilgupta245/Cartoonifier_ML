# Cartoonify Your Image: Code Documentation

## Overview
This code provides an application for cartoonifying an image. It uses libraries like OpenCV for image processing and Tkinter for the graphical user interface. The application provides an interface to upload an image and then apply various transformations to create a cartoon effect. The cartoonified image can be saved using the "Save cartoon image" button.

---

## Libraries Used

#### OpenCV (cv2)
Used for the core image processing functionalities like reading images, resizing, and various transformations.

#### easygui
Provides the file dialog for selecting an image file.

#### NumPy (np)
Used to handle array operations, especially for image data manipulation.

#### imageio
Used to read images stored at a particular path (not actually used in the code though).

#### Tkinter (tk)
Provides the GUI components like buttons and labels.

#### PIL (Pillow)
Used for handling image formats and data.

#### Other Libraries
- matplotlib: For plotting the images.
- os, sys: For filesystem operations and system functionalities.

---

## Core Functions

### `upload()`
This function opens a dialog box to allow the user to choose an image file. Once selected, it passes the image path to the `cartoonify()` function.

### `cartoonify(ImagePath)`
#### Parameters
- `ImagePath`: The file path of the uploaded image.
  
This function performs the following operations:

- Reads the image and converts it to RGB.
- Converts the image to grayscale.
- Applies a median blur.
- Retrieves the edges using adaptive thresholding.
- Removes noise and keeps edges sharp using a bilateral filter.
- Masks the edged image with the original "beautified" image.

Finally, it plots the transition from the original image to the cartoonified image.

#### `save(ReSized6, ImagePath)`
#### Parameters
- `ReSized6`: The final cartoonified image.
- `ImagePath`: The file path of the uploaded image.

This function saves the cartoonified image in the same directory as the uploaded image with the name "cartoonified_Image".

---

## User Interface

### Tkinter GUI
The GUI is created using Tkinter. It has a button for uploading an image and another for saving the cartoonified image. It also includes a title and appropriate layout settings.

---

## Execution Flow
1. User clicks "Cartoonify an Image".
2. An image file is selected.
3. The image goes through various transformations.
4. The cartoonified image is displayed.
5. User can save the cartoonified image.

---
