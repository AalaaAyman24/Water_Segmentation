# Water Segmentation Project

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Data Paths](#data-paths)
- [Model Architecture](#model-architecture)
- [Training](#training)
- [Requirements](#requirements)
- [Usage](#usage)
- [Deployment](#deployment)
- [Conclusion](#conclusion)
- [License](#license)

## Project Overview
This repository provides an implementation of a U-Net model for image segmentation tasks using TensorFlow. The U-Net architecture is well-suited for pixel-level image segmentation, making it ideal for various image analysis applications.

## Dataset
The dataset consists of images and corresponding labels used for training and evaluation. Images are provided in TIFF format, while labels are in PNG format.

## Data Paths
- **Images**: Located at `/kaggle/input/water-segmentation-dataset/data/images`
- **Labels**: Located at `/kaggle/input/water-segmentation-dataset/data/labels`

## Model Architecture
The U-Net model features:
- **Encoder**: Includes convolutional layers followed by max pooling to capture image features.
- **Decoder**: Utilizes upsampling and convolutional layers to reconstruct the segmentation map from the encoded features.
- The model requires input images of size (128, 128, 12).

## Training
The model is trained with:
- **Optimizer**: Adam with exponential decay.
- **Loss Function**: Binary cross-entropy.
- **Metrics**: Accuracy.

Training progress is visualized through accuracy and loss plots.

## Requirements
Ensure that you have the following Python packages installed:
- TensorFlow
- NumPy
- tifffile
- PIL
- Matplotlib
- scikit-learn

## Usage
1. **Data Loading**: Load and preprocess images and labels using the provided functions.
2. **Dataset Creation**: Create a TensorFlow dataset from the processed images and labels.
3. **Model Training**: Train the U-Net model using the prepared dataset.
4. **Evaluation**: Assess the model's performance using accuracy and loss metrics.

## Deployment
The project includes a deployment using Flask to serve the model and make predictions on uploaded TIFF images.

### Flask Application Setup
The Flask application loads the U-Net model and processes uploaded images for water segmentation predictions. The app performs the following:
1. Receives a TIFF image file from the user.
2. Processes the image and predicts the segmentation mask using the pre-trained U-Net model.
3. Generates a visual overlay of the segmentation result.
4. Displays both the input image and the output overlay on a web interface.

### How to Use
1. Run the Flask app:
   ```bash
   python app.py
   ```
2. Navigate to `http://127.0.0.1:5000/` in your browser.
3. Upload a TIFF image for prediction.
4. View the segmentation results displayed on the page.

### Deployment Image
![App Image](https://github.com/AalaaAyman24/Water_Segmentation/blob/main/Water_Segmentation_App.png)

## Conclusion
The model's performance is evaluated based on training and validation accuracy and loss. Results can be visualized to assess the effectiveness of the model.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
