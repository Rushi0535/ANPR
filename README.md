# Automatic Number Plate Detection and Recognition

This project detects license plates in an image file and 
performs optical character recognition (OCR) to extract the text from the license plate. 
The extracted text is then stored in a database and displayed on the web interface.

## Features

- Image upload: Users can upload an image file containing a license plate.
- License plate detection: The application uses computer vision techniques to detect the license plate region in the uploaded image.
- Optical character recognition: The detected license plate region is processed using an OCR engine to extract the alphanumeric characters from the license plate.
- Database storage: The extracted text is stored in a database along with the corresponding image file.
- Web interface: Users can view the uploaded image and the extracted license plate text on the web interface.

## Logical Flow

This project detects license plates in an image file. It first reads the image file and converts it to grayscale. It then applies a Gaussian blur to the image to reduce noise. Next, it applies the Canny edge detection algorithm to the image to find edges. It then finds all the contours in the image and sorts them by area in descending order. It then iterates through the contours and finds the first contour that has four sides. It then creates a mask of the contour and uses it to crop the image to the license plate region. It then passes the cropped image to an OCR engine to read the text on the license plate.

## Installation

1. Clone the repository:

2. Install the required dependencies:
        pip install -r requirements.txt

3. Set up the database:

- Modify the `DATABASES` configuration in the `settings.py` file to use your preferred database backend.
- Run the database migrations:

  ```
  python manage.py migrate
  ```

## Usage

1. Start the Django development server: 
        python manage.py runserver

2. Access the web application in your browser at `http://localhost:8000`.

3. Upload an image file containing a license plate using the provided form.

4. The application will detect the license plate, perform OCR, and display the extracted text on the web interface.
