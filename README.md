
# Soybean Disease Detection Web Application

This project is a Flask-based web application that allows users to upload an image of a soybean leaf and predicts the probability of disease using a pre-trained deep learning model.

## Project Structure

- **app.py**: The main Python script that runs the Flask server and handles image uploads and predictions.
- **models/**: Directory containing the pre-trained model (`soybean_disease_detector.h5`).
- **templates/**: Contains HTML files for rendering the web pages (e.g., `upload.html`).
- **uploads/**: A temporary folder where uploaded images are saved for prediction before being deleted.

## Requirements

- Python 3.x
- Flask
- TensorFlow
- Keras

Install the dependencies by running:

```bash
pip install -r requirements.txt
```

(Ensure you create a `requirements.txt` file with your required packages, like `Flask`, `TensorFlow`, `Keras`, etc.)

## How to Run

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/soybean-disease-detector.git
   cd soybean-disease-detector
   ```

2. **Prepare Folders**: 
   Ensure that the following directories exist:
   
   - `models/`: Place the pre-trained model (`soybean_disease_detector.h5`) here.
   - `templates/`: The `upload.html` page for the user interface.
   - `uploads/`: This folder will be created automatically when the app is run, used for storing temporarily uploaded files.

3. **Run the Flask App**:

   ```bash
   python app.py
   ```

4. **Access the Web App**:

   Once the app is running, open your browser and navigate to:
   
   ```
   http://127.0.0.1:5000/
   ```

## Usage

1. On the main page, upload an image of a soybean leaf.
2. The app will process the image and predict the probability of a disease.
3. A JSON response will display the probability value, indicating the likelihood of the leaf being diseased.

## File Details

- **`app.py`**: The Flask web application handling file uploads and predictions.
- **`soybean_disease_detector.h5`**: The pre-trained model used for disease detection.
- **`upload.html`**: The front-end page where users upload the leaf image.

## Prediction Logic

The uploaded image is processed as follows:
1. Resized to 224x224 pixels.
2. Normalized by dividing the pixel values by 255.
3. Fed into the pre-trained TensorFlow model for prediction.
4. The result is returned as the probability of the image being a diseased leaf.

## Notes

- Ensure the pre-trained model is placed in the `models/` directory.
- The `uploads/` folder will store uploaded files temporarily and delete them after making predictions.
