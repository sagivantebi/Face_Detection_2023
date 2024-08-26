
# Face Recognition

This project leverages OpenCV, and a Keras-based model trained using Google's Teachable Machine to create a real-time face recognition system. The system captures images, trains a model, and then uses the model to recognize faces.



![facere](https://github.com/user-attachments/assets/e8397104-2850-41ef-af5a-84f9716fc972)



## Features

- **Image Capture**: Capture images in real-time using your webcam directly from Google Colab.
- **Face Detection**: Detect faces using Haar cascades from OpenCV.
- **Model Training**: Train a custom face recognition model using the Teachable Machine platform.
- **Face Recognition**: Load the trained model to predict and classify faces with confidence scores.

## Getting Started

### Prerequisites

- Google Colab account
- Python 3.x
- Required Python packages (installed via Colab)

### Installation and Setup

1. **Mount Google Drive**: Ensure you have access to your Google Drive from Colab. This is where all your images and models will be stored.
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```

2. **Capture Images**:
    - Run the provided script to capture 20 images of your face. The images will be stored in your Google Drive under the `FaceImages` directory.
    - You will be prompted to enter your name, which will be used as the folder name in the `FaceImages` directory.
    - Ensure that you are using a consistent path for storing images.

3. **Train the Model**:
    - Go to [Teachable Machine](https://teachablemachine.withgoogle.com/train/) and train a face recognition model using the images you captured.
    - Download the trained model and place it in your Google Drive.

4. **Update the Model Path**:
    - Ensure that the path to your Keras model (`keras_model.h5`) is correctly set in the script.

### Running the Face Recognition

1. **Load the Model**:
    - The provided script will load your trained model from Google Drive.
    - Update the path to your `labels.txt` file, which contains the class names corresponding to your model.

2. **Run the Prediction**:
    - The script loads an image, preprocesses it, and predicts the class (face) using the trained model.
    - The prediction result, along with a confidence score, is printed.

### Example Usage

1. **Capture Images**:
    ```python
    Enter Your Name: sagiv
    ```
    This will create a folder in your Google Drive and store 20 captured images.

2. **Predict Face**:
    - Ensure you have the correct image path:
    ```python
    image = Image.open("images/saggg/1.jpg").convert("RGB")
    ```
    - Run the script to get the class name and confidence score:
    ```python
    Class: Sagiv
    Confidence Score: 0.95
    ```

## Project Structure

- `capture_image.py`: Script to capture images using your webcam.
- `train_model.py`: Instructions to train your model using Teachable Machine.
- `predict_face.py`: Script to predict and classify faces using the trained model.
- `haarcascade_frontalface_default.xml`: Pre-trained Haar Cascade for face detection.
- `keras_model.h5`: Trained model file (to be uploaded from Teachable Machine).
- `labels.txt`: Labels corresponding to the classes in the model.

## License

This project is licensed under the MIT License.
